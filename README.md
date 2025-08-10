# video1

## Overview  
**video1** is a lightweight web application built with **Vue 3**, **Vite**, and **TypeScript**. It showcases a custom interactive HTML5 video player interface.

The application allows users to:  
- Play and pause a video seamlessly.  
- Mute and unmute audio instantly.  
- Skip to any point in the video using an interactive progress/timeline bar.  
- Enjoy a responsive, performant, and accessible UI.

This project serves as both a functional media player and a code sample demonstrating a structured Vue 3 + Vite setup.

---

## Why this project exists  
The purpose of this project is to:  
1. Demonstrate **proficiency in modern front-end frameworks** (Vue 3) and tooling (Vite, TypeScript).  
2. Showcase the **implementation of custom video playback controls** beyond the native HTML5 UI.  
3. Serve as a **portfolio-ready example** of building a user-friendly, interactive web application.

---

## Quick start (clone & run)  
```bash
# 1) Clone the repository
git clone <YOUR_REPO_URL>
cd onm1-main/onm1-main

# 2) Install dependencies
npm install

# 3) Start the development server
npm run dev
```

---

## Dependencies & setup  
- **Core tech stack:** Node.js (v18+), Vue 3, Vite, TypeScript.  
- **Package manager:** npm (compatible with pnpm/yarn).  
- **Recommended:** Use `nvm` or `asdf` to match the correct Node version.

### Direct dependencies  
- `vue` — reactive UI framework for building the video player and controls.

### Dev dependencies  
- `@vitejs/plugin-vue` — Vue integration for Vite.  
- `@vue/tsconfig` — official TypeScript config for Vue projects.  
- `typescript` — static type checking.  
- `vite` — fast development server and build tool.  
- `vue-tsc` — type checking for Vue single-file components.

---

## Features in detail  
- **Play / Pause** — Start and stop video playback smoothly.  
- **Mute / Unmute** — Toggle audio without affecting playback position.  
- **Seek via Timeline** — Jump to any position in the video with a click or drag on the progress bar.  
- **Responsive Design** — Works across desktop and mobile devices.  
- **Custom Controls** — Replaces the default HTML5 controls with a styled, accessible UI.

---

## Common scripts  
- **Install:** `npm install`  
- **Development (HMR):** `npm run dev`  
- **Build (production):** `npm run build`  
- **Preview build:** `npm run preview`  

---

## How to run tests  
Currently, no test suite is configured. Suggested setup:  
```bash
npm install -D vitest @vue/test-utils jsdom
npx vitest
```
Once added, tests can be run via:
```bash
npm test
```

---

## How to contribute  
1. Fork the repository and create a feature branch.  
2. Follow existing code style and keep commits focused.  
3. If introducing new features, add documentation and tests.  
4. Submit a pull request with a clear description of the changes and their purpose.

---

## What powers the core functionality?  
- **Vue 3** — For building a reactive, component-based UI.  
- **Vite** — For lightning-fast builds and hot-module replacement.  
- **TypeScript** — For robust type safety and maintainability.  
- **HTML5 Video API** — To control playback, audio, and seeking programmatically.
