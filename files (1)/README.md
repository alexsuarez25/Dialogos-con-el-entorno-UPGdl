# Diálogos con el Entorno — Mapa Radial Interactivo

**Universidad Panamericana Guadalajara**

Mapa interactivo de vinculación institucional que visualiza las relaciones entre la universidad y su entorno: proyectos, aliados, empresas, centros de investigación y más.

---

## Estructura del proyecto

```
/proyecto-mapa-radial
  ├── index.html      ← Aplicación completa (React SPA)
  ├── netlify.toml     ← Configuración de deploy para Netlify
  └── README.md        ← Este archivo
```

> **Nota:** El proyecto es una Single Page Application (SPA) que funciona como un único archivo HTML autocontenido. Usa React 18 + Babel standalone desde CDN. No requiere build, bundler ni servidor.

---

## Funcionalidades

| Función | Descripción |
|---------|-------------|
| **Mapa radial** (desktop) | SVG interactivo con 4 nodos principales, subcategorías y micro nodos |
| **Vista móvil** | Acordeón jerárquico con selector de temáticas (solo lectura) |
| **Buscador dinámico** | Texto libre + filtro por 24 temáticas estratégicas |
| **Gestión de nodos** | Crear/eliminar hijos y nietos desde panel admin (⚙ Nodos) |
| **Contactos editables** | Agregar, editar y eliminar contactos por nodo |
| **Notas por nodo** | Historial de notas con fecha, edición y eliminación |
| **Etiquetas dinámicas** | Agregar/eliminar etiquetas; sincronizadas con buscador |
| **Persistencia** | Todo se guarda en localStorage (sobrevive recargas) |
| **Eliminación** | Hijos y nietos eliminables desde popup (con confirmación) |

---

## Correr localmente

### Opción 1: Abrir directamente
```bash
# Simplemente abre el archivo en tu navegador
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

### Opción 2: Servidor local (recomendado)
```bash
# Con Python
python3 -m http.server 8080
# Abrir http://localhost:8080

# Con Node.js
npx serve .
# Abrir http://localhost:3000
```

---

## Deploy en Netlify

### Opción A: Drag & Drop (más rápido)
1. Ve a [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arrastra la carpeta `proyecto-mapa-radial` completa
3. Listo — Netlify genera un URL público

### Opción B: Desde GitHub
1. Sube este proyecto a un repositorio de GitHub
2. Ve a [app.netlify.com](https://app.netlify.com) → **Add new site** → **Import from Git**
3. Selecciona tu repositorio
4. Build settings:
   - **Publish directory:** `.`
   - **Build command:** (dejar vacío)
5. Click **Deploy**

---

## Deploy en GitHub Pages

1. Sube el proyecto a un repositorio de GitHub
2. Ve a **Settings** → **Pages**
3. Source: **Deploy from a branch**
4. Branch: `main` / Root: `/ (root)`
5. Click **Save**
6. Tu sitio estará en `https://tu-usuario.github.io/tu-repo/`

---

## Almacenamiento (localStorage)

| Clave | Contenido |
|-------|-----------|
| `map-notes-v21` | Notas por nodo |
| `map-contacts-v1` | Contactos del usuario |
| `map-cH` | Hijos personalizados |
| `map-cN` | Nietos personalizados |
| `map-del` | Nodos eliminados |
| `map-utags` | Etiquetas del usuario |

> Los datos persisten entre recargas y versiones. Para resetear, abre la consola del navegador y ejecuta: `localStorage.clear()`

---

## Stack tecnológico

- **React 18** (CDN)
- **Babel Standalone 7.23** (transpilación en el navegador)
- **SVG** (mapa radial)
- **localStorage** (persistencia)
- **Google Fonts** (Source Sans 3, Cormorant Garamond)
- Zero dependencias de servidor

---

## Licencia

Proyecto interno — Universidad Panamericana Guadalajara
