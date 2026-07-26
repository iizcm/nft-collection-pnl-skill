---
name: nft-collection-pnl
description: "Single-file HTML PNL analyzer for NFT collections — FIFO trade analysis across 18 EVM chains, downloadable visual P&L cards (PNG/WebM). Use when user wants to check NFT portfolio profit/loss, generate trade history reports, or create shareable PNL cards. Deployed at https://nft-pnl-report.vercel.app."
tags: []
---

# NFT Collection PNL Analyzer

## WHEN TO USE
User wants to analyze NFT collection trades → see how many bought/sold/holding, realized/unrealized P&L, and export a visual card.

## DEPLOYED URL
https://nft-pnl-report.vercel.app

## HOW IT WORKS
1. User inputs: wallet address + contract address + Alchemy API key (for most chains)
2. For RBH chain: Blockscout API used automatically (no API key needed)
3. Fetches all trades via Alchemy getNFTSales/getAssetTransfers or Blockscout token-transfers
4. FIFO matching of buys → sells per token ID
5. Renders stats table + trade history table
6. Generates a Canvas-based PNL card (1200×675) that can be downloaded as PNG

## SUPPORTED NETWORKS
ETH, Arbitrum, Arb Nova, Optimism, Base, Polygon, Polygon zkEVM, zkSync Era, Linea, Scroll, Blast, Zora, Mantle, Mode, Shape, World Chain, Fraxtal, Robinhood Chain (RBH)

## KEY FIELDS IN CARD
- Total Risk (ETH spent buying)
- Profit (realized from sells)
- Holding value (floor × held count)
- Total P&L + ROI %
- Per-trade table: Token ID, Type (BUY/SELL/HOLD), Source, Buy Price, Sell Price, P&L

## CUSTOMIZATION
- `by: @username` watermark (cursive font, centered left)
- Censored mode (blurs text for stealth sharing)
- Custom background image/video (uploads via file picker)
- Download as PNG or record as WebM video

## SOURCE CODE
`/home/ubuntu/nft-work/pnl-app/index.html` — single self-contained HTML file, no build step needed.

## IMPORTANT NOTES
- Alchemy API key stored in `.env` as `ALCHEMY_API_KEY` but NOT hardcoded — user pastes manually into form field (client-side only)
- File is frontend-only: all API calls from browser, no server component
- For RBH specifically: uses Blockscout as primary source, no API key needed
- Memory note: see `references/analytics.md` in local system for full API references
