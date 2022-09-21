---
title: El escenario de retrasos en la producción
description: Este artículo describe el escenario de retrasos en la producción, que genera una notificación si el rendimiento de producción cae por debajo de un valor umbral especificado.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 073762581d84646ba12b570e57327b7cab8efd3b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428420"
---
# <a name="the-production-delays-scenario"></a>El escenario de retrasos en la producción

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

El escenario *Retrasos de producción* genera una notificación si el rendimiento de producción cae por debajo de un valor umbral específico. En este escenario, se envía una señal *part-out* a Microsoft Azure IoT Hub para cada artículo producido. En Dynamics 365 Supply Chain Management Management, el retraso de la orden se calcula en función de la cantidad de tiempo en que la orden de producción está programada para ejecutarse, la cantidad de artículos que se deben producir, la cantidad de tiempo que el trabajo ha estado ejecutándose y la cantidad de señales *part-out* que se han recibido. Se genera una notificación de retraso si el número de señales *part-out* para el trabajo caen por debajo del valor umbral del valor esperado.

## <a name="scenario-dependencies"></a>Dependencias del escenario

El escenario *Retrasos de producción* tiene las siguientes dependencias:

- Una orden de producción solo se puede desencadenar si una orden de producción se está ejecutando en una máquina asignada.
- Una señal que representa la señal de inactividad *part-out* de una máquina asignada debe enviarse al IoT Hub y se deberá incluir un nombre de propiedad único.
- Una propiedad de marca de tiempo UNIX, donde el valor se expresa en milisegundos (ms), debe estar presente en el mensaje de Azure IoT Hub.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Prepare datos de demostración para el escenario de retrasos de producción

Si desea utilizar un sistema de demostración para probar el escenario de *retrasos en la producción*, use un sistema donde los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estén instalados, seleccione la entidad legal (empresa) *USMF* y prepare los datos de demostración adicionales como se describe en esta sección. Si está utilizando sus propios sensores y datos, puede omitir esta sección.

### <a name="set-up-sensor-simulator"></a>Configurar simulador de sensor

