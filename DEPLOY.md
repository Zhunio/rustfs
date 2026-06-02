# Deploy To Coolify

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
9. Review the storage mounts in `docker-compose.yml`:

| Host Path                | Purpose                        |
| ------------------------ | ------------------------------ |
| `/mnt/backup/rustfs/data` | RustFS persistent object store |
| `/mnt/backup/rustfs/logs` | RustFS persistent logs         |

> [!WARNING]
> Do not manually modify files inside `/mnt/backup/rustfs/data`.

10. Deploy.

## Environment Variables

```text
AWS_ACCESS_KEY_ID=<email>
AWS_SECRET_ACCESS_KEY=<secret>
```
