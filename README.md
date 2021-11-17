# Tailwind Theme Viewer

[![Docker Build](https://github.com/Schufeli/tailwind-theme-viewer/actions/workflows/docker.yml/badge.svg)](https://github.com/Schufeli/tailwind-theme-viewer/actions/workflows/docker.yml)
![License](https://img.shields.io/github/license/schufeli/tailwind-theme-viewer?label=License)

Single Page Application to visualize and test TailwindCSS theme colours

## 📦 Installation
A Docker image is available on the public [docker registry](https://hub.docker.com/r/schufeli/tailwind-theme-viewer) which you can use as you like. 

### Docker pull
```
docker pull schufeli/tailwind-theme-viewer
```

### Docker run
```
docker run -p "<Port>:8080" --name tailwind-theme-viewer schufeli/tailwind-theme-viewer
```
### Docker-Compose
Please have a look at the provided [docker-compose.yml](https://github.com/Schufeli/tailwind-theme-viewer/blob/main/docker-compose.yml) file.
