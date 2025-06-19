# TradingView to Tradovate Trading Bot

**Automated Trading Bridge v1.0** - Seamlessly execute TradingView alerts as live trades on Tradovate

## Overview

This Chrome extension creates a real-time bridge between TradingView and Tradovate, automatically executing trades based on TradingView alerts. When a TradingView alert fires with buy/sell signals, the extension instantly places corresponding market orders on Tradovate.

## Key Features

- **Real-time Alert Detection** - Monitors TradingView for new alerts instantly
- **Automated Trade Execution** - Clicks buy/sell buttons on Tradovate automatically  
- **Quantity Control** - Always trades exactly 1 contract for risk management
- **Auto-injection Technology** - Automatically loads required scripts when needed
- **Cross-tab Communication** - Seamless message routing between browser tabs
- **Production Ready** - Clean, optimized code with minimal logging

## How It Works

1. **TradingView Alert Fires** → Extension detects alerts containing buy/sell keywords
2. **Signal Processing** → Parses alert text for trading action (buy/sell)
3. **Message Routing** → Background script routes signal to Tradovate tab
4. **Trade Execution** → Automatically clicks appropriate buy/sell button
5. **Quantity Management** → Sets quantity to 1 contract before execution

## Installation

### Prerequisites
- Chrome browser
- Active TradingView account with alerts set up
- Active Tradovate account with trading interface open
 

2. **Install Extension**
   - Open Chrome and go to `chrome://extensions/`
   - Enable "Developer mode" (top right toggle)
   - Click "Load unpacked"
   - Select the folder containing the extension files

3. **Open Required Tabs**
   - TradingView: `https://www.tradingview.com/chart/`
   - Tradovate: `https://trader.tradovate.com/`

4. **Test Connection**
   - Click the extension icon in Chrome toolbar
   - Verify both tabs show "online" status
   - Use "Test Buy" and "Test Sell" buttons to verify functionality

## Usage

### Setting Up TradingView Alerts

Create TradingView alerts with these keywords in the message:
- **Buy signals**: "buy", "long", "enter long", "call"
- **Sell signals**: "sell", "short", "enter short", "put", "exit"

Example alert messages:
- `"BUY  signal triggered"`
- `"SELL  position"`
- `"Enter LONG"`

### Testing the Bridge

1. **Manual Testing**
   - Open extension popup
   - Use "Test Buy" and "Test Sell" buttons
   - Verify trades execute on Tradovate

2. **Alert Testing**
   - Use "Simulate TradingView Alert" feature
   - Enter test alert text like "BUY   signal"
   - Confirm alert flows through to Tradovate

### Production Trading

1. Set up your TradingView alerts with appropriate buy/sell keywords
2. Keep both TradingView and Tradovate tabs open
3. The extension runs automatically in the background
4. Monitor the Activity Log for execution confirmations

## Configuration

### Supported Alert Keywords

**Buy Keywords:**
- buy, long, enter long, go long, call

**Sell Keywords:**  
- sell, short, enter short, go short, put, exit

### Quantity Settings

- Fixed at 1 contract per trade for risk management
- Automatically overrides any existing quantity settings
- Cannot be changed without code modification

## Technical Details

### Architecture
- **Content Scripts**: Monitor TradingView alerts and control Tradovate interface
- **Background Script**: Routes messages between tabs and handles auto-injection
- **Popup Interface**: Provides testing and monitoring capabilities

### Browser Permissions
- `tabs` - Access to browser tabs
- `activeTab` - Interact with active tabs
- `scripting` - Inject scripts when needed

### Supported URLs
- TradingView: `*://www.tradingview.com/*`, `*://tradingview.com/*`
- Tradovate: `*://trader.tradovate.com/*`

## Safety Features

- **Quantity Limitation** - Maximum 1 contract per trade
- **Alert Filtering** - Only processes valid trading signals
- **Duplicate Prevention** - Prevents multiple executions of same alert
- **Error Handling** - Graceful failure recovery with user feedback

## Troubleshooting

### Common Issues

**"Could not establish connection" Error**
- Refresh both TradingView and Tradovate tabs
- Reload the extension
- Verify URLs match supported patterns

**Buttons Not Found**
- Ensure you're on the Tradovate trading interface (not dashboard)
- Check that buy/sell buttons are visible on screen
- Verify you're logged into Tradovate

**Alerts Not Detected**
- Confirm alert text contains buy/sell keywords
- Check TradingView tab is active and loaded
- Verify alerts are firing (check TradingView alerts panel)

### Debug Mode

Enable debug logging by modifying the background script:
```javascript
// Add at top of background.js
const DEBUG = true;
```

## Risk Disclaimer

⚠️ **IMPORTANT**: This extension executes real trades with real money.

- Only use with accounts you can afford to lose
- Start with small position sizes
- Thoroughly test before live trading  
- Monitor trades and market conditions
- Trading involves substantial risk of loss
- Past performance does not guarantee future results

## Version History

### v1.0 Production
- Initial production release
- Real-time alert detection
- Automated trade execution
- Auto-injection technology
- Clean production interface

## Support

For issues, feature requests, or contributions:
1. Test thoroughly in a demo environment first
2. Check troubleshooting section above
3. Verify all prerequisites are met
4. Document exact error messages and steps to reproduce

---

**Built for traders, by traders** 📈

*Remember: Automated trading amplifies both gains and losses. Trade responsibly.*
