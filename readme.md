# Examen Práctico - Soluciones Móviles II

## Historias de Usuario Seleccionadas

Del Product Backlog del proyecto CcontaPub, se seleccionaron las siguientes historias:

1. **EP-05: Implementación de un sistema de mensajería temporal**
   - Como contador público usuario de CcontaPub
   - Quiero poder enviar mensajes temporales a otros contadores
   - Para realizar consultas o compartir información que no necesita ser almacenada permanentemente

2. **EP-05: Sistema de notificaciones y mensajes**
   - Como contador público usuario de CcontaPub
   - Quiero recibir notificaciones y mensajes sobre actividades relevantes
   - Para mantenerme informado sobre interacciones y actualizaciones importantes en la plataforma

## Descripción del Proyecto

CcontaPub es una aplicación móvil para contadores públicos que facilita la comunicación y actualización profesional. En esta versión se han implementado dos funcionalidades principales:

### 1. Sistema de Mensajería Temporal
Permite a los usuarios enviar mensajes que se eliminan automáticamente después de un tiempo específico. Funcionalidades:
- Envío de mensajes con tiempo de expiración configurable
- Lista de mensajes con contador de tiempo restante
- Eliminación automática de mensajes expirados
- Notificaciones de mensajes próximos a expirar

![Pantalla de Mensajes](screenshots/mensajes.png)
*Interfaz de mensajería temporal mostrando la lista de mensajes y el tiempo restante*

### 2. Sistema de Notificaciones con Firebase
Implementación de notificaciones push utilizando Firebase Cloud Messaging. Funcionalidades:
- Integración con FCM para envío y recepción de notificaciones
- Notificaciones push en primer y segundo plano
- Gestión de tokens de dispositivo

![Notificaciones Push](screenshots/notificaciones.png)
*Ejemplo de notificación push recibida en el dispositivo*

## Enlaces y Referencias

### Frontend
- [React Native](https://reactnative.dev/) - Framework para desarrollo móvil
- [React Navigation](https://reactnavigation.org/) - Navegación
- [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging) - Notificaciones Push

### Backend
- [Express](https://expressjs.com/) - Framework de Node.js
- [Mongoose](https://mongoosejs.com/) - ODM para MongoDB
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) - Administración de Firebase

## Repositorio

El código fuente está disponible en: https://github.com/tu-usuario/SM2_EXAMEN_PRACTICO

## Estructura del Proyecto

```
SM2_EXAMEN_PRACTICO/
├── config/                 # Configuraciones
├── controllers/           # Controladores
├── middleware/           # Middleware
├── models/              # Modelos
├── publics/            # Archivos estáticos
├── repositories/       # Acceso a datos
├── routes/            # Rutas API
├── services/          # Servicios
├── utils/             # Utilidades
├── app.js             # Entrada principal
├── config.env         # Variables de entorno
├── package.json       # Dependencias
└── server.js          # Servidor
```

## Instalación y Uso

1. Clonar el repositorio:
```bash
git clone https://github.com/tu-usuario/SM2_EXAMEN_PRACTICO.git
```

2. Instalar dependencias:
```bash
cd SM2_EXAMEN_PRACTICO
npm install
```

3. Configurar variables de entorno:
- Crear archivo `config.env` basado en `config.env.example`
- Configurar credenciales de Firebase

4. Iniciar el servidor:
```bash
npm start
```

## Tecnologías Utilizadas

- Node.js v18.17.0
- Express v4.18.2
- MongoDB v6.0.2
- Firebase Admin SDK v11.11.0
- React Native v0.72.6
