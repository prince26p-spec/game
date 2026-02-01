# Implementación de Evento Mariachi y Radio

Se han realizado las siguientes modificaciones en el juego para integrar el evento solicitado:

## 1. Nuevos Assets
Se han registrado y cargado los siguientes archivos en `game.js`:
- **Personaje**: `assets/artistas/gean.png` (Sprite con 4 frames)
- **Item**: `assets/artistas/radio.png`
- **Partícula**: `assets/artistas/nota.png`
- **Música**: `assets/artistas/musicagean.mp3`

## 2. Lógica del Bloque de Interrogación
- Se identificó el bloque de interrogación a la izquierda de las tuberías (`radio_trigger`).
- **Comportamiento**:
    - **Golpes 1-4**: Suelta una moneda por cada golpe.
    - **Golpe 5**: Activa el evento `spawnRadioDrop`.

## 3. Evento de Caída de Radio (`spawnRadioDrop`)
- La radio aparece cayendo del cielo en una posición calculada (ligeramente a la izquierda de las tuberías, "en el medio").
- Cae hasta tocar el suelo.

## 4. Interacción con Radio y Mariachi
- Al tocar la radio con Mario:
    1.  Se detiene la música de fondo.
    2.  Se reproduce `assets/artistas/musicagean.mp3` (en bucle para "30 minutos").
    3.  Aparece el personaje "Mariachi" (`gean.png`) cerca de Mario animado.
    4.  Se generan partículas de notas musicales (`nota.png`) que flotan desde el personaje.

## Archivos Modificados
- `game.js`
