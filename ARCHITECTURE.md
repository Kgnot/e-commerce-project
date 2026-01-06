# Arquitectura del Sistema: Monolito Modular (Slice Architecture)

Este documento describe la estrategia arquitectónica adoptada para el desarrollo del backend del proyecto E-Commerce.

## Enfoque General

El sistema se está construyendo bajo un enfoque de **Monolito Modular** (Modular Monolith), utilizando principios de **Slice Architecture**. El objetivo principal es mantener un alto nivel de desacoplamiento entre los dominios de negocio, permitiendo que cada módulo funcione casi como una unidad independiente dentro del mismo despliegue (JAR).

### Objetivos Clave

1.  **Separación de Responsabilidades:** Cada carpeta en el código fuente representa un Dominio de Negocio (Bounded Context) claro y encapsulado.
2.  **Facilidad de Migración a Microservicios:** La estructura está diseñada para que, en el futuro, extraer un módulo y convertirlo en un microservicio independiente sea una tarea trivial (básicamente "copiar y pegar" el código a un nuevo repositorio y desplegar).
3.  **Mantenibilidad:** Evitar el "Spaghetti Code" típico de los monolitos en capas tradicionales, donde las dependencias se cruzan desordenadamente.

## Estrategia de Autenticación y Seguridad

Un punto crítico de esta arquitectura es el manejo de la seguridad para soportar la futura transición a microservicios distribuidos:

*   **Módulo `auth` (Centralizado):** 
    *   Es el único responsable de la **Autenticación Inicial**.
    *   Recibe credenciales (usuario/password) y emite tokens (ej. JWT).
    *   Maneja el ciclo de vida de la sesión o token.

*   **Módulos de Negocio (Descentralizados):**
    *   Cada módulo (`sales`, `inventory`, etc.) es responsable de **validar** la autorización para sus propias operaciones.
    *   **No dependen directamente** de la implementación del módulo `auth` para validar cada solicitud interna.
    *   Se utilizan **Interfaces** y contratos definidos para que cada módulo verifique la identidad del solicitante. Esto significa que si mañana el módulo se extrae a un servicio externo, solo se debe cambiar la implementación de la interfaz de validación (ej. de una llamada en memoria a una verificación de firma de Token o llamada gRPC), sin cambiar la lógica de negocio interna.

## Estructura de Módulos

El sistema se divide en los siguientes dominios principales:

*   **Auth:** Puerta de entrada para seguridad.
*   **Identity:** Gestión de usuarios, perfiles y roles.
*   **Catalog:** Gestión de productos, marcas y categorías.
*   **Inventory:** Control de stock, bodegas y transferencias.
*   **Sales:** Procesamiento de pedidos y transacciones de venta.
*   **Shipping:** Logística, transportadoras y rutas.
*   **Payment:** Procesamiento de pagos y pasarelas.
*   **Customer Experience:** Fidelización, cupones y reseñas.
