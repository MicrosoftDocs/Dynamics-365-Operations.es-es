---
title: El escenario de mantenimiento de activo
description: Este artículo describe el escenario de mantenimiento de activos, que le permite usar datos de sensores para crear registros de contador que rastrean el uso de un activo de máquina.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ff3944b987314a688a5829b05f8627479e3e79ed
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428406"
---
# <a name="the-asset-maintenance-scenario"></a>El escenario de mantenimiento de activo

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

El escenario *mantenimiento de activos* le permite usar datos de sensores para crear registros de contadores. Los registros de contador rastrean el uso de un activo de máquina y se utilizan como entrada para generar el programa de mantenimiento para los activos de máquina.

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Prepare datos de demostración para el escenario de mantenimiento de activos

Si desea utilizar un sistema de demostración para probar el escenario de *mantenimiento de activo*, use un sistema donde los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estén instalados, seleccione la entidad legal (empresa) *USMF* y prepare los datos de demostración adicionales como se describe en esta sección. Si está utilizando sus propios sensores y datos, puede omitir esta sección.

En esta sección, configurará el activo *AK-101, cuchillo de aire* en datos de demostración como ejemplo. Luego verá cómo se puede predecir el próximo trabajo de mantenimiento en función de las señales de los sensores que miden la cantidad de horas que la cuchilla de aire ha estado funcionando. También configurará un plan de mantenimiento en el que se debe realizar el mantenimiento de la cuchilla de aire cada 10 000 horas.

### <a name="set-up-a-sensor-simulator"></a>Configurar un simulador de sensor

Si desea probar este escenario sin usar un sensor físico, puede configurar un simulador para generar las señales requeridas. Para obtener más información, consulte [Configurar una sensor simulado para pruebas](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Cree un contador de activos para realizar un seguimiento de las horas de producción

Siga estos pasos para crear un contador de activos para realizar un seguimiento de las horas de producción.

1. Vaya a **Gestión de activos \> Configuración \> Tipos de activos \> Contadores**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear un contador.
1. Establezca los siguientes valores en el encabezado:

    - **Contador:** *ProductionHr*
    - **Nombre**: *Horas de producción*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Unidad:** *hr*
    - **Actualización:** *Manual*
    - **Agregado total:** *Sum*

1. En la ficha desplegable **Tipos de activo**, seleccione **Agregar línea**.
1. En la nueva línea, establezca el campo **Tipo de activo** a *Cuchillo de aire*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Crear un plan de mantenimiento para el activo

Siga estos pasos para crear un plan de mantenimiento para el activo.

1. Vaya a **Administración de activos \> Configuración \> Mantenimiento preventivo \> Plan de mantenimiento**.
1. En el panel de acciones, seleccione **Nuevo** para crear un plan de mantenimiento.
1. Establezca los siguientes valores en el encabezado:

    - **Plan de mantenimiento:** *AirKnife*
    - **Nombre:** *Plan para cuchillos de aire*

1. En la ficha desplegable **Detalles**, establezca los valores siguientes:

    - **Fecha del plan:** introduzca la fecha de hoy.
    - **Activo:** *Sí*

1. En la ficha desplegable **Líneas**, seleccione **Agregar línea de contador de activo** para agregar una línea a la cuadrícula. Establezca los siguientes valores para este registro:

    - **Descripción de la orden de trabajo:** *Mantenimiento de la cuchilla de aire*
    - **Tipo de trabajo de mantenimiento:** *Preventivo*
    - **Tipo de intervalo:** *Repetido de la última orden de trabajo*
    - **Frecuencia de período:** *10000*
    - **Contador:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Configurar el escenario de mantenimiento de activo

Siga estos pasos para configurar el escenario *mantenimiento de activo* en Supply Chain Management.

1. Vaya a **Administración de activo \> Configurar \> Sensor de Data Intelligence \> Escenarios**.
1. En el cuadro de escenario **Mantenimiento de activo**, seleccione **Configurar** para abrir el asistente de configuración para este escenario.
1. En la página **Sensores**, seleccione **Nuevo** para agregar un sensor a la cuadrícula. Entonces establezca los siguientes campos para ello:

    - **Identificación del sensor** – Introduzca el ID del sensor que está utilizando. (Si está utilizando el Simulador en línea de Azure IoT de Raspberry PI y lo configuró como se describe en [Configurar un sensor simulado para probar](sdi-set-up-simulated-sensor.md), introduzca *AssetMaintenance*.)
    - **Descripción del sensor**: escriba una descripción del sensor.

1. Repita el paso anterior para cada sensor adicional que quiera agregar ahora. Puede regresar y agregar más sensores en cualquier momento.
1. Seleccione **Siguiente**.
1. En la página **Asignación de registros comerciales**, en la sección **Sensores**, seleccione el registro para uno de los sensores que acaba de agregar.
1. En la sección **Asignación de registro empresarial**, seleccione **Nuevo** para agregar una fila al a cuadrícula.
1. En la nueva fila, el campo **Tipo de registro comercial** debe establecerse automáticamente en *Assets(EntAssetObjectTable)*. Establezca el campo **Registro comercial** al recurso que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, configúrelos en *AK-101, AK-101 Cuchilla de aire para Línea 1*.)
1. Inmediatamente después de seleccionar un tipo de registro comercial para la fila que agregó en el paso anterior, se agrega automáticamente una segunda fila a la cuadrícula. En esta fila, el campo **Tipo de registro comercial** debe establecerse en *Counters(EntAssetCounterType)*. Establezca el campo **Registro comercial** al contador de activos que está actualizando en función de las señales del sensor seleccionado. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, configúrelos en *ProductionHr, Horas de producción*.)
1. Seleccione **Siguiente**.
1. En la página **Activar sensores**, en la cuadrícula, seleccione el sensor que agregó y luego seleccione **Activar**. Para cada sensor activado en la cuadrícula, aparece una marca de verificación en la columna **Activo**.
1. Seleccione **Fin**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Trabajar con el escenario de mantenimiento de activo

### <a name="view-counter-values"></a>Ver valores del contador

Una vez preparados los datos y el escanario *mantenimiento de activos* está configurado y activado, puede ver cómo se insertan los registros para un contador de activos en función de los datos del sensor.

1. Vaya a **Administración de activos \> Activos \> Todos los activos**.
1. Busque y seleccione el activo que se desea analizar. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, seleccione en *AK-101*.)
1. En el Panel de Acción, en la pestaña **Activo**, en el grupo **Preventivo**, seleccione **Contadores** para abrir la página para registros de contadores del activo *AK-101*.

### <a name="generate-maintenance-work-orders"></a>Generar órdenes de trabajo de mantenimiento

Después de habilitar el escenario *mantenimiento de activos* y configurar el plan de mantenimiento, puede ejecutar el programa de mantenimiento para generar órdenes de trabajo de mantenimiento. Para obtener más información sobre cómo trabajar con mantenimiento preventivo, consulte [Información general mantenimiento preventivo](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
