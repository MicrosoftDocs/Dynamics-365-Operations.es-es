---
title: Página principal de Inteligencia de IoT
description: Este tema proporciona vínculos a información sobre Inteligencia de IoT.
author: robinarh
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: intro-internal
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f32cb5578f3c15a10f863980491a687f64312cd
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652080"
---
# <a name="iot-intelligence-home-page"></a>Página principal de Inteligencia de IoT

[!include [banner](../../includes/banner.md)]

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

+ **Retrasos en la producción** - Este escenario compara el tiempo de ciclo real con el tiempo de ciclo planificado. Supply Chain Management le notifica cuando la producción no está según lo programado, para que pueda intervenir para maximizar la eficiencia operativa y evitar retrasos en los pedidos.
+ **Tiempo de inactividad del equipo** - Este escenario compara el tiempo de actividad medido con los parámetros definidos por el usuario. Supply Chain Management le notifica cuando se excede un umbral de interrupción, para que pueda tomar acciones como reprogramar una orden de trabajo de producción o crear una orden de trabajo de mantenimiento.
+ **Calidad del producto** - Este escenario compara las lecturas de los sensores, como la humedad y la temperatura, con las métricas de calidad definidas por el usuario. Supply Chain Management le notifica cuando ocurre una desviación, para que pueda intervenir para mantener los estándares de calidad y minimizar el desperdicio.

La siguiente ilustración muestra la interacción de Azure IoT Hub, Inteligencia de IoT y Supply Chain Management.

![IoT Hub, Inteligencia de IoT y Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Configurar

Puede instalar y configurar Inteligencia de IoT sin escribir ningún código. Estos son los pasos básicos.

1. [Configurar recursos de Azure](iot-azure-setup.md) - Cree un centro de IoT, una caché de Redis y una bóveda de claves a las que se pueda acceder desde Supply Chain Management.
2. [Formatos de esquema de mensajes para IoT Hub](iot-schema-format.md) - Configure sus dispositivos para enviar mensajes a IoT Hub y defina el formato de mensaje de notación de objetos JavaScript (JSON).
3. En Gestión de funciones, habilite la marca de función de Inteligencia de IoT. 
4. [Instale el complemento Inteligencia de IoT en Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) - Instale el complemento en LCS y configure los secretos de Azure.
5. [Configurar métricas](iot-metrics-setup.md) - Configurar métricas en Supply Chain Management.
6. [Configuración de escenario](iot-scenario-setup.md) - Configurar los escenarios en Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Seguimiento y mantenimiento

+ [Supervisar escenarios en Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Deshabilitar un escenario](iot-scenario-setup.md#disable-a-scenario)
+ [Desinstalar el complemento](iot-lcs-setup.md#uninstall-addin)
+ [Modificar un escenario de Inteligencia IoT en ejecución](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Opciones de simulación](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]