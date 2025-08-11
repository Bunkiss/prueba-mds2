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

## Subir a GitHub (pasos mínimos)
1. Crear repo en GitHub: `ejemplo-ci-cd-node`.
2. En tu carpeta local:
```bash
git init
git add .
git commit -m "Initial commit - ejemplo CI/CD"
git branch -M main
git remote add origin git@github.com:TU_USUARIO/ejemplo-ci-cd-node.git
git push -u origin main
```
3. Ir a la pestaña **Actions** para revisar la ejecución de los workflows.

## Notas sobre CD / GHCR
- El workflow de CD usa `GITHUB_TOKEN` por defecto (pero puede requerir permisos de `packages: write`).
- Si tenés problemas de permisos al pushear la imagen, generá un PAT con `write:packages` y ponelo en Secrets como `GHCR_TOKEN`.
