# nextbasepath

Tiny wrapper components and utilities to make **Next.js static export (`output: "export"`)** work correctly with assets in the `public/` folder when hosting on sub-paths — especially **GitHub Pages**.

## ✨ Features

- Drop-in wrappers:
  - **`<Image>`** → auto-prefix `basePath` for `src="/..."`  
  - **`<Link>`** → auto-prefix `basePath` for internal routes and file links  
  - **`<Anchor>`** → safe prefix for download links to static files  
  - **`<Bg>`** → helper for inline background-image styles
- Utilities:
  - `prefixPath`, `prefixUrlObject`, `prefixCssUrl`
  - `getBasePath` for consistent env reading
- Keep JSX unchanged: `<Image src="/logo.svg" />` → `/<repo>/logo.svg` automatically.

## 🚀 Install (directly from GitHub)

Since this package is not published on npm, install it directly from your public repo:

```bash
npm install hieupth/nextbasepath#main
```

Because this is installed from Git, the package uses `prepare` to build automatically on install.

## 🛠️ Usage

```tsx
import { Image, Link, Anchor, Bg } from "nextbasepath/components";

// Image wrapper: auto-prefix basePath
<Image src="/next.svg" alt="Next.js logo" width={180} height={38} />
// Link wrapper: works for both routes and public files
<Link href="/docs">Docs</Link>
// Anchor: download file from public/
<Anchor href="/files/whitepaper.pdf" download>Download</Anchor>
// Bg: inline background with prefixed URL
<Bg bg="/images/hero.jpg" className="hero-section" />
```

## 📝 License

[GNU AGPL v3.0](LICENSE). <br>
Copyright &copy; 2025 [Hieu Pham](https://github.com/hieupth). All rights reserved.