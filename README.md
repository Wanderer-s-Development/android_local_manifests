# Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) Local Manifest

Official local manifest for building **WandererOS 1.0** (Android 17 / `lineage-24.0`) on Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) maintained by **Wanderer**.

---

## 📂 Manifest Contents (`breeze.xml`)

| Path | Repository | Revision | Purpose |
| :--- | :--- | :--- | :--- |
| `device/xiaomi/breeze` | `device_xiaomi_breeze` | `lineage-24.0` | Core device tree |
| `device/xiaomi/breeze-kernel` | `device_xiaomi_breeze-kernel` | `lineage-24.0` | Prebuilt kernel & ramdisk |
| `vendor/xiaomi/breeze` | `vendor_xiaomi_breeze` | `lineage-24.0` | Proprietary vendor blobs |
| `hardware/xiaomi` | `LineageOS/android_hardware_xiaomi` | `lineage-24.0` | Hardware HALs |
| `vendor/wanderer-priv/keys` | `vendor_wanderer_keys` | `main` | WandererOS Release Signing Keys |

*Note: MIUI Camera (`vendor/xiaomi/breeze-camera`) has been excluded for clean Android 17 compatibility.*

---

## 🚀 Setup Instructions

### 1. Initialize WandererOS Source Tree
```bash
repo init -u https://github.com/Wanderer-s-Development/manifest.git -b lineage-24.0 --git-lfs
```

### 2. Clone Local Manifest
```bash
git clone https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests
```

### 3. Sync Source Tree
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### 4. Build WandererOS
```bash
source build/envsetup.sh
lunch wanderer_breeze-trunk_staging-userdebug
m bacon -j$(nproc --all)
```
