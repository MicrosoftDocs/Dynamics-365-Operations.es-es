---
title: Configuración de escenarios para Inteligencia IoT
description: Este tema describe cómo configurar un escenario en Supply Chain Management para Inteligencia IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597177"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configuración de escenarios para Inteligencia IoT

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar un escenario en Supply Chain Management para Inteligencia IoT. Para poder configurar los escenarios, debe [configurar LCS](iot-lcs-setup.md).

En este tema, configurará el escenario **Tiempo de inactividad del equipo** para generar una notificación en Supply Chain Management cuando una máquina queda inactiva.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configure el escenario **Tiempo de inactividad del equipo** en Supply Chain Management

El escenario **Tiempo de inactividad del equipo** asigna una señal de inactividad parcial a un umbral de alerta de máquina. La máquina se supervisa solo cuando la máquina se selecciona para el escenario y se configura para ejecutarse en Supply Chain Management. Si el tiempo transcurrido desde la última señal de inactividad parcial de la máquina es mayor que el umbral de alerta, entonces se activa una notificación **Máquina inactiva**. Si la máquina todavía está funcionando, cuando se recibe la próxima señal **PartOut**, se activa una notificación **Máquina reactivada**. Si una máquina permanece inactiva durante 30 minutos, ae activa una nueva notificación **Máquina inactiva**.

El escenario **Tiempo de inactividad del equipo** tiene estas dependencias:

+ Una orden de producción debe estar ejecutándose en una máquina asignada para que se active una alerta.
+ Una señal que representa la señal de inactividad parcial de una máquina asignada debe enviarse al IoT Hub con un nombre de propiedad único.
+ Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje del centro de IoT.

Para configurar el escenario, siga estos pasos:

