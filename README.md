# 📦 Homebox – Home Assistant Add-on (ctf12 Fork)

A Home Assistant add-on packaging of **Homebox** — an inventory and organization system for home users.

This fork tracks newer Homebox releases and builds container images automatically via GitHub Actions for use in Home Assistant OS / Supervisor environments.

---

## 🏠 What is Homebox?

Homebox is a modern home inventory system designed to help you:

- Track items, locations, and groups  
- Organize tools, electronics, documents, and assets  
- Maintain structured labeling  
- Search and filter your home inventory easily  

Upstream project:  
👉 https://github.com/sysadminsmedia/homebox

---

## 🔧 About This Fork

This repository:

- Packages Homebox as a Home Assistant add-on  
- Builds images automatically via GitHub Actions  
- Publishes images to GHCR under:

  ```
  ghcr.io/ctf12/homebox-ha-addon
  ```

- Currently built for:
  - ✅ aarch64 (Raspberry Pi 5, HA Yellow, etc.)

---

## 📥 Installation (Home Assistant OS / Supervisor)

### 1️⃣ Add this repository to Home Assistant

Go to:

Settings → Add-ons → Add-on Store → ⋮ → Repositories

Add:

```
https://github.com/ctf12/homebox-ha-addon
```

---

### 2️⃣ Install the Add-on

1. Open **Homebox**
2. Click **Install**
3. Start the add-on
4. Open Web UI

---

## 🔄 Updating Homebox Version

This fork pins the upstream Homebox image version in:

```
homebox/build.yaml
```

To update to a newer Homebox release:

1. Update `build.yaml` to reference the new version:

```yaml
build_from:
  aarch64: ghcr.io/sysadminsmedia/homebox:vX.Y.Z
```

2. Update the add-on version in:

```
homebox/config.yaml
```

Example:

```yaml
version: "0.23.2"
```

3. Commit to `main`

GitHub Actions will:

- Build the image  
- Push to GHCR  
- Make the update available in Home Assistant  

---

## 🏗 Build System

This repository uses the official:

```
home-assistant/builder
```

GitHub Action.

Images are published to:

```
ghcr.io/ctf12/homebox-ha-addon:<version>
ghcr.io/ctf12/homebox-ha-addon:latest
```

---

## 🖥 Architecture Support

Currently enabled:

- ✅ aarch64 (Raspberry Pi 5, HA OS ARM64)

To enable additional architectures, edit:

```
.github/workflows/builder.yaml
```

and update the matrix section.

---

## 📂 Repository Structure

```
repository.yaml
homebox/
  ├── config.yaml
  ├── build.yaml
  ├── Dockerfile
  └── rootfs/
.github/workflows/
  ├── builder.yaml
  └── lint.yaml
```

---

## ⚠️ Disclaimer

This is a community fork and is not officially maintained by the Homebox project.

For upstream issues, feature requests, or bugs related to Homebox itself, please visit:

👉 https://github.com/sysadminsmedia/homebox

---

## ❤️ Credits

- Homebox by Sysadmins Media  
- Home Assistant Add-on Builder  
- Community contributors  
