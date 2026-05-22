# Ghost — Unprecedented Times

Ghost CMS for [unprecedentedtimes.org](https://unprecedentedtimes.org), running via Docker with content persisted to `C:\ghost\data`.

## Restore / First-Time Setup

Pull the image and run the container:

```bash
docker run -d \
  --name ghost \
  -p 2368:2368 \
  -v C:\ghost\data:/var/lib/ghost/content \
  -e NODE_ENV=development \
  -e url=https://unprecedentedtimes.org \
  ghost:latest
```

## Start / Stop (existing container)

```bash
docker start ghost
docker stop ghost
```

## Notes

- **Ghost version:** 6.39.0
- **Content directory:** `C:\ghost\data` — contains themes, images, settings, and the SQLite database. Back this up to preserve all posts and media.
- The container is started on boot via `C:\Users\User\startup.bat`.
- Cloudflare tunnel proxies HTTPS traffic to `localhost:2368`.
