# Nadine · App de contenido para tus empresas

App para asesorar a varias empresas: cada una tiene su propio espacio con planificador, ideas, guiones, mensajes y estadísticas, y puedes comparar los resultados de todas. Se instala en **PC y celular** (es una PWA: una página web que se instala como app y funciona sin internet).

## Qué trae

| Sección | Para qué sirve |
|---|---|
| **Empresas** | Un espacio por cada empresa que asesoras, con su logo, color y **perfil del nicho** (a qué se dedica, público, productos, diferencial, tono y objetivo). Cambias de empresa desde el menú. |
| **Inicio** | Resumen de la empresa activa y de todas tus empresas. |
| **Planificador** | Calendario semanal de la empresa activa, con formatos y estados (Idea, Programado, Publicado). |
| **Ideas con IA** | Ideas de Reels, carruseles, guiones, títulos, descripciones, hashtags y un plan de 7 días, adaptadas al nicho de la empresa y al objetivo (Vender, Educar, Entretener, Conectar, Testimonios). Puedes descartar, guardar, borrar, programar o convertir en guion. |
| **Guiones** | **Guion automático**: escribes el tema, eliges objetivo, duración y red, y la app arma el guion completo (gancho, escenas con tiempos, cierre y texto para publicar). Botón "Otra versión" para variar. |
| **Automatización** | Mensajes de bienvenida, regalos, ofertas y recordatorios de cada empresa, con sus resultados. |
| **Estadísticas** | Números mensuales de cada empresa con gráficas y **Informe PDF** para entregar al cliente. |
| **Comparativo** | Compara todas las empresas: crecimiento, ingresos, tasa de interacción y más. Descarga para Excel (CSV) e informe PDF. |
| **Configuración** | Tu nombre y logo (aparecen en los informes), instalación y copias de seguridad. |

> **Importante:** los datos se guardan en cada dispositivo por separado. Para pasar todo del PC al celular usa *Configuración → Descargar copia* y luego *Importar copia* en el otro dispositivo.

### Sobre las "Ideas con IA"

Las ideas y los guiones se arman con plantillas de marketing que combinan el **perfil del nicho** de cada empresa, la red social, el objetivo y el tema que escribes. Funcionan gratis y sin internet, pero no son una inteligencia artificial conectada: revísalas y ajústalas a la voz de cada marca. Conectar una IA real requiere un pequeño servidor que guarde la clave de forma segura (por ejemplo, Netlify Functions); nunca pongas una clave de API dentro del `index.html`.

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
- **Después de cualquier cambio** sube la versión en `sw.js` (`nadine-v1` → `nadine-v2`) para que los dispositivos instalados se actualicen.
