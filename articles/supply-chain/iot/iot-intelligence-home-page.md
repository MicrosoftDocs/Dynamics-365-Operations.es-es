---
title: Página principal de Inteligencia de IoT
description: Este artículo proporciona vínculos a información sobre Inteligencia de IoT.
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d8b2be25abaeff7404d7f4ef3cd825a50147fef
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228369"
---
# <a name="iot-intelligence-home-page"></a>Página principal de Inteligencia de IoT

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

> [!IMPORTANT]
> Esta característica actualmente solo está disponible en los siguientes países o regiones:
>
> - EE. UU. (Estados Unidos de América)
> - UE (Unión Europea)
> - AU (Australia)
> - CA (Canadá)
> - UK (Reino Unido)

Inteligencia de IoT es un complemento para Microsoft Dynamics 365 Supply Chain Management. Integra señales de Internet de las cosas (IoT) con datos en Supply Chain Management para producir información procesable.

Inteligencia de IoT admite los siguientes escenarios:

- **Retrasos en la producción** - Este escenario compara el tiempo de ciclo real con el tiempo de ciclo planificado. Supply Chain Management le notifica cuando la producción no está según lo programado, para que pueda intervenir para maximizar la eficiencia operativa y evitar retrasos en los pedidos.
- **Tiempo de inactividad del equipo** - Este escenario compara el tiempo de actividad medido con los parámetros definidos por el usuario. Supply Chain Management le notifica cuando se excede un umbral de interrupción, para que pueda tomar acciones como reprogramar una orden de trabajo de producción o crear una orden de trabajo de mantenimiento.
- **Calidad del producto** - Este escenario compara las lecturas de los sensores, como la humedad y la temperatura, con las métricas de calidad definidas por el usuario. Supply Chain Management le notifica cuando ocurre una desviación, para que pueda intervenir para mantener los estándares de calidad y minimizar el desperdicio.

La siguiente ilustración muestra la interacción de Azure IoT Hub, Inteligencia de IoT y Supply Chain Management.

![IoT Hub, Inteligencia de IoT y Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Seguimiento y mantenimiento

- [Supervisar escenarios en Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Deshabilitar un escenario](iot-scenario-setup.md#disable-a-scenario)
- [Modificar un escenario de Inteligencia IoT en ejecución](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Opciones de simulación](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]