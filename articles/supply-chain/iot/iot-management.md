---
title: Supervisar y administrar Inteligencia IoT
description: Este tema explica cómo supervisar y administrar Inteligencia IoT.
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
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908428"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Supervisar y administrar Inteligencia IoT

[!include [banner](../../includes/banner.md)]

Este tema explica cómo supervisar y administrar Inteligencia IoT.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Supervisar escenarios en Microsoft Dynamics 365 Supply Chain Management

Puede monitorear el procesamiento de Inteligencia IoT desde varios lugares:

+ **Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Notificaciones**: mire la lista de notificaciones no resueltas.
+ **Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Notificaciones cerradas**: mire la lista de notificaciones que se han resuelto o desestimado.
+ **Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Claves métricas**: mire las claves métricas para los gráficos de series temporales **Estado del recurso**.
+ **Módulos \> Control de producción \> Ejecución de fabricación \> Estado del recurso**: siga métricas específicas mediante el cuadro de diálogo **Configurar**. Si un escenario detecta una excepción, una notificación muestra los detalles de la excepción.
+ **Espacios de trabajo \> Gestión de planta de producción \> Notificaciones**: mire la lista de notificaciones no resueltas.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Modificar un escenario de Inteligencia IoT en ejecución

Cuando se ejecuta un escenario, puede realizar estos cambios:

+ Agregue nuevas definiciones de esquema de sensor.
+ Seleccione nuevos valores de datos de señal.
+ Cancele la selección de valores de datos de señal existentes.
+ Agregue y asigne nuevos valores de datos de señal.
+ Actualice valores de umbral.

Cuando se ejecuta un escenario, están prohibidos estos cambios:

+ Elimine o modifique cualquier definición de esquema que esté consumiendo actualmente un escenario habilitado.
+ Cambiar las rutas de esquema seleccionadas del escenario habilitado.

## <a name="simulation-options"></a>Opciones de simulación

Puede simular señales de máquina de fábrica. Para obtener más información, consulte estos temas:

+ [Conecte IoT DevKit AZ3166 a Azure IoT Hub](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Conecte el simulador en línea Raspberry Pi a Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Descripción general del acelerador de solución de simulación de dispositivo](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]