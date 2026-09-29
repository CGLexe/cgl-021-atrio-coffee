# ATRIO Coffee Lab

Muestra de página one-page de **CGL Design**. Nicho: `cafe`.

> **Esto es una muestra, no el sitio del negocio.** Se le enseña al dueño para que
> vea cómo se vería el suyo. Si decide contratar, el sitio va en su propio
> dominio con su propio nombre, y este repo deja de ser el sitio.

> **Los datos de esta muestra no están verificados.** Salieron del export de
> Google Stitch, no del dueño. La lista de qué confirmar está en
> `../05-ENTREGA.md`, y es la primera cosa que hay que leer.

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `index.html` | La página. Un solo archivo, HTML/CSS/JS estático, 0 KB de librerías. |
| `img/` | Las nueve imágenes, bajadas del CDN de Stitch a local para que no se caigan. |
| `og.jpg` | La imagen de compartir: campo guinda con el monograma, 1200×630. |
| `DESIGN.md` | El sistema de diseño: los cinco colores y las dos familias. |
| `cabeza.html` | La cabeza del cliente: meta, Open Graph, schema, favicon, movimiento. |
| `crudo.html` | El export de Stitch antes de limpiar. No se sube al repo. |

## Las siete secciones

1. **Hero** — el giro, el horario y la dirección a la vista.
2. **El laboratorio** — el método y los métodos de filtrado.
3. **Menú** — barra, filtrados lentos y repostería.
4. **Cómo pasar** — qué pasa cuando le escriben.
5. **Reseñas** — estado honesto de cero, con el enlace a Google.
6. **Ubicación** — dirección, horario, mapa y cómo llegar.
7. **Cierre** — qué pasa al escribirle.

## Lo que se corrigió del export

El export crudo de Stitch trae nueve problemas que hay que arreglar antes de
enseñar nada. Todos están corregidos aquí, y la lista es el motivo de que exista
el piso de limpieza:

| Del export | Ahora |
|---|---|
| 37 colores y 48 claves de Material | 5 colores, los del `DESIGN.md` |
| `alt` que eran el prompt de generación, en inglés y de 200 caracteres | 8 descripciones en español, de menos de 125 |
| Una "reseña destacada de Google" que era texto generado | Ninguna. La sección dice que no hay reseñas e invita a dejar la primera |
| Instagram y TikTok sin confirmar | No se renderizan |
| Un mapa con el pin en el cerro, a kilómetros del Centro | OpenStreetMap anclado al Zócalo |
| `href="#"` en la navegación | Anclas reales a las secciones |
| Sin `meta description`, sin Open Graph, sin schema, sin favicon | Los cuatro, más `CafeOrCoffeeShop` |
| Sin `prefers-reduced-motion` | Presente, y anula las cinco animaciones |
| Sin WhatsApp | Uno primario y uno flotante, los dos al 951 273 7656 |

## Cómo se corrige y se sube

```bash
# 1. editar index.html
# 2. las dos puertas: tienen que dar 0
node SISTEMA/scripts/tools/auditar-sitio.cjs CLIENTES/021-atrio-coffee/03-DEMO/index.html \
     --brief CLIENTES/021-atrio-coffee/01-BRIEF.md \
     --nicho cafe --tipo demo
node SISTEMA/scripts/tools/verificar-texto.cjs
# 3. commit y push
git add . && git commit -m "corrige: que-sea" && git push
```

El push redespliega: este repo está conectado al proyecto de Vercel.

## Lo que falta y está marcado

`[TESTIMONIOS]` en la sección de reseñas, y los datos sin verificar del brief.
**No es un descuido.** El sistema no inventa datos: se piden en la visita y se
rellenan antes de cobrar el saldo.

---

CGL Design · Páginas web para negocios de barrio en Oaxaca de Juárez
