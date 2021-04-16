---
title: Configuración de escenarios para Inteligencia IoT
description: Este tema explica cómo configurar escenarios para Inteligencia de IoT en Microsoft Dynamics 365 Supply Chain Management.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2927a976c38e9ed8166c62b030d665a159119ae1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826428"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configuración de escenarios para Inteligencia IoT

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar escenarios para Inteligencia de IoT en Microsoft Dynamics 365 Supply Chain Management. Para poder configurar los escenarios, debe [configurar Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).

En este tema, configurará el escenario **Tiempo de inactividad del equipo** para generar una notificación en Supply Chain Management cuando una máquina queda inactiva. El tema también muestra cómo configurar el escenario **Calidad del producto** para que se genere una notificación si un atributo de un elemento está fuera de un rango especificado, y cómo configurar el escenario **Retrasos en la producción** para que se genere una notificación si el rendimiento de producción cae por debajo de un valor umbral.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configure el escenario Tiempo de inactividad del equipo en Supply Chain Management

El escenario **Tiempo de inactividad** del equipo asigna una señal de inactividad **PartOut** a un umbral de alerta de máquina. La máquina se supervisa solo cuando se selecciona para el escenario y cuando se configura para **ejecutarse** en Supply Chain Management. Si el tiempo transcurrido desde la última señal de inactividad **PartOut** de la máquina es mayor que el umbral de alerta, entonces se activa una notificación **Máquina inactiva**. Si la máquina todavía está funcionando, cuando se recibe la próxima señal **PartOut**, se activa una notificación **Máquina reactivada**. Si una máquina permanece inactiva durante 30 minutos, se activa una nueva notificación **Máquina inactiva**.

El escenario **Tiempo de inactividad del equipo** tiene las siguientes dependencias:

+ Una orden de producción solo se puede desencadenar si una orden de producción se está ejecutando en una máquina asignada.
+ Una señal que representa la señal de inactividad **PartOut** de una máquina asignada debe enviarse al IoT Hub y se deberá incluir un nombre de propiedad único.
+ Una propiedad de **marca de tiempo** UNIX, donde el valor se expresa en milisegundos (ms), debe estar presente en el mensaje de Azure IoT Hub.

Para configurar el escenario, siga estos pasos.

