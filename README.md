# FunErrorHTML

A collection of fun, playful HTTP error pages (404, 500, …) — because getting lost on the web should at least be entertaining.

Every page is a **single, self-contained HTML file**: no build step, no framework, no external dependencies. Just drop it on your server and you're done.

## Available pages

| Error | File | Description |
| ----- | ---- | ----------- |
| 404 – Not Found | [`404.html`](404.html) | *Lost in space* — a retro arcade shooter. Pilot your ship with the arrow keys or mouse (or your finger on mobile), shoot with Space or click, pause with `P`. Best score is saved locally. |

More pages are on the way. Contributions are welcome!

## Usage

1. Download the HTML file you want (e.g. `404.html`).
2. Upload it to your web server.
3. Configure your server to serve it for the matching status code.

### Apache (`.htaccess`)

```apache
ErrorDocument 404 /404.html
```

### Nginx

```nginx
error_page 404 /404.html;
location = /404.html {
    internal;
}
```

### GitHub Pages / Netlify / Vercel

Place `404.html` at the root of your site — these platforms pick it up automatically.

## Preview locally

Simply open the file in your browser, or serve the folder:

```bash
npx serve .
# or
python -m http.server 8000
```

## Contributing

Everyone is welcome to contribute — add a new error page, improve an existing one, fix a bug or translate a page.

1. Fork the repository.
2. Create a branch: `git checkout -b feature/my-500-page`.
3. Add your page following the guidelines below.
4. Open a pull request with a short description and, ideally, a screenshot or GIF.

### Guidelines

- **One file per page**, named after the status code (`403.html`, `500.html`, `503.html`, …). If you want to offer several designs for the same code, use a suffix (e.g. `404-retro.html`).
- **Self-contained**: inline your CSS, JavaScript and assets (SVG, data URIs). No CDN or external requests.
- **Responsive & accessible**: works on desktop and mobile, keyboard-friendly, respects `prefers-reduced-motion` where relevant.
- **Lightweight**: keep it fast to load — it's an error page, after all.
- **Fun**: make people smile. 🙂
- Add your page to the table in this README.

## License

This project is licensed under the [MIT License](LICENSE) — free to use, modify and share.
