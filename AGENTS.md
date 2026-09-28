# Repository Guidelines

## Project Structure & Module Organization

The application lives in `buddakPDF.html`. It contains the Korean user interface, CSS, and JavaScript in one file. The browser loads PDF.js and jsPDF from CDN script tags; there are no local assets, package manifest, or separate source and test directories. Keep related UI controls, their event handlers, and processing options aligned when editing this file.

## Development and Verification

Open `buddakPDF.html` in a modern browser to run the app. An internet connection is needed on first load for the CDN libraries. For local HTTP testing, run `python3 -m http.server 8000` from the repository root and visit `http://localhost:8000/buddakPDF.html`. There is no build step or automated test command.

Verify changes manually with a small, multi-page scanned PDF: load it by file picker and drag and drop, inspect the before/after preview at each sharpening level, export the full PDF, and open the result. Check cancellation and an invalid file when changing those paths. Test both narrow and wide browser windows for layout changes.

## Coding Style & Naming

Preserve the single-file structure and existing plain JavaScript approach. Use two-space indentation in newly expanded JavaScript blocks and keep CSS selectors and DOM IDs consistent with their controls. Existing processing functions use short camelCase names such as `boxBlur` and `bgEstimate`; use descriptive camelCase for new functions and variables. Keep user-facing text in Korean. No formatter or linter is configured, so review diffs for consistent spacing and readable changes.

## Commit & Pull Request Guidelines

The Git history currently contains only `Add files via upload`, so it does not establish a commit convention. Use a short imperative subject describing the change, such as `Improve preview error handling`. In pull requests, describe the user-visible behavior, list manual checks performed, and include screenshots for UI changes. Mention any change to CDN versions or browser compatibility.

## Security & Configuration

PDF processing runs in the browser. Keep document data local and avoid adding upload or telemetry behavior without clearly documenting it. Keep CDN URLs and the PDF.js worker version in sync when updating dependencies.
