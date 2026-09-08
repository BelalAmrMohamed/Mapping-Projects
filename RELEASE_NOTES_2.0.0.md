# Release Notes - v2.0.0

**Date:** September 8, 2026  
**Commit:** `4705f50e4d687942a8286d965aaf677341af534d`

## 🎉 Major Release: Improved Structure & Async Support

This release marks a significant milestone with substantial improvements to the core `map.js` module, introducing better code organization and asynchronous operation support.

---

## ✨ Key Improvements

### 🔄 Refactored Architecture
- **Improved Code Structure:** Complete refactoring of `map.js` for better maintainability and readability
- **Async Support:** Added comprehensive async/await support for improved performance and non-blocking operations
- **Enhanced Organization:** Better separation of concerns with clearer module boundaries

### 📈 Performance Enhancements
- Non-blocking directory traversal with async operations
- Optimized file reading and processing
- Better memory management with improved iteration patterns

### 🛠️ Technical Improvements
- Cleaner function signatures and improved error handling
- Better code documentation and comments
- More maintainable structure for future enhancements

---

## 📝 What's Changed

### Major Changes
- Restructured `map.js` for improved code organization and clarity
- Introduced async/await patterns throughout the core module
- Enhanced modularity for easier maintenance and future feature additions

### Previous Versions Updates
This release builds upon recent improvements including:
- Enhanced README with comprehensive documentation
- Intelligent directory tree generation with proper spacing
- Smart file exclusions respecting .gitignore rules
- Detailed codebase summary with LOC counting per extension

---

## 📦 Features

The Project Map Generator includes:

- ✅ **Visual directory tree** – displays your project structure with Unicode box-drawing characters
- ✅ **Intelligent spacing** – inserts blank lines between sibling directories while preserving readability
- ✅ **Markdown output** – wrapped in code blocks with Markdown table formatting
- ✅ **Codebase summary** – automatic counts of files, extensions, and lines of code (LOC)
- ✅ **Smart exclusions** – respects `.gitignore`, ignores binary files and lockfiles for LOC
- ✅ **Flexible ordering** – files before directories at root level, standard tree behavior in folders

---

## 🚀 Installation & Usage

```bash
# Copy map.js to your project (e.g., scripts/ or docs/map/)
# Add to package.json:
"map": "node scripts/map.js"

# Run the script:
npm run map
```

The output will be written to `docs/map/context-map.md` (configurable).

---

## ⚙️ Configuration

You can customize behavior at the top of `map.js`:

| Variable | Description |
|----------|-------------|
| `outputMapPath` | Output file path (default: `docs/map/context-map.md`) |
| `IGNORE_EXT` | File extensions to exclude from tree |
| `EXCEPTION_NAMES` | Files that should not be ignored |
| `IGNORE_HIDDEN_FILES` | Whether to skip dot-files |
| `MAP_DESCRIPTION` | Header text for output file |

---

## 🔗 Commit Details

**Commit Message:** "Refactor map.js for improved structure and async support"  
**Author:** Belal Amr  
**Date:** September 8, 2026

---

## 💡 Use Cases

- **Onboarding** – new developers quickly understand project layout
- **Documentation** – embed the tree in README or docs
- **Auditing** – get instant metrics on file count and code size per language
- **Customization** – adapt ignore rules and output location to your workflow

---

## 📄 License

MIT – feel free to use and adapt for your own projects.

---

**Thank you for using Project Map Generator! 🌳**
