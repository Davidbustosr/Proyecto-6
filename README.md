
# Backend Auth Project

Este proyecto es una aplicación backend que gestiona la autenticación y autorización de usuarios, utilizando JWT (JSON Web Tokens) para la seguridad. El proyecto está estructurado con Express.js, MongoDB y Mongoose, y ofrece un sistema de registro, inicio de sesión y gestión de productos. La aplicación también incluye una API RESTful documentada con OpenAPI (Swagger).

## Tecnologías utilizadas

- **Node.js**: Framework de JavaScript para la ejecución del backend.
- **Express.js**: Framework para la construcción de la API RESTful.
- **MongoDB**: Base de datos NoSQL utilizada para almacenar los datos de los usuarios y productos.
- **Mongoose**: ODM (Object Document Mapper) para interactuar con MongoDB desde Node.js.
- **JWT (JSON Web Tokens)**: Utilizado para la autenticación y autorización de los usuarios.
- **bcryptjs**: Librería para encriptar contraseñas de manera segura.
- **CORS**: Middleware para permitir solicitudes entre diferentes dominios.
- **dotenv**: Para manejar las variables de entorno de manera segura.

## Estructura del Proyecto

La estructura del proyecto es la siguiente:

```
EJEMPLO_TU_PROYECTO
├─ .env
├─ .gitignore
├─ README.md
├─ controllers
│  ├─ userController.js
│  └─ productController.js
├─ models
│  ├─ userModel.js
│  └─ productModel.js
├─ routes
│  ├─ userRoutes.js
│  └─ productRoutes.js
└─ server.js
```

### Descripción de las carpetas y archivos:

- **`controllers/`**: Contiene los controladores para manejar la lógica de negocio. 
  - **`userController.js`**: Controlador para las operaciones de registro e inicio de sesión de usuarios.
  - **`productController.js`**: Controlador para las operaciones de CRUD sobre productos.
  
- **`models/`**: Contiene los modelos de datos de Mongoose.
  - **`userModel.js`**: Modelo de Mongoose para la colección de usuarios.
  - **`productModel.js`**: Modelo de Mongoose para la colección de productos.
  
- **`routes/`**: Define las rutas de la API.
  - **`userRoutes.js`**: Rutas para el registro y el inicio de sesión de usuarios.
  - **`productRoutes.js`**: Rutas para gestionar los productos (crear, leer, actualizar, eliminar).

- **`server.js`**: Archivo principal donde se configura y se inicia el servidor de Express.

- **`.env`**: Archivo que almacena las variables de entorno, como la URI de MongoDB y el secreto para los JWT.

## Instalación

Sigue los siguientes pasos para instalar y ejecutar el proyecto localmente:

1. Clona el repositorio:

   ```bash
   git clone <URL_DEL_REPOSITORIO>
   ```

2. Accede al directorio del proyecto:

   ```bash
   cd backend-auth-project
   ```

3. Instala las dependencias del proyecto:

   ```bash
   npm install
   ```

4. Crea un archivo `.env` en la raíz del proyecto y agrega las siguientes variables:

   ```
   MONGODB_URI=mongodb+srv://<TU_USUARIO>:<TU_CONTRASEÑA>@<cluster>.mongodb.net/<nombre_db>?retryWrites=true&w=majority
   SECRET=<TU_SECRETO_DE_JWT>
   ```

5. Inicia el servidor:

   ```bash
   npm start
   ```

   El servidor estará corriendo en el puerto `3000` (o en el puerto definido en el archivo `.env`).

## Endpoints de la API

### **Usuario**

- **Registrar un usuario**  
  `POST /api/user/register`  
  Registra un nuevo usuario proporcionando el nombre, correo electrónico y una contraseña.

- **Iniciar sesión de usuario**  
  `POST /api/user/login`  
  Inicia sesión con el correo electrónico y la contraseña del usuario, generando un token JWT para la autenticación.

- **Verificar el token del usuario**  
  `GET /api/user/verifytoken`  
  Verifica si el token del usuario es válido y si la sesión está activa.

- **Actualizar información del usuario**  
  `PUT /api/user/update`  
  Permite actualizar los datos del usuario (nombre, correo electrónico, contraseña).

### **Producto**

- **Crear un producto**  
  `POST /api/product/create`  
  Crea un nuevo producto proporcionando detalles como nombre, descripción y precio.

- **Leer todos los productos**  
  `GET /api/product/readall`  
  Obtiene todos los productos disponibles en la base de datos.

- **Leer un producto específico**  
  `GET /api/product/readone/:id`  
  Obtiene los detalles de un producto específico a través de su ID.

- **Actualizar un producto**  
  `PUT /api/product/update/:id`  
  Permite actualizar la información de un producto específico (nombre, descripción, precio).

- **Eliminar un producto**  
  `DELETE /api/product/delete/:id`  
  Elimina un producto específico de la base de datos.
