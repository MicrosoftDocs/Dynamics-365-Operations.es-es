---
title: Parámetros de Sensor Data Intelligence
description: Este artículo proporciona información sobre los ajustes de configuración que están disponibles en la página de parámetros de Sensor Data Intelligence.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 4a6665cc078e54da4ebb7920ec8826352ab7a816
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428435"
---
# <a name="sensor-data-intelligence-parameters"></a>Parámetros de Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

La página **Parámetros de Sensor Data Intelligence** proporciona algunas configuraciones que puede usar para configurar la función. Esta configuración incluye parámetros de conexión de Azure y un parámetro para la duración de los mensajes de alerta que se envían a los usuarios en respuesta a las mediciones del sensor.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Lea y cambie los detalles de conexión para su solución Azure IoT

Por lo general, configurará su solución Azure IoT y la conectará a Microsoft Dynamics 365 Supply Chain Management desde la página **Implementar y conectar recursos de Azure**, que le guiará a través de ambos procedimientos. (Para más información, vea [Implemente una solución de IoT en Azure](sdi-deploy-iot-solution-on-azure.md)). También puede ver y editar los detalles de la conexión en cualquier momento en Supply Chain Management siguiendo estos pasos.

1. Vaya a **Administración del sistema \> Configuración \> Sensor Data Intelligence \> Parámetros del Sensor Data Intelligence**.
1. En la pestaña **Series temporales**, en el campo **Cadena de conexión del almacén de métricas de Redis**, introduzca el valor **Cadena de conexión principal (StackExchange.Redis)** para la solución de Azure IoT a la que desea conectarse. Para obtener más información sobre cómo encontrar este valor, consulte [Implemente una solución de IoT en Azure](sdi-deploy-iot-solution-on-azure.md).
1. En la pestaña **Integraciones**, en el campo **Id. de cliente de la aplicación de Azure AD**, introduzca el valor de la **Identificación del cliente** para la solución de Azure IoT a la que desea conectarse. Para obtener más información sobre cómo encontrar este valor, consulte [Implemente una solución de IoT en Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Establecer la vida útil de los mensajes de alerta

Cada vez que Sensor Data Intelligence detecta una situación que requiere la atención del usuario, envía una notificación al usuario correspondiente. Para evitar que estas notificaciones se acumulen en el sistema, debe configurarlas para que caduquen después de unos días.

1. Vaya a **Administración del sistema \> Configuración \> Sensor Data Intelligence \> Parámetros del Sensor Data Intelligence**.
1. En la pestaña **Notificaciones**, en campo **Días de vida de la notificación**, introduzca el número de días para guardar una notificación. Después de que transcurra la cantidad de tiempo especificada, la notificación se eliminará.
