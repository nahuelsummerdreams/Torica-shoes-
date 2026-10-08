# Torica Shoes · sitio mayorista 2026

Sitio de una sola página (`index.html`), sin servidor. Catálogo mayorista con curva de 8 pares y surtido.

## Cómo editar
Todo está en `index.html`:
- **Datos del negocio:** bloque `CONFIG` (WhatsApp, Instagram, textos de envíos/pagos/cambios, talles).
- **Productos:** bloque `PRODUCTS` (nombre, precios de curva y surtido, colores, medidas).

## Precios y stock desde una planilla de Google (sin tocar código)
1. Subí `precios-plantilla.csv` a Google Sheets (Archivo > Importar).
2. Cambiá `curva` y `surtido`. En `disponible` poné `no` para marcar un modelo sin stock.
3. Archivo > Compartir > **Publicar en la web** > hoja completa > formato **CSV** > Publicar.
4. Copiá el link y pegalo en `CONFIG.hoja` dentro de `index.html`.

La web carga esos valores al abrirse. Si la planilla no responde, usa los precios del catálogo.

## Publicar con dominio propio (GitHub Pages)
1. En GitHub: **Settings > Pages > Build and deployment > Source: GitHub Actions**.
2. Cada vez que se actualice `master`, el workflow `.github/workflows/pages.yml` publica el sitio.
3. Dominio propio: comprá el dominio (por ejemplo `toricashoes.com.ar`), creá un archivo `CNAME` en la raíz con ese dominio y, en el proveedor, apuntá un registro `CNAME` (o los `A` de GitHub Pages) a `<usuario>.github.io`. Luego activá **Enforce HTTPS** en Settings > Pages.

## Estadísticas de visitas (opcional)
En `CONFIG.analytics` completá `plausible: "tudominio.com.ar"` o `ga: "G-XXXXXXXXXX"`.

## Imprimir
`#/lista` (lista de precios) y `#/pedido` (pedido armado) tienen botón de imprimir / guardar PDF.
