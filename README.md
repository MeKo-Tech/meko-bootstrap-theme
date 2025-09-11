# MeKo Bootstrap Theme

A custom Bootstrap 5 theme featuring MeKo branding with primary color `#00aaa7` and Open Sans typography. Includes light and dark theme variants.

🔗 **[View Live Demo](https://meko-tech.github.io/meko-bootstrap-theme/)**

## Features

- ✅ **Custom MeKo Colors**: Primary `#00aaa7`, Secondary `#595959`
- ✅ **Open Sans Typography**: Complete font family integration
- ✅ **Light/Dark Themes**: Full Bootstrap dark mode support
- ✅ **Content Hashing**: CDN-optimized with cache busting
- ✅ **Auto Deployment**: GitHub Actions to DigitalOcean Spaces

## Quick Start

### CDN Usage (Preferred)

```html
<!-- Production (minified) -->
<link href="https://[bucket].[region].digitaloceanspaces.com/meko-bootstrap-theme/bootstrap-meko.min.[hash].css" rel="stylesheet">

<!-- Development -->
<link href="https://[bucket].[region].digitaloceanspaces.com/meko-bootstrap-theme/bootstrap-meko.[hash].css" rel="stylesheet">
```

### GitHub Releases (Alternative)

**Note**: While GitHub releases are available, the CDN approach above is preferred for production use due to optimized caching and global distribution.

```html
<!-- From GitHub Releases -->
<link href="https://github.com/MeKo-Tech/meko-bootstrap-theme/releases/download/v1.0.1/bootstrap-meko.min.css" rel="stylesheet">
```

You can download assets from the [releases page](https://github.com/MeKo-Tech/meko-bootstrap-theme/releases) or reference them directly via URL.

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

## Releases

New versions are automatically released when tags are pushed:

```bash
# Create new version and push tag
npm version patch  # or minor/major
git push origin --tags
```

This triggers the release workflow which:
- Builds minified CSS files
- Creates GitHub release with assets
- Uploads both `.tar.gz` and `.zip` distributions
- Makes individual CSS files available for direct download

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