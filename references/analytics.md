# NFT Collection PNL App — Reference

## Key Alchemy Endpoints Used
- `/nft/v3/{key}/getNFTSales` — marketplace buys/sells
- `alchemy_getAssetTransfers` — mints, transfers, OTC sales
- `eth_getTransactionByHash` — get mint price from tx value
- `getNFTsForOwner` — current holdings
- `getFloorPrice` — floor price data
- `eth_call` for contract metadata (name/symbol)

## Blockscout Alternative (RBH only)
- `/api/v2/addresses/{wallet}/token-transfers?token={contract}` — transfer history
- `/api/v2/transactions/{hash}` — get tx value

## File Structure
```
pnl-app/
└── index.html  (single file, ~64KB, self-contained)
```
