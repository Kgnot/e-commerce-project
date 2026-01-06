# Módulo de Pagos (Payment)

## Descripción
Este módulo encapsula todas las interacciones financieras. Su objetivo es asegurar que se recaude el dinero de las órdenes de venta.

## Responsabilidades
*   **Procesamiento de Pagos:** Registrar los intentos y confirmaciones de pago asociados a una orden.
*   **Integración con Pasarelas:** (Futuro) Adaptadores para comunicarse con proveedores externos (PayU, Wompi, Stripe, etc.). de forma agnóstica al resto del sistema.
*   **Métodos de Pago:** Gestión de los tipos de pago aceptados (`PAYMENT_TYPE`).
*   **Auditoría Financiera:** Registro de IDs de transacción externos y códigos de respuesta para conciliación.

## Datos Clave
*   Órdenes de Pago.
*   Tipos de Pago.
*   Transacciones (Logs de pasarela).
