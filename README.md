# 📦 ORIGEN0 — Arabian Collection
## Catálogo Online de Perfumes

---

## 🎯 ¿Qué tienes?

He refactorizado completamente tu catálogo en una **solución profesional, moderna y escalable**:

### **2 Archivos principales:**

1. **`index.html`** - Página web completa
2. **`perfumes.json`** - Base de datos de perfumes

### **Mejoras implementadas:**

✅ **Responsividad total** - Funciona perfecto en móvil, tablet y desktop  
✅ **Datos separados del HTML** - Fácil mantenimiento y actualización  
✅ **Filtros dinámicos** - Busca por categoría sin recargar  
✅ **Metadata SEO** - Preparado para buscadores  
✅ **Accesibilidad** - Cumple estándares WCAG  
✅ **Animaciones suaves** - Experiencia moderna y fluida  
✅ **Fallback de imágenes** - Si falla una imagen, se muestra un placeholder elegante  
✅ **Performance optimizado** - Lazy loading en imágenes  

---

## 📁 Estructura de carpetas (para Vercel)

```
tu-proyecto/
├── index.html
├── perfumes.json
├── images/              (crea esta carpeta)
│   ├── armaf-green-irish-tweed.jpg
│   ├── armaf-club-de-nuit.jpg
│   └── ... (rest de imágenes)
└── README.md
```

---

## 🚀 Cómo usar localmente

### 1. **Descargar archivos**
- Guarda `index.html` y `perfumes.json` en la misma carpeta

### 2. **Abrir en navegador**
```bash
# Opción 1: Doble clic en index.html
# Opción 2: Usar un servidor local

# Si tienes Python 3:
python -m http.server 8000

# Si tienes Node.js:
npx http-server

# Luego abre: http://localhost:8000
```

### 3. **Agregar tus imágenes**
- Crea una carpeta `images/` en el mismo lugar que `index.html`
- Descarga imágenes reales de tus perfumes (JPG o PNG)
- Renómbralas según el formato: `armaf-green-irish-tweed.jpg`
- El HTML las buscará automáticamente

---

## ✏️ Cómo actualizar perfumes

### **Opción A: Editar JSON directamente (Recomendado)**

Abre `perfumes.json` y sigue esta estructura:

```json
{
  "collections": [
    {
      "id": "armaf-signatures",
      "name": "Armaf",
      "category": "Signatures",
      "products": [
        {
          "id": "armaf-001",
          "name": "Nombre del perfume",
          "brand": "Armaf",
          "category": "Signatures",
          "ml": "100ML",
          "notes": "Nota1 · Nota2 · Nota3",
          "profile": "Descripción del perfil olfativo",
          "image": "/images/nombre-archivo.jpg"
        }
      ]
    }
  ]
}
```

**Ejemplo de agregar un perfume nuevo:**

```json
{
  "id": "armaf-007",
  "name": "Armaf New Fragrance",
  "brand": "Armaf",
  "category": "Signatures",
  "ml": "100ML",
  "notes": "Bergamota · almizcares · cedro",
  "profile": "Fresco y sofisticado",
  "image": "/images/armaf-new-fragrance.jpg"
}
```

### **Opción B: Agregar categoría/colección nueva**

```json
{
  "id": "marka-nueva",
  "name": "Nueva Marca",
  "category": "Luxury",
  "description": "Descripción de la marca",
  "products": [
    { /* perfume aquí */ }
  ]
}
```

---

## 🎨 Personalizar estilos

### Cambiar colores principales

En `index.html`, en la sección `<style>`, busca `:root` y modifica:

```css
:root {
  --gold: #c8aa6e;           /* Color dorado (principal) */
  --gold-dark: #a68a4a;      /* Dorado oscuro (hover) */
  --bg: #f4f0e8;             /* Fondo general */
  --text-primary: #111111;   /* Texto principal */
  --text-secondary: #746c61; /* Texto secundario */
}
```

### Cambiar tipografía

```css
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}
```

Puedes importar Google Fonts agregando en el `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
```

Y luego usarla:

```css
h1, h2, h3 {
  font-family: "Playfair Display", serif;
}
```

---

## 🌐 Desplegar en Vercel

### **Paso 1: Preparar repositorio Git**

```bash
# En la carpeta de tu proyecto
git init
git add .
git commit -m "Initial commit"
```

### **Paso 2: Subir a GitHub**

