
#  Ecommerce — MEAN Stack

Plataforma de comercio electrónico full stack desarrollada con el stack **MEAN** (MongoDB, Express, Angular, Node.js). El proyecto cuenta con un frontend en Angular 15 y una API RESTful en Node.js con Express, autenticación JWT, manejo de archivos y envío de correos electrónicos.

---

##  Arquitectura

```

┌─────────────────────┐        HTTP/REST        ┌──────────────────────┐
│   Frontend          │ ──────────────────────► │   Backend API        │
│   Angular 15        │                         │   Node.js + Express  │
│   Puerto: 4200      │ ◄────────────────────── │   Puerto: 3000       │
└─────────────────────┘       JSON/JWT           └──────────┬───────────┘
│
▼
┌────────────────┐
│   MongoDB      │
│   Mongoose     │
└────────────────┘

```

---

##  Tecnologías

### Frontend (`/ecommerce`)
| Tecnología | Versión |
|---|---|
| Angular | 15.1.x |
| TypeScript | 4.9.x |
| RxJS | 7.8.x |
| Karma + Jasmine | Testing unitario |

### Backend (`/api_ecommerce`)
| Tecnología | Versión |
|---|---|
| Node.js + Express | 4.19.x |
| MongoDB + Mongoose | 8.3.x |
| JSON Web Token | 9.0.x |
| bcryptjs | 2.4.x |
| Nodemailer | 6.9.x |
| Babel | 7.24.x |
| Nodemon | 3.1.x |

---

##  Instalación y configuración

### Prerrequisitos
- Node.js >= 18.x
- MongoDB (local o Atlas)
- Angular CLI 15
- npm >= 9.x

### 1. Clonar el repositorio

```bash
git clone https://github.com/alexgmdev/ecommerce-Solitek/tree/main
cd ecommerce-mean
```


### 2. Configurar el Backend

```bash
cd api_ecommerce
npm install
```

Crea un archivo `.env` en la raíz del backend:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/ecommerce
JWT_SECRET=tu_secreto_jwt
EMAIL_HOST=smtp.tuproveedor.com
EMAIL_PORT=587
EMAIL_USER=tu_correo@ejemplo.com
EMAIL_PASS=tu_contraseña
```

Inicia el servidor:

```bash
npm start
```

El servidor estará disponible en `http://localhost:3000`.

### 3. Configurar el Frontend

```bash
cd ecommerce
npm install
ng serve
```

La aplicación estará disponible en `http://localhost:4200`.

---

##  Scripts disponibles

### Backend

| Comando | Descripción |
| :-- | :-- |
| `npm start` | Inicia el servidor con Nodemon y Babel |
| `npm run build` | Compila el proyecto con Babel a `/dist` |

### Frontend

| Comando | Descripción |
| :-- | :-- |
| `ng serve` | Servidor de desarrollo en `localhost:4200` |
| `ng build` | Build de producción en `/dist` |
| `ng test` | Ejecuta tests unitarios con Karma |
| `ng build --watch` | Build en modo watch (desarrollo) |
| `ng generate component nombre` | Genera un nuevo componente |


---
##  Autenticación

La API implementa autenticación con **JSON Web Tokens (JWT)** y cifrado de contraseñas con **bcryptjs**. El flujo es:

1. El usuario se registra → contraseña hasheada con `bcryptjs`.
2. El usuario hace login → se genera un token JWT.
3. Las rutas protegidas validan el token en cada request mediante middleware.

---

##  Funcionalidades principales

- ✅ Registro e inicio de sesión de usuarios (JWT + bcrypt)
- ✅ Gestión de productos (CRUD)
- ✅ Carga de imágenes de productos (`connect-multiparty`)
- ✅ Envío de correos electrónicos (`nodemailer`)
- ✅ Rutas protegidas con guards en Angular
- ✅ Comunicación frontend-backend vía API REST

---

##  Pruebas

```bash
# Frontend - Tests unitarios
cd ecommerce
ng test
```

Las pruebas del frontend utilizan **Karma** como test runner y **Jasmine** como framework de testing.

---

##  Estructura del proyecto

```
ecommerce-mean/
├── api_ecommerce/          # Backend Node.js
│   ├── index.js            # Punto de entrada
│   ├── routes/             # Rutas de la API
│   ├── controllers/        # Lógica de negocio
│   ├── models/             # Modelos Mongoose
│   ├── middlewares/        # Auth JWT y otros
│   └── .env                # Variables de entorno (no versionar)
│
└── ecommerce/              # Frontend Angular
    ├── src/
    │   ├── app/
    │   │   ├── components/ # Componentes UI
    │   │   ├── services/   # Servicios HTTP
    │   │   ├── guards/     # Route guards
    │   │   └── models/     # Interfaces TypeScript
    │   └── environments/   # Config por entorno
    └── angular.json
```


---

##  Desarrollador

| Nombre | Rol |
| :-- | :-- |
| Alexander Garzon Mariaca | Full Stack Developer |


---

## Licencia

Este proyecto es de uso académico/privado — ISC.

```

***


