---
title: El escenario del estado de la máquina
description: Este artículo describe el escenario de estado de la máquina, que le permite usar datos de sensores para monitorear la disponibilidad de su equipo.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 1f2b424dccf1963a7917059d412b5df7937496ee
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428413"
---
# <a name="the-machine-status-scenario"></a>El escenario del estado de la máquina

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

El escenario de *estado de la máquina*, le permite usar datos de sensores para monitorear la disponibilidad de su equipo. Si configura un sensor que envía una señal cuando un trabajo de producción en un recurso de máquina produce una salida, pero no se recibe ninguna señal del sensor dentro de un intervalo específico, se muestra una notificación en el tablero del supervisor.

## <a name="scenario-dependencies"></a>Dependencias del escenario

El escenario *estado de la máquina* tiene las siguientes dependencias:

- Una notificación solo se puede desencadenar si un trabajo de producción está en curso en una máquina asignada.
- Una señal que representa una señal *part-out* que debe enviarse al centro de IoT.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Prepare datos de demostración para el escenario de estado de la máquina

Si desea utilizar un sistema de demostración para probar el escenario de *estado de la máquina*, use un sistema donde los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estén instalados, seleccione la entidad legal (empresa) *USMF* y prepare los datos de demostración adicionales como se describe en esta sección. Si está utilizando sus propios sensores y datos, puede omitir esta sección.

### <a name="set-up-a-sensor-simulator"></a>Configurar un simulador de sensor

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

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Configurar la interfaz de ejecución de la planta de producción

Utilizará la interfaz de ejecución de la planta de producción para iniciar el trabajo que se programó y liberó para el número de artículo *P0111* en la sección anterior. Siga estos pasos para configurar la interfaz de ejecución de la planta de producción.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. Si no ha configurado previamente la interfaz, aparece una página de inicio de sesión. Escriba sus credenciales.
1. En la página de bienvenida, seleccione **Configurar** para abrir el asistente **Configurar dispositivo**.
1. En la página **Configurar dispositivo - Paso 1 - Seleccionar configuración**, seleccione la configuración *Predeterminada*.
1. Seleccione **Siguiente**.
1. En la página **Configurar dispositivo - Paso 2 - Definir el área de producción**, establezca el campo **Recurso** a *3118*.
1. Seleccione **Aceptar**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Habilitar la opción de búsqueda en la interfaz de ejecución de la planta de producción

Para que sea más fácil encontrar el trabajo de producción para la orden de producción que se lanzó anteriormente, siga estos pasos para habilitar la opción de búsqueda en la interfaz de ejecución de la planta de producción.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. Seleccione la configuración *Predeterminado*.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, configure la opción **Habilitar búsqueda** en *Sí*.
1. Cierre la página.

### <a name="start-the-first-job-in-the-batch-order"></a>Comience el primer trabajo en el orden de lote

Siga estos pasos para iniciar el trabajo programado en el recurso *3118*.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. En el campo **Id. de notificación**, introduzca *123*. A continuación, seleccione **Iniciar sesión**.
1. Si se le solicita un motivo de ausencia, seleccione una de las tarjetas de ausencia y luego seleccione **Aceptar**.
1. En el campo **Búsqueda**, ingrese el número de orden de lote que anotó previamente. Luego seleccione la clave **Devolución**.
1. Seleccione el pedido y seleccione **Iniciar trabajo**.
1. En el **Iniciar trabajo** cuadro de diálogo, seleccione **Comienzo**.

## <a name="set-up-the-machine-status-scenario"></a>Configurar el escenario del estado de la máquina

Siga estos pasos para configurar el escenario *estado de la máquina* en Supply Chain Management.

1. Vaya a **Control de producción \> Configurar \> Sensor de Data Intelligence \> Escenarios**.
1. En el cuadro de escenario **Estado de la máquina**, seleccione **Configurar** para abrir el asistente de configuración para este escenario.
1. En la página **Sensores**, seleccione **Nuevo** para agregar un sensor a la cuadrícula. Entonces establezca los siguientes campos para ello:

    - **Identificación del sensor** – Introduzca el ID del sensor que está utilizando. (Si está utilizando el Simulador en línea de Azure IoT de Raspberry PI y lo configuró como se describe en [Configurar un sensor simulado para probar](sdi-set-up-simulated-sensor.md), introduzca *MachineStatus*.)
    - **Descripción del sensor**: escriba una descripción del sensor.

