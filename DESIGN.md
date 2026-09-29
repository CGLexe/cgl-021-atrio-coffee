# DESIGN.md — ATRIO Coffee Lab

> El design system de este cliente. Cinco colores, dos familias, y nada que el
> generador pueda leer de dos maneras. Es la versión **ya rellena**: los hex viven
> en la tabla de la sección 1 y en ningún otro lado.

---

## 1. Qué produce el color

> de la cereza de café madura y del cantera del patio. El local es una casona
> colonial con patio interior de Oaxaca, y la paleta sale de ahí: la guinda es
> la cereza, el crema es el pergamino del papel de Filters, y el casi negro es
> el espresso, no un negro de pantalla.

| Casilla | Token | Acción |
|---|---|---|
| `#631C24` | `--marca` | el botón de WhatsApp, el precio que se quiere ver, el titular |
| `#4E141B` | `--marca-osc` | el mismo botón al pasar el mouse, y el pie de la barra |
| `#F9F6F0` | `--papel` | el fondo de la página |
| `#231614` | `--tinta` | todo el texto, del titular al pie |
| `#E7DCD8` | `--linea` | bordes, separadores y la línea bajo el encabezado |

Los cinco son distintos entre sí, y ninguno es blanco, negro ni el verde de
WhatsApp: esos tres no cuentan como color de marca.

> **Nota de veracidad:** el fondo real del monograma que trae el export es un
> punto más claro que esta guinda. La diferencia es de 3 sobre 255: no se nota,
> y mantener el valor del design system deja el presupuesto en cinco colores
> exactos en vez de seis.

---

## 2. La tipografía del rubro

Nicho `cafe`: **sans fuerte** para títulos, la misma sans para el cuerpo.

| Rol | Familia | Por qué |
|---|---|---|
| Titulares | Playfair Display | el local es una casona con patio y el rótulo está pintado a mano; una serif con carácter le da ese oficio, y el nicho `cafe` lo admite |
| Cuerpo y datos | Plus Jakarta Sans | los precios, los métodos y las notas se leen de reojo, con el café en la mano |

Reglas que no se negocian:

- Pesos: títulos 500/600, cuerpo 400, botón 600. **Máximo cuatro en toda la página.**
- Cuerpo mínimo de 16 px en móvil.
- Dos familias es el techo, no el punto de partida.

---

## 3. Tres reglas de cómo se ve bien y cómo se ve mal

**1. Contraste primero.**
- Bien: el precio se lee con el celular a un brazo, parado en la calle.
- Mal: la nota de cata se apaga contra el crema y hay que acercarse.

**2. Un solo acento.**
- Bien: `--marca` aparece donde hay algo que hacer: el botón de WhatsApp, el
  precio, el titular.
- Mal: el acento aparece en cinco lugares y ya no acentúa a ninguno.

**3. Jerarquía por tamaño y peso, nunca por color.**
- Bien: el titular es lo más grande y lo más oscuro.
- Mal: se resalta un texto con un tono que no está en la tabla.

---

## 4. El resto de la superficie tonal se deriva, no se declara

Lo que está en la tabla de la sección 1 es todo lo que este design system
declara. El borde de un botón, la sombra de una tarjeta, el fondo alterno de una
fila, el color de un icono: todo sale de estos cinco mezclados entre sí.

**El export de Stitch llegó con 37 hex y 48 claves de Material.** La
transformación 9 de `limpiar-stitch.cjs` colapsó el mapa de colores a los cinco
de esta tabla. Si al revisar aparece un color que no está aquí, ese color no se
agrega: se cambia por una mezcla que ya existe. Agregar es exactamente cómo una
peluquería terminó con cuarenta colores.

---

## 5. La puerta, antes de subir

```
node SISTEMA/scripts/tools/contar-colores.cjs CLIENTES/021-atrio-coffee/03-DEMO/DESIGN.md
```

Después, el checkpoint con CGL, que no es opcional:

> "Para **ATRIO Coffee Lab**: guinda de cereza `#631C24` con su tono oscuro para
> el hover, títulos en Playfair Display y cuerpo en Plus Jakarta Sans. ¿Te late?
> Lo subo al proyecto y con eso Stitch deja de inventar cosas."

Sin ese sí, no se sube. Una marca que sube sin aprobación contamina todas las
pantallas que se generen después.

---

## 6. Lo que nunca va, ni en este archivo ni en la página

- Gradientes. (Por eso la imagen de compartir es un campo guinda liso, no un degradado.)
- Glassmorphism.
- Sombras de varias capas.
- Emojis usados como iconos.
- Un color que no esté en la tabla de la sección 1.
- Una familia tipográfica que no sea la del rubro.