Si desea probar este escenario sin usar un sensor físico, puede configurar un simulador para generar las señales requeridas. Para obtener más información, consulte [Configurar una sensor simulado para pruebas](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Verifique que el recurso 3118 se use para el producto P0111

Se programará y liberará una orden de producción. Por lo tanto, se libera un trabajo de producción al recurso *3118* (*Cortadora de espuma*). Siga estos pasos para verificar ese recurso *3118* se utiliza para el producto *P0111* en sus datos de demostración.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Encuentre y seleccione el producto cuyo campo **Número de artículo** está establecido en *P0111*.
1. En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **Vista**, seleccione **Ruta**.
1. En la página **Ruta**, en la pestaña **Visión general** en la parte inferior de la página, seleccione la línea donde el **Nº. oper.** campo está establecido a *30*.
1. En la pestaña **Requerimientos de recursos** en la parte inferior de la página, asegúrese de que el recurso *3118* (*Cortadora de espuma*) está asociado con la operación.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Cree y libere un pedido de producción para el producto P0111

Siga estos pasos para crear y liberar una orden de producción para el producto *P0111*.

1. Vaya a **Control de producción \> Pedidos de producción \> Todos los pedidos de producción**.
1. En la página **Todas las órdenes de producción**, en el Panel de acciones, seleccione **Nuevo pedido de lote**.
1. En el cuadro de diálogo **Crear lote**, establezca los valores siguientes:

    - **Código de artículo:** *P0111*
    - **Cantidad:** *10*

1. Seleccione **Crear** para crear el pedido y regresar a la página **Todos los pedidos de producción**.
1. Use el campo **Filtrar** para buscar órdenes de producción donde el **Número de artículo** el campo se establece en *P0111*. Después encuentre y seleccione el pedido de producción que acaba de crear.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Proceso**, seleccione **Estimación**.
1. En el cuadro de diálogo **Estimado**, seleccione **Aceptar** para ejecutar la estimación.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Proceso**, seleccione **Lanzar**.
1. En el cuadro de diálogo **Liberar**, tome nota del número del pedido de lote que acaba de crear.
1. Seleccione **Aceptar** para liberar la orden.

### <a name="configure-the-production-floor-execution-interface"></a>Configurar la interfaz de ejecución de la planta de producción

Si aún no lo ha hecho, configure la interfaz de ejecución de la planta de producción para mostrar los trabajos que están asignados al recurso *3118* (*Cortadora de espuma*). Para obtener instrucciones, consulte las secciones siguientes:

- [Configurar la interfaz de ejecución de la planta de producción](sdi-scenario-equipment-downtime.md#config-pfe)
- [Habilitar la opción de búsqueda en la interfaz de ejecución de la planta de producción](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Comience el primer trabajo en el orden de lote

Siga estos pasos para iniciar el primer trabajo en el orden del lote.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. En el campo **Id. de notificación**, introduzca *123*. A continuación, seleccione **Iniciar sesión**.
1. Si se le solicita un motivo de ausencia, seleccione una de las tarjetas de ausencia y luego seleccione **Aceptar**.
1. En el campo **Búsqueda**, ingrese el número de orden de lote que anotó previamente. Luego seleccione la clave **Devolución**.
1. Seleccione el pedido y seleccione **Iniciar trabajo**.
1. En el **Iniciar trabajo** cuadro de diálogo, seleccione **Comienzo**.

## <a name="set-up-the-production-delays-scenario"></a>Configurar el escenario de retrasos en la producción

Siga estos pasos para configurar el escenario *retrasos de producción* en Supply Chain Management.

1. Vaya a **Control de producción \> Configurar \> Sensor de Data Intelligence \> Escenarios**.
1. En el cuadro de escenario **Retrasos en la producción**, seleccione **Configurar** para abrir el asistente de configuración para este escenario.
1. En la página **Sensores**, seleccione **Nuevo** para agregar un sensor a la cuadrícula. Entonces establezca los siguientes campos para ello:

    - **Identificación del sensor** – Introduzca el ID del sensor que está utilizando. (Si está utilizando el Simulador en línea de Azure IoT de Raspberry PI y lo configuró como se describe en [Configurar un sensor simulado para probar](sdi-set-up-simulated-sensor.md), introduzca *ProductionDelay*.)
    - **Descripción del sensor**: escriba una descripción del sensor.

1. Repita el paso anterior para cada sensor adicional que quiera agregar ahora. Puede regresar y agregar más sensores en cualquier momento.
1. Seleccione **Siguiente**.
1. En la página **Asignación de registros comerciales**, en la sección **Sensores**, seleccione el registro para uno de los sensores que acaba de agregar.
1. En la sección **Asignación de registro empresarial**, seleccione **Nuevo** para agregar una fila al a cuadrícula.
1. En la nueva fila, establezca **Registro comercial** al recurso que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, configúrelos en *3118, Cortadora de espuma*.)
1. Seleccione **Siguiente**.
1. En la página **Umbral de desviación de retraso de producción**, si está utilizando los datos de demostración que creó anteriormente en este artículo, siga estos pasos:

    1. Selecciona el encabezado de columna **Relación de artículo** para abrir un cuadro de diálogo desplegable que incluye filtros de búsqueda para la columna. Introduzca *P0111* en el cuadro de búsqueda y, a continuación, seleccione **Aplicar**.
    2. Seleccione la línea donde el campo **Operación** se establece en *Recortar/Cortar*. Establezca el campo **Umbral de notificación por retraso (%)** hasta el umbral (como porcentaje) en el que se debe enviar una notificación.

1. Seleccione **Siguiente**.
1. En la página **Activar sensores**, en la cuadrícula, seleccione el sensor que agregó y luego seleccione **Activar**. Para cada sensor activado en la cuadrícula, aparece una marca de verificación en la columna **Activo**.
1. Seleccione **Fin**.

## <a name="work-with-the-production-delays-scenario"></a>Trabajar con el escenario de retrasos en la producción

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Ver datos de retraso de producción en la página de estado de recursos

En la página **Estado del recurso**, los supervisores pueden supervisar una línea de tiempo de las señales que se reciben de los sensores que se asignan a cada recurso de la máquina. Siga estos pasos para configurar la escala de tiempo.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Estado del recurso**.
1. En el cuadro de diálogo **Configurar**, seleccione los siguientes campos:

    - **Recurso**: seleccione los recursos que quiera supervisar. (Si está trabajando con los datos de demostración, seleccione *3118* .)
    - **Serie temporal 1** – Seleccione el registro (clave métrica) que tenga el siguiente formato para su nombre: *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Nombre para mostrar** - Introduzca *Señal de salida de piezas*.
