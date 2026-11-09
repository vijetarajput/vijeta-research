# Dune: token price data contributions

Open-source contributions to [duneanalytics/spellbook](https://github.com/duneanalytics/spellbook), the open-source data layer behind Dune's curated tables. The work applies the verification method from my GBP stablecoin research ([gbp-stablecoin-analysis](https://github.com/vijetarajput/gbp-stablecoin-analysis)) to Dune's token price tables.

## Contributions

| Date | Pull request | What it does | Status |
|---|---|---|---|
| 21 Oct 2026 | [#10090](https://github.com/duneanalytics/spellbook/pull/10090) | Adds Monerium EURe v2 contracts to Dune's curated price tables on six chains (Ethereum, Gnosis, Polygon, Arbitrum, Base, Linea) | Open, all checks passed |
| 9 Nov 2026 | [#10124](https://github.com/duneanalytics/spellbook/pull/10124) | Adds Tokenised GBP (tGBP), the largest GBP stablecoin, to Dune's curated price tables on seven chains (Ethereum, Base, Arbitrum, Polygon, BNB Chain, Avalanche, Gnosis) | Open, all checks passed |

## How the gap was found (#10090)

- A 2024 attempt to add Monerium GBPe to Dune's price tables (spellbook #5898) was closed because GBPe has no CoinPaprika id, which Dune requires. On 21 Oct 2026, GBPe was still not listed on CoinPaprika.
- Checking the same price tables for Monerium's euro token showed that EURe was listed only with its older v1 contracts on Ethereum and Gnosis, and not at all on Polygon, Arbitrum, Base or Linea.
- The v2 addresses and decimals were verified against Monerium's official token documentation. Gnosisscan labels the Gnosis contracts "EURe Token V1" and "EURe Token V2", and CoinPaprika's EURe id is active and lists the v2 contracts.
- On Gnosisscan, v1 and v2 show nearly identical supply and holders, indicating a shared ledger. The v1 entries were therefore kept, and v2 was added alongside.
- Dune's Contributor License Agreement was signed and all automated checks passed.

## How the gap was found (#10124)

- On 24 Oct 2026, a check of CoinPaprika showed that tGBP is listed with an active id (tgbp-tokenised-gbp), while Spellbook's price tables did not include tGBP on any of its eight chains.
- The addresses were taken from the issuer's official contract register (tokenisedgbp.com), which matches DefiLlama's entry on all eight chains (audit of 24 Oct 2026). Decimals (18) were confirmed on each chain's block explorer on 9 Nov 2026.
- CoinPaprika's own contract list shows tGBP's ERC20 and BEP20 address with two characters transposed; the PR uses the issuer's register instead, and the discrepancy was reported to the issuer.
- Solana was not included because its prices file uses a different format.

## Evidence

Dated screenshots are in the [`evidence/`](evidence/) folder.