1. Inicie sesión en Supply Chain Management.
2. Habilite el indicador de función de Inteligencia IoT. Para más información, consulte [Resumen de administración de funciones](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Configurar las métricas. Para obtener más información consulte [Cómo configurar las métricas](iot-metrics-setup.md#configure-metrics).
4. Navegue a **Control de producción**.
5. Navegue a **Configurar \> Inteligencia IoT \> Gestión de escenarios**.
6. Haga clic en **Configurar**, en el icono **Tiempo de inactividad del equipo**. El asistente de configuración comienza con la página **Definición del esquema del sensor del equipo**. El objetivo aquí es configurar el esquema en Supply Chain Management para que coincida con el formato JSON de los mensajes de IoT. Se pueden definir múltiples esquemas de mensajes. Para obtener más información, consulte [Formatos de esquema de mensaje para IoT Hub](iot-schema-format.md). En este ejemplo, la carga útil del mensaje contiene un lote de mensajes con este formato:

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Agregue una fila a la tabla.

    1. Seleccione el **Nombre de esquema** en **Id.**.
    2. Seleccione la **Ruta de esquema** en **/payload[\*]/id**.
    3. Seleccione la **Descripción** en **Id. del mensaje**.

8. Agregue una fila a la tabla.

    1. Seleccione el **Nombre de esquema** en **Marca de tiempo**.
    2. Seleccione la **Ruta de esquema** en **/payload[\*]/timestamp**.
    3. Seleccione la **Descripción** en **Marca de tiempo del mensaje**.

9. Agregue una fila a la tabla.

    1. Seleccione el **Nombre de esquema** en **Valor**.
    2. Seleccione la **Ruta de esquema** en **/payload[\*]/value**.
    3. Seleccione la **Descripción** en **Valor del mensaje**.

    No necesita definir todas las propiedades del mensaje, solo las que necesita. En este ejemplo, no creó una fila para **Marca de tiempo de raíz**. La ruta para **Marca de tiempo de raíz** sería **/timestamp**.
  
10. Haga clic en **Siguiente** para ir a la página **Mapa del esquema del sensor del equipo**.
11. En la fila de **Id. de recurso de equipo**, seleccione **Nombre del esquema** en **Id.**. Los valores válidos se muestran en una tabla desplegable.
12. En la fila de **Hora UTC**, seleccione el **Nombre del esquema** en **Marca de tiempo**. Los valores válidos se muestran en una tabla desplegable.
13. En la fila de **Señal producida parcialmente**, seleccione **Nombre del esquema** en **Valor**. Los valores válidos se muestran en una tabla desplegable.
14. Haga clic en **Siguiente** para la página **Configuración de id. de recurso de equipo**.
15. En este paso, asigna los valores del mensaje de IoT Hub a los recursos de Supply Chain Management.

    1. En la tabla **Valores de datos de señal**, agregue una nueva fila e introduzca **IoTInt.Machine1225.PartOut** en la columna **Valor**. El valor de **IoTInt.Machine1225.PartOut** proviene de la propiedad **id** de JSON en el mensaje del centro de IoT.
    2. Haga clic en **Guardar**.
    3. En la tabla **Asignación de registros comerciales**, haga clic en **Nuevo**. El valor predeterminado para **Tipo de registro comercial** está autorellenado y no es necesario cambiarlo.
    4. En la columna **Registro empresarial**, seleccione el recurso de máquina Administración de cadena suplementaria desde el que se envía este valor de señal.
    5. Haga clic en **Guardar**.
    6. Repita estos pasos, agregando una nueva asignación de registros comerciales para **Máquina1226**. Puede asignar múltiples valores de datos de señal a un solo registro en Supply Chain Management.

16. Utilice la columna **Seleccionado** para elegir qué máquinas desea procesar. No tiene que definir todos los valores de señal y no tiene que seleccionar todas las máquinas.
17. Haga clic en **Siguiente** para ir a la página **Configuración de señal producida parcialmente**.
18. En la tabla **Valores de datos de señal**, agregue una fila y establezca **Valor** en **Verdadero**. El valor **Verdadero** proviene de la propiedad **valor** de JSON en el mensaje del centro de IoT. Puede agregar tantos valores como necesite para su escenario.
19. Haga clic en **Guardar**.
20. Haga clic en **Siguiente** para ir a la página **Umbral de inactividad del equipo**. Las máquinas enumeradas son las máquinas asignadas previamente a valores de señal. En este paso, definirá un umbral para determinar si una máquina está inactiva. Por ejemplo, si establece el umbral en 10, Supply Chain Management genera una notificación si no hay un mensaje de inactividad parcial de una máquina durante 10 minutos.
21. Haga clic en **Siguiente** para pasar a la página **Activar escenario**. Mueva el control deslizante para habilitar el escenario.
22. Haga clic en **Finalizar**.

La configuración del escenario está completa. Inteligencia IoT comenzará a procesar automáticamente los mensajes de IoT Hub.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurar el escenario **Calidad de producto** en Supply Chain Management

El escenario **Calidad de producto** genera una notificación si un atributo de un artículo está fuera de un rango especificado. Por ejemplo, un sensor podría enviar el peso de cada elemento a IoT Hub. En Supply Chain Management, se generaría una notificación si el artículo era demasiado pesado o demasiado ligero.

El escenario tiene estas dependencias:

+ Una orden de producción debe ejecutarse en una máquina asignada y producir un producto con un atributo de lote asignado para que se active una alerta.
+ Una señal que representa el atributo de lote debe enviarse al IoT Hub con un nombre de propiedad único.
+ Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje de IoT Hub.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurar el escenario **Retrasos de producción** en Supply Chain Management

El escenario **Retrasos de producción** genera una notificación si el rendimiento de producción cae por debajo de un valor umbral. En este escenario, se envía una señal **PartOut** a IoT Hub para cada artículo producido. En Supply Chain Management, el retraso del pedido se calcula en función de cuánto tiempo está programada la ejecución de la orden de producción, cuántos artículos se deben producir, cuánto tiempo ha estado funcionando el trabajo y cuántas señales **PartOut** se reciben. Se generaría una notificación de retraso si el número de señales **PartOut** para el trabajo caen por debajo del valor umbral del valor esperado.

El escenario tiene estas dependencias:

+ Una orden de producción debe estar ejecutándose en una máquina asignada para que se active una alerta.
+ Una señal que representa la señal de inactividad parcial de una máquina asignada debe enviarse al IoT Hub con un nombre de propiedad único.
+ Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje de IoT Hub.

## <a name="how-to-disable-a-scenario"></a>Cómo deshabilitar un escenario

Para desactivar un escenario, siga estos pasos:

1. En Supply Chain Management, navegue hasta **Control de producción \> Configurar \> Inteligencia IoT \> Gestión de escenarios**.
2. Haga clic en **Configurar** en el escenario.
3. Haga clic en **Siguiente** para llegar a la última pestaña del asistente.
4. Mueva el control deslizante para desactivar el escenario.
