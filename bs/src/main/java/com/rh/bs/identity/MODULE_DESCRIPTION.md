# Módulo de Identidad (Identity)

## Descripción
Este módulo gestiona la **información de las personas** y entidades que interactúan con el sistema. A diferencia de `Auth` (que solo verifica credenciales), `Identity` conoce quién es el usuario, dónde vive y qué rol desempeña en la organización.

## Responsabilidades
*   **Gestión de Usuarios:** CRUD de usuarios del sistema (`APP_USER`).
*   **Perfiles:** Gestión de datos demográficos y personales (`APP_PROFILE`).
*   **Roles y Permisos:** Definición de qué puede hacer cada usuario (`ROL`, `USER_ROL`).
*   **Clientes y Empleados:** Diferenciación y gestión de datos específicos para clientes externos (`CUSTOMER`) y staff interno (`EMPLOYEE`).
*   **Direcciones:** Gestión centralizada de direcciones físicas para usuarios (`ADDRESS_NODE`).

## Datos Clave
*   Usuarios y Credenciales (hash).
*   Perfiles Expandidos.
*   Roles.
*   Direcciones.
