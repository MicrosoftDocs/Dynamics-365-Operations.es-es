---
title: El escenario de la calidad del producto
description: Este artículo proporciona información acerca del escenario de calidad del producto. Este escenario utiliza un sensor para medir la calidad de un lote de productos y genera una alerta si una medición cae fuera de un umbral definido.
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
ms.openlocfilehash: c0f1c57251234921779f67faf61d47cdde119e64
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690058"
---
# <a name="the-product-quality-scenario"></a>El escenario de la calidad del producto

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

En el escenario *calidad del producto*, se configura un sensor para medir la calidad de un lote de producto en el piso de producción. Si una medición cae fuera de un umbral definido para el producto, se muestra una notificación en el tablero del supervisor. Por ejemplo, un sensor mide la humedad de un producto alimenticio que sale de la línea de producción. Si la medición está fuera del valor mínimo o máximo permitido para la humedad del producto, se genera una notificación.

## <a name="scenario-dependencies"></a>Dependencias del escenario

El escenario *Calidad del producto* tiene las siguientes dependencias:

- Se puede desencadenar una alerta solo si se está ejecutando una orden producción en una máquina asignada y si esa máquina está produciendo un producto con un atributo de lote asignado.
- Una señal que representa el atributo de lote debe enviarse al IoT Hub y se debe incluir un nombre de propiedad único.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Prepare datos de demostración para el escenario de calidad de producción

Si desea utilizar un sistema de demostración para probar el escenario de *calidad del producto*, use un sistema donde los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estén instalados, seleccione la entidad legal (empresa) *USMF* y prepare los datos de demostración adicionales como se describe en esta sección. Si está utilizando sus propios sensores y datos, puede omitir esta sección.

En esta sección, configurará los datos de demostración para que pueda usar el producto lanzado *P0111* (*Caso compuesto*) con el escenario *calidad del producto*. En este escenario, el sistema rastrea si un valor de atributo de lote medido por un sensor está fuera del umbral definido para un atributo de lote asociado con el producto.

### <a name="set-up-a-sensor-simulator"></a>Configurar un simulador de sensor

Si desea probar este escenario sin usar un sensor físico, puede configurar un simulador para generar las señales requeridas. Para obtener más información, consulte [Configurar una sensor simulado para pruebas](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Asociar un atributo de lote y un recurso con el producto P0111

Siga estos pasos para asociar un atributo de lote con el producto *P0111* (*Caso compuesto*) y verificar ese recurso *3118* (*Cortadora de espuma*) se utiliza para ello.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Encuentre y seleccione el producto cuyo campo **Número de artículo** está establecido en *P0111*.
1. En el panel de acciones, en la ficha **Administrar inventario** del grupo **Atributos de lote**, haga clic en **Específico de producto**.
1. En la página **Específico del producto** página, seleccione **Nuevo** para crear un atributo de lote específico del producto.
1. Establezca los siguientes campos en el encabezado:

    - **Código de atributo** – Seleccione el alcance de los atributos que supervisará (*Tabla*, *Grupo*, o *Todos*). Para este escenario, seleccione *Tabla*, porque siempre supervisará un solo atributo.
    - **Relación de atributo** – Seleccione el atributo que usará el escenario *calidad del producto* para supervisar el valor de. Para este ejemplo, seleccione *Concentración*, que es un atributo que se incluye en los datos de demostración estándar.

1. En la ficha desplegable **Valores**, en los campos **Mínimo** y **Máximo**, defina el rango de valores aceptables que el atributo debe informar para pasar el control de calidad. Si el sensor informa un valor fuera de este rango, el sistema lo identificará como una violación de calidad. Los demás campos de esta ficha desplegable no son relevantes para el escenario *calidad del producto*. Los valores predeterminados que ve actualmente provienen de los datos de demostración. Por tanto, déjelos como están y cierre la página **Específico del producto** para volver a la página **Detalles del producto publicado** para el artículo *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Configurar el escenario de la calidad del producto

Siga estos pasos para configurar el escenario *calidad del producto* en Supply Chain Management.

1. Vaya a **Control de producción \> Configurar \> Sensor de Data Intelligence \> Escenarios**.
1. En el cuadro de escenario **Calidad del producto**, seleccione **Configurar** para abrir el asistente de configuración para este escenario.
1. En la página **Sensores**, seleccione **Nuevo** para agregar un sensor a la cuadrícula. Entonces establezca los siguientes campos para ello:

    - **Identificación del sensor** – Introduzca el ID del sensor que está utilizando. (Si está utilizando el Simulador en línea de Azure IoT de Raspberry PI y lo configuró como se describe en [Configurar un sensor simulado para probar](sdi-set-up-simulated-sensor.md), introduzca *Calidad*.)
    - **Descripción del sensor**: escriba una descripción del sensor.

1. Repita el paso anterior para cada sensor adicional que quiera agregar ahora. Puede regresar y agregar más sensores en cualquier momento.
1. Seleccione **Siguiente**.
1. En la página **Asignación de registros comerciales**, en la sección **Sensores**, seleccione el registro para uno de los sensores que acaba de agregar.
1. En la sección **Asignación de registro empresarial**, seleccione **Nuevo** para agregar una fila al a cuadrícula.
1. En la nueva fila, el campo **Tipo de registro comercial** debe establecerse automáticamente en *Resources(WrkCtrTable)*. Establezca el campo **Registro comercial** al recurso que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, configúrelos en *3118, Cortadora de espuma*.)
1. Inmediatamente después de seleccionar un tipo de registro comercial para la fila que agregó en el paso anterior, se agrega automáticamente una segunda fila a la cuadrícula. En esta fila, el campo **Tipo de registro comercial** debe establecerse en *Atributos de lote(PdsBatchAttrib)*. Establezca el campo **Registro comercial** al atributo de lote que está usando el sensor seleccionado para monitorear. (Si está utilizando los datos de demostración que creó anteriormente en este artículo, configúrelos en *Concentración, Porcentaje de concentración*.)
1. Seleccione **Siguiente**.
1. En la página **Activar sensores**, en la cuadrícula, seleccione el sensor que agregó y luego seleccione **Activar**. Para cada sensor activado en la cuadrícula, aparece una marca de verificación en la columna **Activo**.
1. Seleccione **Fin**.

