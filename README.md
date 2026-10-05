# Práctica de direcciones

Entrenador de **mecanografía** para proyectar en clase. Los alumnos teclean
direcciones, una tras otra, y no se repiten en toda la sesión.

Un solo archivo: [`index.html`](index.html). Sin instalación ni servidor.

## Cómo se usa

1. Abre `index.html` en Chrome o Edge.
2. Proyecta. Pulsa **Pantalla completa** si hace falta.

El alumno teclea la dirección que aparece. Al terminarla sale otra distinta.
Cuando se acaba la ronda de 120, se baraja una nueva con otras direcciones.

## Controles

| Tecla | Qué hace |
|-------|----------|
| teclas normales | teclear la dirección |
| `Enter` | pasar a la siguiente dirección |
| `⌫` | borrar un caracter |

## Qué practica

- **Acentos:** `´` + vocal → `á é í ó ú`. Para la `ü`: `Shift` + `´` + `u`.
- **Mayúsculas**, números, punto (`.`) y espacios.
- **`ñ`** en nombres como *Niños Héroes* o *Peña*.
- Signs and prefixes: `Av.`, `Calle`, `Sta.`

El comparador usa `KeyboardEvent.key`, o sea el **carácter ya compuesto**, por
lo que funciona con cualquier distribución de teclado: no importa qué tecla
física presses.

## Botones

- **Ocultar texto** — esconde la dirección. Útil cuando el maestro la dicta o
  cuando se quiereDictado.
- **Pantalla completa.**
- **Reiniciar** — baraja de nuevo y pone los errores en cero.

En la barra superior van el número de dirección y los errores acumulados, para
que el maestro vea el avance de un vistazo.

## Para el maestro

- Las direcciones se cruzan entre calles y números: hay miles de combinaciones
  posibles, así que nunca se repite la misma.
- No se guarda nada: ni cookies, ni `localStorage`, ni cuentas. No sale nada a
  internet. Los récords viven solo en la pantalla.
- Las tipografías vienen de Google Fonts. Si el aula no tiene internet, el juego
  funciona igual con la tipografía del sistema.
- Para cambiar o agregar calles, edita el arreglo `CALLES` dentro del `<script>`.
  Los números están en `NUMEROS` y los prefijos en `PREFIJOS`.
- Las direcciones duran entre 9 y 18 caracteres, que es lo cómodo para 4.º de
  primaria sin que se haga eterno.