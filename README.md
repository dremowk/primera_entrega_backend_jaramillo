Primera Entrega - API Products & Carts
👨‍💻 Autor

Gabriel Jose Jaramillo

📌 Descripción del Proyecto

Este proyecto consiste en el desarrollo de un servidor backend utilizando Node.js y Express, que permite gestionar productos y carritos de compra mediante una API REST.

La persistencia de datos se realiza mediante archivos JSON utilizando el sistema de archivos (File System).

🚀 Tecnologías Utilizadas

Node.js

Express

File System (fs)

Postman para pruebas

📁 Estructura del Proyecto
📦 primera_entrega_jaramillo
 ┣ 📂 src
 ┃ ┣ 📂 routes
 ┃ ┃ ┣ products.router.js
 ┃ ┃ ┗ carts.router.js
 ┃ ┣ 📂 managers
 ┃ ┃ ┣ ProductManager.js
 ┃ ┃ ┗ CartManager.js
 ┃ ┣ 📂 data
 ┃ ┃ ┣ products.json
 ┃ ┃ ┗ carts.json
 ┃ ┗ app.js
 ┣ package.json
 ┣ README.md

⚙ Instalación

1️⃣ Clonar el repositorio o descargar el proyecto

2️⃣ Instalar dependencias:

npm install


3️⃣ Iniciar el servidor:

npm start


El servidor se ejecutará en:

http://localhost:8080

📌 Endpoints Disponibles
🛍 Products → /api/products
🔹 GET /

Obtiene todos los productos.

🔹 GET /:pid

Obtiene un producto por ID.

🔹 POST /

Crea un nuevo producto.

Campos requeridos en el body:

{
  "title": "string",
  "description": "string",
  "code": "string",
  "price": number,
  "status": boolean,
  "stock": number,
  "category": "string",
  "thumbnails": []
}


⚠ El id se genera automáticamente.

🔹 PUT /:pid

Actualiza un producto por ID.
No permite modificar el id.

🔹 DELETE /:pid

Elimina un producto por ID.

🛒 Carts → /api/carts
🔹 POST /

Crea un nuevo carrito.

Estructura:

{
  "id": number,
  "products": []
}

🔹 GET /:cid

Obtiene los productos de un carrito específico.

🔹 POST /:cid/product/:pid

Agrega un producto al carrito.

Formato almacenado:

{
  "product": productId,
  "quantity": number
}


Si el producto ya existe en el carrito, incrementa automáticamente la cantidad.

💾 Persistencia

Los datos se almacenan en:

products.json

carts.json

Ubicados en:

src/data/

🧪 Pruebas

Las pruebas fueron realizadas utilizando Postman.

Se incluye colección exportada para facilitar la evaluación.

✅ Requisitos Cumplidos

✔ Servidor en puerto 8080
✔ Rutas separadas con Router
✔ CRUD completo de productos
✔ Creación y gestión de carritos
✔ Persistencia en archivos JSON
✔ IDs autogenerados
✔ Incremento de quantity en carrito
✔ Sin implementación visual (API REST)
