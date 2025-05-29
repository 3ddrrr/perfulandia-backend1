# Perfulandia SPA - Sistema de Ventas de Perfumes

**Perfulandia SPA** es un proyecto académico desarrollado bajo arquitectura de **microservicios**,
con el objetivo de modernizar el sistema monolítico original. Está orientado a la venta de perfumes, 
integrando múltiples módulos que trabajan de forma independiente para facilitar el mantenimiento, la escalabilidad y la implementación continua.


# Plan de Migración

El proyecto sigue una estrategia completa para la migración desde un sistema monolítico a microservicios, basada en los siguientes pasos:


# 1. Análisis del sistema actual
- Identificación de las funciones clave del sistema monolítico de Perfulandia.
- Clasificación de funcionalidades por dominio (usuarios, productos, carrito, pedidos, boletas).

# 2. División en microservicios
- Separación lógica de responsabilidades:
  - `usuarioservice`: registro y gestión de usuarios.
  - `productoservice`: gestión de perfumes.
  - `carritoservice`: operaciones del carrito de compras.
- Cada servicio cuenta con su base de datos independiente en MySQL.

# 3. Pruebas piloto
- Se desarrollan prototipos funcionales de cada microservicio.
- Se realizan pruebas de integración con Postman para validar las rutas y la conexión entre servicios.

# 4. Contenerización con Docker
- Se prepara el entorno para contenerizar cada servicio de forma independiente.
- Se trabaja en un `docker-compose.yml` para levantar todos los servicios localmente de forma orquestada.

# 5. Implementación de CI/CD
- Planificación de pipelines con GitHub Actions:
  - Compilación automática.
  - Ejecución de pruebas.
  - Despliegue en ambientes de prueba.

# 6. Migración de datos
- Las bases de datos se configuran por servicio.
- Se define una estrategia para trasladar datos desde el sistema monolítico a las nuevas estructuras normalizadas.

# 7. Pruebas de integración y carga
- Pruebas automáticas con **Postman** y **Newman**.
- Pruebas de carga y estrés con **k6**.



# Microservicios Actuales

# 1. "usuarioservice"
- Registro y gestión de usuarios.
- Endpoint base: `/api/usuarios`

# 2. "productoservice"
- Administración de perfumes: nombre, precio, descripción y stock.
- Endpoint base: `/api/productos`

# 3. "carritoservice"
- Agregado y eliminación de productos en el carrito por parte de los usuarios.
- Endpoint base: `/api/carrito`

> Cada servicio se comunica mediante APIs REST, y se conecta a su propia base de datos MySQL.



# Tecnologías Utilizadas

- Java 21
- Spring Boot 3.5.0
- Maven
- Spring Web y Spring Data JPA
- Lombok
- MySQL
- Postman & Newman
- Docker (en progreso)
- GitHub Actions (planificado)
- k6 (planificado)


# Cómo Ejecutar el Proyecto

1. Clona el repositorio:
gitbash
git clone https://github.com/3ddrrr/perfulandia.git
cd perfulandia
