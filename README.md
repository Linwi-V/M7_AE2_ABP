# Módulo 7 Actividad AE2 Individual – Django con MySQL

Proyecto desarrollado como parte del Módulo 7 del Bootcamp de Desarrollo Full Stack Python. Consiste en la creación de un proyecto Django conectado a una base de datos MySQL, incluyendo la implementación del modelo `Producto` y operaciones CRUD utilizando el ORM de Django.

## Descripción del Proyecto

El proyecto tiene como objetivo configurar Django para conectarse a MySQL, crear un modelo de productos y comprobar el funcionamiento de operaciones CRUD desde el Django Shell.
Incluye migraciones, creación de tablas y manipulación de datos mediante el ORM.

## Funcionalidades Implementadas

### Configuración Django – MySQL

- Conexión mediante `mysqlclient`
- Base de datos utilizada: `mi_proyecto_db`
- Usuario y contraseña configurados: `root`

### Gestión de Productos

- Modelo `Producto` con:
  - nombre (único)
  - descripcion
  - precio
  - stock
  - fecha_creacion (automática)
- Migraciones aplicadas correctamente
- CRUD completo desde el Shell:
  - Crear
  - Leer
  - Actualizar
  - Eliminar

## Tecnologías Utilizadas

- Python 3.12
- Django
- MySQL
- mysqlclient
- Git / GitHub

## Requisitos Previos

- Python 3.8 o superior
- MySQL instalado
- pip
- Git

## Instalación y Configuración

### 1. Clonar el repositorio

```bash

git clone https://github.com/Linwi-V/M7_AE2_ABP.git
cd M7_AE2_ABP

##2. Crear y activar entorno virtual

python -m venv venv
venv\Scripts\activate

##3. Instalar dependencias

pip install django mysqlclient

##4. Crear base de datos en MySQL

CREATE DATABASE mi_proyecto_db CHARACTER SET utf8mb4;

##5. Configurar settings.py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'mi_proyecto_db',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': 'localhost',
        'PORT': '3306',
        'OPTIONS': {'charset': 'utf8mb4'}
    }
}

##6. Aplicar migraciones

python manage.py makemigrations
python manage.py migrate

##Operaciones CRUD (Django Shell)

##Abrir Shell:

python manage.py shell

##Crear:

from productos.models import Producto

p = Producto(
    nombre="Laptop Gamer",
    descripcion="Laptop con GPU RTX",
    precio=1500.00,
    stock=10
)
p.save()

##Leer:

producto = Producto.objects.get(nombre="Laptop Gamer")
print(producto.nombre, producto.precio, producto.stock, producto.fecha_creacion)

##Actualizar:

producto.precio = 1700.00
producto.save()

##Eliminar:

producto.delete()


```

## Evidencia del Trabajo Realizado

A continuación se incluyen las capturas exigidas en la actividad, demostrando:

* Migraciones realizadas correctamente
* Conexión con la base de datos MySQL
* Ejecución completa de operaciones CRUD en el Django Shell

### 1. Migraciones aplicadas
<img width="1920" height="1080" alt="Captura de pantalla 2025-11-25 182621" src="https://github.com/user-attachments/assets/c3196845-f0dc-467e-ab51-6d85f0d5eb73" />

### 2. Conexión a MySQL y estructura de tablas
<img width="1920" height="1080" alt="Captura de pantalla 2025-11-25 182643" src="https://github.com/user-attachments/assets/65add5ea-4488-4e63-93d3-6daa3e1f201b" />

### 3. CRUD ejecutado en Django Shell
<img width="1920" height="1080" alt="Captura de pantalla 2025-11-25 182654" src="https://github.com/user-attachments/assets/fb2c603a-949d-446b-b3b2-2d4fb3c0907c" />

## Estructura del Proyecto

M7_AE2_ABP/
├── manage.py
├── README.md
├── mi_proyecto/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── productos/
    ├── migrations/
    ├── models.py
    ├── apps.py
    

## Autor

**Linwi Vargas** - Productor de Videojuegos en formación

* GitHub: [@Linwi-V](https://github.com/Linwi-V)
* LinkedIn: [Linwi Vargas Campos](https://www.linkedin.com/in/linwi-vargas-campos/)
* Itch.io: [linwi.itch.io](https://linwi.itch.io/)

Proyecto desarrollado como parte del Bootcamp de Desarrollo Full Stack Python -  Actividad AE2 del Módulo 7
