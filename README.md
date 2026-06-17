# Sitio web — Florencia González · Contadora Pública

Sitio _one page_ estático (HTML + CSS + JavaScript puro, sin frameworks ni build).
Liviano, rápido, optimizado para SEO local y pensado para entregarse 100% en manos de la clienta.

---

## 📁 Estructura

```
.
├── index.html              # Toda la página (8 secciones + schema markup)
├── css/
│   └── styles.css          # Estilos (paleta verde azulado + cobre)
├── js/
│   └── main.js             # Menú móvil, animaciones, botón flotante
├── assets/
│   ├── favicon.svg         # Ícono del sitio (monograma FG)
│   └── img/
│       ├── florencia-hero.svg    # PLACEHOLDER → reemplazar por foto real
│       └── florencia-sobre.svg   # PLACEHOLDER → reemplazar por foto real
├── netlify.toml            # Configuración de despliegue en Netlify
├── robots.txt              # SEO
├── sitemap.xml             # SEO
├── site.webmanifest        # PWA / ícono
└── README.md               # Este archivo
```

---

## ✅ Antes de publicar: checklist de personalización

Buscá los textos marcados con **`[EDITAR]`** y el número de WhatsApp de prueba para reemplazarlos.

### 1. Número de WhatsApp (lo más importante)
El número de prueba es **`549299XXXXXXX`**. Aparece en varios botones y links.

- Buscar y reemplazar en **todo el proyecto** `549299XXXXXXX` por el número real.
- Formato: código de país + área + número, **sin** `+`, espacios ni guiones.
  Ejemplo para un celular de Neuquén: `5492991234567`
  (54 = Argentina · 9 = celular · 299 = área Neuquén · resto = número).
- Los mensajes prediseñados ya están cargados (ej. _"Hola Florencia, me gustaría consultarte sobre..."_).
  Si querés cambiarlos, editá el texto que sigue a `?text=` en cada link (debe ir codificado para URL).

### 2. Fotos reales
Reemplazá los dos placeholders manteniendo el **mismo nombre de archivo** (o actualizá la ruta en `index.html`):

- `assets/img/florencia-hero.svg` → foto profesional vertical (recomendado **800×1000 px**, formato `.jpg`/`.webp`).
- `assets/img/florencia-sobre.svg` → foto más informal y cercana (cuadrada **800×800 px**).

> Si subís un `.jpg`/`.webp`, acordate de actualizar la extensión en el `src` de las etiquetas `<img>` dentro de `index.html`.

### 3. Imagen para compartir en redes (Open Graph)
Subí una imagen **1200×630 px** a `assets/img/og-image.jpg`. Es la que se ve al compartir el link en WhatsApp, Facebook, etc.

### 4. Datos de contacto y dirección
En `index.html`, buscá `[EDITAR]` y completá:
- Dirección del estudio (sección **Contacto** y bloque de schema `application/ld+json`).
- El **mapa** (sección Contacto): cambiá el parámetro `q=Neuquén,Argentina` del `iframe` por la dirección exacta.
- Teléfono en el bloque schema (`telephone`).
- Horario: ya está cargado como **lunes a viernes de 9 a 12 hs** (cambialo si corresponde).

### 5. Textos personales
- Sección **Sobre mí**: completar formación, años de experiencia y el detalle personal (`[EDITAR]`).
- Datos numéricos de la sección "Sobre mí" (`+[X]` años, etc.).
- Revisar/confirmar las **preguntas frecuentes** y sus respuestas (algunas tienen `[EDITAR]` con datos impositivos a confirmar según normativa vigente).

### 6. Dominio (SEO)
Cuando tengas el dominio definitivo, reemplazá `https://www.florenciagonzalez.com.ar/` en:
- `index.html` (etiquetas `canonical`, Open Graph y schema)
- `robots.txt`
- `sitemap.xml`

---

## 🎨 Identidad visual

| Elemento | Valor |
|----------|-------|
| Verde azulado (primario) | `#134E4A` |
| Verde azulado profundo | `#0B2E2C` |
| Cobre terracota (acento) | `#BE6A3C` |
| Fondo crema | `#FAF7F2` |
| Tipografía títulos | Poppins |
| Tipografía texto | Open Sans |

Todos los colores están centralizados como variables CSS en `:root` (arriba de `css/styles.css`).
Cambiando ahí, se actualiza todo el sitio.

---

## 🚀 Cómo verlo localmente

Al ser estático, alcanza con abrir `index.html` en el navegador.
Para que el mapa y las fuentes carguen igual que en producción, conviene levantar un servidor local:

```bash
# Con Python (ya instalado en la mayoría de los equipos)
python -m http.server 5500
# luego abrir http://localhost:5500
```

---

## 🌐 Despliegue en Netlify

**Opción A — Arrastrar y soltar (la más simple)**
1. Entrar a [app.netlify.com](https://app.netlify.com) → _Add new site_ → _Deploy manually_.
2. Arrastrar la carpeta completa del proyecto.
3. Listo: Netlify da una URL `*.netlify.app`.

**Opción B — Desde Git (recomendado para actualizaciones)**
1. Subir el proyecto a un repo de GitHub/GitLab.
2. En Netlify: _Add new site_ → _Import from Git_ → elegir el repo.
3. Build command: _(vacío)_ · Publish directory: `.`
4. Deploy.

**Dominio propio:** en Netlify → _Domain settings_ → _Add a domain_, y seguir las instrucciones de DNS.
El archivo `netlify.toml` ya incluye cabeceras de seguridad y caché optimizada.

---

## ♿ Accesibilidad y rendimiento

- Contraste de color acorde a WCAG, foco visible para teclado, `alt` en imágenes y `aria-label` en íconos.
- Respeta `prefers-reduced-motion` (desactiva animaciones para quien lo configura).
- Áreas táctiles ≥ 44px, responsive verificado a 375 / 768 / 1024 / 1440 px.
- Sin dependencias externas salvo Google Fonts y el mapa de Google.

---

## 🔎 SEO incluido

- Metadatos optimizados para **"contadora Neuquén"** y variantes.
- Datos estructurados `AccountingService` (negocio local) + `FAQPage` (para _featured snippets_).
- `sitemap.xml` y `robots.txt` listos.
- HTML semántico con jerarquía de encabezados correcta.

> Tras publicar, dar de alta el sitio en **Google Search Console** y en el **Perfil de Empresa de Google** (Google Business Profile) para potenciar el SEO local.
