# dApp Design Evaluation Checklist

Comprehensive checklist for evaluating decentralized application designs.

## Wallet Connection [ /10]

- [ ] Progressive access (browse before connecting)
- [ ] Multiple wallet support (MetaMask, WalletConnect, etc.)
- [ ] Clear connection status indicator
- [ ] Persistent sessions (auto-reconnect)
- [ ] Easy disconnect option
- [ ] Wrong network detection & switching
- [ ] Mobile wallet support (WalletConnect, deep links)
- [ ] Connection error handling
- [ ] First-time user guidance
- [ ] Permission explanations

## Transaction Experience [ /15]

- [ ] Comprehensive preview before wallet popup
- [ ] All costs shown upfront (gas + fees)
- [ ] Real-time transaction status updates
- [ ] Block confirmation counter (when relevant)
- [ ] Transaction history accessible
- [ ] Failed transaction explanations
- [ ] Stuck transaction recovery (speed up/cancel)
- [ ] Multi-step transaction tracking
- [ ] Success confirmations with details
- [ ] Transaction notifications
- [ ] Link to block explorer
- [ ] Updated balances after transactions
- [ ] Retry failed transactions easily
- [ ] Clear error messages with recovery steps
- [ ] Transaction simulation/pre-flight checks

## Gas Fee UX [ /10]

- [ ] Gas displayed in fiat currency first
- [ ] Three-tier selection (slow/normal/fast)
- [ ] Time estimates for each tier
- [ ] Current gas price indicator (low/high)
- [ ] Gas price history/context
- [ ] L2 recommendations when gas is high
- [ ] Batch operation suggestions
- [ ] Gas optimization explanations
- [ ] Failed transaction gas explanation
- [ ] Gas alert/scheduling options

## Information Display [ /10]

- [ ] Clear visual hierarchy (primary/secondary/tertiary)
- [ ] Fiat values shown prominently
- [ ] Progressive disclosure (glance/evaluate/deep-dive)
- [ ] Real-time price updates
- [ ] Data freshness indicators
- [ ] Comparison context (vs benchmarks, averages)
- [ ] Risk indicators visible
- [ ] Security audit information accessible
- [ ] TVL and trust signals displayed
- [ ] Mobile-optimized information density

## Network Handling [ /8]

- [ ] Active network always visible
- [ ] Network color-coding consistent
- [ ] One-click network switching
- [ ] Network-specific costs shown
- [ ] Unified multi-chain balance view
- [ ] Network recommendations for actions
- [ ] Testnet warning (if applicable)
- [ ] Handle disconnected state gracefully

## Security & Trust [ /12]

- [ ] Clear smart contract risk warnings
- [ ] Security audit information prominent
- [ ] Token verification indicators
- [ ] Unverified token warnings
- [ ] Permission request clarity (approvals)
- [ ] Approval management dashboard
- [ ] Phishing detection/warnings
- [ ] Address verification tools
- [ ] Large transaction confirmations
- [ ] Honeypot/scam detection
- [ ] MEV protection options
- [ ] Contract interaction explanations

## Terminology & Education [ /8]

- [ ] Plain language throughout
- [ ] Jargon explained with tooltips
- [ ] Contextual help available
- [ ] Glossary or help center
- [ ] Progressive education (learn as you go)
- [ ] Video tutorials or guides
- [ ] Testnet/practice mode available
- [ ] Error messages user-friendly

## Mobile Experience [ /8]

- [ ] Mobile-responsive design
- [ ] WalletConnect integration
- [ ] Touch-friendly targets (44x44pt min)
- [ ] Bottom-sheet actions
- [ ] One-handed mode support
- [ ] Simplified mobile flows
- [ ] Push notifications
- [ ] Fast load times

## Accessibility [ /10]

- [ ] Screen reader compatible
- [ ] Keyboard navigation complete
- [ ] Sufficient color contrast (4.5:1)
- [ ] No color-only information
- [ ] Text alternatives for images
- [ ] Form labels present
- [ ] Dynamic content announced
- [ ] Text scales to 200%
- [ ] Focus indicators visible
- [ ] Skip links provided

## Performance [ /5]

- [ ] Fast initial load (<3 seconds)
- [ ] Optimized bundle size
- [ ] Lazy loading implemented
- [ ] Works on slower connections
- [ ] Minimal layout shift

## Error Handling [ /4]

- [ ] Graceful error states
- [ ] Clear error messages
- [ ] Recovery paths obvious
- [ ] Help/support accessible

---

**Total Score: [ ] / 100**

**Rating:**
- 90-100: Excellent
- 75-89: Good
- 60-74: Needs Improvement
- <60: Significant Issues

**Priority Issues:**
1. [Issue]
2. [Issue]
3. [Issue]

**Recommendations:**
1. [Recommendation]
2. [Recommendation]
3. [Recommendation]
