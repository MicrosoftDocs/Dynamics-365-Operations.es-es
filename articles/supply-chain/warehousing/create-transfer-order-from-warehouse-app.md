---
title: Crear pedidos de transferencia desde la aplicación de almacén
description: Este tema describe cómo crear y procesar pedidos de transferencia desde la función de la aplicación de almacén.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c30b0e74053480a08f84f4d7579021084ded5799
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436636"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Crear pedidos de transferencia desde la aplicación de almacén

[!include [banner](../includes/banner.md)]

Esta característica permite a los trabajadores de almacén crear y procesar pedidos de transferencia directamente desde la aplicación de almacén. Los trabajadores del almacén comienzan seleccionando el almacén de destino y luego pueden escanear una o más placas con la aplicación para agregar placas a la orden de transferencia. Cuando el trabajador del almacén selecciona **Orden completa**, un trabajo por lotes creará la orden de transferencia requerida y las líneas de orden según el inventario disponible registrado para esas placas.

## <a name="enable-the-create-transfer-orders-from-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Habilitar la característica para crear pedidos de transferencia desde la aplicación de almacén

Antes de poder usar esta característica, esta y sus requisitos previos deben estar habilitados en su sistema. Los administradores pueden usar la página [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario.

1. Primero habilite la característica [Procesar eventos de aplicaciones de almacén](warehouse-app-events.md), que se enumera en [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) como:
    - **Módulo**: gestión de almacén
    - **Nombre de característica** - Procesar eventos de aplicación de almacén
1. Luego habilite la característica *Crear pedidos de transferencia desde la aplicación de almacén*, que se enumera como:
    - **Módulo**: gestión de almacén
    - **Nombre de característica** - Crear y procesar pedidos de transferencia desde la aplicación de almacén
1. Para automatizar el procesamiento de los envíos salientes, también debe habilitar la característica [Confirmar envíos salientes de trabajos por lotes](confirm-outbound-shipments-from-batch-jobs.md). Esta característica aparece como:
    - **Módulo**: gestión de almacén
    - **Nombre de la característica**: Confirmar envíos salientes desde trabajos por lotes

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Configurar un elemento de menú del dispositivo móvil para crear pedidos de transferencia

A continuación, se incluyen pautas generales para configurar un elemento de menú de dispositivo móvil para crear una orden de transferencia. Dependiendo de sus requisitos comerciales para el nivel de automatización que se establecerá cuando los usuarios creen órdenes de transferencia desde el piso, se habilitarán diferentes configuraciones. El escenario de este documento describirá una de esas configuraciones.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccionar **Nuevo** para agregar un elemento de menú nuevo. Luego, realice los siguientes ajustes para comenzar:

    - **Nombre del elemento del menú** - Asigne un nombre como debería aparecer en Supply Chain Management.
    - **Título** - Asigne un nombre de menú como se debe presentar a los trabajadores en la aplicación del almacén.
    - **Modo** - Establezca en *Indirecto* (esta aplicación de almacén no creará trabajo).
    - **Código de actividad** - Ajustado como *Crear orden de transferencia a partir de matrículas* para permitir que los trabajadores del almacén creen una orden de transferencia basada en una o más placas escaneadas.

1. Utilice la opción **Política de creación de línea de orden de transferencia** para controlar cómo las líneas de orden de transferencia serán creadas por este elemento de menú. Las líneas se crearán/actualizarán según el inventario disponible registrado para las matrículas escaneadas. Elija uno de los siguientes valores:

    - **Sin reserva** - No se reservarán las líneas de la orden de transferencia.
    - **Matrícula guiada con reserva de línea** - Las líneas de la orden de transferencia se reservarán y utilizarán la opción de estrategia guiada por matrículas, que almacena las identificaciones de matrículas relevantes asociadas con las líneas de la orden. Por lo tanto, los valores de Id. de matrícula localizado se pueden utilizar como parte del proceso de creación de trabajo para las líneas de pedido de transferencia.

1. Utilizce la opción **Política de envío saliente** para agregar más automatización al proceso de envío de órdenes de transferencia salientes, según sea necesario. Cuando un trabajador selecciona el botón **Completar pedido**, la aplicación crea el evento de aplicación de almacén *Completar pedido*, que guardará el valor del campo **Política de envío saliente** para cada línea del pedido de transferencia actual. Más tarde, cuando la cola de eventos es procesada por un trabajo por lotes para crear la orden de transferencia, el trabajo por lotes puede leer el valor almacenado en este campo y, por lo tanto, puede controlar cómo ese trabajo procesa cada línea. Elija una opción de las siguientes:

    - **Ninguna** - No se realiza ningún procesamiento automatizado.
    - **Liberar al almacén** - Automatiza el proceso de liberación al almacén.
    - **Enviar confirmar** - Automatiza el proceso de confirmación del barco.
    - **Liberar y enviar confirmar** - Automatiza tanto la liberación al almacén como los procesos de confirmación de envío.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Agregar el elemento de menú del dispositivo móvil a un menú

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**
1. Seleccione **Editar**.
1. Seleccione un menú existente después de seleccionar el nuevo elemento de menú en **Menús y elementos de menú disponibles**. Agregue el elemento de menú seleccionando el botón de flecha hacia la derecha.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Cree una orden de transferencia basada en matrículas

La aplicación del almacén tiene un proceso simple para crear órdenes de transferencia basadas en matrículas. Para hacer esto, el trabajador hace lo siguiente usando la aplicación del almacén:

1. Cree la orden de transporte e identifique el almacén de destino.
1. Identifique cada placa que se enviará.
1. Seleccione **Completar pedido**.

>[!NOTE]
> Es posible que varios trabajadores asignen placas destinadas a la misma orden de transferencia mediante el uso del botón **Seleccionar orden de transferencia** para seleccionar un número de orden de transferencia existente, sin procesar, de la cola de eventos de la aplicación del almacén. Para obtener información sobre cómo encontrar los valores del número de orden de transporte, consulte [Consultar los eventos de la aplicación del almacén](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario proporciona una descripción general del proceso para obtener órdenes de transferencia creadas y procesadas automáticamente en función del inventario disponible registrado en las placas de matrícula seleccionadas.

Para trabajar en este escenario usando los valores sugeridos, debe trabajar en un sistema con datos de demostración instalados y seleccionar la entidad jurídica *USMF* antes de comenzar.

Este escenario asume que ya ha habilitado tanto la característica [Crear y procesar pedidos de transferencia desde la aplicación de almacén](#enable-create-transfer-order-from-warehouse-app) como la funcionalidad de [procesamiento de eventos de la aplicación de almacén](warehouse-app-events.md).

Además de configurar la orden de transferencia de creación en los elementos del menú del dispositivo móvil, también se deben configurar y habilitar plantillas adicionales, directivas de ubicación y trabajos por lotes.

### <a name="example-scenario-blueprint"></a>Plano de escenario de ejemplo

Usted es un minorista y tiene varias placas de matrícula, cada una con una combinación de artículos colocados en una ubicación específica dentro de uno de sus almacenes (*Almacén 51*). Le gustaría habilitar el proceso que permite a los trabajadores crear una orden de transferencia a otro almacén (*Almacén 61*) para una colección de matrículas escaneadas. Enviará-actualizará automáticamente la orden de transferencia tan pronto como se haya identificado la última placa para la orden.

![Ejemplo de proceso de orden de transporte automatizado](media/create-transfer-order-from-app-example.png "Ejemplo de proceso de orden de transporte automatizado")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Crear un elemento de menú del dispositivo móvil para crear pedidos de transferencia

Esta sección explica cómo crear un nuevo elemento de menú de dispositivo móvil para crear órdenes de transferencia. Seleccione el **Modo** como *Indirecto* y el **Código de actividad** como *Crear orden de transferencia a partir de matrículas*.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre del elemento del menú**, ingrese el nombre *Crear PARA*.
1. En el campo **Título**, ingrese la descripción *Crear para*.
1. En el campo **Modo**, seleccione *Indirecto*.
1. En **Código de actividad**, seleccione *Crear orden de transferencia a partir de matrículas*
1. En **Política de creación de línea de pedido**, seleccione *Matrícula guiada con reserva de línea*.
1. En **Política de envío saliente**, seleccione *Liberar y enviar confirmar*.
1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. Seleccione **Editar**.
1. Seleccione el menú **Inventario** existente y luego seleccione el nuevo elemento de menú en **Menús y elementos de menú disponibles**. Agregue el elemento de menú en el menú **Inventario** seleccionando el botón de flecha hacia la derecha.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Configure plantillas de trabajo para procesar automáticamente y dividir el trabajo por matrícula ubicada

Esta sección explica cómo habilitar una plantilla de trabajo para procesar automáticamente el trabajo creado por la plantilla cuando se lanza una ola.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Problema de transferencia*.
1. Seleccione **Nuevo** para crear una nueva plantilla de trabajo.
1. En el campo **Plantilla de trabajo**, ingrese *51 Proceso automático LP*.
1. En el campo **Descripción de plantilla de trabajo**, ingrese *51 Proceso automático LP*.
1. Seleccione la casilla **Procesar automáticamente**. Esto debe seleccionarse para que se procesen los pasos de automatización.
1. En los datos de demostración, ya existe una plantilla de trabajo *51 Transferencia*, edite el campo **Secuencia de números** para que la nueva plantilla de trabajo tenga un número de secuencia más bajo que la plantilla de trabajo existente *51 Transferencia*.
1. Seleccione **Guardar** en la barra de herramientas para habilitar la ficha desplegable **Detalles de plantilla de trabajo**.
1. En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo**. Agregará dos líneas.
1. En el campo **Tipo de trabajo**, seleccione *Recoger*.
1. En el campo **Identificador de la clase de trabajo**, seleccione *TransfOut*.
1. En la barra de herramientas **Detalles de plantilla de trabajo**, seleccione **Nuevo**.
1. En el campo **Tipo de trabajo**, seleccione *Colocar*.
1. En el campo **Identificador de la clase de trabajo**, seleccione *TransfOut*.
1. Seleccione **Guardar** para habilitar el campo **Código de directiva**.
1. En **Tipo de trabajo**, en la línea *Ubicación*, seleccione **Código de directiva** *Baydoor*. Asegúrese de que esta nueva plantilla de trabajo obtenga la más baja **Secuencia de números**.
1. En la barra de herramientas, seleccione **Editar consulta** para abrir el editor de consultas.
1. En la ficha **Intervalo**, seleccione **Agregar**.
1. En la línea agregada, en **Campo**, seleccione *Almacén*.
1. En el campo **Criterios**, seleccione *51*.
1. Seleccione la pestaña **Ordenar**.
1. Seleccione **Añadir** y establezca **Campo** en *Identificación de matrícula ubicada*. Seleccionar este campo habilitará el botón de la barra de herramientas **Descansos del encabezado de trabajo**.
1. Seleccione **Aceptar** seguido de **Sí** para restablecer la agrupación y volver a la página **Plantillas de trabajo**.
1. Seleccione **Descansos del encabezado de trabajo** y habilite **Agrupar por este campo** para **Identificación de matrícula ubicada** y cierre.

> [!NOTE]
> No todas las configuraciones se pueden procesar automáticamente, por ejemplo, artículos de peso capturado y el uso de dimensiones de seguimiento mixtas.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Configurar directivas de ubicación para la estrategia guiada por matrículas

Esta sección explica cómo configurar un proceso de selección de directiva de ubicación para usar la estrategia **Matrícula guiada**.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. Seleccione **Editar**.
1. En el encabezado de la lista de navegación, seleccione el **Tipo de orden de trabajo** *Problema de transferencia*.
1. En la lista de navegación, seleccione la directiva de ubicación existente **51 PARA Picking**.
1. En la ficha **Líneas**, seleccione la casilla **Permitir dividir**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para agregar una línea de acción.
1. En el campo **Nombre**, especifique *Guiado por LP*.
1. En el campo **Estrategia**, seleccione *Guiado por matrícula*. Esta acción necesita el número de secuencia más bajo.
1. Seleccione **Guardar** en la barra de herramientas.
1. Seleccione el icono de la página **Actualizar** en la barra de herramientas.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione la línea *TOPick*.
1. En la barra de herramientas **Acciones de directiva de ubicación**, seleccione **Mover hacia abajo** para cambiar el número de secuencia para que sea mayor que el número de secuencia para la acción recién creada *Guiado por LP*.

> [!NOTE]
> La estrategia guiada por matrículas tratará de reservar y crear trabajo de picking en las ubicaciones que contienen las matrículas solicitadas que se han asociado con las líneas de orden de transferencia. Pero si esto no es posible y aún desea crear un trabajo de picking, debe recurrir a otra estrategia de acción de directiva de ubicación y tal vez también buscar inventario en otra área del almacén, según las necesidades de su proceso comercial.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar un trabajo por lotes para procesar eventos de aplicaciones de almacén

Esta sección explica cómo configurar un trabajo por lotes programado para procesar eventos de aplicaciones de almacén.

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar eventos de aplicación de almacén**.
2. En el cuadro de diálogo, habilite **Procesamiento por lotes** bajo la sección **Ejecutar en segundo plano**.
3. Seleccione **Repetición** y configure el trabajo por lotes para procesar según el intervalo necesario para su negocio.
4. Seleccione **Aceptar** para volver al cuadro de diálogo principal.
5. Seleccione **Aceptar** en el cuadro de diálogo principal para agregar el trabajo a la cola por lotes.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Configurar un trabajo por lotes para liberar pedidos de transferencia automáticamente

Esta sección explica cómo configurar un trabajo por lotes programado para liberar las órdenes de transferencia que se han marcado como "listas para lanzar".

1. Vaya a **Gestion de almacén \> Despachar al almacén \> Despacho automático de pedidos de transferencia**.
1. En el cuadro de diálogo, expanda la sección **Registros para incluir**.
1. En la sección **Registros a incluir**, seleccione **Filtro**.
1. En la página de consulta **WHSTransferAutoRTWQuery**, pestaña **Rango**, seleccione **Añadir** para agregar una nueva línea a la consulta.
1. En el campo **Tabla** de la nueva linea, seleccione el menú desplegable y seleccione la tabla **Transferir liberación de línea al almacén**.
1. En el menú desplegable **Campo**, seleccione **Política de envío saliente**.
1. En el campo **Criterios**, seleccione **Liberar y enviar confirmar**.
1. En la linea donde **Campo** se establece en *Desde el almacén*, en el campo **Criterios**, seleccione *51*.
1. Seleccione **Aceptar** para volver al cuadro de diálogo principal.
1. Expanda la sección **Ejecutar en segundo plano** para configurar el procesamiento por lotes.
1. Habilite **Procesamiento por lotes** bajo la sección **Ejecutar en segundo plano**.
1. Seleccione **Repetición** y configure el trabajo por lotes para procesar según el intervalo necesario para su negocio.
1. Seleccione **Aceptar** para volver al cuadro de diálogo principal.
1. Seleccione **Aceptar** en el cuadro de diálogo principal para agregar el trabajo a la cola por lotes.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Configurar el trabajo por lotes "Procesar envío saliente"

Esta sección explica cómo configurar un trabajo por lotes programado para ejecutar la confirmación de envío saliente para cargas listas para enviar relacionadas con líneas de orden de transferencia que están "listas para enviar".

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar envíos salientes**.
1. Expanda la sección **Registros que incluir**.
1. Seleccione **Filtro**.
1. En la consulta **WHSLoadShipConfirm**, seleccione la pestaña **Uniones**.
1. Expanda la jerarquía de la tabla para que **Cargas** y **Cargar detalles** se amplíen.
1. Seleccione la tabla **Detalles de la carga**.
1. Seleccione el botón **Agregar unión de tabla**.
1. En la lista de relaciones de tabla, filtre o busque por la columna **Relación** para *Líneas de orden de transferencia (referencia)*.
1. Concéntrese en la relación de la tabla en la lista y luego presione el botón **Seleccionar**.
1. Seleccione la tabla **Líneas de orden de transferencia**.
1. Seleccione el botón **Agregar unión de tabla**.
1. En la lista de relaciones de tabla, filtre o busque por la columna **Relación** para *Campos adicionales de transferencia de inventario (Id. de registro)*.
1. Concéntrese en la relación de la tabla en la lista y luego presione el botón **Seleccionar**.
1. Seleccione la ficha **Intervalo**.
1. En las tablas de consulta **Rango**, configurará tres rangos de criterios de consulta. Seleccione el botón **Agregar** para agregar una línea.
1. Agregar un rango para la tabla **Cargas**. Establezca **Campo** en *Estado de carga* y establezca **Criterios** en *Cargado*.
1. Agrega otro rango para la tabla **Campos adicionales de transferencia de Invent**. Establezca **Campo** en *Política de envío saliente* y establezca **Criterios** en *Liberar y enviar confirmar*.
1. Agregue otro rango para la tabla **Cargar detalles**. Establezca **Campo** en *Referencia* y establezca **Criterios** en *Envío de orden de transferencia*.
1. Seleccione **Aceptar** para volver al cuadro de diálogo principal.
1. Expanda la sección **Ejecutar en segundo plano**.
1. Habilite **Procesamiento por lotes**.
1. Seleccione **Repetición** y configure el trabajo por lotes para procesar según el intervalo necesario para su negocio.
1. Seleccione **Aceptar** para volver al cuadro de diálogo principal.
1. Seleccione **Aceptar** en el cuadro de diálogo principal para agregar el trabajo a la cola por lotes.

> [!NOTE]
> Para obtener más información, consulte [Confirmar envíos salientes de trabajos por lotes](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Procesando el ejemplo de "Crear orden de transporte desde la aplicación de almacén"

### <a name="add-on-hand-on-a-license-plate"></a>Agregue a mano en una matrícula

Como punto de partida para este escenario, deberá tener a mano una placa que contenga el inventario físico disponible.

| Artículo | Almacén | Estado de inventario | Ubicación | Matrícula de entidad de almacén | Cantidad |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Disponibles | LP-010 | LP10 | 1 |
| A0002 | 51 | Disponibles | LP-010 | LP10 | 2 |

Agregue cantidades disponibles de inventario físico utilizando los siguientes valores:

> [!NOTE]
> Deberá crear la placa de matrícula y utilizar ubicaciones que le permitan transportar artículos mixtos, como LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Crear y procesar pedidos de transferencia desde la aplicación de almacén

1. Abra la aplicación e inicie sesión como usuario *51*. El almacén de usuarios actual será 51.
1. Seleccione el elemento del menú **Crear para** desde la ubicación del menú a la que lo agregó durante la configuración.
1. Inicie la creación de una orden de transporte ingresando el almacén de destino (A almacén) en el campo **Almacén**, ingrese *61*. La nueva orden de transporte irá del almacén actual 51 (Desde el almacén) al almacén de destino *61*.
1. Seleccione **Aceptar**.
1. Escanee una identificación de matrícula en el campo **Matrícula**. Ingrese la matrícula del inventario agregado en un paso anterior, *LP10*.
1. Seleccione **Aceptar**.
1. Seleccione el botón de menú y luego seleccione **Orden completa** para finalizar la creación de la orden de transferencia de la aplicación de almacén.

Para el ejemplo mencionado, dos **Eventos de la aplicación de almacén** (*Crear orden de transferencia* y *Orden de transferencia completa*) son usados.

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Consultar los eventos de la aplicación del almacén

Puede ver la cola de eventos y los mensajes de eventos generados por la aplicación del almacén yendo a **Gestión de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de la aplicación de almacén**.

Los mensajes de eventos *Crear orden de transferencia* recibirán el estado *Esperando*, lo que significa que el trabajo por lotes **Procesar eventos de aplicaciones de almacén** no recogerá ni procesará los mensajes de eventos. Tan pronto como el mensaje del evento se actualice al estado *Puesto en cola*, el trabajo por lotes procesará los eventos. Esto sucederá al mismo tiempo que la creación del evento *Orden de transferencia completa* (cuando un trabajador selecciona el botón **Orden completa** en la aplicación del almacén). Cuando los mensajes del evento *Crear orden de transferencia* se han procesado, el estado se actualiza a *Terminado* o *Error*. Cuando el estado *Orden de transferencia completa* se actualiza a *Terminado*, todos los eventos relacionados se eliminan de la cola.

Porque **Eventos de la aplicación de almacén** para la creación de datos de orden de transferencia no serán procesados por el trabajo por lotes antes de que los mensajes se actualicen al estado *Puesto en cola*, deberá buscar los números de orden de transferencia solicitados como parte del campo **Identificador**. El campo **Identificador** está en el encabezado de la página **Eventos de la aplicación de almacén**.

Como parte del procesamiento de eventos de almacén, la creación de la línea de orden de transferencia puede fallar. En este caso, el estado del mensaje de evento se actualiza a *Error* y puede usar la información de **Registro de lotes** para saber por qué y tomar medidas para corregir cualquier problema.

Los problemas típicos podrían estar relacionados con la falta de configuración del proceso, como un almacén de tránsito faltante para el evento *Crear orden de transferencia*. En un ejemplo como este, agregaría un almacén de tránsito al almacén de envío y usaría la opción **Reiniciar** para cambiar el estado de todos los mensajes de eventos de la aplicación de almacén de *Error* a *Puesto en cola*, lo que significa que el trabajo por lotes procesará los mensajes de evento nuevamente después de la corrección de los datos de configuración.

Dentro de los entornos de producción, las excepciones estarían más relacionadas con el proceso, como tener una matrícula solicitada, que en el momento del procesamiento del trabajo por lotes está vacía y, por lo tanto, no se crean líneas de orden de transferencia. Este mensaje de evento fallido puede eliminarse utilizando la opción **Eliminar** opción o puede agregar el físico necesario a mano en la matrícula y usar la opción **Reiniciar** para todos los mensajes de eventos relacionados.

Para más información, vea [Procesamiento de eventos de la aplicación de almacén](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Seguimiento del procesamiento del escenario de ejemplo

Durante este escenario, se produce lo siguiente:

1. Usando la aplicación del almacén, seleccionó un elemento de menú que usa el código de actividad **Crear orden de transferencia a partir de matrículas**.
1. La aplicación le pidió que seleccionara el almacén de destino para la orden de transferencia. El almacén de origen es siempre en el que está conectado actualmente como trabajador.
1. En la selección del almacén de destino, el sistema reservó un número de identificación para la próxima orden de transferencia (basado en la secuencia de números de orden de transferencia definida en su sistema) pero aún no creó la orden de transferencia.
1. Cuando escaneaste la matrícula *LP10* que contiene inventario disponible que debe trasladarse al nuevo almacén, un **Evento de aplicación de almacén** fue agregado a la cola de eventos para ser procesado más tarde. El evento del almacén contenía detalles del mensaje sobre el escaneo, incluido el número de orden de transferencia previsto.
1. En la aplicación del almacén, cuando se selecciona el botón **Orden completa**, un nuevo evento de aplicación de almacén, **Orden de transferencia completa**, se crea y el evento existente relacionado, **Crear orden de transferencia**, cambia el estado a **Puesto en cola**.
1. En la parte trasera, el **Proceso por lotes de eventos de aplicaciones de almacén** recogió el eveneto **Puesto en cola** y recogió lo disponible relacionado con la matrícula escaneada. Sobre la base de la disponibilidad, se crearon el registro de la orden de transporte real y las líneas asociadas. El trabajo también pobló el campo **Política de envío saliente** para la orden de transferencia con el valor basado en la configuración de *Liberar y enviar confirmar* y vinculó la matrícula con las líneas para la estrategia **Guiado por matrícula guiada**.
1. Basado en el valor del campo **Política de envío saliente** de la línea de la orden de transferencia, la consulta **Liberación automática del trabajo por lotes de órdenes de transferencia** ahora resultó en la liberación de la orden de transferencia al almacén de envío. Y debido a la configuración de los valores usados para **Plantilla de onda**, **Plantilla de trabajo** y **Directivas de ubicación**, el trabajo tiene procesos automáticos que resultan en el **Estado de carga** actualizado como *Cargado*.
1. **Procesar trabajo por lotes de envío saliente** se ejecuta para la carga, lo que resulta en el envío de la orden de transferencia y se genera el Aviso de envío anticipado (ASN).
1. El momento de todos estos eventos depende de la configuración de **Reaparición** para los trabajos por lotes creados.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="mobile-device-menu-item-setup"></a>Configuración del elemento de menú del dispositivo móvil

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>¿Por qué no puedo ver "Crear orden de transferencia desde matrícula" en la lista desplegable de actividades de trabajo del elemento del menú?

La característica *Crear y procesar pedidos de transferencia desde la aplicación de almacén* debe habilitarse. Para más información, vea [Habilitar la creación de órdenes de transferencia desde la aplicación Warehouse](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-app-processes"></a>Procesos de aplicación de almacén

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>¿Por qué no puedo ver el botón de menú "Completar pedido"?

Debe tener al menos una placa asignada a la orden de transferencia.

#### <a name="can-several-warehouse-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>¿Pueden varios usuarios de aplicaciones de almacén agregar placas de matrícula a la misma orden de transferencia al mismo tiempo?

Sí, varios trabajadores del almacén pueden escanear matrículas en la misma orden de transferencia.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>¿Se puede agregar la misma placa a diferentes órdenes de transferencia?

No, solo se puede agregar una placa a una orden de transferencia a la vez.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>Después de haber seleccionado el botón "Completar pedido", ¿puedo agregar más placas para ese pedido de transferencia?

No, no puede agregar más placas a una orden de transferencia que tiene un evento de aplicación de almacén **Orden de transferencia completa**.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>¿Cómo puedo encontrar órdenes de transferencia existentes para usar a través del botón "Seleccionar orden de transferencia" en la aplicación del almacén, si la orden aún no se ha creado en el sistema backend?

Actualmente, no puede buscar órdenes de transferencia en la aplicación, pero puede encontrar los números de las órdenes de transferencia en la página **Eventos de la aplicación de almacén**. Para más información, vea [Consultar los eventos de la aplicación de almacén](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-app"></a>¿Puedo seleccionar manualmente el número de orden de transferencia que se utilizará desde la aplicación del almacén?

Solo se admiten los números de orden de transferencia generados automáticamente mediante secuencias de números.

### <a name="background-processing"></a>Procesamiento en segundo plano

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>¿Cómo debo limpiar los registros en las tablas de mensajes de la cola de eventos de mi aplicación de almacén?

Puede ver y mantener esto en la página **Eventos de la aplicación de almacén**. Para más información, vea [Consultar los eventos de la aplicación de almacén](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>¿Por qué la orden de transferencia "Fecha de recepción" no se actualiza según mi configuración de "Control de fecha de entrega"?

Las órdenes de transporte se crean sin utilizar las capacidades de **Control de fecha de entrega**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>¿Puedo usar una placa que tenga un inventario físico negativo a mano?

La función solo admite cantidades físicas positivas disponibles. Asegúrese de tener cantidades físicas positivas disponibles en el nivel de estado de inventario y almacén antes de asignar placas de matrícula a una orden de transferencia.
