# Módulo de Autenticación (Auth)

## Descripción
Este módulo actúa como la **Puerta de Enlace de Seguridad** del sistema. Su única responsabilidad es establecer la identidad de quien intenta acceder al sistema.

## Responsabilidades
*   **Login:** Validar credenciales (usuario y contraseña) contra los registros de identidad.
*   **Emisión de Tokens:** Generar tokens de acceso (JWT u otros) firmados que contengan los "claims" necesarios (Id de usuario, roles básicos).
*   **Gestión de Sesión:** (Si aplica) Manejar refresh tokens o invalidación de sesiones.

## Relación con otros Módulos
Este módulo **no** contiene la lógica de negocio de usuarios (eso es `Identity`), ni decide si un usuario puede comprar un producto (eso es `Sales` o `Inventory`). Solo dice: "Este usuario es quien dice ser".

En un futuro esquema de microservicios, este módulo sería el **Identity Provider (IdP)**.