1. Inicie sesión en de Supply Chain Management.
2. Habilite el indicador de función de Inteligencia IoT. Para más información, consulte [Resumen de administración de funciones](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
3. Configurar las métricas. Para obtener más información consulte [Cómo configurar las métricas](iot-metrics-setup.md#configure-metrics).
4. Vaya a **Control de producción \> Configurar \> Inteligencia de IoT \> Administración de escenarios**.
6. En el icono **Tiempo de inactividad del equipo**, seleccione **Configurar** para abrir el asistente de configuración.

   La primera página del asistente es la página **Definición del esquema del sensor del equipo**. En esta página, su objetivo es configurar el esquema en Supply Chain Management para que coincida con el formato de notación de objetos JavaScript (JSON) de los mensajes de IoT Hub. Se pueden definir múltiples esquemas de mensajes. Para obtener más información, consulte [Formatos de esquema de mensajes para IoT Hub](iot-schema-format.md). En este ejemplo, la carga útil del mensaje contiene un lote de mensajes con el siguiente formato:

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

7. Agregue una fila a la tabla de trabajo y establezca los siguientes valores:

    1. Seleccione el campo **Nombre de esquema** en **Id.**.
    2. Seleccione el campo **Ruta de acceso de esquema** en **/payload\[\*\]/id**.
    3. Seleccione el campo **Descripción** en **Id. del mensaje**.

8. Agregue otra fila a la tabla de trabajo y establezca los siguientes valores:

    1. Seleccione el campo **Nombre de esquema** en **Marca de tiempo**.
    2. Seleccione el campo **Ruta de acceso de esquema** en **/payload\[\*\]/timestamp**.
    3. Seleccione el campo **Descripción** en **Marca de tiempo del mensaje**.

9. Agregue otra fila a la tabla de trabajo y establezca los siguientes valores:

    1. Seleccione el campo **Nombre de esquema** en **Valor**.
    2. Seleccione el campo **Ruta de acceso de esquema** en **/payload\[\*\]/value**.
    3. Seleccione el campo **Descripción** en **Valor del mensaje**.

    > [!NOTE]
    > No tiene que definir todas las propiedades en el mensaje. Defina solo las propiedades que necesite. En los pasos anteriores, no creó una fila para **Marca de tiempo de raíz**. La ruta de acceso de **Marca de tiempo de raíz** sería **/timestamp**.

10. Seleccione **Siguiente** para ir a la página **Mapa del esquema del sensor del equipo**.
11. En la fila de **Id. de recurso de equipo**, en el campo **Nombre del esquema** seleccione **Id.**.
12. En la fila de **Hora UTC**, en el campo **Nombre del esquema**, seleccione **Marca de tiempo**.
13. En la fila de **Señal producida parcialmente**, en el campo **Nombre del esquema**, seleccione **Valor**.
14. Seleccione **Siguiente** para ir a la página **Configuración de id. de recurso de equipo**.
15. Siga estos pasos para asignar los valores en el mensaje de IoT Hub para los recursos de Supply Chain Management:

    1. En la tabla **Valores de datos de señal**, agregue una nueva fila. En el campo **Valor**, especifique **IoTInt.Machine1225.PartOut**. Este valor proviene de la propiedad **Id.** de JSON en el mensaje de IoT Hub.
    2. Seleccione **Guardar**.
    3. En la tabla **Asignación de registros comerciales**, seleccione **Nuevo**. Un valor predeterminado para **Tipo de registro comercial** está autorellenado y no es necesario cambiarlo.
    4. En el campo **Registro empresarial**, seleccione el recurso de máquina de Supply Chain Management desde el que se envía este valor de señal.
    5. Seleccione **Guardar**.
    6. Repita estos pasos para agregar una nueva asignación de registros comerciales para **Máquina1226**. Puede asignar múltiples valores de datos de señal a un solo registro en Supply Chain Management.

16. Utilice la columna **Seleccionado** para seleccionar qué máquinas desea procesar. No tiene que definir todos los valores de señal y no tiene que seleccionar todas las máquinas.
17. Seleccione **Siguiente** para ir a la página **Configuración de señal producida parcialmente**.
18. En la tabla **Valores de datos de señal**, agregue una fila y establezca el campo **Valor** en **Verdadero**. Este valor proviene de la propiedad **valor** de JSON en el mensaje de IoT Hub. Puede agregar tantos valores como necesite para su escenario.
19. Seleccione **Guardar**.
20. Seleccione **Siguiente** para ir a la página **Umbral de inactividad del equipo**. Las máquinas enumeradas son las máquinas asignadas previamente a valores de señal. En esta página, definirá un umbral para determinar si una máquina está inactiva. Por ejemplo, si establece el umbral en **10**, Supply Chain Management generará una notificación si no se recibe un mensaje de señal **PartOut** de una máquina durante 10 minutos.
21. Seleccione **Siguiente** para pasar a la página **Activar escenario**. Establezca la opción para habilitar el escenario.
22. Seleccione **Fin**.

La configuración del escenario está ahora completada. Inteligencia IoT comenzará a procesar automáticamente los mensajes de IoT Hub.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurar el escenario Calidad de producto en Supply Chain Management

El escenario **Calidad de producto** genera una notificación si un atributo de un artículo está fuera de un rango especificado. Por ejemplo, un sensor envía el peso de cada elemento a IoT Hub. Si un elemento es muy pesado o muy ligero, se generará una notificación en Supply Chain Management.

El escenario **Calidad del producto** tiene las siguientes dependencias:

+ Se puede desencadenar una alerta solo si se está ejecutando una orden producción en una máquina asignada y producir un producto con un atributo de lote asignado.
+ Una señal que representa el atributo de lote debe enviarse al IoT Hub y se debe incluir un nombre de propiedad único.
+ Una propiedad de **marca de tiempo** UNIX, donde el valor se expresa en milisegundos (ms), debe estar presente en el mensaje de IoT Hub.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurar el escenario Retrasos de producción en Supply Chain Management

El escenario **Retrasos de producción** genera una notificación si el rendimiento de producción cae por debajo de un valor umbral. En este escenario, se envía una señal **PartOut** a IoT Hub para cada artículo producido. En Supply Chain Management, el retraso de la orden se calcula en función de la cantidad de tiempo en que la orden de producción está programada para ejecutarse, la cantidad de artículos que se deben producir, la cantidad de tiempo que el trabajo ha estado ejecutándose y la cantidad de señales **PartOut** que se reciben. Se genera una notificación de retraso si el número de señales **PartOut** para el trabajo caen por debajo del valor umbral del valor esperado.

El escenario **Retrasos de producción** tiene las siguientes dependencias:

+ Una orden de producción solo se puede desencadenar si una orden de producción se está ejecutando en una máquina asignada.
+ Una señal que representa la señal de inactividad **PartOut** de una máquina asignada debe enviarse al Azure IoT Hub y se deberá incluir un nombre de propiedad único.
+ Una propiedad de **marca de tiempo** UNIX, donde el valor se expresa en milisegundos (ms), debe estar presente en el mensaje de IoT Hub.

## <a name="disable-a-scenario"></a>Deshabilitar un escenario

Para desactivar un escenario, siga estos pasos.

1. En Supply Chain Management, vaya a **Control de producción \> Configurar \> Inteligencia IoT \> Gestión de escenarios**.
2. En el icono del escenario, seleccione **Configurar**.
3. Seleccione **Siguiente** para pasar a la última página del asistente.
4. Establezca la opción para deshabilitar el escenario.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]