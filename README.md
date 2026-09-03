# Skunkworks Horizon Shopify theme

Reusable Shopify Online Store 2.0 base theme for Skunkworks online stores. It centralizes brand tokens, responsive navigation and footer, commerce and content templates, reusable sections, accessible defaults, and store-independent configuration.

## Requirements

- A Shopify development store or store with Theme Access credentials
- Shopify CLI for local development (`npm install -g @shopify/cli@latest`)
- GitHub Actions for the included automated validation and deployment workflows

## Local development

1. Clone the repository and enter its root.
2. Run `shopify theme dev --store your-store.myshopify.com`.
3. Open the preview URL and customize the theme in the Shopify editor.
4. Run `shopify theme check` before opening a pull request.

## Reusing and syncing

Create a store-specific repository from this base or add this repository as an upstream remote. Keep store content and credentials out of Git. Configure branding in **Online store → Themes → Customize → Theme settings**, and select navigation menus in the header and footer sections.

For later improvements, merge tagged releases from this repository into each store repository, resolve deliberate store overrides, run Theme Check, and preview on an unpublished theme before production.

## Deployment

The manual `Deploy Shopify theme` workflow supports `development` and `production` GitHub environments. Configure these environment secrets:

- `SHOPIFY_STORE`: store domain, for example `example.myshopify.com`
- `SHOPIFY_THEME_ACCESS_PASSWORD`: Theme Access app password

Development deploys as an unpublished theme. Production uses a protected GitHub environment and pushes to the live theme; require reviewers on that environment.

## Structure

- `config/`: global design tokens and saved settings
- `layout/`: document shell and section groups
- `sections/`: merchant-configurable page modules
- `snippets/`: reusable rendering primitives
- `templates/`: Online Store 2.0 JSON templates
- `assets/`: global CSS and progressive-enhancement JavaScript

## Pull request checklist

- Previewed on desktop and mobile
- Keyboard navigation and visible focus checked
- Theme Check passes
- Product, collection, search, cart, contact, blog, and article flows tested
- No store credentials or store-specific content committed

Demo: [liquid.skunkworks.africa](https://liquid.skunkworks.africa/)
