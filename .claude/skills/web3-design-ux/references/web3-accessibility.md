# Web3 Accessibility

Making Web3 applications accessible to all users, including those with disabilities.

## Core Requirements

### Screen Reader Support

**Critical Elements:**
```html
<!-- Wallet connection -->
<button aria-label="Connect wallet">
  Connect
</button>

<!-- Transaction status -->
<div role="status" aria-live="polite">
  Transaction confirmed
</div>

<!-- Network selector -->
<button aria-label="Switch network. Currently Ethereum">
  Ethereum
</button>
```

### Keyboard Navigation

**Essential flows keyboard-accessible:**
- Connect wallet (Tab + Enter)
- Switch network (Tab + Enter)
- Enter amounts (Tab, type)
- Confirm transactions (Tab + Enter)
- Close modals (Esc)

**Focus Management:**
```
Focus order:
1. Main navigation
2. Wallet button
3. Primary actions
4. Secondary actions
5. Footer

Skip link to main content
Visible focus indicators
Trap focus in modals
```

### Color Contrast

**WCAG 2.1 AA Minimum:**
- Text: 4.5:1 contrast
- Large text (18px+): 3:1
- UI components: 3:1
- Status indicators: Not color-only

**Good Contrasts:**
```
✓ Black text on white: 21:1
✓ Dark gray #333 on white: 12.6:1
✓ Blue #0066CC on white: 5.9:1

✗ Light gray #999 on white: 2.8:1
✗ Yellow on white: 1.2:1
```

### Visual Design

**Don't rely on color alone:**
```
✓ Red + icon for error
✓ Green + "✓" for success
✓ Yellow + "⚠️" for warning

✗ Color only to show status
```

**Readable text sizes:**
- Minimum: 14px body text
- Buttons: 16px+ minimum
- Headings: Clear hierarchy
- Allow text scaling to 200%

## Web3-Specific Considerations

### Wallet Addresses

**Make addresses accessible:**
```
Full address for screen readers:
<span aria-label="Wallet address: 0x742d35Cc6634C0532925a3b844Bc9e7595f8f3a">
  0x742d...8f3a
</span>

Copy button:
<button aria-label="Copy wallet address">
  📋 Copy
</button>
```

### Transaction States

**Announce state changes:**
```html
<div role="status" aria-live="polite" aria-atomic="true">
  Transaction status: Pending
</div>

<!-- Updates to: -->
<div role="status" aria-live="polite" aria-atomic="true">
  Transaction status: Confirmed. You received 0.27 ETH
</div>
```

### Gas Fees

**Accessible gas selection:**
```html
<fieldset>
  <legend>Select transaction speed</legend>
  <label>
    <input type="radio" name="gas" value="slow">
    Slow: 8 dollars, approximately 10 minutes
  </label>
  <label>
    <input type="radio" name="gas" value="normal" checked>
    Normal: 12 dollars, approximately 3 minutes
  </label>
  <label>
    <input type="radio" name="gas" value="fast">
    Fast: 25 dollars, approximately 30 seconds
  </label>
</fieldset>
```

### Numbers & Currency

**Format for screen readers:**
```
Visual: $1,234.56
Screen reader: "1234 dollars and 56 cents"

Visual: 0.001234 ETH
Screen reader: "0.001234 ETH" (read as is)
```

## Mobile Accessibility

### Touch Targets

**Minimum size: 44x44pt**
```
✓ Button: 48x48pt
✓ Icon button: 44x44pt
✓ Checkbox: 44x44pt

✗ Small icon: 24x24pt (too small)
```

### Gestures

**Provide alternatives:**
- Swipe → Button alternative
- Pinch zoom → +/- buttons
- Long press → Button menu

### Motion

**Reduce motion:**
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```

## Testing Checklist

### Automated Testing
- [ ] Lighthouse accessibility score > 90
- [ ] axe DevTools no critical issues
- [ ] WAVE no errors
- [ ] Color contrast checker passes

### Manual Testing
- [ ] Keyboard-only navigation works
- [ ] Screen reader (NVDA/JAWS) usable
- [ ] Tab order logical
- [ ] Focus visible throughout
- [ ] No keyboard traps
- [ ] Modals trap focus correctly

### Real User Testing
- [ ] Test with screen reader users
- [ ] Test with keyboard-only users
- [ ] Test with low vision users
- [ ] Test with motor impairments
- [ ] Test on mobile devices

## Common Issues

**Missing labels:**
```html
❌ <input type="text" placeholder="Amount">
✓ <label for="amount">Amount</label>
   <input type="text" id="amount" placeholder="0.00">
```

**Insufficient contrast:**
```
❌ Light gray text (#999) on white
✓ Dark gray text (#333) on white
```

**No keyboard access:**
```html
❌ <div onclick="connect()">Connect</div>
✓ <button onclick="connect()">Connect</button>
```

**Images without alt:**
```html
❌ <img src="eth-logo.png">
✓ <img src="eth-logo.png" alt="Ethereum logo">
```

## Resources

- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WebAIM](https://webaim.org/)
- [A11y Project](https://www.a11yproject.com/)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)

## Best Practices

1. Test with screen readers regularly
2. Ensure keyboard navigation works
3. Maintain 4.5:1 text contrast minimum
4. Don't rely on color alone
5. Provide text alternatives for images
6. Label all form inputs
7. Announce dynamic content changes
8. Support text scaling to 200%
9. Provide skip links
10. Test with real users with disabilities
