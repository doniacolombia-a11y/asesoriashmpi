# Nadine · App de contenido para tus empresas

App para asesorar a varias empresas: cada una tiene su propio espacio con planificador, ideas, guiones, mensajes y estadísticas, y puedes comparar los resultados de todas. Se instala en **PC y celular** (es una PWA: una página web que se instala como app y funciona sin internet).

## Qué trae

| Sección | Para qué sirve |
|---|---|
| **Empresas** | Un espacio por cada empresa que asesoras, con su logo y su color. Cambias de empresa desde el menú. |
| **Ficha del negocio** | Toda la información de cada empresa: nicho, descripción, ciudad, **productos con precios**, promoción, público, problemas y beneficios del cliente, diferencial, preguntas frecuentes, WhatsApp, Instagram, horario, entregas, pagos, tono y uso de emojis. Muestra el % completado y se guarda sola. |
| **Inicio** | Resumen de la empresa activa y de todas tus empresas. |
| **Planificador** | Calendario semanal de la empresa activa, con formatos y estados (Idea, Programado, Publicado). |
| **Ideas con IA** | Ideas de Reels, carruseles, guiones, títulos, descripciones, hashtags y un plan de 7 días, adaptadas a la ficha de la empresa y al objetivo. |
| **Guiones y copys** | **Creador automático**: eliges qué crear (guion de Reel/TikTok, carrusel, historias, copy, mensaje de WhatsApp o anuncio pagado), el **caso** (15 opciones: promoción, lanzamiento, fecha especial, tips, testimonio, preguntas frecuentes, objeción de precio, sorteo y más) y el producto. La app lo escribe con los datos de la ficha. |
| **Automatización** | Mensajes de bienvenida, regalos, ofertas y recordatorios de cada empresa, con sus resultados. |
| **Estadísticas** | Números mensuales de cada empresa con gráficas e **Informe PDF**. |
| **Comparativo** | Compara todas las empresas. Descarga para Excel (CSV) e informe PDF. |
| **Configuración** | Tu marca, **diseño de la app** (modo claro/oscuro, color, tipografía, esquinas, menú), **archivo de datos compartido**, instalación y copias de seguridad. |

### Misma información en Chrome y Edge

Cada navegador guarda sus propios datos. Para ver lo mismo en los dos (en el mismo computador):

1. En Chrome, entra a **Configuración → Crear archivo de datos** y guárdalo, por ejemplo, en Documentos (`nadine-datos.json`).
2. En Edge, abre la app, entra a **Configuración → Usar un archivo existente** y elige ese mismo archivo. Escoge "Usar solo los datos del archivo".
3. Listo: los cambios de uno aparecen en el otro en pocos segundos. Si guardas el archivo en una carpeta de OneDrive o Google Drive, también funciona entre computadores.

Al volver a abrir el navegador, puede pedir permiso otra vez: toca **Reconectar** en el aviso. Funciona en Chrome y Edge de computador con la app publicada (Netlify o GitHub Pages). En el celular usa *Descargar copia* e *Importar copia*.

### Sobre las ideas y los textos automáticos

Se arman con plantillas de marketing que combinan la **ficha del negocio**, el caso, el formato y la red social. Funcionan gratis y sin internet, pero no son una inteligencia artificial conectada: revísalos y ajústalos a la voz de cada marca. Lo que aparece entre [corchetes] lo completas tú (por ejemplo, el nombre de un cliente en un testimonio real). Conectar una IA real requiere un pequeño servidor que guarde la clave de forma segura (por ejemplo, Netlify Functions); nunca pongas una clave de API dentro del `index.html`.

## Archivos

```
index.html             ← la app completa
manifest.webmanifest   ← nombre, colores e íconos para instalarla
sw.js                  ← permite usarla sin internet
netlify.toml           ← configuración para Netlify
icons/                 ← íconos de la app
```

---

## Publicarla

### Opción 1 · Netlify (la más fácil)
1. Descomprime el `.zip`.
2. Entra a **app.netlify.com/drop** (crea tu cuenta gratis si no tienes).
3. Arrastra la **carpeta `nadine-app`** completa.
4. Netlify te da un enlace; cámbialo en *Site configuration → Change site name* (por ejemplo `nadine-contenido.netlify.app`).

### Opción 2 · GitHub Pages
1. En **github.com** crea un repositorio nuevo (por ejemplo `nadine-app`), público.
2. Toca **uploading an existing file** y sube **todo lo que hay dentro** de la carpeta (incluida `icons`). Luego **Commit changes**.
3. **Settings → Pages** → Branch `main`, carpeta `/ (root)` → **Save**.
4. En uno o dos minutos queda en `https://TU-USUARIO.github.io/nadine-app/`.

### Opción 3 · GitHub + Netlify (se actualiza sola)
Sube los archivos a GitHub y en Netlify usa **Add new site → Import an existing project → GitHub**.

## Instalarla
- **PC (Chrome o Edge):** ícono de instalar en la barra de direcciones, o botón **Instalar** dentro de la app.
- **Android (Chrome):** menú ⋮ → **Instalar app**.
- **iPhone (Safari):** **Compartir** → **Agregar a inicio**.

Solo funciona con la app publicada (enlace `https`), no abriendo el archivo desde el computador.

## Si ya usabas la versión anterior
Si abres esta versión en el **mismo enlace y dispositivo** donde usabas la anterior, tus datos pasan solos a una empresa llamada "Mi empresa". Si la publicas en un enlace nuevo, descarga una copia en la versión anterior e impórtala aquí (*Configuración → Importar copia*).

## Hacer cambios
- **Color principal:** en `index.html`, `--brand:#800020`.
- **Nombre e ícono al instalar:** `manifest.webmanifest` y las imágenes de `icons/` (mismos nombres y tamaños).
- **Después de cualquier cambio** sube la versión en `sw.js` (por ejemplo `nadine-v2` → `nadine-v3`) para que los dispositivos instalados se actualicen.
