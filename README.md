# Feeds de productos

Genera cada hora un feed completo para Google Merchant Center (y una versión para asistentes de IA)
de cada tienda listada en `tiendas.json`. Detecta solo la plataforma: Shopify, WooCommerce,
Tiendanube, Luna, VTEX, Magento, o cualquier otra con datos estructurados (JSON-LD).

## URLs (GitHub Pages)

- Resumen de todas las tiendas: `https://<usuario>.github.io/<repo>/`
- Feed para Google: `https://<usuario>.github.io/<repo>/feeds/<slug>.xml`
- Versión para IA: `https://<usuario>.github.io/<repo>/feeds/<slug>.json`

## Agregar una tienda

Sumá un bloque a `tiendas.json`. Solo `slug`, `nombre` y `url` son obligatorios:

| Campo | Para qué sirve |
|---|---|
| `slug` | Nombre corto del archivo del feed (sin espacios) |
| `nombre` | Nombre de la tienda |
| `url` | Página principal de la tienda |
| `moneda` | Moneda (ARS, CLP, COP, UYU, USD...). Obligatoria en VTEX; en las demás se detecta, pero conviene ponerla |
| `marca` | Marca para productos que no tengan una propia |
| `genero` | `male`, `female` o `unisex` si toda la tienda es de un género |
| `categoria_google` | Categoría de Google para toda la tienda (si no, se deduce de cada producto) |
| `plataforma` | Forzar la plataforma (`shopify`, `woocommerce`, `tiendanube`, `luna`, `vtex`, `magento`, `generico`) |
| `quitar_parrafos` | Textos cuyos párrafos se eliminan de las descripciones (ej. políticas de devolución) |
| `ignorar_opciones` | Opciones de variante que no son variantes reales (ej. `puntos`) |
| `preorden_como` | `preorder` (por defecto) o `in_stock` para productos en pre-orden |
| `tiempo_max_min` | Minutos máximos por tienda en cada corrida (por defecto 8) |
| `activa` | `false` para pausar una tienda sin borrarla |
| `patron_productos` | Solo tiendas genéricas: expresión que identifica las URLs de producto en el sitemap |
