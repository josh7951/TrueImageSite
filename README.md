# True Image Enterprises

An [Astro](https://astro.build) + [Tailwind CSS](https://tailwindcss.com) site.

## Table of Contents

- [Project Structure](#-project-structure)
- [Commands](#-commands)
- [Development Workflow](#️-development-workflow)
- [Linting & Formatting](#-linting--formatting)
- [Deploying to Production (GoDaddy)](#-deploying-to-production-godaddy)

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src
│   ├── assets
│   │   └── astro.svg
│   ├── components
│   │   └── Welcome.astro
│   ├── layouts
│   │   └── Layout.astro
│   └── pages
│       └── index.astro
└── package.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                       |
| :--------------------- | :------------------------------------------- |
| `npm install`          | Installs dependencies                        |
| `npm run dev`          | Starts local dev server at `localhost:4321`  |
| `npm run build`        | Build your production site to `./dist/`      |
| `npm run preview`      | Preview your build locally, before deploying |
| `npm run lint`         | Run ESLint and oxlint against the project    |
| `npm run format`       | Format the project with Prettier             |
| `npm run format:check` | Check formatting without writing changes     |

## 🛠️ Development Workflow

1. Clone the repo and install dependencies:
   ```sh
   git clone <repo-url>
   cd TrueImageSite
   npm install
   ```
2. Start the dev server:
   ```sh
   npm run dev
   ```
   The site is available at `http://localhost:4321` with hot reload.
3. Make your changes in `src/`. Components, layouts, and pages live under `src/components`, `src/layouts`, and `src/pages` respectively.

## ✅ Linting & Formatting

Before committing or opening a pull request, run:

```sh
npm run lint
```

This runs both ESLint (`.astro`/`.ts`/`.tsx` files) and oxlint. Fix any reported issues, then check formatting:

```sh
npm run format:check
```

If formatting issues are found, fix them automatically with:

```sh
npm run format
```

The `.github/workflows/lint.yml` CI workflow runs `npm run lint` and `npm run format:check` on every push and pull request, so make sure both pass locally first.

## 🚀 Deploying to Production (GoDaddy)

This project builds to static files, which works with GoDaddy's shared hosting (cPanel).

1. Build the production site:
   ```sh
   npm run build
   ```
   This outputs static HTML/CSS/JS to `./dist/`.
2. Upload the contents of `dist/` (not the `dist/` folder itself) to your GoDaddy hosting account's web root, typically `public_html/` (or a subfolder if deploying to a subdirectory):
   - **Via cPanel File Manager**: log in to GoDaddy cPanel, open File Manager, navigate to `public_html/`, and upload/extract the contents of `dist/`.
   - **Via FTP/SFTP**: use an FTP client (e.g. FileZilla) with the credentials from GoDaddy's cPanel (Files → FTP Accounts), connect, and copy the contents of `dist/` into `public_html/`.
3. Overwrite existing files when prompted so old builds don't linger.
4. Verify the site by visiting your domain once the upload completes.

[Back to Top](#true-image-enterprises)
