---
title: Configurar métricas de Azure para Inteligencia IoT
description: Este artículo explica cómo configurar métricas para la Inteligencia IoT.
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
ms.openlocfilehash: 147df50a9d0baf78f2efc3e57b2cda935e38cee3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882703"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Configurar métricas de Azure para Inteligencia IoT

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Configurar las métricas

Si desea ver los gráficos de series de tiempo de sus mensajes en Microsoft Dynamics 365 Supply Chain Management, debe configurar las métricas siguiendo estos pasos.

1. Copie la cadena de conexión para la caché Redis:

    1. En Azure Portal, vaya a la caché Redis.
    2. Vaya a **Configuración** \> **Claves de acceso**.
    3. Copie el valor en el campo **Cadena de conexión primaria**.

2. En Supply Chain Management, vaya a **Control de producción \> Configurar \> Inteligencia IoT \> Parámetros de escenario**.
3. Sobre la página **Parámetros de escenario**, en la pestaña **Series de tiempo**, en el campo **Cadena de conexión de la tienda de métricas de Redis**, pegue la cadena de conexión que copió anteriormente. Este paso permite visualizar las métricas de Azure IoT Hub en Supply Chain Management. Cuando pega el valor en el campo, se muestra como **\*\*\*\*\*\***.

    > [!NOTE]
    > Siempre que actualice la cadena de conexión de la caché Redis, también debe actualizar este campo.

4. Vaya a **Control de producción \> Consultas e informes \> Inteligencia de IoT \> Claves de métricas**.
5. En la página **Claves de métricas**, seleccione **Actualizar**.
6. En el cuadro de diálogo **Actualizar claves de métricas**, observe que **Ejecutar en segundo plano** se selecciona en el campo. Seleccione **Aceptar**.

Todas las claves de métricas en la caché de Redis se recuperan y agregan a la lista **Claves métricas**. Los valores de las métricas no aparecerán hasta que se [habiliten los escenarios](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Configurar la serie de tiempo del estado del recurso

Para configurar la serie temporal **Estado del recurso**, siga estos pasos.

1. En Supply Chain Management, vaya a **Control de producción \> Ejecución de fabricación \> Estado del recurso**.
2. En la página **Estado del recurso**, seleccione **Configurar**.
2. En el cuadro de diálogo **Configurar**, en la lista **Recurso**, seleccione un elemento para monitorear.
3. Seleccione el botón **Editar** para **Serie temporal 1**.
4. En el cuadro de diálogo **Seleccionar serie temporal**, seleccione una métrica en la cuadrícula. (También puede utilizar el enlace **Actualizar claves de métricas** para actualizar las claves de métricas desde este cuadro de diálogo).
5. Seleccione **Aceptar** para volver al cuadro de diálogo **Configurar**.
6. Escriba un nombre para mostrar.
7. En el campo **Mostrar datos de**, seleccione un período de tiempo.
8. Seleccione **Aceptar**.

Se muestra el gráfico.

## <a name="delete-a-metric-key"></a>Eliminar una clave de métrica

1. En Supply Chain Management, vaya a **Control de producción \> Consultas e informes \> Inteligencia de IoT \> Claves de métricas**.
2. Sobre la página **Claves métricas**, seleccione la clave de métrica que desee eliminar.
3. Seleccione **Eliminar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]