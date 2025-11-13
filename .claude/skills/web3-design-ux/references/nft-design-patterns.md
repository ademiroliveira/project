# NFT Design Patterns

Design patterns for NFT marketplaces, galleries, and minting interfaces.

## NFT Display

### Gallery View

```
[Grid of NFT thumbnails]

Options:
- Grid (2x2, 3x3, 4x4)
- List with details
- Featured/spotlight view

Per NFT:
- Image/video preview
- Collection name
- Token ID
- Price (if listed)
- Rarity indicators
```

### Detail View

```
[Large NFT image/video/3D]

Token #1234
Collection: Cool NFTs

Owner: alice.eth
Price: 2.5 ETH ($4,625)

Properties:
• Background: Blue (15% rarity)
• Eyes: Laser (2% rarity)
• Hat: Crown (5% rarity)

[Buy Now] [Make Offer] [Share]
```

## Minting Interface

### Mint Flow

```
Step 1: Preview
[NFT Preview]
Minting: Cool NFT #TBD
Price: 0.08 ETH + gas

Step 2: Confirm Amount
Quantity: [1] (Max: 5 per wallet)

Step 3: Review
Total: 0.08 ETH + $12 gas
Reveal: 24 hours after mint

[Mint Now]
```

### Fair Launch Patterns

```
Mint Live!

Progress: ████░░░░░░ 4,234 / 10,000

Price: 0.08 ETH
Remaining: 5,766
Your limit: 5 NFTs

[Mint] [View Collection]
```

## Trading Patterns

### Listing

```
List NFT for Sale

Token #1234

Price: [2.5] ETH ($4,625)

Duration:
○ 1 day
● 7 days  
○ 1 month
○ No expiration

Marketplace fee: 2.5% (0.0625 ETH)

[List NFT]
```

### Offer Making

```
Make Offer

Token #1234
Floor price: 2.0 ETH

Your offer: [1.8] ETH
Expiration: [7 days]

Offer will use: 1.8 WETH
(You'll need to wrap ETH first)

[Wrap ETH] [Make Offer]
```

## Collection Pages

```
Cool NFTs Collection

Floor: 2.0 ETH
Volume (24h): 125 ETH
Owners: 3,421
Total supply: 10,000

[Items] [Activity] [Analytics]

Filters:
Price: [Min] - [Max]
Properties: [Dropdown]
Status: [Listed] [Has offers]

Sort: [Price: Low to High]
```

## Rarity Display

```
Rarity: Rank #234 / 10,000

Trait Rarity:
Background: Blue (15%) ⭐⭐
Eyes: Laser (2%) ⭐⭐⭐⭐⭐
Hat: Crown (5%) ⭐⭐⭐⭐

Rarity Score: 342.5

[Rarity Tools]
```

## Best Practices

1. High-quality image rendering
2. Support all media types (image, video, 3D, audio)
3. Show rarity indicators
4. Enable filtering by traits
5. Display provenance/history
6. Show real-time floor price
7. Batch operations (bulk list)
8. Mobile-optimized galleries
9. IPFS/decentralized storage indicators
10. Verify collection authenticity
