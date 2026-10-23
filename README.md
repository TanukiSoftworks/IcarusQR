# IcarusQR

Client-side QR code generator with custom image overlay support. Built for deployment on Cloudflare Pages and Workers.

All encoding, matrix calculation and image manipulation take place strictly in the user's browser runtime. No data is transmitted to, cached by, or processed on remote infrastructure.

### Capabilities
- **Local Generation:** Generates standard QR codes (Model 2, Error Correction Level H) client-side via canvas.
- **Center Overlay:** Embeds arbitrary logos (PNG, SVG, JPEG) onto the generated matrix with white protective padding.
- **Zero Telemetry:** Operates fully offline after the initial page load; no external tracking or storage hooks.
- **Export:** Direct high-resolution PNG export.

### Architecture & Runtime
- **Static Frontend:** Plain HTML5, vanilla CSS3 variables and client-side JavaScript.
- **Edge Delivery:** Packaged for Cloudflare Workers (`src/index.js`) and Cloudflare Pages (`wrangler.toml`, `_redirects`).
- **Dependencies:** Uses `qrcodejs` loaded via CDN for raster canvas rendering.

### Local Development
To serve locally using Cloudflare Wrangler:

```bash
npx wrangler dev
```

Alternatively, serve the directory with any static HTTP server:

```bash
python -m http.server 8080
```

### Deployment

#### Cloudflare Pages
1. Link your repository in **Cloudflare Dashboard > Workers & Pages > Pages**.
2. Set Build Command to **None** and Output Directory to root `/` (or deploy via Direct Upload).
3. Confirm deployment.

---

Maintained under [Tanuki Softworks](https://github.com/TanukiSoftworks).
