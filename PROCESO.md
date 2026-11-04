# Proceso de desarrollo

1. **Versión base**: fútbol 5v5 con canvas, IA rival, porteros, goles, 90 minutos acelerados (2 min reales), controles táctiles y de teclado.
2. **Gráficos v1**: cámara con zoom que sigue el balón, jugadores con camiseta y número, balón con giro y estela, confeti al marcar gol.
3. **Cancha más realista**: césped con franjas, líneas completas, porterías con red, estadio con público y vallas.
4. **Botón PASE doble función**: con balón pasa; sin balón cambia al jugador más cercano al balón (cicla entre los más cercanos). Tras un pase el control salta al receptor.
5. **Tiro con carga**: mantener Tiro acumula potencia (1 s), al soltar dispara. Barra de potencia sobre el jugador y botón que se llena.
6. **Cancha de cemento tipo futsal/Volta**: áreas de futsal, paredes con grafitis y reja.
7. **Cancha de favela**: casas de ladrillo, paredes azules, mural, pintura desgastada (referencia: 2 fotos aportadas por el usuario).
8. **Realismo extra**: render a 2x, texturas de ruido, desgaste de pintura con máscara, desenfoque de fondo, luz de atardecer, postes de luz, grano de película.
9. **Personajes**: los jugadores dejaron de ser círculos. Ahora son muñecos vectoriales con 3 vistas (frente, espalda, perfil), ciclo de carrera, patada, portero con guantes, peinados y tonos de piel distintos, número en la espalda y celebración al marcar gol. Todo está en el bloque `PERSONAJES` de `index.html` (se edita en `ROSTER`, `KITS` y `GKK`).

## Decisiones
- Un solo archivo para poder abrirlo sin servidor.
- Sin multijugador por ahora (se deja para el final).
