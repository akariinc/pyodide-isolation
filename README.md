# pyodide-isolation

Isolate fixed version pyodide runtime environment anytime on your localhost or on your website.
Supporting standard library only.

This repository is created from a request to isolate fixed python version runtime for educational use.

[Try it on github pages.](https://akariinc.github.io/pyodide-isolation/)


## Note

* micropip is disabled by `"disabledExtensions": ["@jupyterlite/piplite"]` in `jupyter-lite.json` to avoid runtime error that corrupts python code execution.


## Build and run pyodide environment locally

Download the version you want.
https://akariinc.github.io/pyodide-isolation/pyodide/console.html

```bash
# Install dependencies
pip install -r requirements.txt

# Build jupyter
jupyter lite build

# Download pyodide assets and extract into jupyter build
mkdir -p _output
# Use 0.29.0 for python3.12, 0.28.x has python3.13 runtime
PYODIDE_VERSION=0.28.3
curl -LO https://github.com/pyodide/pyodide/releases/download/$PYODIDE_VERSION/pyodide-$PYODIDE_VERSION.tar.bz2
tar -xjf pyodide-$PYODIDE_VERSION.tar.bz2 -C _output


# Run locally
python -m http.server -d _output 8000

# Access http://localhost:8000/pyodide/console.html
```


