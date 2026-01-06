# Módulo de Inventario (Inventory)

## Descripción
Este módulo es responsable de gestionar el mundo físico: dónde están los productos y cuántos hay. Es crítico para asegurar que no se venda lo que no se tiene.

## Responsabilidades
*   **Gestión de Bodegas:** Administración de los puntos de almacenamiento (`WAREHOUSE`) y su ubicación.
*   **Control de Stock:** Tracking en tiempo real de la cantidad de productos por bodega (`INVENTORY_STOCK`).
*   **Alertas de Stock:** Monitoreo de niveles mínimos y máximos para reabastecimiento.
*   **Transferencias:** Gestión logística interna para mover mercancía entre bodegas (`WAREHOUSE_TRANSFER`).
*   **Reservas:** (Lógica futura) Capacidad de reservar stock temporalmente durante el proceso de checkout.

## Datos Clave
*   Bodegas (Warehouses).
*   Inventarios locales.
*   Niveles de stock.
*   Movimientos de transferencia.
