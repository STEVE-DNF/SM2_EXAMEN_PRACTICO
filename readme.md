## Estructura del Proyecto

```
SM2_EXAMEN_PRACTICO/
├── config/                 # Configuraciones de la aplicación
├── controllers/           # Controladores de la lógica de negocio
├── middleware/           # Middleware personalizado
├── models/              # Modelos de datos y esquemas
├── node_modules/        # Dependencias de Node.js
├── publics/            # Archivos públicos estáticos
├── repositories/       # Capa de acceso a datos
├── routes/            # Definición de rutas de la API
├── services/          # Servicios de la aplicación
├── utils/             # Utilidades y helpers
├── app.js             # Punto de entrada de la aplicación
├── config.env         # Variables de entorno
├── package.json       # Dependencias y scripts
├── package-lock.json  # Versiones específicas de dependencias
└── server.js          # Configuración del servidor
```

### Descripción de los Directorios

- **config/**: Contiene archivos de configuración para diferentes entornos (desarrollo, producción)
  - Configuración de base de datos
  - Configuración de Firebase
  - Otras configuraciones del sistema

- **controllers/**: Controladores que manejan la lógica de negocio
  - `messageController.js`: Manejo de mensajes temporales
  - `notificationController.js`: Gestión de notificaciones

- **middleware/**: Middleware personalizado para la aplicación
  - Autenticación
  - Validación
  - Manejo de errores

- **models/**: Definición de modelos de datos
  - Esquemas de MongoDB
  - Entidades del sistema

- **publics/**: Archivos estáticos
  - Imágenes
  - CSS
  - JavaScript del cliente

- **repositories/**: Capa de acceso a datos
  - Implementación del patrón repositorio
  - Consultas a la base de datos

- **routes/**: Definición de rutas de la API
  - `messageRoutes.js`: Rutas para mensajería
  - `notificationRoutes.js`: Rutas para notificaciones

- **services/**: Lógica de negocio y servicios
  - `firebaseService.js`: Integración con Firebase
  - `messageService.js`: Servicio de mensajería

- **utils/**: Funciones de utilidad
  - Helpers
  - Funciones comunes
  - Constantes

### Archivos Principales

- **app.js**: Configuración principal de Express
  ```javascript
  const express = require('express');
  const app = express();
  
  // Middlewares básicos
  app.use(express.json());
  app.use(express.urlencoded({ extended: true }));
  
  // Rutas
  app.use('/api/messages', require('./routes/messageRoutes'));
  app.use('/api/notifications', require('./routes/notificationRoutes'));
  
  module.exports = app;
  ```

- **server.js**: Inicialización del servidor
  ```javascript
  const app = require('./app');
  const dotenv = require('dotenv');
  
  // Configuración de variables de entorno
  dotenv.config({ path: './config.env' });
  
  const port = process.env.PORT || 3000;
  
  // Inicio del servidor
  app.listen(port, () => {
    console.log(`Servidor corriendo en puerto ${port}`);
  });
  ```

- **config.env**: Variables de entorno
  ```env
  PORT=3000
  MONGODB_URI=mongodb://localhost:27017/ccontapub
  FIREBASE_CONFIG={...}
  JWT_SECRET=your-secret-key
  ```

### Dependencias Principales del Backend

```json
{
  "dependencies": {
    "express": "^4.18.2",
    "mongoose": "^6.0.2",
    "firebase-admin": "^11.11.0",
    "dotenv": "^16.3.1",
    "jsonwebtoken": "^9.0.2",
    "cors": "^2.8.5",
    "express-validator": "^7.0.1"
  },
  "devDependencies": {
    "nodemon": "^3.0.1"
  }
}
```
