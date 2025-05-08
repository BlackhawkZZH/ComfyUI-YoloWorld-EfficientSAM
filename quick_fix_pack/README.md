# 🚑 Quick Fix Pack

This quick fix pack helps resolve common issues that may arise when installing and using this custom node.

## 🗂️ Directory Structure

```
quick_fix_pack/
├── README.md
├── efficient_sam_s_cpu.jit
├── efficient_sam_s_gpu.jit
└── yolo_world/
    ├── l/
    │   └── yolo-world.pt
    ├── m/
    │   └── yolo-world.pt
    └── s/
        └── yolo-world.pt
```

### 📄 File Descriptions

- `README.md`  
  → Guidance of how to make a quick fix when met .

- `*.jit`  
  → Packages for ESAM Model Loader.

- `/yolo_world`  
  → Packages for Yoloworld Model Loader.

## 🔧 Quick Fix Guidance

### Installation Debug

When running `pip install -r requirements.txt` using Python 3.12, you may encounter an error

```bash
AttributeError: module 'pkgutil' has no attribute 'ImpImporter'. Did you mean: 'zipimporter'?
```

A quick fix is to take [pyenv](https://github.com/pyenv/pyenv) or [conda](https://github.com/conda/conda) with Python version 3.11.9 to solve this problem. After successfully installing the dependencies of this custom node, you can still use the Python 3.12 version to run the ComfyUI Web UI.

---

### Running Debug

When running the workflow in China, it may sometimes wait a long time when first loading and/or get a popup showing an error message

```bash
inference.core.exceptions.RoboflowAPIConnectionError: Could not connect to Roboflow API.
```

with Yoloworld Model Loader with red highlighted. When it happens, follow the instructions below for a quick fix:

#### Quick Fix for Linux

```bash
cp -r yolo_world /tmp/cache/
```

Besides, if you could not download the models for ESAM Model Loader, just copy all `*.jit` to the root folder of this custom node.
