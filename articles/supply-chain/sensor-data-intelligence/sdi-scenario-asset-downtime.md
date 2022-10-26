---
title: El escenario de tiempo de inactividad de activo
description: Este artículo describe el escenario de tiempo de inactividad de activo, que le permite usar datos de sensores para monitorear la disponibilidad de sus activos.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: b82d757d1e69203012949bc397220fa42ada4ac2
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689439"
---
# <a name="the-asset-downtime-scenario"></a>El escenario de tiempo de inactividad de activo

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

El escenario de tiempo de inactividad de activos genera un registro de tiempo de inactividad por mantenimiento si no se recibe ninguna señal de una máquina dentro de un umbral de tiempo definido desde que se recibió la última señal. El escenario requiere que instale en su máquina un sensor que envíe periódicamente una señal a Azure IoT Hub mientras la máquina está en funcionamiento, pero que no envíe una señal cuando la máquina no esté en funcionamiento.

## <a name="set-up-the-asset-downtime-scenario"></a>Configurar el escenario de tiempo de inactividad de activo

Siga estos pasos para configurar el escenario *tiempo de inactividad de activo* en Supply Chain Management.

1. Vaya a **Administración de activo \> Configurar \> Sensor de Data Intelligence \> Escenarios** para abrir la página **Escenarios**.
2. En el cuadro de escenario **Tiempo de inactividad de activo**, seleccione **Configurar** para abrir el asistente de configuración para este escenario.
3. En la página **Sensores**, seleccione **Nuevo** para agregar un sensor a la cuadrícula. Entonces establezca los siguientes campos para ello:

    - **Identificación del sensor** – Introduzca el ID del sensor que está utilizando. (Si está utilizando el Simulador en línea de Azure IoT de Raspberry PI y lo configuró como se describe en [Configurar un sensor simulado para probar](sdi-set-up-simulated-sensor.md), introduzca *AssetDownTime*.)
    - **Descripción del sensor**: escriba una descripción del sensor.

4. Repita el paso anterior para cada sensor adicional que quiera agregar ahora. Puede regresar y agregar más sensores en cualquier momento.
5. Seleccione **Siguiente**.
6. En la página **Asignación de registros comerciales**, en la sección **Sensores**, seleccione el registro para uno de los sensores que acaba de agregar.
7. En la sección **Asignación de registro empresarial**, seleccione **Nuevo** para agregar una fila al a cuadrícula.
8. En la nueva fila, establezca el campo **Registro comercial** al recurso que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración, seleccione *AK-101, Cuchilla de aire para Línea 1*.)
9. Seleccione **Siguiente**.
10. En la página **umbral de tiempo de inactividad de activos**, defina cuánto tiempo después de la última señal debe esperar el sistema antes de enviar una notificación de tiempo de inactividad del activo. Hay dos formas de definir el umbral:

    - **Umbral predeterminado (minutos)** – Establezca este campo para definir el umbral predeterminado. Este valor se aplica a todos los recursos donde el campo **Umbral de notificación (minutos)** está configurado en dos minutos o menos. El valor mínimo es de *2* (minutos).
    - **Umbral para determinar que la máquina no responde (minutos)** – Para cada recurso de la cuadrícula donde no desee utilizar el umbral predeterminado, introduzca un valor de anulación en este campo. Los recursos que están configurados para usar un umbral de dos minutos o menos usarán la configuración **Umbral predeterminado (minutos)** en su lugar.
11. Seleccione **Siguiente**.
12. En la página **Activar sensores**, en la cuadrícula, seleccione el sensor que configuró y luego seleccione **Activar**. Para cada sensor activado en la cuadrícula, aparece una marca de verificación en la columna **Activo**.
13. Seleccione **Fin**.

## <a name="work-with-the-asset-downtime-scenario"></a>Trabajar con el escenario de tiempo de inactividad de activo

Si no se recibe ninguna señal del sensor de un activo dentro del umbral definido en la configuración del escenario, el sistema creará un registro de tiempo de inactividad por mantenimiento para ese activo. Los gerentes deben revisar periódicamente los registros de tiempo de inactividad (por ejemplo, una vez durante cada turno de trabajo) y aplicar códigos de razón y tiempos de finalización apropiados para cada registro de tiempo de inactividad. Siga estos pasos para ver los registros de tiempo de inactividad por mantenimiento de un activo:

1. Vaya a **Administración de activos > Activos > Todos los activos**.
2. Busque y seleccione el activo que se desea analizar. (Si está usando los datos de demostración, seleccione *AK-101*.)
3. En el Panel de acciones, abra la pestaña **Activo** y, desde el grupo **Orden de trabajo**, seleccione **Tiempo de inactividad por mantenimiento** para abrir la página de registros de tiempo de inactividad por mantenimiento para el activo seleccionado.
