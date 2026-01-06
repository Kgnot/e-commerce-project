# Módulo de Logística y Envíos (Shipping)

## Descripción
Una vez que una venta se ha concretado (módulo `Sales`) y hay stock confirmado (módulo `Inventory`), este módulo se encarga de la realidad operativa de entregar el paquete al cliente.

## Responsabilidades
*   **Gestión de Envíos:** Creación de las guías de despacho (`SHIPMENT`) asociadas a las órdenes.
*   **Transportadoras:** Administración de proveedores logísticos externos (`CARRIER`) e internos.
*   **Flota Propia:** Gestión de vehículos propios (`VEHICLE`) si aplica.
*   **Rutas:** Planificación y registro de rutas de entrega (`TRANSPORT_ROUTE`).
*   **Tracking:** Actualización y consulta del estado de la entrega (En tránsito, Entregado, Fallido).

## Datos Clave
*   Envíos (Shipments).
*   Transportadoras (Carriers).
*   Vehículos.
*   Rutas y Trazabilidad.
