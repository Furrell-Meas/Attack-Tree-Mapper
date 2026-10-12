# Attacker Tree

Attacker Tree is a local-first workspace for mapping attack paths and documenting findings during authorised security assessments or cybersecurity learning. Build a clear tree of investigation steps, track their status, and keep notes and evidence together.

It is a documentation tool: it does not scan targets or run exploits.

## Features

- **Visual attack trees** — add, connect, move, collapse, and focus branches on an interactive canvas.
- **Investigation tracking** — mark nodes as Untested, Investigating, Confirmed, or Dead End.
- **Notes and evidence** — record descriptions, observations, repeatable steps, tags, and supporting files.
- **Search** — find nodes across titles, notes, tags, and evidence details.
- **Local projects** — autosave projects in your browser and manage multiple investigations.
- **Portable exports** — save or import project files as JSON and export a tree view to PDF.
- **Undo and redo** — step back through supported changes.

## Built with

React, Vite, React Flow, IndexedDB, jsPDF, html-to-image, and Vitest.

No account, backend, or external API is required. Project data is stored locally in your browser. The app's stylesheet imports Google Fonts; remove that import if you want to avoid the external font request.

## Getting started

### Requirements

- Node.js 20 or later
- npm
- A modern browser such as Chrome or Microsoft Edge

### Run locally

1. Clone or download this repository.
2. Open a terminal in the project folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open the local URL shown in the terminal, usually `http://127.0.0.1:5173`.

### Other commands

```bash
npm test       # Run tests
npm run build  # Create a production build
npm run preview # Preview the production build locally
```

## Basic workflow

1. Create a project and use its root node for the overall objective.
2. Add child nodes to map possible paths or investigation steps.
3. Select a node to edit its status, notes, tags, and evidence.
4. Use search and branch focus to navigate larger trees.
5. Export a JSON project file for backup or sharing, or generate a PDF snapshot.

## Data and privacy

Projects are saved in your browser's local IndexedDB storage and are not sent to a project backend. Clearing browser site data may delete local projects, so export important work regularly. Evidence files are limited to 5 MB each, and portable project imports are limited to 20 MB.

## Project status

Attacker Tree is a functional starter implementation and may not cover every advanced workflow. Large trees may be difficult to read in the current single-page PDF export. Review the app carefully before relying on it for production assessment workflows.

## Responsible use

Use Attacker Tree only for systems you own or have explicit permission to assess. Keep exported project files and evidence secure, especially when they contain sensitive findings.
