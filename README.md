# Project Map Generator

A Node.js script that generates a beautifully formatted directory tree of your codebase, complete with a detailed codebase summary.

## Description
<img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/128352cd-3806-4eca-8e63-ff2c8fde4361" />

## Great Structure Format
<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/6cba6c8f-aebd-4b56-9511-af64804e3ad0" />

## CodeBase Summary
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/60150fe1-9895-42d4-aad1-73c2e0f0a600" />

## Features

- **Visual directory tree** – displays your project structure with Unicode box‑drawing characters.
- **Intelligent spacing** – inserts blank lines between sibling directories while preserving vertical pipes (`│`) for perfect readability.
- **Markdown output** – the tree is wrapped in a code block, and the summary uses Markdown tables for clean rendering on GitHub or any MD viewer.
- **Codebase summary** – automatically counts:
  - Total files
  - Number of files per extension
  - Lines of code (LOC) per extension (excluding binary files and lockfiles)
  - Grand total LOC
- **Smart exclusions**:
  - Respects `.gitignore` rules
  - Ignores binary files (images, videos, fonts, etc.) for LOC counting
  - Ignores lockfiles (`package-lock.json`, `yarn.lock`, etc.) from LOC
  - Can be extended via config
- **Flexible ordering** – at the root, files are listed before directories; inside folders, directories come first (standard tree behavior).

## Installation & Usage

1. **Clone or copy** `map.js` into your project (e.g., in `docs/map/map.js`).
2. **Ensure Node.js** is installed (v14+ recommended).
3. **Run** the script:

   ```bash
   node docs/map/map.js
   ```

4. The output will be written to `docs/map/context-map.md` (configurable).

## Configuration

At the top of `map.js` you can tweak these settings:

| Variable | Description |
|----------|-------------|
| `outputMapPath` | Output file path (relative to project root). Default: `docs/map/context-map.md` |
| `IGNORE_EXT` | Array of file extensions to exclude from the tree entirely. Default: `[]` |
| `EXCEPTION_NAMES` | File names that should **not** be ignored even if they match hidden‑file rules. Default: `["README.md", "robots.txt"]` |
| `IGNORE_HIDDEN_FILES` | Whether to skip dot‑files (like `.env`). Default: `true` |
| `MAP_DESCRIPTION` | Header text inserted at the top of the output file. |

The script automatically parses your `.gitignore` – any paths matching those patterns will be omitted from the tree and summary.

### Binary & Lockfile Exclusions

The following file types are **not** counted for LOC (they appear in the summary under "Binary / Media Files" with only a file count):

- Images: `.png`, `.jpg`, `.jpeg`, `.gif`, `.bmp`, `.ico`, `.svg`
- Videos/audio: `.mp4`, `.webm`, `.avi`, `.mov`, `.mp3`, `.wav`
- Archives: `.zip`, `.tar`, `.gz`, `.rar`, `.7z`
- Fonts: `.ttf`, `.woff`, `.woff2`, `.eot`, `.otf`
- Other binary: `.pdf`, `.exe`, `.dll`, `.so`, `.dylib`, `.bin`, `.dat`, `.db`, `.sqlite`

Lockfiles (`package-lock.json`, `yarn.lock`, `pnpm-lock.yaml`, `composer.lock`) are **included** in the tree but contribute `0` LOC.

## Output Example

### Tree (Markdown code block)

````markdown
```text
my-project/
├── about.html
├── control.html
├── create-quiz.html
├── favicon.ico
├── index.html
├── manifest.json
├── docs/
│   ├── map/
│   │   ├── context-map.md
│   │   └── map.js
│   │   
│   ├── plans/
│   │   ├── ai-agent-on-quiz-page-prompt.md
│   │   └── plan-to-update-exports.md
│   │   
│   ├── Database-Schema-Context.md
│   ├── image.png
│   └── issues.md
│
├── public/
│   ├── assets/
│   │   └── ...
│   └── ...
└── src/
    ├── api/
    ├── components/
    └── ...
```
````

### Codebase Summary

````markdown
## Codebase Summary

### Code Files

| Extension | Files | Lines of Code |
|-----------|-------|---------------|
| .js       | 42    | 3847          |
| .html     | 12    | 1256          |
| .css      | 8     | 812           |
| .md       | 5     | 297           |
| **Total** | **67**| **6212**      |

### Binary / Media Files

| Extension | Files |
|-----------|-------|
| .png      | 23    |
| .ico      | 3     |
| .svg      | 2     |
| **Total** | **28**|

**Grand Total Files:** 95  
**Total Lines of Code (code files only):** 6212
````

## Why This Tool?

- **Onboarding** – new developers can quickly understand the project layout.
- **Documentation** – embed the tree in your README or docs.
- **Auditing** – get instant metrics on file count and code size per language.
- **Customizable** – adapt ignore rules and output location to your workflow.

## Customization Ideas

- Modify `BINARY_EXTENSIONS` to add/remove file types you consider binary.
- Adjust `IGNORE_EXT` to hide specific extensions from the tree.
- Change `EXCEPTION_NAMES` to always include certain files (e.g., `.env.example`).
- Use a different output path (e.g., `./README.md`) to embed the tree directly.

## License

MIT – feel free to use and adapt for your own projects.

---

**Happy mapping!** 🌳
