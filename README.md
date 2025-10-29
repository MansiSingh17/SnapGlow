# ✨ SnapGlow

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Cross Platform](https://img.shields.io/badge/Cross_Platform-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

**Lightweight cross-platform tool and library for adding stunning glow and enhancement effects to images**

[Quick Start](#quick-start) • [Features](#features) • [Documentation](#configuration) • [Contributing](#contributing)

</div>

---

## 🎯 About

**SnapGlow** is a powerful yet lightweight image enhancement tool designed for quick prototyping, batch processing, and seamless integration into larger image-processing pipelines. Whether you're enhancing photos for social media, creating visual effects, or building an automated image processing workflow, SnapGlow provides the tools you need with minimal overhead.

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🌟 Effects & Filters
- ✅ **Glow & Bloom Filters**
  - Adjustable strength (0.0 - 1.0)
  - Customizable radius
- ✅ **Color Grading Tools**
  - Brightness adjustment
  - Contrast control
  - Saturation tuning
- ✅ **Basic Retouch Tools**

</td>
<td width="50%">

### 🛠️ Development Features
- ✅ **CLI for Batch Processing**
- ✅ **Simple Programmatic API**
- ✅ **Dependency-Light Core**
- ✅ **Plugin-Friendly Architecture**
- ✅ **Cross-Platform Support**
  - macOS
  - Linux
  - Windows

</td>
</tr>
</table>

---

## 🚀 Quick Start

### 📥 Clone the Repository
```bash
git clone https://github.com/<your-org>/SnapGlow.git
cd SnapGlow
```

### 🔧 Build & Install

<details>
<summary><b>Node.js / JavaScript Setup</b></summary>
```bash
# Install dependencies
npm install

# Build the project
npm run build

# Optional: Link globally for CLI access
npm link
```

</details>

<details>
<summary><b>Python Setup</b></summary>
```bash
# Create virtual environment
python -m venv .venv

# Activate virtual environment
# On macOS/Linux:
source .venv/bin/activate
# On Windows:
.venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Install in development mode
pip install -e .
```

</details>

---

## 💻 Usage

### 🖥️ CLI Usage
```bash
# Apply default glow to a single image
snapglow input.jpg output.jpg --glow 0.6 --radius 30

# Batch process an entire directory
snapglow --input ./photos --output ./processed --glow 0.5

# Apply multiple effects
snapglow input.jpg output.jpg --glow 0.7 --brightness 1.2 --saturation 1.1

# Use custom blend mode
snapglow input.jpg output.jpg --glow 0.8 --blend-mode screen
```

### 📚 Programmatic Usage

<details>
<summary><b>JavaScript Example</b></summary>
```javascript
const { applyGlow, applyEffects } = require("snapglow");

// Simple glow effect
await applyGlow("input.jpg", "output.jpg", { 
  strength: 0.6, 
  radius: 30 
});

// Multiple effects
await applyEffects("input.jpg", "output.jpg", {
  glow: { strength: 0.6, radius: 30 },
  brightness: 1.2,
  contrast: 1.1,
  saturation: 1.05
});
```

</details>

<details>
<summary><b>Python Example</b></summary>
```python
from snapglow import apply_glow, apply_effects

# Simple glow effect
apply_glow('input.jpg', 'output.jpg', strength=0.6, radius=30)

# Multiple effects
apply_effects('input.jpg', 'output.jpg', 
    glow={'strength': 0.6, 'radius': 30},
    brightness=1.2,
    contrast=1.1,
    saturation=1.05
)
```

</details>

---

## ⚙️ Configuration

### 📋 Parameters

| Parameter | Type | Range | Default | Description |
|-----------|------|-------|---------|-------------|
| `strength` | float | 0.0 - 1.0 | 0.5 | Glow effect intensity |
| `radius` | integer | 1 - 100 | 25 | Glow radius in pixels |
| `blend_mode` | string | normal / screen / add | screen | Blending mode for glow effect |
| `brightness` | float | 0.0 - 2.0 | 1.0 | Brightness adjustment |
| `contrast` | float | 0.0 - 2.0 | 1.0 | Contrast adjustment |
| `saturation` | float | 0.0 - 2.0 | 1.0 | Saturation adjustment |

### 📝 Configuration File

Create a `snapglow.config.json` or `snapglow.config.yaml`:

**JSON Example:**
```json
{
  "glow": {
    "strength": 0.6,
    "radius": 30,
    "blend_mode": "screen"
  },
  "adjustments": {
    "brightness": 1.1,
    "contrast": 1.05,
    "saturation": 1.1
  }
}
```

**YAML Example:**
```yaml
glow:
  strength: 0.6
  radius: 30
  blend_mode: screen

adjustments:
  brightness: 1.1
  contrast: 1.05
  saturation: 1.1
```

---

## 🧪 Testing

Run the test suite to ensure everything works correctly:
```bash
# Node.js
npm test

# Python
pytest

# With coverage
npm run test:coverage  # or: pytest --cov
```

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### 📝 Contribution Guidelines

1. **🐛 Report Bugs**: Open an issue with detailed reproduction steps
2. **💡 Suggest Features**: Discuss major changes in an issue first
3. **🔧 Submit PRs**: 
   - Fork the repository
   - Create a feature branch (`git checkout -b feature/AmazingFeature`)
   - Commit your changes (`git commit -m 'Add some AmazingFeature'`)
   - Push to the branch (`git push origin feature/AmazingFeature`)
   - Open a Pull Request

### 🎨 Code Standards

- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

> 📖 See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines

---

## 🏗️ Architecture
```
SnapGlow/
├── src/
│   ├── core/           # Core image processing algorithms
│   ├── filters/        # Glow and enhancement filters
│   ├── cli/            # Command-line interface
│   └── api/            # Programmatic API
├── plugins/            # Plugin system for extensions
├── tests/              # Unit and integration tests
├── docs/               # Documentation
└── examples/           # Usage examples
```

---

## 📊 Performance

- **🚀 Fast Processing**: Optimized algorithms for quick results
- **💾 Low Memory**: Efficient memory usage even with large images
- **📦 Small Footprint**: Minimal dependencies for easy deployment
- **⚡ Batch Friendly**: Process hundreds of images efficiently

---

## 🛣️ Roadmap

- [ ] GPU acceleration support
- [ ] Additional blend modes (multiply, overlay, soft light)
- [ ] Advanced color grading (curves, levels)
- [ ] Real-time preview in CLI
- [ ] Web-based GUI
- [ ] Docker container support
- [ ] Cloud processing API

---



## 🌐 Resources

<div align="center">

### 📚 Documentation & Support

[![Documentation](https://img.shields.io/badge/Documentation-4285F4?style=for-the-badge&logo=google-docs&logoColor=white)](https://github.com/<your-org>/SnapGlow/wiki)
[![Issues](https://img.shields.io/badge/Issues-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/<your-org>/SnapGlow/issues)
[![Discussions](https://img.shields.io/badge/Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/<your-org>/SnapGlow/discussions)

</div>

---

## 📞 Contact

- **Issue Tracker**: [GitHub Issues](https://github.com/<your-org>/SnapGlow/issues)
- **Discussions**: [GitHub Discussions](https://github.com/<your-org>/SnapGlow/discussions)
- **Email**: snapglow@yourorg.com

---

<div align="center">

**Made with ✨ by developers who love beautiful images**

⭐ **Star this repo if you find it useful!** ⭐

[![GitHub Stars](https://img.shields.io/github/stars/<your-org>/SnapGlow?style=social)](https://github.com/<your-org>/SnapGlow)
[![GitHub Forks](https://img.shields.io/github/forks/<your-org>/SnapGlow?style=social)](https://github.com/<your-org>/SnapGlow/fork)

</div>
