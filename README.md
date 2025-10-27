# pyodide-isolation

Isolate fixed version pyodide runtime environment anytime on your localhost or on your website.
Supporting standard library only.

This repository is created from a request to isolate fixed python version runtime for educational use.

[Try it on github pages.](https://akariinc.github.io/pyodide-isolation/)


## Note

* micropip is disabled by `"disabledExtensions": ["@jupyterlite/piplite"]` in `jupyter-lite.json` to avoid runtime error that corrupts python code execution.


## Build and run pyodide environment locally

Download the version you want.
https://github.com/pyodide/pyodide/releases

```bash
# Install dependencies
pip install -r requirements.txt

# Build jupyter
jupyter lite build

# Download pyodide assets and extract into jupyter build
mkdir -p _output
curl -LO https://github.com/pyodide/pyodide/releases/download/0.29.0/pyodide-0.29.0.tar.bz2
tar -xjf pyodide-0.29.0.tar.bz2 -C _output


# Run locally
cd _output && python -m http.server 8000
```


