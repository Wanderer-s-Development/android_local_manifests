# Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) Unified Local Manifest

Official unified local manifest for building custom ROMs on Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) maintained by **Wanderer**.

A single manifest that seamlessly supports both **The Clover Project** and **Project Infinity-X** out of the box.

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

### 2. Clone the Unified Local Manifest (Single Command for Both ROMs)

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

---

## 📦 Repositories Included in Manifest (`breeze.xml`)

| Path | Repository | Purpose / ROM |
| :--- | :--- | :--- |
| `device/xiaomi/breeze` | `device_xiaomi_breeze` (branch `lineage-23.2`) | Device tree (Clover & Infinity-X) |
| `device/xiaomi/breeze-kernel` | `device_xiaomi_breeze-kernel` (branch `lineage-23.2`) | Prebuilt Kernel & DTBOs |
| `vendor/xiaomi/breeze` | `vendor_xiaomi_breeze` (branch `lineage-23.2`) | Proprietary vendor blobs |
| `vendor/xiaomi/breeze-camera` | `xiaomi_breeze_camera` (branch `main`) | HyperOS Camera blobs & HAL |
| `hardware/xiaomi` | `LineageOS/android_hardware_xiaomi` (branch `lineage-24.0`) | Xiaomi hardware HALs |
| `hardware/clover/interfaces` | `hardware_clover_interfaces` (branch `17`) | Clover IR & Touch HALs (Clover) |
| `vendor/infinity-priv/keys` | `infinityx_vendor_infinity_keys` (branch `main`) | Release signing keys (Infinity-X) |
