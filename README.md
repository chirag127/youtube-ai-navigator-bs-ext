<p align="center">
  <a href="https://github.com/chirag127/youtube-ai-navigator-bs-ext">
    <img src="https://raw.githubusercontent.com/chirag127/youtube-ai-navigator-bs-ext/main/.github/assets/hero-banner.png" alt="YouTube AI Navigator Browser Extension Hero Banner" width="800">
  </a>
</p>

<p align="center">
  <a href="https://github.com/chirag127/youtube-ai-navigator-bs-ext/actions/workflows/ci.yml">
    <img src="https://github.com/chirag127/youtube-ai-navigator-bs-ext/actions/workflows/ci.yml/badge.svg?branch=main&event=push&style=flat-square" alt="Build Status">
  </a>
  <a href="https://codecov.io/gh/chirag127/youtube-ai-navigator-bs-ext" target="_blank">
    <img src="https://codecov.io/gh/chirag127/youtube-ai-navigator-bs-ext/branch/main/graph/badge.svg?style=flat-square" alt="Code Coverage">
  </a>
  <img src="https://img.shields.io/badge/Tech-TypeScript%20%7C%20WXT%20%7C%20Gemini%20AI-blueviolet?style=flat-square" alt="Tech Stack">
  <img src="https://img.shields.io/badge/Lint/Format-Biome-00B3A6?style=flat-square" alt="Lint/Format">
  <a href="https://github.com/chirag127/youtube-ai-navigator-bs-ext/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square" alt="License">
  </a>
  <a href="https://github.com/chirag127/youtube-ai-navigator-bs-ext/stargazers">
    <img src="https://img.shields.io/github/stars/chirag127/youtube-ai-navigator-bs-ext?style=flat-square&label=Stars&color=yellow" alt="GitHub Stars">
  </a>
</p>

<h3 align="center">Star ⭐ this Repo! Your support fuels innovation!</h3>

<p align="center">
  <strong>Live site:</strong> <a href="https://yt-nav.oriz.in/">https://yt-nav.oriz.in/</a>
</p>

---

## 🚀 YouTube AI Navigator

YouTube AI Navigator is an apex-grade, privacy-first browser extension designed for real-time, AI-powered YouTube content analysis. It provides intelligent summaries using Google Gemini, smart interactive transcripts, integrated SponsorBlock functionality, and advanced comment analysis to enhance your viewing and research experience.

This extension empowers users with unparalleled control over YouTube content, offering deep insights, efficient navigation, and a cleaner viewing environment, all while upholding a strict privacy-first policy with zero-configuration overhead.

## 🌟 Features

- **AI-Powered Summaries (Gemini):** Get instant, concise summaries of YouTube videos using Google's advanced Gemini AI model, saving valuable time.
- **Smart Interactive Transcripts:** Seamlessly navigate video content with synchronized, searchable transcripts. Jump to any point in the video by clicking on text.
- **Integrated SponsorBlock:** Automatically skip sponsored segments, introductions, outros, and other non-content sections for an uninterrupted viewing experience.
- **Advanced Comment Analysis:** Utilize AI to categorize, summarize, and highlight key discussions within comment sections, helping you quickly gauge sentiment and find relevant information.
- **Privacy-First Design:** Operates with a strong commitment to user privacy, processing data locally where possible and minimizing external requests.
- **Zero-Configuration:** Installs and works out-of-the-box, providing powerful features without complex setup.
- **Real-time Analysis:** Delivers insights as you browse, making your YouTube experience more productive and enjoyable.

## 🛠️ Architecture

This project adheres to the **Feature-Sliced Design (FSD)** architecture, ensuring a scalable, maintainable, and highly modular structure for browser extensions. Each feature is self-contained, promoting clear separation of concerns and ease of development.

mermaid
graph TD
A[Extension Root] --> B[manifest.json];
A --> C[src/entrypoints];
A --> D[src/shared];
A --> E[src/features];
A --> F[src/widgets];
A --> G[src/pages];

    C --> C1[content.ts];
    C --> C2[background.ts];
    C --> C3[popup.html];

    D --> D1[ui/];
    D --> D2[lib/api/];
    D3[lib/utils/];
    D4[config/];

    E --> E1[gemini-summary/];
    E --> E2[transcript-viewer/];
    E --> E3[sponsor-block/];
    E --> E4[comment-analyzer/];
    E --> E5[settings/];

    F --> F1[PopupWidget];
    F --> F2[ContentOverlayWidget];

    G --> G1[options/];

    E1 --> D;
    E2 --> D;
    E3 --> D;
    E4 --> D;
    F1 --> E;
    F2 --> E;

