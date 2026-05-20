# 📝 PLANTILLA PARA AGREGAR PERFUMES

Copia y pega esta plantilla en tu `perfumes.json` para agregar nuevos perfumes rápidamente.

---

## 🔧 Agregar UN perfume a una colección existente

En `perfumes.json`, busca la colección donde quieres agregar el perfume y pega esto dentro del array `products`:

```json
{
  "id": "armaf-nuevo-001",
  "name": "Armaf Nueva Fragancia",
  "brand": "Armaf",
  "category": "Signatures",
  "ml": "100ML",
  "notes": "Nota1 · Nota2 · Nota3",
  "profile": "Descripción corta del aroma",
  "image": "/images/armaf-nueva-fragancia.jpg",
  "fallbackImage": "https://via.placeholder.com/200x300?text=Perfume"
}
```

**Asegúrate de agregar una coma después si no es el último producto.**

---

## 🎁 Agregar una NUEVA COLECCIÓN/MARCA

Busca `"collections": [` en el JSON y agrega esto:

```json
{
  "id": "nueva-marca-signatures",
  "name": "Nueva Marca",
  "category": "Signatures",
  "description": "Fragancias premium de Nueva Marca",
  "products": [
    {
      "id": "nueva-marca-001",
      "name": "Primer perfume",
      "brand": "Nueva Marca",
      "category": "Signatures",
      "ml": "100ML",
      "notes": "Notas aquí",
      "profile": "Perfil aquí",
      "image": "/images/nueva-marca-001.jpg"
    },
    {
      "id": "nueva-marca-002",
      "name": "Segundo perfume",
      "brand": "Nueva Marca",
      "category": "Signatures",
      "ml": "100ML",
      "notes": "Notas aquí",
      "profile": "Perfil aquí",
      "image": "/images/nueva-marca-002.jpg"
    }
  ]
}
```

**Recuerda:** Agregar coma después de la llave de cierre `}` si no es la última colección.

---

## 📋 Referencia de campos

| Campo | Obligatorio | Ejemplo | Notas |
|-------|-----------|---------|-------|
| `id` | ✅ | `armaf-001` | Único, sin espacios |
| `name` | ✅ | `Armaf Club De Nuit` | Nombre del perfume |
| `brand` | ✅ | `Armaf` | Marca |
| `category` | ✅ | `Signatures` | Debe coincidir con filtros |
| `ml` | ✅ | `100ML` | Volumen |
| `notes` | ✅ | `Citrus · Alcanfor` | Separadas por ` · ` |
| `profile` | ✅ | `Fresco y herbal` | Descripción breve |
| `image` | ✅ | `/images/nombre.jpg` | Ruta local |
| `fallbackImage` | ❌ | URL externa | Para si falla imagen local |

---

## 🎯 Categorías disponibles

Asegúrate de que el `category` en el producto coincida con UNA de estas:

- `Signatures` - Filtro: "Signatures"
- `Women` - Filtro: "Para Damas"
- `Body Care` - Filtro: "Body Care"
- `Luxury` - Filtro: "Luxury"

Si quieres **agregar una categoría nueva**, también debes actualizarla aquí en el JSON:

```json
"filters": [
  {
    "id": "all",
    "label": "Todos"
  },
  {
    "id": "signatures",
    "label": "Signatures"
  },
  {
    "id": "women",
    "label": "Para Damas"
  },
  {
    "id": "body-care",
    "label": "Body Care"
  },
  {
    "id": "luxury",
    "label": "Luxury"
  },
  {
    "id": "tu-nueva-categoria",
    "label": "Tu Etiqueta"
  }
]
```

El `id` debe ser en minúsculas con guiones. El `label` es lo que ven los usuarios.

---

## ⚡ Ejemplos prácticos

### Ejemplo 1: Agregar Body Mist
```json
{
  "id": "armaf-bm-nuevo",
  "name": "Body Mist I Am Awesome",
  "brand": "Armaf",
  "category": "Body Care",
  "ml": "250ML",
  "notes": "Frutas · flores · vainilla",
  "profile": "Refrescante y juvenil",
  "image": "/images/body-mist-awesome.jpg"
}
```

### Ejemplo 2: Agregar fragancia para damas
```json
{
  "id": "armaf-w-nuevo",
  "name": "Armaf Creed Love In Gold",
  "brand": "Armaf",
  "category": "Women",
  "ml": "100ML",
  "notes": "Flor de loto · almizcares · ámbar",
  "profile": "Floral cálido y sensual",
  "image": "/images/armaf-love-gold.jpg"
}
```

### Ejemplo 3: Agregar marca de lujo
```json
{
  "id": "lujo-premium",
  "name": "Lujo Premium",
  "category": "Luxury",
  "description": "Fragancias de lujo exclusivas",
  "products": [
    {
      "id": "lujo-001",
      "name": "Essence of Royalty",
      "brand": "Lujo Premium",
      "category": "Luxury",
      "ml": "50ML",
      "notes": "Oud · rosa · almizcares",
      "profile": "Oriental aristocrático",
      "image": "/images/lujo-essence-royalty.jpg"
    }
  ]
}
```

---

## ✅ Checklist antes de guardar

- [ ] Todos los campos están completos (excepto `fallbackImage`)
- [ ] Los `id` son únicos
- [ ] No hay comas faltantes
- [ ] Las comillas están balanceadas
- [ ] El `category` coincide con uno de los filtros
- [ ] Las imágenes tienen extensión (.jpg, .png)
- [ ] Las notas están separadas por ` · ` (espacio + punto + espacio)

---

## 🔗 Validar JSON

Antes de usar, valida que tu JSON sea correcto:

1. Copia todo el contenido de `perfumes.json`
2. Ve a [jsonlint.com](https://jsonlint.com)
3. Pégalo y valida
4. Si muestra errores, corrígelos

---

## 💾 Guardar cambios

Después de editar:
1. Guarda el archivo (Ctrl+S o Cmd+S)
2. Recarga el navegador (F5 o Cmd+R)
3. Los cambios deberían aparecer inmediatamente

Si no ves cambios:
1. Abre la consola (F12)
2. Busca errores en rojo
3. Valida el JSON en jsonlint.com

---

**Tip**: Abre el JSON original en un editor de texto como VS Code, Sublime Text o incluso Notepad++. Estos editores suelen avisar si hay errores de sintaxis.
