# Awesome-Web-Font-Delivery-API

# Top Web PDF Rendering API Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Browser-Native Rendering, WASM-Powered Engines & Self-Hosted Annotation Layers*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Web PDF Rendering APIs**. These tools embed PDF viewing, annotation, and form-filling into web applications — handling the hard parts of parsing the PDF spec, rendering pages to canvas, and managing interactive layers — without sending documents to a third-party server.

**Examples** include PDF.js, MuPDF.js, react-pdf, Fresh Air PDF, and the commercial SDKs (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, WASM-based rendering, and transparent document handling — ideal for developers who need PDF viewing inside their product without per-document API fees or vendor lock-in.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Adobe PDF Embed API** — Adobe's free JavaScript API for embedding PDF viewing into web pages. **Free to use** with Adobe branding; removes branding on paid plans. **Best for simple viewing** where Adobe's rendering fidelity matters and you don't need deep customization.

- **PSPDFKit (Nutrient)** — **The most feature-complete commercial PDF SDK.** Full annotation, form filling, digital signatures, and document editing. **Subscription-based** per platform. **Best for enterprises** needing production-grade PDF editing with vendor support.

- **Apryse WebViewer** — Commercial PDF SDK with rendering, annotation, and editing capabilities. **Best for teams wanting a mature commercial SDK** with extensive format support beyond PDF.

## Open-Source GitHub Projects

- **PDF.js** — **The browser-native PDF standard.** Apache 2.0 licensed, maintained by Mozilla. **A general-purpose, web standards-based platform for parsing and rendering PDFs** using HTML5 and JavaScript, without requiring a browser plugin. **Three layers**: **Core** (binary PDF parsing), **Display** (rendering API), and **Viewer** (the UI powering Firefox's built-in PDF viewer). **The foundation most open-source PDF viewers build on** — react-pdf, lumipdf, and countless wrappers use PDF.js as their engine. **Best for any web application needing PDF rendering** without server-side conversion.

- **MuPDF.js** — **The WASM build of MuPDF for JavaScript.** **AGPL-3.0 or commercial license**. **A build of MuPDF for JavaScript and TypeScript, powered by WebAssembly** [citation:1]. **Works in all common JavaScript environments**: Firefox, Safari, Chrome, Node, Bun. **Features**: open, manipulate, and save PDF files; render documents to raster images; extract structured text; create and edit annotations; fill out forms; redact sensitive content [citation:1]. **The AGPL license means commercial use requires either open-sourcing your application or purchasing a commercial license** [citation:1]. **Best for teams needing MuPDF's rendering fidelity** in the browser, accepting the AGPL obligation or commercial license.

- **react-pdf** — **The React wrapper for PDF.js.** **Renders PDF pages as React components** with `<Document>` and `<Page>`. **Supports annotations and text layers** via CSS imports (`AnnotationLayer.css`, `TextLayer.css`). **Requires configuring the PDF.js worker** — either copying `pdf.worker.mjs` to your output folder or using a CDN [citation:7]. **Best for React applications** wanting PDF viewing without building on raw PDF.js.

- **Fresh Air PDF** — **The self-hosted React viewer with built-in annotations and forms.** **A fully-featured, open-source PDF viewer React component with built-in annotations, form fields, signatures, search, and more — powered by Mozilla's PDF.js** [citation:9]. **No commercial SDK required, no data leaves the browser** [citation:9]. **Features**: full annotation toolbar (highlight, underline, strikeout, free text, shapes, ink), **form fields with persistent values** (text, checkbox, radio, dropdown, signature), **signature capture via canvas**, search with highlighting, thumbnails, outline navigation, and **JSON import/export** for all annotation and form data [citation:9]. **Best for React teams** wanting annotations and forms without paying for a commercial SDK — the closest open-source match to PSPDFKit's feature set.

### Additional Strong Open-Source Options

- **@jacktea/pdf-viewer-component** — **Vanilla Web Components PDF viewer with annotations** [citation:8]. Framework-agnostic — runs in Vue, React, Angular, Svelte, or plain HTML. **WASM-based rendering** with highlight, underline, ink, and text label annotations [citation:8]. Best for teams wanting a framework-agnostic component.
- **lumipdf** — React PDF viewer built on PDF.js with **Canva-style editable annotations** (select, move, resize, delete) . Virtualized rendering for 1000+ page documents. Annotations are viewer overlays only — download and print use the original PDF . Best for React teams wanting interactive annotation UX.
- **pdf_document (Dart)** — **Pure Dart PDF library with annotations, forms, signatures, and incremental-save editing** [citation:3]. Web-compatible. Best for Dart/Flutter web applications needing document-level PDF manipulation.
- **pdf-to-images-cli** — Python CLI and **FastAPI REST microservice** for converting PDF pages to images [citation:4]. Best for server-side PDF-to-image pipelines, not client-side rendering.

**Frameworks for building custom systems**: Combine **PDF.js** for the rendering engine, **react-pdf** for React integration, **Fresh Air PDF** for annotations and forms without a commercial SDK, **MuPDF.js** for WASM-powered parsing with AGPL licensing, and **@jacktea/pdf-viewer-component** for framework-agnostic embedding — to build a web PDF rendering stack tailored to your framework, annotation requirements, and licensing constraints.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Web PDF rendering APIs differ significantly in licensing, annotation depth, and deployment model. **PDF.js is the foundation most open-source viewers build on** — it's the engine, not a complete viewer UI . **MuPDF.js is AGPL-3.0 licensed** — commercial use requires either open-sourcing your application or purchasing a commercial license [citation:1]. **Fresh Air PDF provides annotations and forms** without commercial SDK fees, but it's a newer project — validate maintenance activity before production . **react-pdf requires configuring the PDF.js worker** — either copy `pdf.worker.mjs` to your output or use a CDN [citation:7]. **lumipdf's annotations are viewer overlays only** — they don't modify the underlying PDF file .
- Self-hosted open-source solutions require proper worker file configuration, CORS headers for remote PDFs, and awareness that browser rendering is limited by available memory for very large documents.

---

**Made for web developers embedding PDF viewing, annotation, and forms into their applications.**
Let's make web PDF rendering more open, self-hostable, and annotation-capable.