## 📖 Table of Contents

- [🌟 Features](#-features)
- [🛠️ Architecture](#%EF%B8%8F-architecture)
- [⚙️ Installation & Usage](#%EF%B8%8F-installation--usage)
  - [Development Setup](#development-setup)
  - [Building for Production](#building-for-production)
  - [Loading the Extension](#loading-the-extension)
- [🧑‍💻 Development Standards](#-development-standards)
  - [Principles](#principles)
  - [Scripts](#scripts)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [🛡️ Security](#%EF%B8%8F-security)
- [🙏 Acknowledgments](#-acknowledgments)

---

## ⚙️ Installation & Usage

### Development Setup

To get started with local development, follow these steps:

1.  **Clone the Repository:**
    bash
    git clone https://github.com/chirag127/youtube-ai-navigator-bs-ext.git
    cd youtube-ai-navigator-bs-ext

2.  **Install Dependencies:**
    This project uses `npm` for package management.
    bash
    npm install

3.  **Start Development Server:**
    WXT provides a development server with Hot Module Replacement (HMR) for rapid iteration.
    bash
    npm run dev

### Building for Production

To create a production-ready build of the extension:

bash
npm run build

This command will generate the compiled extension files in the `dist` directory.

### Loading the Extension

Once built, you can load the extension into your browser:

1.  Open your browser's extension management page (e.g., `chrome://extensions` for Chrome, `about:debugging#/runtime/this-firefox` for Firefox).
2.  Enable "Developer mode" (usually a toggle in the top right).
3.  Click "Load unpacked" or "Load Temporary Add-on".
4.  Navigate to the `dist` folder within your cloned repository and select it.

## 🧑‍💻 Development Standards

### Principles

- **SOLID:** Adhere to the Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion principles.
- **DRY (Don't Repeat Yourself):** Avoid redundant code. Abstract common functionalities and components.
- **YAGNI (You Ain't Gonna Need It):** Implement only what is necessary, avoiding premature optimization or feature creep.
- **Code Clarity:** Write clean, readable, and well-commented code.
- **Type Safety:** Leverage TypeScript's strict mode to prevent common errors and enhance code maintainability.

### Scripts

Here are the essential development scripts:

| Script             | Description                                                           |
| :----------------- | :-------------------------------------------------------------------- |
| `npm run dev`      | Starts the development server with HMR for local development.         |
| `npm run build`    | Compiles the extension for production, outputting to `dist/`.         |
| `npm run lint`     | Runs Biome linter to check for code quality and style issues.         |
| `npm run format`   | Runs Biome formatter to automatically fix code style issues.          |
| `npm run test`     | Executes unit and integration tests using Vitest.                     |
| `npm run test:e2e` | Executes end-to-end tests using Playwright for browser interaction.   |
| `npm run preview`  | Builds and serves the extension for local testing without publishing. |

## 🤝 Contributing

We welcome contributions! Please refer to our [CONTRIBUTING.md](https://github.com/chirag127/youtube-ai-navigator-bs-ext/blob/main/.github/CONTRIBUTING.md) for guidelines on how to submit bug reports, feature requests, and pull requests.

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](https://github.com/chirag127/youtube-ai-navigator-bs-ext/blob/main/LICENSE) file for details.

## 🛡️ Security

We prioritize security. For information on how to report vulnerabilities and our security practices, please refer to [SECURITY.md](https://github.com/chirag127/youtube-ai-navigator-bs-ext/blob/main/.github/SECURITY.md).

## 🙏 Acknowledgments

- [Google Gemini API](https://ai.google.dev/) for powerful AI capabilities.
- [WXT](https://wxt.dev/) for an excellent web extension development experience.
- [Biome](https://biomejs.dev/) for blazing-fast linting and formatting.
- [SponsorBlock](https://sponsor.ajay.app/) for the open-source community-driven skipping functionality.
