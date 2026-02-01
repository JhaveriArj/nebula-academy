# Nebula Coding Academy

Static coding-academy site: space-themed landing, lessons with code editor, simulated Python (print parsing), progress tracking, and localStorage.

## GitHub Pages deployment

1. Push this repo to GitHub (e.g. `https://github.com/your-username/nebula-academy`).
2. In the repo: **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. **Branch**: `main` (or `master`), folder: **/ (root)**.
5. Save. The site will be at `https://your-username.github.io/nebula-academy/`.

## Extending with real Python (Pyodide)

To run real Python in the browser, load [Pyodide](https://pyodide.org/) and replace the simulated runner in `script.js`:

1. Add before `</body>`:  
   `<script src="https://cdn.jsdelivr.net/pyodide/v0.24.1/full/pyodide.js" defer></script>`
2. Await `loadPyodide()` once, then call `pyodide.runPythonAsync(code)` in your Run handler and show `sys.stdout` or capture output via `pyodide.runPython('...')` with redirected stdout.

The current lesson/editor/UI flow can stay the same; only the execution path in `runCode()` needs to call Pyodide instead of `runSimulatedPython()`.
