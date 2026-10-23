# Ingenia-Web

Páginas públicas de **Ingenia Mobiliario**: presentaciones de muebles a medida
que se comparten con el cliente por enlace.

Cada página es un archivo HTML autocontenido. No necesita servidor, base de
datos ni instalación: se abre en cualquier navegador.

## Páginas

| Carpeta | Qué es |
|---|---|
| `nube-king/` | Cama Nube, tamaño king. El cliente elige cantidad de figuras y tono de tela y la ve en 3D. |
| `paneles-verticales-queen/` | Cama queen de paneles verticales, espaldar de pared a pared. La habitación del cliente levantada a escala desde las medidas de sitio. |
| `pedido/` | Ficha de pedido. El cliente carga fotos y medidas; la página arma un mensaje de WhatsApp y una ficha `.json`. |

## Formato de los pedidos

La ficha de pedido produce un JSON con esquema `ingenia.pedido.v1`. Ese objeto
es la unidad que se trabaja por chat y la que luego se migra a la base de datos
del catálogo. Los campos de `taller` (modelo, nombre del mueble, presupuesto)
van vacíos: los llena el taller, no el cliente.

El número de WhatsApp del taller se configura en una sola línea, al principio
del `<script>` de `pedido/index.html`:

```js
var WHATSAPP = "584162054982";   // formato internacional, sin + ni espacios
```

## Publicar con GitHub Pages

Settings → Pages → Source: `Deploy from a branch`, rama `main`, carpeta `/ (root)`.

Las páginas quedan en `https://ricardomarcano71-dev.github.io/Ingenia-Web/<carpeta>/`.

## Nota

Este repositorio es **público**. Todo lo que se suba aquí es visible para
cualquiera. El código del taller y la documentación del negocio van en los
repositorios privados, no aquí.
