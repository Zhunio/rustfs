# RustFS S3 Storage

## Purpose

RustFS provides S3-compatible object storage for backups.

Services (Coolify, Immich, Home Assistant, etc.) upload backups to RustFS via the S3 API.

## S3 Endpoint

```text
https://s3.example.com
```

## Bucket Structure

```text
backups/
├── immich/
│   ├── data/
│   └── postgres-db/
│
├── homeassistant/
│   └── data/
│
├── tax-report/
│   ├── data/
│   └── postgres-db/
│
└── time-tracking/
    ├── data/
    └── mysql-db/
```

## Deploy To Coolify

1. Create a new project named `rustfs`.
2. Create a new resource.
3. Select `Private Repository (with GitHub App)`.
4. Select GitHub App `zhunio-coolify`.
5. Select the `rustfs` repository.
6. Set `Configuration`:
   - `Branch`: `main`
   - `Build Pack`: `Docker Compose`
7. Set `General`:
   - `Name`: `rustfs`
8. Set `Environment Variables`:

| Variable            | Description       |
| ------------------- | ----------------- |
| `RUSTFS_ACCESS_KEY` | admin             |
| `RUSTFS_SECRET_KEY` | RustFS secret key |

9. Review the storage mounts in `docker-compose.yml`:

| Host Path            | Purpose                        |
| -------------------- | ------------------------------ |
| `/mnt/backup/rustfs` | RustFS persistent object store |

> [!WARNING]
> Do not manually modify files inside `/mnt/backup/rustfs`.

10. Deploy.