## <a name="work-with-the-product-quality-scenario"></a>Trabajar con el escenario de la calidad del producto

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Ver datos de calidad de producto en la página de estado de recursos

En la página **Estado del recurso**, los supervisores pueden supervisar una línea de tiempo de la señal de calidad de producto que se recibe de los sensores que se asignan a cada recurso de la máquina. Siga estos pasos para configurar la escala de tiempo.

1. Vaya a **Control de producción \> Ejecución de fabricación \> Estado del recurso**.
1. En el cuadro de diálogo **Configurar**, seleccione los siguientes campos:

    - **Recurso**: seleccione los recursos que quiera supervisar. (Si está trabajando con los datos de demostración, seleccione *3118* .)
    - **Serie temporal 1** – Seleccione el registro (clave métrica) que tenga el siguiente formato para su nombre: *ProductQuality;&lt;JobId&gt;&lt;AttributeName&gt;*
    - **Nombre para mostrar** - Ingresar *Valores de atributo de lote*.

La siguiente ilustración muestra un ejemplo de datos de calidad del producto en la página **Estado del recurso** cuando el valor está en el rango de valores aceptables.

![Datos de calidad del producto en la página de estado del recurso cuando el valor está dentro del rango.](media/sdi-product-quality-in-range.png "Datos de calidad del producto en la página de estado del recurso cuando el valor está dentro del rango")

La siguiente ilustración muestra un ejemplo de datos de calidad del producto cuando se detecta un valor fuera de rango.

![Datos de calidad del producto en la página de estado del recurso cuando un valor fuera del rango se detecta.](media/sdi-product-quality-out-of-range.png "Datos de calidad del producto en la página de estado del recurso cuando un valor fuera del rango se detecta")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Ver datos de calidad de producto en la página Notificaciones

En la página **Notificaciones**, los supervisores pueden ver la notificación que se genera cuando el sensor mide un valor de atributo de lote que cae fuera del umbral definido para el atributo de lote. Cada notificación proporciona una descripción general del trabajo de producción afectado por la interrupción y brinda la opción de reasignar el trabajo afectado a otro recurso.

Para abrir la página **Notificación**, vaya **Control de producción \> Consultas e informes \> Sensor de Data Intelligence \> Notificaciones**.

En la ilustración siguiente se muestra un ejemplo de la notificación de calidad de un producto.

![Ejemplo de una página de notificación de calidad.](media/sdi-product-quality-notification.png "Ejemplo de una página de notificación de calidad")
