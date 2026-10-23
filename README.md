# Homebrew tap de los programas del repositorio de JMW Studio

Tap oficial para instalar apps de escritorio en macOS.

## Instalación

```bash
brew tap MustangXPress7/tap
brew install --cask --no-quarantine mustangxpress7/tap/cosechamedia
```
```bash
brew tap MustangXPress7/homebrew-tap
brew install scenecutbatch
```
- `--no-quarantine`: evita el aviso de Gatekeeper (el binario está firmado ad-hoc, sin notarización). 
- Requiere Mac **Apple Silicon** (los assets son arm64 por ahora).
- `ffmpeg` se instala automáticamente como dependencia (la app lo necesita para metadatos y proxies).

## Mantenimiento (por release)

Al publicar cada release `v<VERSIÓN>`:

1. Descargar el asset `.zip` del release.
2. Calcular su hash: `shasum -a 256 (...).app.zip`
3. Actualizar `version` y `sha256` en `Casks/(...).rb`.
4. Commit y push — Homebrew detecta el cambio con `brew update && brew upgrade`.

Checklist completo y contexto en `docs/HOMEBREW.md` del repo principal.
