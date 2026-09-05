# Ayaris & Co. — Sitio web

Sitio web estático (HTML + CSS + JS puro, sin frameworks ni build tools) para
**Ayaris & Co. — Firma Legal & Contable**. Está listo para subir directamente a
GitHub Pages.

## Estructura del proyecto

```
ayaris-web/
├── index.html              → toda la página (una sola página con secciones ancladas)
├── css/
│   └── style.css           → estilos y diseño responsivo
├── js/
│   └── script.js           → menú móvil y pequeños detalles
├── assets/
│   └── img/
│       ├── logo-full.jpg       → tu logo completo (usado en "Nosotros")
│       ├── logo-mark.png       → el monograma "AR" recortado (usado en el header y footer)
│       ├── favicon-32.png, favicon-16.png, apple-touch-icon.png, favicon-512.png
│       ├── team/                → fotos de tus asociados (placeholders por ahora)
│       └── clientes/            → carpeta lista para tus logos de clientes reales
└── README.md
```

## ⚠️ Antes de publicarlo: contenido de ejemplo a reemplazar

Para que la web quedara completa y navegable te agregué **contenido de ejemplo**
en tres secciones. Revísalas y reemplázalas antes de que el sitio sea público:

1. **"Asociados"** (`index.html`, sección `id="equipo"`): nombres, cargos y
   biografías son de relleno. Reemplaza cada `Nombre del Asociado` por el
   nombre real, y cada `team-photo` con una foto real (ideal 600×600px) en
   `assets/img/team/`.
2. **"Clientes"** (`index.html`, sección `id="clientes"`): en vez de inventar
   nombres de empresas, puse **sectores** genéricos (Construcción, Retail, etc.).
   Si quieres mostrar logos de clientes reales, colócalos en
   `assets/img/clientes/` y reemplaza la lista `.sector-strip` por imágenes.
3. **Testimonios**: están anonimizados ("Gerencia General — empresa del sector
   construcción"). Reemplázalos por citas reales, siempre con autorización del
   cliente.
4. **Dirección de oficina**: en la sección de contacto puse
   "Lima, Perú (actualiza con tu dirección exacta)" — cámbialo por tu dirección real.
5. **Correo de contacto**: usé `contacto@ayariscompania.pe` como ejemplo.
   Reemplázalo por tu correo real en dos lugares de `index.html` (busca
   `contacto@ayariscompania.pe`).

El teléfono **+51 943 535 692** ya está puesto correctamente en el botón de
llamada y en el enlace directo de WhatsApp.

## Sobre el formulario de contacto

El formulario actual usa `mailto:`, es decir, abre el programa de correo del
visitante con el mensaje precargado. Esto funciona sin servidor, pero depende
de que el visitante tenga un cliente de correo configurado en su dispositivo.

Si más adelante quieres que los mensajes lleguen directo a tu bandeja sin ese
paso intermedio, la opción más simple (gratis para poco volumen) es
[Formspree](https://formspree.io/): creas una cuenta, te dan una URL, y solo
cambias en `index.html`:

```html
<form class="contact-form" action="https://formspree.io/f/TU_ID" method="POST">
```

y quitas el atributo `enctype="text/plain"`.

---

## Cómo subirlo a GitHub y verlo en línea (paso a paso)

No necesitas saber programar para esto — son los mismos pasos sin importar el
contenido del sitio.

### 1. Crea una cuenta y un repositorio en GitHub

1. Ve a [github.com](https://github.com) y crea una cuenta si no tienes una.
2. Haz clic en el botón **"New"** (o el ícono **+** arriba a la derecha →
   **New repository**).
3. Ponle de nombre, por ejemplo: `ayaris-web` (puede ser el nombre que quieras).
4. Déjalo como **Public** (público) — es obligatorio para usar GitHub Pages
   gratis.
5. **No marques** la casilla de "Add a README file" (ya tienes uno en el ZIP).
6. Haz clic en **Create repository**.

### 2. Sube los archivos

En la página del repositorio recién creado, GitHub te muestra un enlace que
dice algo como **"uploading an existing file"**:

1. Descomprime el ZIP que te entregué en tu computadora.
2. Haz clic en **"uploading an existing file"** (o **Add file → Upload files**).
3. Arrastra **todo el contenido** de la carpeta `ayaris-web` (el archivo
   `index.html`, y las carpetas `css`, `js`, `assets`, `README.md`) — no la
   carpeta en sí, sino lo que está adentro.
4. Abajo, en "Commit changes", deja el mensaje por defecto y haz clic en
   **Commit changes**.

### 3. Activa GitHub Pages

1. Dentro de tu repositorio, ve a la pestaña **Settings** (Configuración).
2. En el menú de la izquierda, haz clic en **Pages**.
3. En **"Build and deployment" → "Source"**, elige **Deploy from a branch**.
4. En **"Branch"**, selecciona `main` (o `master`, según cómo se llame la tuya)
   y la carpeta `/ (root)`.
5. Haz clic en **Save**.

### 4. Verlo en línea

Espera 1–2 minutos. Luego, en esa misma pantalla de **Settings → Pages**,
GitHub te mostrará un mensaje verde con la URL pública, con este formato:

```
https://TU-USUARIO.github.io/ayaris-web/
```

Esa es la dirección de tu sitio web, ya en línea y visible para cualquier
persona con ese enlace.

### 5. Actualizaciones futuras

Cada vez que quieras cambiar algo (texto, fotos, teléfono, etc.):

1. Edita el archivo correspondiente directamente en GitHub (ícono de lápiz ✏️
   al abrir el archivo) o sube una versión nueva con **Add file → Upload files**.
2. Haz **Commit changes**.
3. GitHub Pages se actualiza solo, en 1–2 minutos, sin que tengas que repetir
   los pasos anteriores.

### (Opcional) Dominio propio

Si más adelante compras un dominio como `ayariscompania.pe` o `.com`, en
**Settings → Pages → Custom domain** puedes escribirlo ahí, y GitHub te indica
qué registros DNS configurar con quien te vendió el dominio.

---

## Notas técnicas

- El sitio es **100% responsivo**: se adapta a celulares, tablets y pantallas
  de escritorio (probado con breakpoints en 900px y 760px de ancho).
- No usa frameworks externos (React, Bootstrap, etc.) — es HTML, CSS y
  JavaScript simples, fáciles de editar incluso sin experiencia previa.
- Las tipografías (Playfair Display y Work Sans) se cargan desde Google Fonts,
  por lo que el sitio necesita conexión a internet para verse con esas
  fuentes exactas (si no hay conexión, el navegador usa una fuente similar
  del sistema automáticamente).