1. Repita el paso anterior para cada sensor adicional que quiera agregar ahora. Puede regresar y agregar más sensores en cualquier momento.
1. Seleccione **Siguiente**.
1. En la página **Asignación de registros comerciales**, en la sección **Sensores**, seleccione el registro para uno de los sensores que acaba de agregar.
1. En la sección **Asignación de registro empresarial**, seleccione **Nuevo** para agregar una fila al a cuadrícula.
1. En la nueva fila, establezca el campo **Registro comercial** al recurso que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, establezca el campo en *3118, Cortadora de espuma*.)
1. Seleccione **Siguiente**.
1. En la página **Umbral de estado de la máquina**, defina cuánto tiempo después de la última señal *part-out*, el sistema debe enviar una notificación de estado de la máquina. Hay dos formas de definir el umbral:

    - **Umbral predeterminado (minutos)** – Establezca este campo para definir el umbral predeterminado. El valor se aplicará entonces a todos los recursos en los que el campo **Umbral para determinar que la máquina no responde (minutos)** está configurado en dos minutos o menos. El valor mínimo es de *2* (minutos).
    - **Umbral para determinar que la máquina no responde (minutos)** – Para cada recurso de la cuadrícula para el que no desee utilizar el umbral predeterminado, introduzca un valor de anulación en este campo. Los recursos que están configurados para usar un umbral de dos minutos o menos usarán la configuración **Umbral predeterminado (minutos)** en su lugar.

    > [!NOTE]
    > Por lo general, utilizará una señal *part-out* para supervisar el estado de la máquina. Por lo tanto, debe verificar que el umbral para cada recurso de la máquina sea más largo de lo que la máquina requiere para producir cada pieza.

1. Seleccione **Siguiente**.
1. En la página **Activar sensores**, en la cuadrícula, seleccione el sensor que agregó y luego seleccione **Activar**. Para cada sensor activado en la cuadrícula, aparece una marca de verificación en la columna **Activo**.
1. Seleccione **Fin**.

## <a name="work-with-the-machine-status-scenario"></a>Trabajar con el escenario del estado de la máquina

Después de instalar sus sensores y configurar el escenario, puede ver los eventos de estado de la máquina en Supply Chain Management. Esta sección describe dónde y cómo ver esta información.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Ver datos de estado de la máquina en la página de estado de recursos

En la página **Estado del recurso**, los supervisores pueden supervisar una línea de tiempo de la señal de *part-out* que se recibe de los sensores que se asignan a cada recurso de la máquina. Siga estos pasos para configurar la escala de tiempo.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Estado del recurso**.
1. En el cuadro de diálogo **Configurar**, seleccione los siguientes campos:

    - **Recurso**: seleccione los recursos que quiera supervisar. (Si está trabajando con los datos de demostración, seleccione *3118* .)
    - **Serie temporal 1** – Seleccione el registro (clave métrica) que tenga el siguiente formato para su nombre: *MachineReportingStatus:&lt;Sensor&gt;*
    - **Nombre para mostrar** - Introduzca *Señal de salida de piezas*.

La siguiente ilustración muestra un ejemplo de datos de estado de la máquina en la página **Estado del recurso** durante el funcionamiento estándar.

![Estado de la máquina en la página de estado de recursos durante la operación estándar.](media/sdi-resource-status-downtime-up.png "Estado de la máquina en la página de estado de recursos durante la operación estándar")

La siguiente ilustración muestra un ejemplo de datos de estado de la máquina cuando se detecta tiempo de inactividad.

![Datos de estado de la máquina en la página de estado de recursos cuando se detecta tiempo de inactividad.](media/sdi-resource-status-downtime-down.png "Datos de estado de la máquina en la página de estado de recursos cuando se detecta tiempo de inactividad")

### <a name="view-machine-status-on-the-notifications-page"></a>Ver el estado de la máquina en la página de notificaciones

En la página **Notificaciones**, los supervisores pueden ver las notificaciones que se generan cuando ha pasado demasiado tiempo desde la última vez que el sensor entregó una señal *part-out*. Cada notificación proporciona una descripción general del trabajo de producción afectado por la interrupción y brinda la opción de reasignar el trabajo afectado a otro recurso.

Para abrir la página **Notificación**, vaya **Control de producción \> Consultas e informes \> Sensor de Data Intelligence \> Notificaciones**.

En la ilustración siguiente se muestra un ejemplo de la notificación de estado de la máquina.

![Ejemplo de notificación de un estado de máquina.](media/sdi-resource-status-downtime-notification.png "Ejemplo de notificación de un estado de máquina")
