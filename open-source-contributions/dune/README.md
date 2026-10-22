# Dune: token price data contributions

Open-source contributions to [duneanalytics/spellbook](https://github.com/duneanalytics/spellbook), the open-source data layer behind Dune's curated tables. The work applies the verification method from my GBP stablecoin research ([gbp-stablecoin-analysis](https://github.com/vijetarajput/gbp-stablecoin-analysis)) to Dune's token price tables.

## Contributions

| Date | Pull request | What it does | Status |
|---|---|---|---|
| 21 Oct 2026 | [#10090](https://github.com/duneanalytics/spellbook/pull/10090) | Adds Monerium EURe v2 contracts to Dune's curated price tables on six chains (Ethereum, Gnosis, Polygon, Arbitrum, Base, Linea) | Open, all checks passed |

## How the gap was found (#10090)

- A 2024 attempt to add Monerium GBPe to Dune's price tables (spellbook #5898) was closed because GBPe has no CoinPaprika id, which Dune requires. On 21 Oct 2026, GBPe was still not listed on CoinPaprika.
- Checking the same price tables for Monerium's euro token showed that EURe was listed only with its older v1 contracts on Ethereum and Gnosis, and not at all on Polygon, Arbitrum, Base or Linea.
- The v2 addresses and decimals were verified against Monerium's official token documentation. Gnosisscan labels the Gnosis contracts "EURe Token V1" and "EURe Token V2", and CoinPaprika's EURe id is active and lists the v2 contracts.
- On Gnosisscan, v1 and v2 show nearly identical supply and holders, indicating a shared ledger. The v1 entries were therefore kept, and v2 was added alongside.
- Dune's Contributor License Agreement was signed and all automated checks passed.

## Evidence

Dated screenshots are in the [`evidence/`](evidence/) folder.
