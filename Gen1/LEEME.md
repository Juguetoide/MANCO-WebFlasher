# MANCO Web Flasher

Página estática (GitHub Pages) que flashea firmware ESP32-S3 con [ESP Web Tools](https://esphome.github.io/esp-web-tools/).
Solo Chrome/Edge en PC (necesitan Web Serial).

## Publicar en GitHub
1. Creá un repo (por ejemplo `manco-webflasher`) y subí **el contenido de esta carpeta** (no la carpeta en sí): `index.html`, `catalog.json`, `firmware/`, `.nojekyll`.
2. En GitHub: Settings → Pages → Source: *Deploy from a branch* → Branch `main`, carpeta `/ (root)` → Save.
3. A los ~1-2 minutos queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

## Agregar una versión nueva
1. Copiá el `firmware.factory.bin` compilado a `firmware/lightgun/MANCO-Gen1-vX.Y.Z.bin`.
2. En `catalog.json`, agregá una línea al principio de `versions` del dispositivo:
   `{ "version": "X.Y.Z", "file": "firmware/lightgun/MANCO-Gen1-vX.Y.Z.bin", "note": "qué cambió" }`
3. Commit y push. La primera de la lista se marca como "última".

## Agregar Pedal
Copiá sus `.bin` a `firmware/pedal/` y completá `versions` de ese dispositivo en `catalog.json`.
Siempre usar el archivo `firmware.factory.bin` (incluye bootloader + particiones + app y se escribe en offset 0).
