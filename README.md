# BODY RECOMPOSITIONS · NEXUS KNOWLEDGE

**Web completa, responsive y estática (HTML + CSS + JavaScript).** Incluye cuatro páginas, carrito de ebooks y formulario de consulta por WhatsApp. Edición: noviembre de 2026.

## 1. Archivos principales

- `index.html` — Inicio, hero editorial, magazine, guías destacadas y barra de confianza.
- `ebooks.html` — Catálogo de seis guías, filtros, buscador, ordenamiento, fichas con temario y carrito.
- `informacion.html` — Historia, fundamentos, GLP-1/GIP/glucagón/GHK-Cu, etapas de investigación, noticias y glosario.
- `comunidad.html` — Comunidad, recursos, FAQ, formulario de contacto y política informativa de privacidad.
- `assets/css/styles.css` — Toda la identidad gráfica responsive, transparencias y animaciones.
- `assets/js/data.js` — **Configuración editable** de WhatsApp, productos, precios, noticias y glosario.
- `assets/js/app.js` — Interacciones, detalles, carrito, filtros, formularios y WhatsApp.
- `assets/img/` — Logo BR entregado por la marca, portadas SVG originales, iconos y gráficos de ADN.
- `robots.txt` y `sitemap.xml` — Archivos SEO básicos.

## 2. Abrir la web

En VS Code, abre la carpeta y ejecuta **Live Server** o abre `index.html` en un navegador. Para comprobar el almacenamiento local del carrito entre páginas, usa un servidor web local en lugar de abrir cada archivo con `file://`.

Ejemplo si tienes Python:

```bash
cd Body_Recompositions_Nexus_2026
python -m http.server 8000
```

Luego abre `http://localhost:8000`. Para publicar, sube **el contenido de la carpeta** a `public_html` del dominio, o a la raíz documental correspondiente. Conserva las rutas de las cuatro páginas y la carpeta `assets/`.

## 3. Configurar precios reales de los ebooks

Los precios de los viales originales **NO** se han empleado como precios de ebooks. En `assets/js/data.js` cada producto contiene:

```js
price: null
```

Reemplaza, por ejemplo, por:

```js
price: 19990
```

El valor se interpreta como pesos chilenos CLP. El precio aparece automáticamente en la ficha y en el carrito. Cuando **todos** los ebooks del carro tienen precio, se calcula el subtotal; en caso contrario muestra **«A confirmar por WhatsApp»**.

Los títulos del catálogo son ediciones editoriales basadas en el listado de referencia: RT 10, RT 15, RT 20, RT 30, TZ 10 y GC 100. Sus números en mg son códigos editoriales heredados del catálogo original y no indicaciones de uso.

## 4. Configurar WhatsApp y redes

Edita estas variables en `assets/js/data.js`:

```js
window.BR_CONFIG = {
  brand: 'Body Recompositions',
  whatsapp: '56986743340',
  whatsappDisplay: '+56 9 8674 3340',
  instagram: '',
  currency: 'CLP',
  supportEmail: '',
  publicationYear: 2026
};
```

El número corresponde al que figuraba en el catálogo adjunto. **Confírmalo antes de publicar.** Usa el formato internacional sin signos en la propiedad `whatsapp`. Cuando configures `instagram` con una URL verificada, aparecerá en el pie de página.

## 5. Cómo funciona el carro

1. El cliente pulsa **Agregar al carro** en un ebook.
2. Puede abrir el carrito, modificar cantidades y eliminar guías. El carrito se guarda en `localStorage` del navegador.
3. Ingresa nombre, correo electrónico, una observación opcional y acepta la casilla de privacidad.
4. La web construye un mensaje con el detalle de los ebooks, cantidades y subtotal (si hay precios), y abre `wa.me` en nueva pestaña.
5. El cliente revisa y **debe pulsar Enviar en WhatsApp**. La web no puede confirmar que lo haya enviado.

**IMPORTANTE:** No hay pasarela de pago integrada, base de datos de clientes, stock, comprobantes, entrega automática ni archivos de ebooks PDF. El ZIP incluye la plataforma de ecommerce de consulta, **no el contenido de los libros**. Una vez recibida la solicitud, el administrador debe coordinar precio definitivo, disponibilidad, un medio de pago apropiado y la entrega digital. No afirmar «pago seguro» hasta implementar y verificar un proveedor de pagos.

## 6. Cambiar texto y publicaciones

- Portadas: `assets/img/cover-*.svg` — editables en Figma, Illustrator o un editor de texto.
- Títulos, temarios, descripciones, enlaces y categorías: `assets/js/data.js` → `BR_PRODUCTS`.
- Noticias y enlaces a estudios: `assets/js/data.js` → `BR_NEWS`.
- Glosario: `assets/js/data.js` → `BR_GLOSSARY`.
- Textos, secciones, banners y navegación: archivos `.html` (las plantillas principales son editables).
- Paleta oficial: variables CSS al comienzo de `assets/css/styles.css`.

Noticias verificadas al **16 de noviembre de 2026**. El contenido no se actualiza solo; revisa fecha y fuente antes de publicar nuevas entradas.

## 7. Avisos editoriales y sanitarios

- Tienda de **ebooks 100 % informativos**. **No** incluye venta de viales, compuestos farmacológicos, agua bacteriostática ni material de administración.
- No hay instrucciones de reconstitución, dosis, inyección ni tratamientos personales.
- La retatrutida sigue siendo objeto de investigación a la fecha editorial mencionada; se enlaza una alerta del ISP de Chile sobre productos comercializados sin registro sanitario.
- GHK-Cu se explica distinguiendo hallazgos preclínicos y evidencia humana limitada.
- El estudio de una molécula o su presencia en un artículo no implica autorización sanitaria ni aval a su uso.

Fuentes utilizadas en la curaduría editorial:

- ISP Chile, alerta Retatrutide, 19-08-2026: <https://www.ispch.cl/alerta/alerta-de-productos-farmaceuticos-sin-registro-falsificados-alerta-a-la-comunidad-sobre-el-producto-comercializado-como-retatrutide-10-mg-y-retatrutide-20-mg/>
- NEJM, TRIUMPH-1, publicado 29-09-2026: <https://www.nejm.org/doi/10.1056/NEJMoa2604169>
- NEJM, estudios de retatrutida/osteoartritis, publicado 08-11-2026: <https://www.nejm.org/doi/full/10.1056/NEJMoa2610676>
- PubMed, revisión sobre GHK-Cu: <https://pubmed.ncbi.nlm.nih.gov/42797253/>
- PubMed, revisión sobre tirzepatida: <https://pubmed.ncbi.nlm.nih.gov/41200927/>

## 8. Lista antes del lanzamiento

- [ ] Confirmar que el número de WhatsApp oficial sea correcto.
- [ ] Definir precios **de ebooks**, disponibles y derechos de distribución de cada PDF.
- [ ] Completar razón social, términos de compra, devoluciones aplicables y política de privacidad con asesoría legal si corresponde.
- [ ] Integrar o definir un medio de pago verificable; no mostrar sellos que aún no corresponden.
- [ ] Verificar URLs de redes sociales y enlaces científicos.
- [ ] Publicar en hosting HTTPS y verificar todas las páginas, SEO y funcionamiento de WhatsApp en móviles.
- [ ] Sustituir fechas de noticias cuando exista nueva información verificada.

**La web está completa como frontend interactivo; el procesamiento de pagos y la entrega automática de PDFs no están implementados.**
