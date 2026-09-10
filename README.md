# Kmareo Print Bridge — releases

Este repositorio **solo distribuye binarios** del [Print Bridge](https://github.com/andejevito/Kmareo/tree/main/print-bridge) de Kmareo — el código fuente vive en el repo privado principal.

Es público a propósito: los bridges ya instalados en cada negocio descargan `latest.json` y el `.exe` directamente del contenido "raw" de este repo, sin ningún token ni credencial — así no hace falta meter ningún secreto dentro de un ejecutable que corre fuera de nuestra infraestructura, en el PC de cada cliente.

## Contenido

- `latest.json` — `{ version, sha256, download_url, published_at }` de la última versión publicada.
- `kmareo-print-bridge.exe` — el binario correspondiente a esa versión.

## Cómo se publica una versión nueva

Desde el repo principal, en `print-bridge/`:

```powershell
npm run release
```

Compila el `.exe`, calcula su SHA-256, y hace commit+push aquí con la versión leída de `print-bridge/lib/version.js`. Ver `print-bridge/lib/updater.js` en el repo principal para el mecanismo de auto-actualización que consume esto.
