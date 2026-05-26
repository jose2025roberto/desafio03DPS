# 📚 LearnHub — Sistema de Gestión de Recursos de Aprendizaje
### DPS441 — Tercer Desafío Práctico | Universidad Don Bosco

---

## 🚀 Configuración Inicial (Pasos OBLIGATORIOS)

### 1. Crear tu API en MockAPI.io

1. Ve a https://mockapi.io y crea una cuenta gratuita
2. Crea un nuevo proyecto (ej: `learnhub`)
3. Crea dos recursos (endpoints):

**Endpoint 1: `recursos`**
```json
{
  "id": "autoincrement",
  "titulo": "string",
  "descripcion": "string",
  "tipo": "string",
  "enlace": "string",
  "imagen": "string",
  "ratings": "object",
  "ratingUsers": "object",
  "createdAt": "string"
}
```

**Endpoint 2: `usuarios`**
```json
{
  "id": "autoincrement",
  "nombre": "string",
  "email": "string",
  "password": "string",
  "rol": "string",
  "createdAt": "string"
}
```

4. Copia tu URL base, ejemplo: `https://XXXXXXXX.mockapi.io/api/v1`

### 2. Configurar la URL de la API

Abre `src/services/api.js` y reemplaza:
```js
const BASE_URL = 'https://6830d79c0f0188d7313e3547.mockapi.io/api/v1';
```
Con tu URL de MockAPI.

### 3. Agregar datos de prueba en MockAPI

Agrega algunos recursos de prueba en el endpoint `/recursos`:
```json
{
  "titulo": "Clean Code",
  "descripcion": "Guía de buenas prácticas de programación por Robert C. Martin.",
  "tipo": "libro",
  "enlace": "https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882",
  "imagen": "https://m.media-amazon.com/images/I/41xShlnTZTL._SX376_BO1,204,203,200_.jpg"
}
```

---

## 🔧 Instalación y ejecución

```bash
# Instalar dependencias
npm install

# Ejecutar en web (Expo Web)
npx expo start --web

# Ejecutar en móvil
npx expo start
```

---

## 📱 Funcionalidades Implementadas

### ✅ Autenticación
- [x] Registro con validación completa de contraseña
  - Mínimo 12 caracteres
  - Mayúscula, minúscula, número, carácter especial
- [x] Login con email y contraseña
- [x] Logout con confirmación
- [x] Persistencia de sesión con AsyncStorage
- [x] Sistema de roles: **Estudiante** y **Docente**

### ✅ Gestión de Recursos (Docente)
- [x] Visualización en tarjetas con imagen, tipo, título, descripción
- [x] Filtrado por tipo (libro, video, tutorial, etc.)
- [x] Ordenado por título o tipo
- [x] Búsqueda avanzada por ID, título o tipo
- [x] Crear recurso (POST) con validación
- [x] Editar recurso (PUT) con formulario prellenado
- [x] Eliminar recurso (DELETE) con confirmación
- [x] Botón "+" en header para crear nuevos recursos

### ✅ Interacción Estudiante
- [x] Favoritos locales persistidos por usuario
- [x] Sistema de calificación de 1–5 estrellas
- [x] Rating promedio visible para todos
- [x] Rating individual por usuario guardado en backend

### ✅ UI/UX
- [x] Tema oscuro "Dark Academic" con acentos dorados y violeta
- [x] Tarjetas con imagen, badge de tipo con color único
- [x] Indicadores visuales de carga
- [x] Alerts de confirmación y feedback
- [x] Pull to refresh en la lista
- [x] Navegación con pestañas (tabs) y stacks

---

## 🗂️ Estructura del Proyecto

```
LearnHub/
├── App.js                    # Entry point
├── src/
│   ├── theme/index.js        # Colores, estilos globales
│   ├── context/
│   │   ├── AuthContext.js    # Estado de autenticación
│   │   └── FavoritesContext.js
│   ├── services/
│   │   └── api.js            # Llamadas a MockAPI (CRUD)
│   ├── utils/
│   │   └── helpers.js        # Validación, utilidades
│   ├── navigation/index.js   # Navegación completa
│   ├── components/
│   │   └── ResourceCard.js   # Tarjeta reutilizable
│   └── screens/
│       ├── LoginScreen.js
│       ├── RegisterScreen.js
│       ├── HomeScreen.js     # Lista con búsqueda/filtros
│       ├── DetailScreen.js   # Detalle + calificación
│       ├── FormScreen.js     # Crear/Editar (Docente)
│       ├── DeleteScreen.js   # Confirmar eliminación
│       ├── FavoritesScreen.js
│       └── ProfileScreen.js
```

---

## 🎨 Diseño

- **Tema**: Dark Academic — índigo profundo, dorado y violeta
- **Paleta**: `#0D0F1A` bg, `#6C63FF` primary, `#F0B429` accent
- **Tipografía**: Serif para headings, sans-serif para body
- **Componentes**: Tarjetas con gradientes, badges, iconografía Ionicons
