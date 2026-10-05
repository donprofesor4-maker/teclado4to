# Práctica de direcciones

Entrenador de **mecanografía** para proyectar en clase. Los alumnos teclean
direcciones de internet, una tras otra, barajadas y sin repetir durante la sesión.

Un solo archivo: [`index.html`](index.html). Sin instalación ni servidor.

## Qué aparece en pantalla

- Una **dirección grande** (hasta 86 px en pantallas grandes) que el alumno teclea.
- Debajo, un **teclado físico completo** con la forma escalonada de uno real:
  cinco filas, teclas anchas para `Shift`, `Enter`, `Tab`, `Ctrl` y la barra
  espaciadora, y keycaps con relieve.
- Las teclas se iluminan: **verde** la que acaba de pulsar, **azul** la que toca
  ahora, y **amarillo** el `Shift` cuando la letra o el signo lo necesita.
- Arriba, el número de dirección y los errores acumulados.

## Direcciones

Todas son **direcciones de internet** y todas empiezan con **`https://`**:

```
https://www.colegio.edu.mx
https://videos.com.mx/aulas
https://méxico.gob.mx
https://peña.travel/deportes
```

El dominio es **ficticio pero verosímil** (`.mx`, `.com`, `.edu.mx`, `.gob.mx`,
`.travel`, `.es`, `.ar`) y a veces lleva una ruta corta (`/2026`, `/deportes`,
`/ayuda`, `/mapa`). Una de cada cinco lleva **acentos o `ñ`**, como los dominios
reales que las usan: `méxico.gob.mx`, `españa.es`, `música.com.mx`,
`cañón.com.mx`, `ñandú.com.ar`, `peña.travel`.

Máximo 30 caracteres para que no se haga eterno en 4.º de primaria.

Cada ronda son 120 direcciones barajadas: **no se repite ninguna** durante la
sesión. Las listas están en el `<script>`:

| Arreglo | Qué es |
|---------|--------|
| `DOMINIOS` | dominios ficticios sin acentos |
| `DOMINIOS_LATIN` | dominios con acentos y `ñ` |
| `RUTAS` | sufijos de la URL (`/2026`, `/deportes`, …) |
| `CON_SHIFT` | qué carácter sale en cada tecla al apretar `Shift` |

## El teclado y el `Shift`

El teclado dibuja el **layout latino** completo, con doble leyenda en las teclas
que lo necesitan: el `7` muestra `/` arriba, el `.` muestra `:`, el `-` muestra `_`.

Cuando la dirección pide algo que sale con `Shift` —una mayúscula, el `:` de
`https:`, la `/`, el `_`—, se encienden **las dos teclas a la vez**: la del carácter
y el `Shift`. Soltar el `Shift` lo vuelve a apagar.

```
https:   →  ⇧ + .    produce  :
https:// →  ⇧ + 7    produce  /
```

## Teclado: Windows o Mac

Detecta solo si el equipo es **Windows** o **Mac** y dibuja el layout
correspondiente. La diferencia real está en la tercera fila:

```
Windows:  a s d f g h j k l ñ ' \
Mac:      a s d f g h j k l ñ '
```

El distintivo azul de la barra superior dice cuál está puesto. **Si te equivoca**
—porque usas teclado Mac en una PC, por ejemplo— tócalo y alterna entre los dos.

La fila de abajo también cambia, como en un teclado real:

```
Windows:  Ctrl  ⊞  Alt  [espacio]  Alt  ⊞  Ctrl
Mac:      fn  Ctrl  ⌥  ⌘  [espacio]  ⌘  ⌥  Ctrl
```

`⊞` es el logo de Windows (las cuatro ventanitas).

## El acento: por qué a veces «no lo reconoce»

El acento es una **tecla muerta**: al pulsarla no sale ningún carácter, y el
carácter acentuado aparece en la pulsación *siguiente*. Por eso el programa
recuerda qué acento se apretó y lo compone con la vocal que viene después.

Funciona en los tres estilos de teclear el acento:

| Cómo lo teclea el alumno | Pasos que ve el programa |
|---|---|
| **Estándar (Windows/Mac)** | `Dead` → `é` ya compuesta |
| **Acento suelto** | `´` → `e` (la compone el programa) |
| **Atajo de Mac** | `Option`+`e` → `é` |

Igual para la `ñ` (`~` + `n`), la `ü` (`Shift` `¨` + `u`) y las mayúsculas
acentuadas (`Shift` `´` + `a` → `Á`).

## Controles

| Tecla | Qué hace |
|-------|----------|
| teclas normales | teclear la dirección |
| `Enter` | pasar a la siguiente dirección |
| `⌫` | borrar un caracter |

## Botones

- **Ocultar texto** — difumina la dirección. Útil cuando el maestro la dicta.
- **Ocultar teclado** — quita el teclado si molesta al proyectar.
- **Pantalla completa.**
- **Reiniciar** — baraja otra ronda y pone los errores en cero.
- **Otra dirección** — salta a la siguiente.

## Qué practica

- **`Shift`** — toda mayúscula y los signos `:` `/` `_` `"` `*` etc.
- **Acentos:** `´` + vocal → `á é í ó ú`. Para la `ü`: `Shift` + `´` + `u`.
- **`ñ`** en dominios como *peña.travel* o *ñandú.com.ar*.
- **Números** en rutas como `/2026`.
- **Punto** y **dos puntos** de `https://`.

El comparador usa `KeyboardEvent.key`, o sea el **carácter ya compuesto**, así
que funciona con cualquier distribución de teclado: no importa qué tecla física
se pulse. Cuando la tecla es incorrecta, el carácter se marca en rojo y **no
avanza** — hay que acertarlo.

## Para el maestro

- No se guarda nada: ni cookies, ni `localStorage`, ni cuentas. Los contadores
  viven solo en la pantalla.
- Las tipografías vienen de Google Fonts; sin internet funciona igual con la del
  sistema.
- Funciona en Chrome, Edge, Firefox y Brave, en computadora y proyector.
  Probado de 1366×768 a 2560×1440 sin desbordes.