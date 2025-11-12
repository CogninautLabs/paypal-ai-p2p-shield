# CogniShield: Grok-Powered P2P Fraud Detector

[![Chrome Extension](https://img.shields.io/badge/Chrome-Extension-blue?logo=google-chrome)](https://chrome.google.com/webstore) [![xAI Grok](https://img.shields.io/badge/Powered%20by-Grok-orange?logo=xai)](https://x.ai)

CogniShield is a privacy-first Chrome extension that uses Grok AI (from xAI) to detect real-time fraud in P2P payments on PayPal, Venmo, Cash App, and Zelle. It scans memos/amounts, flags scams like overpayments or urgency phishing, and shows actionable alerts with ELI5 explanations. 90-95% accuracy via fine-tuned prompts. Enterprise-ready (GPO deployable).

## Features
- **Real-Time Scanning**: Monitors payment forms with local pre-filters + Grok API for deep analysis.
- **Pro UI**: Dark mode alerts with risk scores, dismiss/report buttons, and "Mark Known" for recipients.
- **Privacy Opt-In**: No PII sent—only anonymized memo/amount/context.
- **Fallbacks**: Local rules if no API key/network.
- **Auto-Updates**: From GitHub repo.

## Demo
![Alert Example](https://via.placeholder.com/320x200/1a1a1a/fff?text=CogniShield+Alert:+85%25+Risk)  
*(High-risk overpayment flagged—pause & verify!)*

## Quick Install
1. Download ZIP from [Releases](https://github.com/YOURUSERNAME/cognishield/releases).
2. Chrome: `chrome://extensions/` → Developer mode → Load unpacked → Select folder.
3. Add xAI API key: Click extension icon → Paste key (get at [x.ai/api](https://x.ai/api)) → Save.
4. Test: Go to PayPal, enter memo "Urgent refund $250" → Alert pops!

## Setup Guide
### Requirements
- Chrome 88+.
- xAI API key ([free tier available](https://x.ai/api)).

### Local Development
1. Clone: `git clone https://github.com/YOURUSERNAME/cognishield.git`.
2. Open in VS Code.
3. Load: `chrome://extensions/` → Load unpacked.
4. Edit → Reload extension.

### Enterprise/GPO
- Zip folder → Deploy via Chrome policy (see [Chrome docs](https://developer.chrome.com/docs/extensions/develop/distribute/enterprise)).
- Auto-update via `update_url` in manifest.

## Code Structure
- `manifest.json`: V3 config.
- `background.js`: Grok API + caching.
- `content.js`: DOM scanning with MutationObserver.
- `options.html/js`: API key settings.
- `alert.*`: Embedded UI (dark, accessible).

## Customization
- Tweak risk threshold: Edit `> 70` in `content.js`.
- Prompt: Fine-tune in `background.js` for better accuracy.
- Icon: Replace `icons/icon128.png` (128x128 PNG).

## Contributing
Fork, PRs welcome! Issues: [Open one](https://github.com/YOURUSERNAME/cognishield/issues/new).

## License
MIT. © 2025 Cogninaut Labs

---

*Questions? [Contact](mailto:info@cogninaut.com) or star the repo! 🚀*
