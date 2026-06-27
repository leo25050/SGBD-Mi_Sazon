# Guía Rápida de Uso del Monitor SGBD

Este documento explica cómo utilizar el panel web para probar las restricciones de seguridad y el comportamiento de MongoDB ante distintos roles.

## 1. Simulación de Sesiones y Roles
En la parte superior del dashboard se encuentra el panel de "Simulación de Sesión Activa".
Utilice la lista desplegable para alternar entre el entorno de un usuario con privilegios restringidos (Empleado) y un administrador. Todas las peticiones enviadas desde el frontend utilizarán automáticamente las credenciales reales del usuario seleccionado para conectarse a MongoDB.

## 2. Prueba de Denegación (Prevención de Intrusiones)
1. Seleccione la cuenta **Empleado (Solo Lectura)** en el menú de sesión.
2. Diríjase a la sección "Gestión del Menú".
3. Intente agregar un platillo escribiendo el nombre, el precio y haciendo clic en **Ejecutar INSERT**.
4. Observe la "Terminal de Respuestas SGBD" en la parte inferior. La acción será bloqueada nativamente por MongoDB (Código de error 13), demostrando que la seguridad DML está activa.
5. Intente hacer clic en **Ejecutar DROP**. La acción también será bloqueada, protegiendo la estructura DDL de la base de datos.

## 3. Prueba de Otorgamiento y Acceso Exitoso
1. Cambie la sesión activa a la cuenta **Administrador (DML/DDL)**.
2. Repita las acciones de agregar un platillo (INSERT) o eliminar colección (DROP).
3. La "Terminal de Respuestas SGBD" mostrará un log de éxito en color verde, indicando que MongoDB ha validado correctamente el rol y ha ejecutado la operación en la base de datos.

## 4. Monitoreo del Servidor
El panel principal incluye indicadores del estado del servidor, estado del motor de base de datos, porcentaje de uso de CPU y memoria RAM. Estos datos, junto con la gráfica de comportamiento histórico, se consultan y actualizan de forma automática cada 5 segundos.
