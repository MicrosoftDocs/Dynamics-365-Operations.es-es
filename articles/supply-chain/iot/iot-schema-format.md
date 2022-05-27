---
title: Formatos de esquema para mensajes del centro de IoT
description: Este tema explica cómo debe diseñar un esquema de mensajes que pueda usar en Inteligencia de IoT.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60d5bc4eacdd7e7d713490998bd1d20c9271ad02
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673953"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Formatos de esquema para mensajes del centro de IoT

[!include [banner](../../includes/banner.md)]

Este tema explica cómo debe diseñar un esquema de mensajes que pueda usar en Inteligencia de IoT.

## <a name="message-requirements"></a>Requisitos para mensajes

Las siguientes reglas se aplican al monitoreo de mensajes en Inteligencia de IoT:

+ Los esquemas de mensajes deben estar en formato de notación de objetos JavaScript (JSON).
+ Una propiedad de **marca de tiempo** UNIX, donde el valor se expresa en milisegundos (ms), debe estar presente en el mensaje del centro de IoT de Microsoft Azure.
+ Se realiza un seguimiento de un mensaje solo si contiene todas las propiedades definidas en la configuración del escenario. Por ejemplo, si define las propiedades **id.**, **marca de tiempo** y **valor**, se monitorea el siguiente mensaje.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Este mensaje no se supervisa porque falta la propiedad **valor**.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ Inteligencia de IoT ignora las propiedades del mensaje que no están definidas en la configuración del escenario. Por ejemplo, si define las propiedades **id.**, **marca de tiempo** y **valor**, Inteligencia de IoT supervisará todos los siguientes mensajes.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ Inteligencia de IoT ignora silenciosamente los mensajes que no coinciden con los criterios de configuración del escenario.
+ Puede definir y utilizar varios tipos de esquemas de mensajes.
+ No se deben definir todos los tipos de esquemas de mensajes. Solo se deben definir los esquemas que se utilizarán para los escenarios de Inteligencia de IoT.

## <a name="id-value-pair-schema"></a>Esquema de par id-valor

Un par id-valor es un patrón común para los esquemas de mensajes de Inteligencia de IoT. Al utilizar un par id-valor, se asegura de que el esquema de su mensaje sea el mismo en todos los escenarios. Por ejemplo, aquí hay un mensaje para el escenario **Tiempo de inactividad del equipo** o **Retrasos en la producción**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Aquí hay un mensaje para el escenario **Calidad del producto**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

Ambos mensajes anteriores contienen las propiedades **id.** y **valor**. Los valores de **id.** se pueden mapear en la tabla **Valores de datos de señal** durante la configuración del escenario. Para el escenario **Tiempo de inactividad del equipo**, mapeará el valor **IoTInt.Machine1225.PartOut**. Para el escenario **Calidad de producto**, mapeará el valor **IoTInt.Machine1225.Temperature**.

Para obtener más información, consulte la [Documentación del centro de IoT de Azure](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]