# SnapGlow

Lightweight cross-platform tool and library for adding glow and enhancement effects to images. Designed for quick prototyping, batch processing, and integration into larger image-processing pipelines.

## Features

- Glow and bloom filters with adjustable strength and radius
- Color grading and basic retouch tools (brightness, contrast, saturation)
- CLI for batch processing and a simple programmatic API
- Small, dependency-light core and extensible plugin-friendly architecture
- Cross-platform (macOS / Linux / Windows)

## Quick Start

### Clone

```bash
git clone https://github.com/<your-org>/SnapGlow.git
cd SnapGlow
```

### Build & Install

Instructions depend on the chosen stack. Example (Node-based project):

```bash
# install dependencies
npm install

# build
npm run build
```

For a Python-based project:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### CLI Usage (example)

```bash
# apply default glow to an image
snapglow input.jpg output.jpg --glow 0.6 --radius 30

# batch process a directory
snapglow --input ./photos --output ./processed --glow 0.5
```

### Programmatic Usage (example)

JavaScript:

```js
const { applyGlow } = require("snapglow");
await applyGlow("input.jpg", "output.jpg", { strength: 0.6, radius: 30 });
```

Python:

```py
from snapglow import apply_glow
apply_glow('input.jpg', 'output.jpg', strength=0.6, radius=30)
```

## Configuration

- strength: 0.0 — 1.0 (default 0.5)
- radius: integer pixels (default 25)
- blend_mode: normal|screen|add (default: screen)

Put configuration in a JSON/YAML file or pass flags to the CLI.

## Contributing

Contributions welcome. Please:

- Open an issue to discuss major changes
- Fork the repo and submit a pull request
- Follow the code style and add tests for new features

Add a CONTRIBUTING.md with your preferred workflow and code standards.

## Tests

Run unit and integration tests:

```bash
npm test      # or: pytest
```

## License

This project is licensed under the MIT License. See LICENSE for details.

## Contact

Maintainance and issue tracker: https://github.com/<your-org>/SnapGlow/issues
