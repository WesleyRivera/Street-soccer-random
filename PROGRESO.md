# PROGRESO — Cancha 19 (versión 3D en Godot)

> Este archivo es el "punto de guardado" del proyecto. Se actualiza después de cada paso.
> Si Claude se queda sin límites, aquí está exactamente dónde quedó y qué sigue.
> **Última actualización:** 2026-11-04 15:00 (hora de El Salvador)

## Decisiones tomadas (por Wesley)
- Ya no se usan personajes de marcas (Mario, Bob Esponja, etc.): se hace un **elenco original** con el mismo humor: animales raros, robots/monstruos y comida con cara.
- Ambiente: **cancha de favela brasileña** (piso de cemento desgastado, paredes azules con graffiti, casas de ladrillo, rejas, luces de noche), según las 4 fotos de referencia.
- Camino elegido: **rehacerlo en Godot 4 (3D)** para poder sacar un **.exe** de PC.
- La versión web (`index.html`) se queda como está: ya tiene los jugadores nuevos dibujados en 2D y funciona.

## Estado general

| # | Tarea | Estado |
|---|-------|--------|
| 1 | Versión web: jugadores como muñecos 2D (`index.html`) | ✅ Hecho y probado |
| 2 | Instalar Godot 4.4.1 en el entorno de Claude para probar | ✅ Hecho (funciona con capturas headless) |
| 3 | Elenco de 12 personajes 3D (`scripts/character.gd`, `scripts/cast.gd`) | ✅ Hecho y probado (sin errores, se ven bien) |
| 4 | Cancha-favela 3D (`scripts/stage.gd`) | ✅ Hecho y probado (captura revisada, sin errores) |
| 5 | Lógica del juego, controles, HUD, cámara (`scripts/main.gd`) | ✅ Hecho y probado |
| 6 | Probar todo en Godot headless (partida simulada + capturas) | ✅ Hecho: partida automática sin errores (gol, festejo, reinicio, goles del rival) |
| 7 | Exportar a `.exe` de Windows | ✅ Hecho: `Cancha19.exe` (97 MB, todo incluido). Generado con Godot headless; no se pudo ejecutar el .exe aquí (Linux), pero el mismo proyecto corrió sin errores. |
| 8 | Mejoras pendientes (opcional) | ⏳ Sonido, menú de elegir personajes, dificultad del rival, más detalles de favela (gente en las rejas, motos), versión nocturna con focos |

## Archivos del proyecto 3D (carpeta `cancha19-3d/`)
- `project.godot` — configuración (Godot 4.4, renderer Compatibility, ventana 1280x720). ✅
- `main.tscn` — escena principal, solo carga `scripts/main.gd`. ✅
- `scripts/cast.gd` — lista de los 12 personajes. ✅
- `scripts/character.gd` — construye cada personaje con formas 3D y lo anima (correr, patear, celebrar, portero). ✅
- `scripts/stage.gd` — piso con líneas y desgaste, paredes azules con graffiti, rejas, porterías con red, casas de ladrillo con ventanas, cerros con luces, postes de luz, ropa tendida, cielo del atardecer. Se construye llamando `build()`. ✅
- `scripts/main.gd` — ✅ reglas (5 vs 5, pases, tiros cargados, correr, IA rival, goles, 120 s), cámara, marcador, menú de inicio y final.

## Plan de lo que falta (en orden)
1. ~~Escribir `scripts/stage.gd`~~ (hecho).
2. ~~Escribir `scripts/main.gd`~~ (hecho; reglas portadas del `index.html` a metros: cancha 40 x 24 m, porterías de 6 m).
3. ~~Probar con la partida automática~~ (hecho: `godot --path cancha19-3d -- --autotest --shots=/carpeta`).
4. ~~Generar el .exe~~ (hecho).
5. **(AQUÍ VOY)** Esperar tu prueba del .exe en Windows y corregir lo que veas (velocidad, cámara, dificultad, personajes).

## Cómo continuar tú manualmente
1. Instala **Godot 4.4** (https://godotengine.org/download, versión estándar, no .NET).
2. Abre Godot → *Importar* → elige `cancha19-3d/project.godot`.
3. Presiona **F5** para correr: ya es jugable (menú → Jugar).
4. Para el `.exe`: *Proyecto → Exportar → Añadir → Windows Desktop*, instala las plantillas cuando Godot lo pida, y *Exportar proyecto*.

## Controles previstos
Mover: WASD o flechas · Pase / cambiar jugador: X o J · Tiro (mantén y suelta): Espacio · Correr: Shift · Mando: A pase, X tiro, gatillo derecho correr.

## Notas
- Los personajes ya se ven bien en pruebas: se pueden ajustar colores y accesorios en `character.gd` (funciones `_params` y `_d_<especie>`).
- Para agregar un personaje nuevo: añadirlo en `cast.gd` y crear su aspecto en `character.gd`.
- GitHub: conectado el 2026-11-04. Claude sube el avance directo a este repo (rama `main`), así que este archivo siempre refleja el último estado.

## Cómo regenerar el .exe (por si cambias algo)
1. En Godot: *Proyecto → Exportar → Windows Desktop* (ya hay un preset guardado en `export_presets.cfg`) → *Exportar proyecto*. Si falta, Godot te ofrece descargar las plantillas.
2. O por consola: `godot --headless --path cancha19-3d --export-release "Windows Desktop" ../build/Cancha19.exe`
3. Windows puede mostrar "Windows protegió tu PC" porque el .exe no está firmado: *Más información → Ejecutar de todos modos*.

## Cómo probar sin ventana (lo que usa Claude)
`godot --path cancha19-3d -- --autotest --shots=/carpeta` juega una partida sola, fuerza un gol y guarda capturas.
