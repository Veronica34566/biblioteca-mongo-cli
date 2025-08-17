📚 Biblioteca CLI (MongoDB + PyMongo)

Aplicación de línea de comandos para gestionar una biblioteca personal, almacenando cada libro como un documento JSON dentro de una colección en MongoDB.

🚀 Características principales

➕ Agregar libros con título, autor, género y estado de lectura (pendiente, leyendo, terminado).

✏️ Actualizar información de cualquier campo de un libro.

🗑️ Eliminar libros por su ID.

📋 Listar todos los libros guardados.

🔎 Buscar libros por título, autor o género (con coincidencia parcial).

🚪 Salir de la aplicación.

🛠️ Tecnologías utilizadas

Python 3.9+

MongoDB (local o Atlas en la nube)

PyMongo

📦 Instalación y configuración

1. Clonar el repositorio

git clone https://github.com/USUARIO/biblioteca-mongo-cli.git
cd biblioteca-mongo-cli

2. Crear un entorno virtual e instalar dependencias

python -m venv .venv
# Activar entorno
# Windows
.venv\\Scripts\\activate
# Linux/Mac
source .venv/bin/activate

pip install -r requirements.txt

3. Configurar variables de entorno

Copia el archivo de ejemplo y modifica la URI según tu caso:

cp .env.example .env

🗄️ Opciones de configuración de MongoDB

🔹 Opción A: Local

Instala MongoDB Community Server.

Inicia el servicio (mongod).

URI por defecto: mongodb://localhost:27017

🔹 Opción B: Atlas (nube)

Crea cuenta en MongoDB Atlas.

Configura clúster, usuario y red.

Obtén la connection string:

mongodb+srv://usuario:clave@cluster.mongodb.net/?retryWrites=true&w=majority

Guárdala en tu archivo .env como MONGODB_URI.

▶️ Uso de la aplicación

Ejecuta:

python app.py

Menú principal

=== Biblioteca (MongoDB) ===
1) Agregar nuevo libro
2) Actualizar información de un libro
3) Eliminar libro existente
4) Ver listado de libros
5) Buscar libros
6) Salir

📂 Estructura del proyecto

.
├── app.py
├── README.md
├── requirements.txt
├── .env.example
    └── libro_ejemplo.json

📘 Ejemplo de documento en MongoDB

{
  "_id": ObjectId("..."),
  "titulo": "El nombre del viento",
  "autor": "Patrick Rothfuss",
  "genero": "Fantasía",
  "estado": "pendiente",
  "creado_en": "2025-08-17T16:25:30.123456",
  "actualizado_en": "2025-08-17T16:25:30.123456"
}

🔍 Búsquedas

Filtrado por título, autor o género.

Coincidencias parciales (regex, insensible a mayúsculas/minúsculas).

Mensaje amigable si no hay resultados.


.venv/
.env
*.env
__pycache__/
*.pyc
.vscode/
.idea/
.DS_Store
Thumbs.db
*.log

📝 Notas

No subas tu .env al repositorio.

Si usas Atlas, limita los accesos de red.

Para inspeccionar datos en MongoDB:

show dbs
use biblioteca_cli
show collections
db.libros.find().pretty()

📄 Licencia

MIT
