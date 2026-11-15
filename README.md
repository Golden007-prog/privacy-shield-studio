# PrivacyShield Studio

**Client-side privacy & AI data sanitizer.** 100% local: 0 bytes leave your browser.

🔗 **Live:** https://reseachrandomv.github.io/privacy-shield-studio/

## Tools
- **AI Prompt & Code Secret Scrubber**: redacts emails, IPs, phone numbers, credit cards, API keys (OpenAI, Anthropic, GitHub, AWS and more), bearer tokens/JWTs and private key blocks before you paste into an LLM.
- **EXIF & GPS Metadata Stripper**: inspects JPEG/PNG/WebP headers for EXIF, GPS, XMP, ICC and text chunks, then re-encodes through a canvas to remove them.
- **Bulk URL Unclutter**: strips 100+ tracking parameters (utm_*, fbclid, gclid, msclkid, igshid, _hsenc…) from up to 50 links at once.
- **Crypto Generator**: passwords, diceware-style passphrases and 128/256/512-bit API secrets from `crypto.getRandomValues()`, with entropy and crack-time estimates.

## Run locally
No build step. Clone the repo and open `index.html`, or serve the folder with any static server.

## Credits
Passphrase word list: [EFF Short Wordlist #1](https://www.eff.org/dice) by the Electronic Frontier Foundation (CC BY 3.0 US).

## License
[MIT](LICENSE) © 2026 Fathimath Malaak Jaufar
