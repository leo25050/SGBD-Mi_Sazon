# SGBD-Mi_Sazon
Entrega: Monitor SGBD Mi Sazon con RBAC

# Monitor de Seguridad SGBD - Mi Sazón

Este proyecto es un panel de control web desarrollado para monitorear el estado de un contenedor de MongoDB y probar la seguridad a nivel de datos (DML) y objetos (DDL) mediante el uso de Control de Acceso Basado en Roles (RBAC).

## Arquitectura
- **Frontend:** HTML5, CSS3, JavaScript (Vanilla).
- **Backend:** Python (Flask, PyMongo).
- **Base de Datos:** MongoDB (Docker).

## Requisitos Previos
- Docker instalado y ejecutándose.
- Python 3.8 o superior.
- Navegador Web.

## 1. Configuración de la Base de Datos
Levantar un contenedor de MongoDB en el puerto `27017`.
Se deben crear la base de datos `mi_sazon_db` y configurar dos usuarios nativos:
- `empleadoLectura` (con rol `read`)
- `adminSazon` (con rol `dbOwner` o permisos DML/DDL completos)

## 2. Instalación y Ejecución del Backend
Abrir una terminal en la carpeta `Back`.
Instalar las librerías necesarias:

bash
pip install flask flask-cors pymongo psutil

Ejecutar el servidor de la API:

python api_main.py
El backend se ejecutará en http://127.0.0.1:5001.

3. Ejecución del Frontend
Abrir una terminal independiente en la carpeta Front.
Levantar un servidor local:

python -m http.server 3000
Abrir el navegador y acceder a http://localhost:3000
