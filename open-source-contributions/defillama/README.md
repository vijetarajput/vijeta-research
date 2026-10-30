# DefiLlama: GBP stablecoin data contributions

Open-source contributions to [DefiLlama/peggedassets-server](https://github.com/DefiLlama/peggedassets-server), the repository behind DefiLlama's stablecoin dashboard. The work applies the verification method from my GBP stablecoin research ([gbp-stablecoin-analysis](https://github.com/vijetarajput/gbp-stablecoin-analysis)) to a widely used public data platform.

## Contributions

| Date | Pull request | What it does | Status |
|---|---|---|---|
| 18 Oct 2026 | [#948](https://github.com/DefiLlama/peggedassets-server/pull/948) | Adds Monerium GBP emoney (GBPE) to the stablecoins dashboard across six chains (Ethereum, Gnosis, Polygon, Arbitrum, Base, Linea) | Merged 20 Oct 2026 |
| 20 Oct 2026 | [#949](https://github.com/DefiLlama/peggedassets-server/pull/949) | Corrects the GBPE mint/redeem description after verifying that Monerium does not currently offer GBP IBANs | Merged 22 Oct 2026 |
| 22 Oct 2026 | [#957](https://github.com/DefiLlama/peggedassets-server/pull/957) | Corrects the tGBP description, which called tGBP "the only" GBP stablecoin issued by a UK FCA-registered firm; the FCA register shows a second such firm (Agant Finance Limited, registered since 11 Feb 2026) | Merged 29 Oct 2026 |

## How the gap was found (#948)

- On 18 Oct 2026, DefiLlama tracked Monerium EUR emoney (EURe) as a stablecoin, but GBPE appeared only as a token page.
- No existing or past pull request had added GBPE.
- All six contract addresses were verified against Monerium's official token documentation; the Gnosis address was cross-checked with CoinGecko.
- Only current v2 contracts were included, consistent with DefiLlama's existing EURe adapter.

## How the outdated claim was found (#957)

- DefiLlama's tGBP description claimed tGBP was "the only British Pound backed stablecoin issued by a UK FCA-registered firm".
- The FCA Financial Services Register shows BCP Technologies Ltd (tGBP issuer, FRN 928840, registered since 3 Dec 2021) and Agant Finance Limited (GBPA issuer, FRN 1037671, registered since 11 Feb 2026), both with type "MLD cryptoassets".
- The PR replaced the claim with the issuer's name and registration type (one line changed), using the same wording as DefiLlama's GBPA description.

## Data audits: other GBP stablecoins

| Date | Token | Check | Result |
|---|---|---|---|
| 20 Oct 2026 | Agant GBP (GBPA) | Supply by chain vs Etherscan (6 decimals) | Consistent, no change needed |
| 20 Oct 2026 | VNX British Pound (VGBP) | Supply by chain vs my register | Consistent; Ethereum contract deployed with zero supply |
| 22 Oct 2026 | Agant GBP (GBPA) | Addresses on all five chains vs Agant's official docs; supply on Base, Solana, Arc and Tempo explorers | Consistent, no change needed |
| 24 Oct 2026 | Tokenised GBP (tGBP) | Addresses on all eight chains vs the official tGBP contract register | Consistent, no change needed |

## Evidence

Dated screenshots (before and after) are in the [`evidence/`](evidence/) folder.
