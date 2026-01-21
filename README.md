# Automatización: Control de Luz por Movimiento (Zigbee)

Este archivo documenta la configuración lógica para el control automático de iluminación en Home Assistant. El sistema utiliza un sensor de movimiento para gestionar el estado de la bombilla, optimizando el consumo energético.

## Descripción del Flujo

El sistema funciona mediante dos automatizaciones complementarias:

1.  **Activación (ON):**  **Disparador:** El sensor detecta movimiento (pasa a estado `on`).
    * **Acción:** Enciende la luz inmediatamente.

2.  **Desactivación (OFF):**  **Disparador:** El sensor deja de detectar movimiento (estado `off`) y mantiene este estado durante **30 segundos**.
    * **Acción:** Apaga la luz automáticamente.

## Entidades Utilizadas

| Tipo | ID de Entidad | Descripción |
| :--- | :--- | :--- |
| **Sensor** | `binary_sensor.sensor_movimiento` | Sensor de presencia (Zigbee) |
| **Luz** | `light.bombilla` | Foco o interruptor inteligente |

## Código YAML

El codigo de la configuracion de la automatización esta en el archivo `automations.yaml`, donde se puede ver claramente cada una de las entidades utilizadas.