# Práctica de direcciones

Entrenador de **mecanografía** para proyectar en clase. Los alumnos teclean
direcciones, una tras otra, y no se repiten en toda la sesión.

Un solo archivo: [`index.html`](index.html). Sin instalación ni servidor.

## Qué aparece en pantalla

- Una **dirección grande** (72 px) que el alumno teclea.
- Debajo, el **teclado completo**, que se ilumina conforme el alumno teclea:
  verde la tecla que acaba de pulsar, azul la que toca ahora.
- Arriba, el número de dirección y los errores acumulados.

## Direcciones

Se mezclan dos tipos, como pidió el maestro:

| Tipo | Ejemplos |
|------|----------|
| Calles | `Av. París 60` · `Niños Héroes 15` · `Constitución 130` |
| Páginas web | `https://www.colegio.edu.mx` · `https://videos.com.mx/aulas` |

Las de internet siempre empiezan con **`https://`** y van seguidas de un dominio
**ficticio pero verosímil** (`.mx`, `.com`, `.edu.mx`, `.gob.mx`) y, a veces, una
ruta corta. Miden entre 6 y 30 caracteres, promedio 17, para que no se haga
eterno en 4.º de primaria.

Cada ronda son 120 direcciones mezcladas y barajadas: **no se repite ninguna**
durante la sesión. Las listas están en el `<script>`:

| Arreglo | Qué es |
|---------|--------|
| `CALLES` | nombres de calle (con acentos y `ñ`) |
| `PREFIJOS` | `Av.`, `Calle`, `Sta.` o nada |
| `NUMEROS` | números de casa |
| `DOMINIOS` | dominios ficticios |
| `RUTAS` | sufijos de la URL (`/2026`, `/deportes`, …) |

## Teclado: Windows o Mac

Detecta solo si el equipo es **Windows** o **Mac** y dibuja el layout latino
correspondiente. La diferencia real entre ambos está en la tercera fila:

```
Windows:  a s d f g h j k l ñ ' \
Mac:      a s d f g h j k l ñ '
```

El distintivo azul de la barra superior dice cuál está puesto. **Si te equivoca**
—porque usas teclado Mac en una PC, por ejemplo— tócalo y alterna entre los dos.

## Controles

| Tecla | Qué hace |
|-------|----------|
| teclas normales | teclear la dirección |
| `Enter` | pasar a la siguiente dirección |
| `⌫` | borrar un caracter |

## Botones

- **Ocultar texto** — difumina la dirección. Útil cuando el maestro la dicta.
- **Ocultar teclado** — quita el teclado simolesta al proyectar.
- **Pantalla completa.**
- **Reiniciar** — baraja otra ronda y pone los errores en cero.
- **Otra dirección** — salta a la siguiente.

## Qué practica

- **Acentos:** `´` + vocal → `á é í ó ú`. Para la `ü`: `Shift` + `´` + `u`.
- **Mayúsculas**, números, punto (`.`), dos puntos (`:`) y barra (`/`).
- **`ñ`** en nombres como *Niños Héroes* o *Peña*.
- Signs y prefijos: `Av.`, `Calle`, `Sta.`

El comparador usa `KeyboardEvent.key`, o sea el **carácter ya compuesto**, así
que funciona con cualquier distribución de teclado: no importa qué tecla física
se pulse. Cuando la tecla es incorrecta, el carácter se marca en rojo y **no
avanza** — hay que acertarlo.

## Para el maestro

- No se guarda nada: ni cookies, ni `localStorage`, ni cuentas. Los contadores
  viven solo en la pantalla.
- Las tipografías vienen de Google Fonts; sin internet funciona igual con la del
  sistema.
- Funciona en Chrome, Edge, Firefox y Brave, enputer y proyector. Probado de
  1366×768 a 2560×1440 sin desbordes.