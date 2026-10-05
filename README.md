# teclado4to

Juego de tecleo para **4.º de primaria**, en español latinoamericano.

Un solo archivo: [`index.html`](index.html). No necesita instalación, ni servidor,
ni conexión a internet (solo las tipografías, que si faltan el juego igual funciona).

## Cómo jugar

1. Abre `index.html` con Chrome o Edge.
2. Elige un nivel y luego el modo: **solo** o **dos jugadores**.

### Los 5 niveles

| Nivel | Qué practica |
|-------|--------------|
| 1 | Letras de la fila de arriba |
| 2 | Sílabas y palabras cortas |
| 3 | Palabras más largas |
| 4 | Mayúsculas y `ñ` |
| 5 | Acentos y signos (`¿ ¡ ' ´`) |

### Acentuar

- Acento agudo y grave: pulsa `´` y luego la vocal. Aparece el acento solo.
- `ü`: `Shift` + `´` y después `u`.
- `¿` está en la tecla de `'` y `¡` con `AltGr` + `1`.

El juego reconoce la tecla pulsada, no la tecla física, así que funciona con
cualquier distribución de teclado.

### Modo dos jugadores

Los dos teclean en el **mismo teclado**, por turnos. El primero en completar las
palabras gana. Cuando ambos esperan la misma tecla, la pulsación cuenta para el
que va más adelante: nadie roba teclas al rival.

## Para el docente

- Los récords se guardan en el navegador (`localStorage`), en el dispositivo.
  No se envía nada a internet.
- El sonido se activa con la primera pulsación (los navegadores lo exigen).
- Para cambiar las palabras, edita el arreglo `NIVELES` dentro del `<script>`.
- Cada ronda sortea palabras distintas al azar, así que no se repite entre
  partidas.

## Requisitos técnicos

Cualquier navegador moderno. No hay build, ni dependencias, ni servidor.