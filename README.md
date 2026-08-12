# BJ Group

This repository hosts the BJ Group website built with Vue 3, Vite, and a Node server component.

## Project structure

- `client/` - Vue 3 frontend app
- `server/` - backend services and API routes
- `package.json` - root metadata and workspace tooling

## Frontend

The client app uses Vite and Vue 3.

### Useful commands

From the workspace root:

```bash
pnpm install
pnpm --dir client install
pnpm --dir client run dev
```

From `client/`:

```bash
pnpm install
pnpm run dev
pnpm run build
pnpm run preview
```

## Deployment

The project is configured for Netlify auto-deploy using GitHub Actions.

### GitHub repository

- https://github.com/Cstrp/BjGroup.git

### Netlify setup

1. Create a Netlify site and connect it to the GitHub repo.
2. Set the build command:
   ```bash
   pnpm --dir client run build
   ```
3. Set the publish directory:
   ```bash
   client/dist
   ```
4. Add any required environment variables in Netlify if needed.

## GitHub Actions

A workflow is included at `.github/workflows/netlify-deploy.yml` to build the client and trigger Netlify deployment using the `netlify/site-deploy` action.

## Tags

- `vue`
- `vite`
- `netlify`
- `pnpm`
- `frontend`
- `landing-page`
- `bj-group`

## Notes

- The Netlify action assumes you have `NETLIFY_AUTH_TOKEN` and `NETLIFY_SITE_ID` configured in GitHub Secrets.
- The deployment workflow builds only the frontend from `client/`.
