# A+Z — Software Engineering & Web Development

Marketing and portfolio site for A+Z (Alex Partida & Zach Queen). Built as a static site with vanilla HTML, CSS, and JavaScript.

🌐 **Live**: [atoz.codes](https://www.atoz.codes)

## Tech Stack

- **HTML5 / CSS3 / JavaScript** — Static site, no framework
- **jQuery** — DOM manipulation and plugins
- **Font Awesome** — Icons
- **Owl Carousel / Magnific Popup / Waypoints** — UI plugins
- **reCAPTCHA Enterprise** — Contact form spam protection

## Local Development

Open `index.html` directly in a browser, or use a local server:

```bash
npx serve .
```

### Linting

```bash
npm install
npm test
```

This runs HTMLHint on `index.html` and ESLint on `js/main.js`.

## CI/CD Pipeline

The GitHub Actions pipeline (`.github/workflows/static.yml`) runs on every push to `main`:

1. **Test** — Runs linting (HTMLHint + ESLint)  
2. **Deploy to GitHub Pages** — Automatic after tests pass  
3. **Deploy to AWS S3** — Requires manual approval via the `production` environment  

### Required GitHub Secrets

| Secret | Description |
|--------|-------------|
| `AWS_ROLE_ARN` | IAM role ARN for OIDC authentication |
| `AWS_REGION` | AWS region (e.g. `us-east-1`) |
| `S3_BUCKET_NAME` | S3 bucket for the site |
| `CLOUDFRONT_DISTRIBUTION_ID` | CloudFront distribution to invalidate |

## Project Structure

```
├── index.html          # Single-page site
├── css/                # Stylesheets (base, main, vendor, fonts)
├── js/                 # jQuery, plugins, main app logic
├── images/             # Portfolio images and assets
├── fonts/              # Custom fonts
├── favicon.svg         # Site icon
├── package.json        # Linting dependencies
└── .github/workflows/  # CI/CD pipeline
```

## Contact

📧 contact@atoz.codes
