# MeKo Bootstrap Theme

A custom Bootstrap 5 theme featuring MeKo branding with primary color `#00afaa` and Open Sans typography. Includes light and dark theme variants.

## Features

- ✅ **Custom MeKo Colors**: Primary `#00afaa`, Secondary `#595959`
- ✅ **Open Sans Typography**: Complete font family integration
- ✅ **Light/Dark Themes**: Full Bootstrap dark mode support
- ✅ **Content Hashing**: CDN-optimized with cache busting
- ✅ **Auto Deployment**: GitHub Actions to DigitalOcean Spaces

## Quick Start

### CDN Usage

```html
<!-- Production (minified) -->
<link href="https://[bucket].[region].digitaloceanspaces.com/meko-bootstrap-theme/bootstrap-meko.min.[hash].css" rel="stylesheet">

<!-- Development -->
<link href="https://[bucket].[region].digitaloceanspaces.com/meko-bootstrap-theme/bootstrap-meko.[hash].css" rel="stylesheet">
```

### Theme Toggle

```html
<button onclick="toggleTheme()">Toggle Dark Mode</button>

<script>
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-bs-theme');
  const newTheme = current === 'dark' ? 'light' : 'dark';
  html.setAttribute('data-bs-theme', newTheme);
}
</script>
```

## Development

```bash
# Install dependencies
npm install

# Build theme
npm run build

# Start demo server
npm run dev

# Watch mode (live reload)
npm run dev:watch

# Build for CDN (hashed assets)
npm run build:cdn
```

## Deployment

### GitHub Secrets

Add these secrets to your repository:

```
DO_SPACES_KEY=your_digitalocean_spaces_access_key
DO_SPACES_SECRET=your_digitalocean_spaces_secret_key  
DO_SPACES_REGION=your_region (e.g., fra1, nyc3, sfo3)
DO_SPACES_BUCKET=your_bucket_name
```

### Automatic Deployment

- **Trigger**: Push to `main` branch
- **Output**: `https://[bucket].[region].digitaloceanspaces.com/meko-bootstrap-theme/`
- **Cache**: 1-year cache headers with content hashing

## Project Structure

```
├── scss/              # Source SCSS files
├── assets/fonts/      # Open Sans font files
├── demo/              # Theme demo application
├── dist/              # Built CSS + hashed assets
└── .github/workflows/ # Auto-deployment
```

## Built With

- **Bootstrap 5.3.8**: Base framework
- **Sass**: CSS preprocessing  
- **PostCSS**: CSS optimization
- **GitHub Actions**: CI/CD pipeline
- **DigitalOcean Spaces**: CDN hosting

## License

MIT