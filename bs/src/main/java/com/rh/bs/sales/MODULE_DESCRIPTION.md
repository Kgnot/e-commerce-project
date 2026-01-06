# Módulo de Ventas (Sales)

## Descripción
Este es el corazón transaccional del e-commerce. Orquesta el ciclo de vida de un pedido desde que el cliente confirma su intención de compra hasta que se completa la transacción comercial.

## Responsabilidades
*   **Gestión de Pedidos:** Creación y seguimiento de órdenes de venta (`SALE_ORDER`).
*   **Detalle de Órdenes:** Gestión de las líneas del pedido, preservando los precios pactados en el momento de la compra (`SALE_ORDER_DETAILS`).
*   **Ciclo de Vida del Pedido:** Máquina de estados para controlar la evolución del pedido (Creado, Pagado, Confirmado, Cancelado).
*   **Cálculos Moneratios:** Totalización de montos, impuestos y aplicación final de descuentos (coordinado con otros módulos).
*   **Histórico de Direcciones:** Persistencia de la dirección de envío válida para el momento de la orden.

## Datos Clave
*   Órdenes de Venta.
*   Detalles de productos en la orden.
*   Historial de estados de la orden.
*   Montos finales.
