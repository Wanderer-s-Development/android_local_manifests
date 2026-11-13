# Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) Local Manifests

Official unified local manifests for building custom ROMs on Xiaomi Redmi 13 5G / POCO M6 Plus 5G (`breeze`) maintained by **Wanderer**.

---

## 🌿 Supported ROMs & Branches

| ROM | Branch | Local Manifest Command |
| :--- | :--- | :--- |
| **The Clover Project** | `clover` | `git clone -b clover https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests` |
| **Project Infinity-X** | `infinityx` | `git clone -b infinityx https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests` |

---

## 🚀 Quick Setup Instructions

### 1. For The Clover Project (Android 17 / Baklava)
```bash
# Initialize Clover source tree
repo init -u https://github.com/The-Clover-Project/manifest.git -b 15.1 --git-lfs

# Clone Clover local manifest
git clone -b clover https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests

# Sync source tree
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune -j$(nproc)

# Build Clover
source build/envsetup.sh
lunch clover_breeze-cp2a-user
m clover -j$(nproc)
```

### 2. For Project Infinity-X (Android 17)
```bash
# Initialize Infinity-X source tree
repo init -u https://github.com/ProjectInfinity-X/manifest -b 17 --depth=1

# Clone Infinity-X local manifest
git clone -b infinityx https://github.com/Wanderer-s-Development/android_local_manifests.git .repo/local_manifests

# Sync source tree
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune -j$(nproc)

# Build Infinity-X
source build/envsetup.sh
lunch infinity_breeze-user
m bacon -j$(nproc)
```

---

## 📦 Shared Device Repositories
Both ROMs utilize the unified device tree repositories maintained by Wanderer on branch `lineage-23.2`:
* **Device Tree**: [device_xiaomi_breeze](https://github.com/Wanderer-s-Development/device_xiaomi_breeze)
* **Prebuilt Kernel**: [device_xiaomi_breeze-kernel](https://github.com/Wanderer-s-Development/device_xiaomi_breeze-kernel)
* **Vendor Blobs**: [vendor_xiaomi_breeze](https://github.com/Wanderer-s-Development/vendor_xiaomi_breeze)
