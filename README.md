# Ejemplo CI/CD con Node.js

Este repo es un ejemplo minimalista para practicar CI (tests + lint) y CD (build + push de imagen Docker)
usando **GitHub Actions** y **GitHub Container Registry (GHCR)**.

## Contenido
- `src/` : código fuente (un `sum` sencillo).
- `tests/` : test con Jest.
- `.github/workflows/ci.yml` : workflow de CI (lint + tests).
- `.github/workflows/cd.yml` : workflow de CD (build & push a GHCR).
- `Dockerfile` : imagen ligera basada en node:18-alpine.

## Comandos rápidos (local)
```bash
npm install
npm run lint
npm test
```

## Docker (local)
```bash
docker build -t ejemplo-ci-cd-node .
docker run --rm ejemplo-ci-cd-node
```

