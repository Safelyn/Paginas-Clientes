# Plantilla de tatuador

Cliente nuevo en 10 minutos. El contenido siempre es el mismo (portada, botones, trabajos, videos, cómo llegar, horario), pero cada cliente tiene su propio estilo: colores, letras y forma. Todo se controla desde `datos.json`; el `index.html` no se toca.

## Pasos

1. **Copia la carpeta.** Copia `_plantillas/tatuador` a la raíz del repo y ponle el nombre del cliente, sin espacios ni tildes. Ejemplo: `juan-tattoo`.
   Su link queda: `identinfc.com/juan-tattoo/`
2. **Pon las fotos** en la carpeta `fotos/` del cliente:
   - `perfil.jpg`: foto cuadrada del cliente (también sirve para la vista previa al compartir).
   - `logo.png`: opcional.
   - `portada.jpg`: opcional, horizontal, va arriba de todo.
   - `trabajo1.jpg` a `trabajo12.jpg`: de 6 a 12 fotos de tatuajes.
   - `video1.mp4` (y `video1.jpg` como portada del video): opcional, de 1 a 3 videos. Que pesen poco (menos de 10 MB cada uno).
3. **Llena `datos.json`.** Cambia solo lo que va entre comillas:
   - `nombre`, `frase`: nombre o marca y una frase corta.
   - `whatsapp`: el número con o sin 57 (ejemplo `3001234567`).
   - `instagram`, `tiktok`: solo el usuario, sin @ (ejemplo `juan.tattoo`).
   - `direccion`: texto de la dirección. `ubicacion_maps`: el link de Google Maps (en Maps: Compartir → Copiar enlace).
   - `horario`: una línea por grupo de días, con `dias` y `horas`.
   - `trabajos` y `videos`: la lista de archivos que pusiste en `fotos/`. Si son 8 fotos, deja 8 líneas.
4. **Cambia el nombre en `index.html`**: solo las 3 líneas de arriba que dicen "Nombre del tatuador" (es lo que se ve al compartir el link por WhatsApp).
5. **Sube los cambios** al repo. En 1 o 2 minutos queda en `identinfc.com/nombre-carpeta/`.
6. **Graba el chip** con `https://identinfc.com/nombre-carpeta/?t=nfc` y el **QR** con `https://identinfc.com/nombre-carpeta/?t=qr`. Así más adelante sabemos si entraron por el llavero o por el código.

## El estilo de cada cliente (bloque "tema")

Antes de llenar el tema, mándale a Claude el Instagram del cliente y su logo o 2 o 3 fotos. Claude revisa sus redes (colores que usa, tipo de letra del logo, si su estilo es oscuro o claro, delicado o fuerte) y te devuelve el bloque "tema" listo para pegar.

Qué significa cada campo:
- `estilo`: "claro" u "oscuro" (fondo y textos base).
- `fondo`, `texto`, `tarjetas`: colores en formato #RRGGBB. Vacíos = los del estilo.
- `acento`: color del botón de WhatsApp y de la portada. Normalmente el color de su marca.
- `texto_boton`: color de la letra del botón (casi siempre "#ffffff").
- `fuente_titulos`, `fuente_texto`: nombre exacto de una letra de Google Fonts (fonts.google.com). Ejemplos: "Pirata One" (old school), "Playfair Display" (elegante), "Bebas Neue" (fuerte), "Inter" (limpia).
- `titulo_mayusculas`: true o false.
- `bordes`: "recto", "redondo" o "muy_redondo".

Ejemplos con el mismo contenido y estilos distintos:
- `identinfc.com/ejemplo-tatuador/`: oscuro, rojo, letra old school, bordes rectos.
- `identinfc.com/ejemplo-tatuador-2/`: claro, terracota, letra elegante, bordes muy redondos.

## Reglas

- Si un dato queda vacío (`""`) o la lista vacía (`[]`), esa sección no sale en la página. No hay que borrar nada del diseño.
- Si una foto de la lista no existe, simplemente no aparece.
- Ojo con las comas: entre cada dato va una coma, y después del último no. Si la página sale en blanco con el mensaje "se está actualizando", casi siempre es una coma o comilla de más en `datos.json`.
- No toques las carpetas de otros clientes.

