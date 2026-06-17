# 🦀 RustFS Object Storage

Self-hosted S3-compatible object storage service built with RustFS.

## ✨ Features

- 📦 S3-compatible object storage.
- 🌐 Web console for management.
- 🔐 Access key and secret key authentication.
- 💾 Persistent data and logs on mounted storage.
- 🐳 Run with Docker Compose or Coolify.
- ❤️ Built-in health checks for API and console services.
- 🔧 Automatic permission helper container runs before RustFS starts to ensure the storage path is owned by the RustFS runtime user: `10001`

## 🚀 Coolify

Deploy this repository as a Docker Compose service.

- 🔐 Repository Type: `Private Repository (with GitHub App)`
- 🐙 GitHub App: `zhunio-coolify`
- 🌿 Branch: `main`
- 🐳 Build Pack: `Docker Compose`
- 📂 Data mount: `/mnt/backup/rustfs/data`
- 📁 Logs mount: `/mnt/backup/rustfs/logs`
- 🔑 Environment variables:
  - `RUSTFS_ACCESS_KEY`
  - `RUSTFS_SECRET_KEY`

## 🚇 Cloudflare Tunnel

Configure public hostnames for RustFS:

### S3 API

- 🌐 Hostname: `rustfs.goodnessgardens.team`
- 🔗 Service Type: `HTTP`
- 🏠 Origin URL: `http://localhost:9000`

### Web Console

- 🌐 Hostname: `rustfs-console.goodnessgardens.team`
- 🔗 Service Type: `HTTP`
- 🏠 Origin URL: `http://localhost:9001`

Cloudflare provides HTTPS automatically, while RustFS serves HTTP internally.
