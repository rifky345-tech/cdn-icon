# 🎨 Private Icon CDN (Font Awesome Pro v7.3.0)

A lightweight, self-hosted static CDN for Font Awesome Pro assets with pre-configured CORS, caching, and multi-platform deployment support.

## 🚀 Quick Integration

Add the following stylesheet links to the `<head>` of your website or app:

```html
<!-- Core Font Awesome Pro CSS -->
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/fontawesome.css">

<!-- Style Extensions (Include what you need) -->
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/solid.css">
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/regular.css">
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/light.css">
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/duotone.css">
<link rel="stylesheet" href="https://your-cdn-domain.com/v7.3.0/css/brands.css">
```

---

## 📁 Repository Structure

```text
cdn-icon/
├── _headers             # CORS & Cache rules for Cloudflare Pages / Netlify
├── vercel.json          # CORS & Cache rules for Vercel
├── index.html           # Interactive CDN Landing Page & Documentation
├── package.json         # Project metadata & local server runner
├── README.md            # Usage documentation
└── v7.3.0/              # Font Awesome Pro v7.3.0 static distribution
    ├── css/             # Stylesheet files
    ├── webfonts/        # Highly optimized WOFF2 web fonts
    ├── ttf/             # TrueType fonts
    └── icons.json       # Icon metadata & unicode mapping
```

---

## 🛠️ Deployment Instructions

### 1. Vercel / Cloudflare Pages / Netlify (Recommended)
1. Push this repository to GitHub/GitLab.
2. Import the repository into your platform dashboard.
3. Deploy directly without build commands. CORS and caching headers are handled automatically via `vercel.json` or `_headers`.

### 2. Self-Hosted (Nginx)
Ensure CORS headers are enabled for cross-origin font loading:

```nginx
server {
    listen 80;
    server_name cdn.yourdomain.com;
    root /path/to/cdn-icon;

    location / {
        add_header Access-Control-Allow-Origin "*";
        add_header Cache-Control "public, max-age=31536000, immutable";
        try_files $uri $uri/ =404;
    }
}
```

---

## 📄 License
Internal / Private CDN asset hosting. Font Awesome Pro is subject to [Font Awesome License](https://fontawesome.com/license).
