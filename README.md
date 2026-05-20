# 🗽 NYTimes Video Parser

> A lightweight, fast, and versatile tool for extracting video content from The New York Times (Educational & Research Version)

[🌐 Online Demo](https://twittervideodownloaderx.com/nytimes_downloader) • [📝 Usage Guide](#-usage-guide) • [❓ FAQ](#-faq)

---

## 📋 Project Overview

This project is a web-based video parsing tool designed to safely extract media resource metadata from publicly accessible articles on The New York Times website, while providing options for format conversion and local saving. No client software installation or account registration required—use it directly through your browser.

> ⚠️ **Important Notice**: This tool is intended exclusively for personal learning, technical research, and use within reasonable limits. Please comply with the [NYTimes Terms of Service](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), the 《U.S. Copyright Act》, and other applicable regulations. Respect the work of news organizations and creators; do not use downloaded content for commercial purposes or to infringe upon others' rights. **This tool only supports publicly accessible video content and does not bypass paywalls, subscription restrictions, or login-required content.**

---

## ✨ Key Features

- 🔗 **Link Parsing**: Supports standard NYTimes article/video page URLs; automatically identifies publicly available video resources
- 📥 **Multi-Format Export**:
  - Public video streams (supports publicly available resolution options provided by the platform)
  - Audio extraction → MP3 format (convenient for offline listening to news reports/podcasts)
  - Video clip → Animated GIF conversion (ideal for creating educational materials/content summaries)
- 🌍 **Multilingual Interface**: Supports English, Chinese, Japanese, Korean, and more
- 📱 **Cross-Platform Compatibility**: Works seamlessly on Chrome / Firefox / Safari / Edge; optimized experience for mobile devices and tablets
- 🔒 **Privacy-First**: No NYTimes account login required, no personal data collection; fully anonymous parsing process
- ⚡ **Fast Processing**: Analysis completes in an average of 5-10 seconds; supports concurrent requests

---

## 🚀 Quick Start

### Online Usage (Recommended)
1. Visit [https://twittervideodownloaderx.com/nytimes_downloader](https://twittervideodownloaderx.com/nytimes_downloader)
2. Copy the target video page link (e.g., `https://www.nytimes.com//01/01/world/example-video.html`)
3. Paste the link into the input field → Click the 「Parse」button
4. Select your desired format → Save the file following your browser's instructions

### Local Deployment (For Developers)
```bash
# Clone the repository
git clone https://github.com/your-repo/nytimes-video-parser.git

# Install dependencies
cd nytimes-video-parser && npm install

# Configure environment variables (optional)
cp .env.example .env

# Start the development server
npm run dev
```

> 💡 Note: This project uses a Node.js + Express architecture. Please refer to `/docs/DEPLOY.md` for detailed deployment documentation.

---

## 🛠 Technology Stack

| Module | Technologies Used |
|--------|------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Video Processing | ffmpeg.wasm (lightweight client-side conversion) |
| Proxy Forwarding | Cloudflare Workers / Custom Middleware |
| Internationalization | vue-i18n + JSON Language Packs |

---

## 📚 Usage Guide

### Basic Workflow
```
1. Obtain the video link
   └─ Open the target article/video page on NYTimes → Copy the URL from your browser's address bar

2. Submit parsing request
   └─ Paste the link into the tool's input field → Click 「Start Parsing」

3. Select output configuration
   ├─ 🎬 Download Video: Choose available resolution (public content only)
   ├─ 🎵 Extract Audio: Generate MP3 file (ideal for offline news/podcast listening)
   └─ 🎞 Generate GIF: Create animation from specified time range (recommended: ≤15 seconds)

4. Save the file
   └─ Resource opens in a new tab → Right-click/menu → 「Save As」
```

### Mobile Usage Tips
- iOS Safari: Share button → 「Save to Files」
- Android Chrome: Long-press video preview → 「Download video」
- If video auto-plays: Tap `⋮` in the player's top-right corner → Select 「Download」

---

## ❓ Frequently Asked Questions

**Q: Where are downloaded files saved?**  
A: Files are saved to the download folder configured in your browser. You can check or modify this path in your browser settings.

**Q: Can I parse paywalled, subscription-only, or login-required content?**  
A: No. This tool only works with publicly accessible video content and respects the access permissions of the original content. Content behind paywalls, subscription restrictions, or requiring login is not supported.

**Q: Does conversion reduce image/audio quality?**  
A: Video downloads maintain the original bitrate of the selected resolution. MP3 uses standard 128kbps encoding. GIF optimizes frame rate based on duration to balance file size and smoothness.

**Q: Is download history or cache stored?**  
A: No. All resources are transmitted directly to the user's device via a temporary proxy; the server does not store any requests or media files.

**Q: What should I do if parsing fails?**  
A: Please verify: ① The link points to a valid public video page ② Your internet connection is stable ③ Try using a different browser. If the issue persists, feel free to report it via an Issue.

---

## ⚖️ Compliance & Disclaimer

- This tool **does not bypass or violate any technical protection measures, paywalls, or access controls** of the platform; it only obtains metadata through publicly available interfaces
- Users are responsible for ensuring their use complies with local laws and the platform's terms of service
- Recommended use cases: Personal learning archives, news research reference, educational material preparation... always within the framework of fair use
- If you discover content that may infringe upon rights or have copyright questions, please contact the official channel via [NYTimes Copyright Contact Page](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html)
- This tool is not affiliated with, endorsed by, or authorized by The New York Times Company. All trademarks and content copyrights belong to their respective owners

---

## 🤝 Contributing

We welcome your Pull Requests and Issue reports! Before contributing, please review:
- [Code Standards](/CONTRIBUTING.md)
- [Multilingual Translation Guide](/locales/README.md)
- [Security & Compliance Requirements](/SECURITY.md)

---

## 📄 License

This project is released under the [MIT License](/LICENSE). It may be used freely for educational and research purposes. For commercial use, please carefully verify compliance with applicable legal regulations.

---

> 🌟 If this tool has been helpful to you, please ✨give it a Star! Your support is the greatest motivation for us to continue maintaining and improving this project~

*Last updated: May  | Version: v1.0.0*
