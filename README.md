# Awesome-Web-Font-Delivery-API

### Top Web Font Delivery API Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted Font Serving, GDPR-Compliant Subsetting & Build-Time Embedding*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Web Font Delivery APIs**. These tools serve font files to websites — handling the CSS generation, subsetting, and caching that makes typography fast and privacy-compliant — with a spectrum running from commercial font foundries to open-source self-hosted services that eliminate third-party tracking.

**Examples** include Fontless, Google Webfonts Helper, Fontsource, and Fontsource Downloader (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, build-time font embedding, and GDPR-compliant delivery — ideal for developers who want Google Fonts convenience without Google tracking their users.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Google Fonts** — **The ubiquitous free font API.** Serves 1,500+ font families via a simple `<link>` tag, with automatic browser-appropriate format selection (WOFF2) and CSS generation. **Free to use**. **The privacy problem**: Google logs IP addresses and user agents for every font request, creating GDPR compliance issues for European sites. **Best for rapid prototyping** where privacy compliance isn't yet a concern.

- **Adobe Fonts** — **The Creative Cloud font library with web embedding.** Requires an Adobe subscription; fonts are served via Typekit project IDs. **Best for existing Creative Cloud subscribers** wanting licensed commercial fonts without separate hosting.

- **Monotype Fonts** — Enterprise font licensing and delivery platform with web font serving and brand compliance controls. **Best for large organizations** needing licensed font catalogs with governance.

## Open-Source GitHub Projects

- **Fontless** — **The Vercel-deployable Google Fonts privacy replacement.** MIT licensed, built to provide the same simplicity as Google Fonts but for self-hosted fonts . **Drop-in API compatibility**: replace `fonts.googleapis.com` with your Fontless instance hostname, and existing `<link>` tags work unchanged — full support for the Google Fonts CSS2 API . **No tracking, no cookies, no analytics** — just fonts served from your own domain . **Web-based setup**: select fonts in a browser UI, then deploy to Vercel or download the generated service . **Works by downloading fonts from Google Fonts at build-time** and placing them in a `/fonts` directory, with a serverless function implementing the CSS2 API . **Best for teams wanting Google Fonts convenience without Google tracking**, especially those already on Vercel.

- **Google Webfonts Helper** — **The self-hosted font downloader with CSS snippets.** MIT licensed, available as a public instance at `gwfh.mranftl.com` or self-hosted via Docker . **Downloads font files in eot, ttf, svg, woff, and woff2 formats**, with customized CSS `@font-face` snippets . **Requires a Google Fonts API key** for self-hosting (`GOOGLE_FONTS_API_KEY`) . **The classic solution** for developers who want to download Google Fonts once and serve them locally . **Best for one-time font extraction** where you want static files and CSS rather than a running service.

- **Fontsource** — **The NPM package approach to self-hosted fonts.** MIT licensed, **45+ versions** with active maintenance as of March 2026 . **Packages open-source fonts as installable npm modules** — `npm install @fontsource/open-sans` — so fonts are bundled into your build rather than fetched from a third-party CDN . **Self-hosting improves performance** by eliminating extra DNS resolution and TCP connection establishment required by CDN like Google Fonts, and **fonts remain version locked** — Google often pushes updates without notice, which can interfere with production projects . **Privacy**: Google tracks font usage; self-hosting is the alternative . **Supports fonts outside the Google Font ecosystem**, including variable fonts like `@fontsource-variable/roboto-flex` . **Best for JavaScript/TypeScript projects** where build-time font embedding fits the bundler workflow.

- **Fontsource Downloader** — **The library for downloading and caching Fontsource fonts programmatically.** MIT licensed . **Downloads a batch of fonts per family based on a given query**, with **asynchronous downloads with true parallelism** . **Generates CSS `@font-face` rules** — both CDN URLs and self-hosting relative path URLs are supported, and self-hosted font files can be copied from cache to a destination directory . **Caching enabled** (with customizable cache root dir) for both metadata and font files . **Rust consumers get to choose their desired TLS backend** . **Best for teams wanting programmatic control** over Fontsource font downloads with caching, rather than manual npm installation.

### Additional Strong Open-Source Options

- **Coolify Fonts** — **Privacy-friendly drop-in replacement for Google Fonts.** Apache-2.0 licensed, **602 GitHub stars**, actively maintained through January 2026 . **A CDN alternative** that serves Google Fonts without the tracking. **Best for teams already in the Coolify ecosystem** or wanting a simple privacy-focused Google Fonts CDN replacement.

- **MkDocs Fontkit** — **Static analysis font kit builder for MkDocs.** MIT licensed . **Self-hosts fonts from Adobe Fonts (Typekit) and Google Fonts locally** without relying on client-side JS or external CDNs . **Static analysis for Typekit** reverses the dynamic loading logic to generate stable WOFF2 URLs and CSS using Bloom filters and hash generation — no Headless Chrome required . **Smart CJK font splitting** integrates `cn-font-split` to chunk large Chinese/Japanese/Korean fonts for faster initial load . **Best for MkDocs documentation sites** needing self-hosted fonts with CJK support.

- **Bengal Fonts System** — **Built-in font management for the Bengal static site generator.** MIT licensed . **Automatically downloads and hosts Google Fonts locally** — zero configuration, just specify fonts in `bengal.toml` . **No external requests to Google Fonts CDN at runtime**, faster page loads, GDPR/privacy compliance, offline builds, and cache control . **Downloads WOFF2 and TTF formats**, generates `@font-face` CSS with CSS custom properties . **Best for Bengal users** wanting automatic self-hosted font handling without manual setup.

**Frameworks for building custom systems**: Combine **Fontless** for a Vercel-deployed Google Fonts replacement with drop-in API compatibility, **Fontsource** for NPM-based font embedding in JavaScript builds with version locking, **Google Webfonts Helper** for one-time static font extraction with CSS snippets, and **Fontsource Downloader** for programmatic font downloading with caching — to build a web font delivery stack tailored to your privacy requirements, build toolchain, and deployment model.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Web font delivery APIs differ significantly in privacy model, build integration, and hosting requirements. **Google Fonts is free and ubiquitous** but logs IP addresses and user agents for every request, creating GDPR compliance issues. **Fontless provides drop-in API compatibility** — replace the hostname and existing `<link>` tags work unchanged — while eliminating third-party tracking . **Fontsource moves fonts into your build**, improving performance by eliminating extra DNS resolution and TCP connection establishment, and keeps fonts version locked so Google's unannounced updates can't break production . **Google Webfonts Helper requires a Google Fonts API key** for self-hosting . **Self-hosting shifts responsibility to you** — font licensing, cache headers, and CORS configuration become your operations.
- Self-hosted open-source solutions require proper CORS headers for cross-origin font files, cache-control configuration for immutable asset hashing, and awareness that WOFF2 is the only format modern browsers need.

---

**Made for web developers serving typography that's fast, private, and properly licensed.**
Let's make web font delivery more open, GDPR-compliant, and build-integrated.
# Awesome-Web-Font-Delivery-API

## Top Web Font Delivery API Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted Font Serving, GDPR-Compliant Subsetting & Build-Time Embedding*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Web Font Delivery APIs**. These tools serve font files to websites — handling the CSS generation, subsetting, and caching that makes typography fast and privacy-compliant — with a spectrum running from commercial font foundries to open-source self-hosted services that eliminate third-party tracking.

**Examples** include Fontsource, Fontless, Web Fonts Repository, and google-webfonts-helper (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, build-time font embedding, and GDPR-compliant delivery — ideal for developers who want Google Fonts convenience without Google tracking their users.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Google Fonts** — **The ubiquitous free font API.** Serves 1,500+ font families via a simple `<link>` tag, with automatic browser-appropriate format selection (WOFF2) and CSS generation [citation:1][citation:11]. **Free to use**. **The privacy problem**: Google logs IP addresses and user agents for every font request, creating GDPR compliance issues for European sites [citation:2][citation:12]. **Best for rapid prototyping** where privacy compliance isn't yet a concern.

- **Adobe Fonts** — **The Creative Cloud font library with web embedding.** Requires an Adobe subscription; fonts are served via Typekit project IDs. **Best for existing Creative Cloud subscribers** wanting licensed commercial fonts without separate hosting.

- **Monotype Fonts** — Enterprise font licensing and delivery platform with web font serving and brand compliance controls. **Best for large organizations** needing licensed font catalogs with governance.

## Open-Source GitHub Projects

- **Fontsource** — **The NPM package approach to self-hosted fonts.** MIT licensed, **45+ versions** with active maintenance as of March 2026 [citation:4]. **Packages open-source fonts as installable npm modules** — `npm install @fontsource/open-sans` — so fonts are bundled into your build rather than fetched from a third-party CDN . **Self-hosting improves performance** by eliminating extra DNS resolution and TCP connection establishment required by CDN like Google Fonts, and **fonts remain version locked** — Google often pushes updates without notice, which can interfere with production projects . **Privacy**: Google tracks font usage; self-hosting is the alternative . **Supports fonts outside the Google Font ecosystem**, including variable fonts. **Most fonts use SIL OFL 1.1; some use Apache 2; Ubuntu fonts use the Ubuntu Font License** . **Best for JavaScript/TypeScript projects** where build-time font embedding fits the bundler workflow.

- **Fontless** — **The Vercel-deployable Google Fonts privacy replacement.** MIT licensed, built to provide the same simplicity as Google Fonts but for self-hosted fonts. **Drop-in API compatibility**: replace `fonts.googleapis.com` with your Fontless instance hostname, and existing `<link>` tags work unchanged — full support for the Google Fonts CSS2 API. **No tracking, no cookies, no analytics** — just fonts served from your own domain. **Web-based setup**: select fonts in a browser UI, then deploy to Vercel or download the generated service. **Works by downloading fonts from Google Fonts at build-time** and placing them in a `/fonts` directory, with a serverless function implementing the CSS2 API. **Best for teams wanting Google Fonts convenience without Google tracking**, especially those already on Vercel.

- **Web Fonts Repository (finesse)** — **The self-hosted webfont hosting service inspired by Google Fonts.** PHP-based, runs on your own server, stores and distributes webfont files, and **generates CSS on-the-go for embedding fonts on web pages** [citation:5]. **Usage syntax mirrors Google Fonts**: `<link rel="stylesheet" href="http://your-server/css?family=Open+Sans:400,400i,700|Roboto:300,400" />` [citation:5]. **Configure fonts via a PHP settings file** with glob patterns mapping weights and styles to files in the `public/fonts` directory [citation:5]. **Requires**: PHP ≥ 7.0, Composer, and CORS headers on font files (`Access-Control-Allow-Origin: *`) [citation:5]. **Best for PHP-based stacks** wanting a self-hosted Google Fonts clone with familiar URL syntax.

- **google-webfonts-helper** — **The self-hosted font downloader with CSS snippets.** MIT licensed, available as a public instance at `gwfh.mranftl.com` or self-hosted via Docker. **Downloads font files in eot, ttf, svg, woff, and woff2 formats**, with customized CSS `@font-face` snippets [citation:2][citation:12]. **Requires a Google Fonts API key** for self-hosting. **The classic solution** for developers who want to download Google Fonts once and serve them locally [citation:2][citation:12]. **Best for one-time font extraction** where you want static files and CSS rather than a running service.

### Additional Strong Open-Source Options

- **Coolify Fonts** — **Privacy-friendly drop-in replacement for Google Fonts.** Apache-2.0 licensed, **602 GitHub stars**, actively maintained through January 2026 [citation:9]. **A CDN alternative** that serves Google Fonts without the tracking. **Best for teams already in the Coolify ecosystem** or wanting a simple privacy-focused Google Fonts CDN replacement.

- **fontello-server** — **Self-hosted icon font server.** MIT licensed, persists fontello icon fonts in LevelDB and serves them with hashed links [citation:10]. **Best for icon font delivery** rather than text typefaces.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Web font delivery APIs differ significantly in privacy model, build integration, and hosting requirements. **Google Fonts is free and ubiquitous** but logs IP addresses and user agents for every request, creating GDPR compliance issues [citation:2][citation:12]. **Fontsource moves fonts into your build**, improving performance by eliminating extra DNS resolution and TCP connection establishment, and keeps fonts version locked so Google's unannounced updates can't break production . **Fontless provides drop-in API compatibility** — replace the hostname and existing `<link>` tags work unchanged — while eliminating third-party tracking. **Web Fonts Repository requires PHP and Composer** — it is not a static file solution [citation:5]. **google-webfonts-helper requires a Google Fonts API key** for self-hosting [citation:2]. **Self-hosting shifts responsibility to you** — font licensing, cache headers, and CORS configuration become your operations.
- Self-hosted open-source solutions require proper CORS headers for cross-origin font files, cache-control configuration for immutable asset hashing, and awareness that WOFF2 is the only format modern browsers need.

---

**Made for web developers serving typography that's fast, private, and properly licensed.**
Let's make web font delivery more open, GDPR-compliant, and build-integrated.
