# rares cazan — portfolio & blog

[![Astro](https://img.shields.io/badge/Astro-v5-%23FF5D01.svg?style=flat&logo=astro&logoColor=white)](https://astro.build/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)](https://vercel.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A minimal, fast personal website and blog built to showcase my software engineering projects, background, and writings on tech, literature, and philosophy.

🔗 **Live Website**: [https://rares-cazan-logs.vercel.app](https://rares-cazan-logs.vercel.app)

---

## Why I Built This

I wanted a clean space on the web that felt personal and deliberate. Rather than using a template or an overly complex framework, I designed and built this from the ground up to reflect my aesthetic: warm muted tones, subtle typography, and fast, native performance.

It serves two purposes:
1. **Portfolio**: A showcase of my work across systems programming, client-side computer vision, and agentic AI architectures.
2. **Blog**: A space to write about technical challenges and ideas from philosophy and literature.

---

## Tech Stack & Architecture

- **[Astro](https://astro.build/) (v5)**: Selected for its content-first philosophy, static site generation, and zero-JS baseline.
- **Vanilla CSS**: Styled with a warm parchment background (`#FAF8F5`), terracotta accents (`#C46353`), and crisp Montserrat typography.
- **Content Collections**: Type-safe Markdown blog workflow backed by Astro's Content Layer schema validation (`src/content.config.ts`). Writing a new post is as simple as dropping a `.md` file in `src/content/blog/`.
- **Seamless View Transitions**: Integrated Astro `ClientRouter` with custom scroll-interception scripts. Navigating between the multi-section homepage and blog routes smoothly scrolls to the top before cross-fading, preventing abrupt jumps while preserving native page anchor navigation.
- **Inline Project Previews**: Interactive expandable project cards that load details inline without full-page reloads.
- **Hosting**: Deployed and hosted globally with [Vercel](https://vercel.com) at [rares-cazan-logs.vercel.app](https://rares-cazan-logs.vercel.app).

---

## Getting Started

### Prerequisites
- Node.js `v22.12.0` or higher
- npm

### Installation
```bash
git clone https://github.com/rarescazan30/portfolio-website.git
cd portfolio-website
npm install
```

### Development
```bash
npm run dev
# or expose on your local network:
npm run dev -- --host
```

### Build
```bash
npm run build
```

---

## License

This project is licensed under the [MIT License](LICENSE).
