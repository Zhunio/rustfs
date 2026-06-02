# 🪣 RustFS S3 Storage

S3-compatible object storage for home lab backups.

## ✨ Features

- ☁️ Provide an S3-compatible endpoint.
- 📦 Store persistent object data.
- 🧰 Run with Docker Compose or Coolify.

## 🚀 Getting Started

Create the required environment variables:

```text
RUSTFS_ACCESS_KEY=<email>
RUSTFS_SECRET_KEY=$(openssl rand -base64 32)
```

## 🧭 Coolify

Deploy this repository as a Docker Compose service.

- 🌿 Branch: `main`
- 🐳 Build Pack: `Docker Compose`
- 🪣 Data mount: `/mnt/backup/rustfs/data`
- 🧾 Logs mount: `/mnt/backup/rustfs/logs`
- 🔐 Required variables: `RUSTFS_ACCESS_KEY`, `RUSTFS_SECRET_KEY`
