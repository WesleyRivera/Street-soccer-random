# Cancha 19 ⚽

Juego de fútbol 5 contra 5 que corre 100% en el navegador (un solo archivo HTML, sin dependencias).
Inspirado en el estilo de cancha de cemento de las favelas de Brasil (tipo FIFA Street / Volta).
No usa nombres, equipos ni licencias de EA / FIFA.

## Cómo jugar
Abre `index.html` en el navegador (doble clic) o publícalo con GitHub Pages.

| Acción | Móvil | Teclado |
|---|---|---|
| Moverse | Joystick | Flechas o WASD |
| Pasar (con balón) | Pase | X |
| Cambiar de jugador (sin balón) | Pase | X |
| Tirar (mantén para cargar potencia, suelta para disparar) | Tiro | Espacio |
| Correr | Correr | Shift |

## Publicar en GitHub Pages
Settings → Pages → Branch `main` / carpeta `/ (root)` → Save.
El juego quedará en `https://TU_USUARIO.github.io/cancha19/`.

## Estructura
- `index.html`: todo el juego (HTML + CSS + JavaScript).
- `PROCESO.md`: historial de cómo se construyó, paso a paso.
- `ROADMAP.md`: lo que falta por hacer.

## Notas técnicas
- Canvas 2D a 2100x1280 (2x), cámara que sigue el balón con zoom 1.3.
- El fondo (cancha, casas, paredes) se prerenderiza una vez en un canvas fuera de pantalla.
- Pesa más en celulares; está pensado para PC.
- Código antiguo de versiones previas del fondo (`pc`, `pf`, `draw`) sigue dentro del archivo y se puede limpiar.
