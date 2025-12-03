# Next.js Static Export + Wasmer

This example shows how to export a **Next.js** app as static HTML and host it on **Wasmer Edge**.

## Demo

https://wasmer-edge-next-ssg-sample.wasmer.app/

## How it Works

* `next.config.js` sets `output: "export"`, so `next build && next export` emit static files into the `out/` directory.
* `src/app/page.tsx` contains the landing page (App Router), but any other static routes you add will be exported too.
* No serverless runtime is required—Wasmer simply serves the generated HTML/CSS/JS.

## Running Locally

```bash
npm install
npm run dev
```

Open `http://127.0.0.1:3000/` to develop with hot reload. To preview the static export:

```bash
npm run build
npm run export
npm run serve  # serves the ./out folder
```

## Deploying to Wasmer (Overview)

1. Build the site: `npm run build && npm run export` (creates the `out/` folder).
2. Configure Wasmer Edge to publish the `out/` directory.
3. Deploy and access `https://<your-subdomain>.wasmer.app/`.
