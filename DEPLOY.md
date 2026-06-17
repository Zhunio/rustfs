# Deploy To Coolify

1. Create new `Project`: `rustfs`
2. Create new `Resource`
3. Select `Private Repository (with GitHub App)`
4. Select GitHub App: `coolify-deploy-zhunio`
5. Select repo: `rustfs`
6. Set the `Configuration`:
   - Branch: `main`
   - Build Pack: `Docker Compose`
   - Docker Compose Location: `/docker-compose.yml`
7. In `General`, Set:
   - `Name`: `rustfs`
8. Set `Environment Variables`
9. Deploy

## Environment Variables

```text
RUSTFS_ACCESS_KEY=<access-key>
RUSTFS_SECRET_KEY=<secret-key>
```

## Data Storage

RustFS stores persistent data on the host in the following locations:

| Directory                 | Purpose                                    |
| ------------------------- | ------------------------------------------ |
| `/mnt/backup/rustfs/data` | Object storage data, buckets, and metadata |
| `/mnt/backup/rustfs/logs` | RustFS application logs                    |

## Access

- S3 Endpoint: `http://<server>:9000`
- Console: `http://<server>:9001`
