# Attacker Tree

A local-first, manually operated attack-tree documentation workspace for authorised security assessments and cybersecurity learning. It records investigation paths; it does not scan targets or execute exploits.

## Technology choices

- **React + Vite** provide a lightweight interface and a straightforward Windows development workflow.
- **@xyflow/react** provides the interactive hierarchical canvas, node dragging, connectors, zoom, pan, controls and minimap.
- **IndexedDB** stores multiple projects and their evidence locally in the browser.
- **html-to-image + jsPDF** render a tree image into a downloadable PDF.
- **Vitest** tests the core data-model helpers.

No account, backend, analytics, telemetry or external API is required. The stylesheet uses a Google Fonts import for DM Sans/DM Mono; remove the `@import` line to keep even fonts fully offline.

## Requirements

- Windows 10/11
- Node.js 20 LTS or later (npm is included)
- A current Chromium-based browser such as Edge or Chrome

## Install and run

1. Extract the `attacker-tree` folder.
2. Open PowerShell in that folder.
3. Install dependencies:

   ```powershell
   npm install
   ```

4. Start the development server:

   ```powershell
   npm run dev
   ```

5. Open the local URL printed by Vite (normally `http://127.0.0.1:5173`).

Build a production bundle with `npm run build`. To preview the built bundle locally, run `npm run preview`.

## Use

- **Create a project:** select **New**, then enter a name. The root node represents the overall target/objective.
- **Add branches:** select a node and click its `+` button, use **Add child**, or press `N`. Use **Shift+N** to add a sibling.
- **Edit:** select a node and use the right-side inspector. Double-click the node title or click the pencil to rename it.
- **Statuses:** choose Untested, Investigating, Confirmed or Dead End in the inspector. Marking a node Dead End asks before applying the status to descendants.
- **Notes and recreation:** write findings, observations, commands and repeatable steps in the relevant text fields.
- **Evidence:** attach PNG/JPG/JPEG screenshots or TXT files (5 MB maximum per file). Evidence is kept in IndexedDB and included in the portable JSON project.
- **Tags:** add a tag with or without a leading `#`; suggestions include predefined and previously used tags.
- **Identical nodes:** choose another node in the inspector and link it. The relationship is stored separately from the parent-child tree.
- **Search:** open Search or press `Ctrl+F`. Results cover names, descriptions, notes, recreation, tags, and evidence filenames/text. Click a result to centre on it.
- **Navigate:** use the canvas controls, mouse wheel, drag the blank canvas to pan, or drag nodes to reposition. **Tidy layout** restores a simple hierarchy.
- **Focus:** select a node and choose **Focus branch**; use **Exit focus** or `Esc` to return to the full tree.
- **Save/reopen:** changes autosave to local IndexedDB. **Save file** downloads a portable JSON project, including evidence. **Import** loads a JSON project as a separate local project.
- **PDF:** choose **PDF** to generate a read-only preview and then **Download PDF**.
- **Undo/redo:** `Ctrl+Z` and `Ctrl+Y`. `Ctrl+S` requests an immediate local save.

## Tests

```powershell
npm test
```

## Data and privacy

Project data remains in the browser profile's IndexedDB unless you explicitly download or import a project file. Clearing browser site data can remove locally stored projects; export portable project files regularly. Imported project files are treated as JSON data, not executable code.

Evidence accepts image MIME types for PNG/JPEG and checks that the image can be decoded, or plain text/TXT. File names are normalised to remove path separators. Each evidence file is limited to 5 MB; portable project imports are limited to 20 MB.

## Current implementation notes

This is a functional starter implementation, but it does **not yet implement every item** in the long specification. In particular, automatic depth-five collapsing, full drag-and-drop snap guides, a multi-page PDF layout for very large trees, full history coverage for every evidence/file operation, and a dedicated project-manager screen need further development. PDF rendering currently exports the canvas view as one fitted page, so very large trees may be small. Please verify the app against your full acceptance checklist before presenting it as production-complete.