1. Crea un repo en GitHub
2. Sube tu código:

```bash
git remote add origin https://github.com/tu-usuario/tu-repo.git
git push -u origin main
```

### **Paso 3: Desplegar en Vercel**

1. Ve a [vercel.com](https://vercel.com)
2. Haz login con GitHub
3. Click en "New Project"
4. Selecciona tu repositorio
5. **Importante**: En "Build and Output Settings", selecciona:
   - **Framework Preset**: Other
   - **Build Command**: (dejar vacío)
   - **Output Directory**: (dejar vacío)
6. Click "Deploy"

**¡Listo!** Tu catálogo estará en vivo en algo como:  
`https://tu-proyecto.vercel.app`

---

## 📊 Estructura del JSON en detalle

```json
{
  "store": {
    "name": "ORIGEN0",
    "tagline": "Arabian Collection",
    "description": "Tu descripción aquí"
  },
  
  "collections": [
    {
      "id": "id-único",                    // Identificador único
      "name": "Nombre de la colección",   // Se muestra como título
      "category": "Signatures",            // Categoría (para filtros)
      "description": "Descripción",        // (Opcional) descripción
      "products": [
        {
          "id": "producto-001",            // Identificador único
          "name": "Nombre del perfume",
          "brand": "Marca",
          "category": "Signatures",        // Debe coincidir con uno de los filtros
          "ml": "100ML",
          "notes": "Nota1 · Nota2",        // Separadas por " · "
          "profile": "Descripción breve",
          "image": "/images/nombre.jpg",   // Ruta de imagen (relativa)
          "fallbackImage": "url-alternativo" // (Opcional) si falla la imagen local
        }
      ]
    }
  ],
  
  "filters": [
    {
      "id": "all",
      "label": "Todos"
    }
    // ... más filtros
  ]
}
```

---

## 🔍 Categorías disponibles

Por defecto están configuradas estas categorías:

- **Signatures** - Fragancias principales
- **Women** - Para damas
- **Body Care** - Body splash y mist
- **Luxury** - Productos de lujo

Puedes **agregar más categorías** editando la sección `"filters"` en el JSON.

---

## 🐛 Troubleshooting

### **Las imágenes no cargan**

1. Asegúrate de que la carpeta `images/` esté en el mismo nivel que `index.html`
2. Verifica que el nombre del archivo coincida exactamente con la ruta en JSON
3. Las imágenes deben ser JPG o PNG
4. Tamaño recomendado: 400x600px

### **Los filtros no funcionan**

1. Abre la consola del navegador (F12)
2. Revisa si hay errores en rojo
3. Asegúrate de que `perfumes.json` esté en el mismo nivel que `index.html`
4. Revisa que el JSON tenga sintaxis válida (sin comas extras, etc.)

### **Error de CORS al cargar JSON**

Necesitas servir los archivos a través de un servidor HTTP, no abriendo el HTML directamente. Ver sección "Usar localmente".

---

## 💡 Tips y mejoras futuras

### Posibles mejoras:
- ✅ Agregar búsqueda por nombre
- ✅ Zoom en imágenes al hacer clic
- ✅ Compartir en redes sociales
- ✅ Carrito de compras (si lo necesitas)
- ✅ Integrar WhatsApp para consultas

### Para móvil:
- ✅ Agregar PWA (Progressive Web App)
- ✅ Instalable como app nativa

---

## 📝 Notas importantes

1. **Seguridad**: Este es un catálogo estático. No hay sensibilidad de datos.
2. **Performance**: La página carga rápido porque es HTML + JSON puro.
3. **SEO**: Los metadatos están configurados para Google.
4. **Mantenimiento**: Cambios rápidos editando solo el JSON.

---

## 🎁 Bonus: Editar en línea

Puedes usar herramientas online para editar JSON:
- [jsoncrack.com](https://jsoncrack.com) - Visualiza y edita JSON con interfaz gráfica
- [jsonlint.com](https://jsonlint.com) - Valida que tu JSON sea correcto

---

## 📞 Soporte

Si tienes dudas sobre cómo:
- Agregar más perfumes
- Cambiar colores
- Ajustar el diseño
- Desplegar en Vercel

¡Pregúntame! Estoy aquí para ayudarte. 🚀

---

**Versión**: 1.0  
**Última actualización**: 2024  
**Licencia**: Libre para uso personal y comercial
