# DefiLlama: GBP stablecoin data contributions

Open-source contributions to [DefiLlama/peggedassets-server](https://github.com/DefiLlama/peggedassets-server), the repository behind DefiLlama's stablecoin dashboard. The work applies the verification method from my GBP stablecoin research ([gbp-stablecoin-analysis](https://github.com/vijetarajput/gbp-stablecoin-analysis)) to a widely used public data platform.

## Contributions

| Date | Pull request | What it does | Status |
|---|---|---|---|
| 18 Oct 2026 | [#948](https://github.com/DefiLlama/peggedassets-server/pull/948) | Adds Monerium GBP emoney (GBPE) to the stablecoins dashboard across six chains (Ethereum, Gnosis, Polygon, Arbitrum, Base, Linea) | Merged 20 Oct 2026 |
| 20 Oct 2026 | [#949](https://github.com/DefiLlama/peggedassets-server/pull/949) | Corrects the GBPE mint/redeem description after verifying that Monerium does not currently offer GBP IBANs | Open |

## How the gap was found (#948)

- On 18 Oct 2026, DefiLlama tracked Monerium EUR emoney (EURe) as a stablecoin, but GBPE appeared only as a token page.
- No existing or past pull request had added GBPE.
- All six contract addresses were verified against Monerium's official token documentation; the Gnosis address was cross-checked with CoinGecko.
- Only current v2 contracts were included, consistent with DefiLlama's existing EURe adapter.

## Data audit: other GBP stablecoins (20 Oct 2026)

| Token | Check | Result |
|---|---|---|
| Agant GBP (GBPA) | Supply by chain vs Etherscan (6 decimals) | Consistent, no change needed |
| VNX British Pound (VGBP) | Supply by chain vs my register | Consistent; Ethereum contract deployed with zero supply |

## Evidence

Dated screenshots (before and after) are in the [`evidence/`](evidence/) folder.
