# Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) Modular Local Manifests

Official modular local manifests for building custom ROMs on Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) maintained by **Wanderer**.

---

## 📂 Modular Structure

This repository provides three clean, modular manifest files designed to work together in a single branch without conflicts:

| Manifest | Purpose | Included Repositories |
| :--- | :--- | :--- |
| **`breeze.xml`** | **Core Hardware & Device Trees** (Common for all ROMs) | • `device/xiaomi/breeze` (`lineage-23.2`)<br>• `device/xiaomi/breeze-kernel` (`lineage-23.2`)<br>• `vendor/xiaomi/breeze` (`lineage-23.2`)<br>• `vendor/xiaomi/breeze-camera` (`main`)<br>• `hardware/xiaomi` (`lineage-24.0`) |
| **`clover.xml`** | **The Clover Project** | • `hardware/clover/interfaces` (`17`) |
| **`infinity.xml`** | **Project Infinity-X** | • `vendor/infinity-priv/keys` (`main`) |

---

## 🚀 Quick Setup Instructions

### 1. Initialize Your ROM Source Tree

* **For The Clover Project (Android 17 / Baklava)**:
  ```bash
  repo init -u https://github.com/The-Clover-Project/manifest.git -b 15.1 --git-lfs
  ```

* **For Project Infinity-X (Android 17)**:
  ```bash
  repo init -u https://github.com/ProjectInfinity-X/manifest -b 17 --depth=1
  ```

### 2. Clone the Local Manifests

Clone directly into `.repo/local_manifests`:
```bash
git clone https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests
```

### 3. Sync Source Tree

```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune -j$(nproc)
```

### 4. Build

* **To build Clover**:
  ```bash
  source build/envsetup.sh
  lunch clover_breeze-cp2a-user
  m clover -j$(nproc)
  ```

* **To build Infinity-X**:
  ```bash
  source build/envsetup.sh
  lunch infinity_breeze-user
  m bacon -j$(nproc)
  ```
