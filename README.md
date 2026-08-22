# Homebrew tap de CosechaMedia

Tap oficial para instalar la app de escritorio [CosechaMedia](https://github.com/MustangXPress7/CosechaMedia) en macOS.

## Instalación

```bash
brew tap MustangXPress7/tap
brew install --cask --no-quarantine mustangxpress7/tap/cosechamedia
```

- `--no-quarantine`: evita el aviso de Gatekeeper (el binario está firmado ad-hoc, sin notarización). Detalles en [`docs/SIGNING.md`](https://github.com/MustangXPress7/CosechaMedia/blob/master/docs/SIGNING.md) del repo principal.
- Requiere Mac **Apple Silicon** (los assets son arm64 por ahora).
- `ffmpeg` se instala automáticamente como dependencia (la app lo necesita para metadatos y proxies).

## Mantenimiento (por release)

Al publicar cada release `v<VERSIÓN>`:

1. Descargar el asset `CosechaMedia-macos.app.zip` del release.
2. Calcular su hash: `shasum -a 256 CosechaMedia-macos.app.zip`
3. Actualizar `version` y `sha256` en `Casks/cosechamedia.rb`.
4. Commit y push — Homebrew detecta el cambio con `brew update && brew upgrade`.

Checklist completo y contexto en `docs/HOMEBREW.md` del repo principal.
