---
title: Interfaz de equipo de gestión de material (MHAX)
description: Este tema describe cómo configurar la interfaz del equipo de manipulación de materiales (MHAX) para que pueda conectarse a sistemas externos de manipulación de materiales físicos (MH).
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7e71ca2877effe671723be53e844e8401714038a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565218"
---
# <a name="material-handling-equipment-interface-mhax"></a>Interfaz de equipo de gestión de material (MHAX)

[!include [banner](../../includes/banner.md)]

Puede usar la *interfaz del equipo de manipulación de materiales* (MHAX) para conectar sistemas externos de manipulación de materiales físicos (MH) a un almacén gestionado por la gestión avanzada de almacenes (WMS) en Microsoft Dynamics 365 Supply Chain Management. La interfaz entre los sistemas WMS y MH consta de dos colas: una para eventos salientes (WMS a MH) y otra para eventos entrantes (MH a WMS). El sistema WMS genera eventos de salida basados en líneas de trabajo que se crean durante varios procesos de creación y ejecución de trabajos. El sistema MH luego sondea periódicamente el sistema WMS en busca de nuevos eventos y procesa las respuestas. Una vez que el sistema MH ha terminado de manejar los eventos de acuerdo con las instrucciones de trabajo, envía eventos entrantes, como la finalización de la línea de trabajo y el picking corto.

La siguiente ilustración muestra los diversos elementos y el orden en que ocurren los procesos cuando usa la integración MHAX.

![Componentes e interacciones de MHAX.](media/mhax-components.png "Componentes e interacciones de MHAX")

A continuación, se ofrece una explicación de las interacciones que se muestran en la ilustración anterior:

1. Durante la creación o ejecución del trabajo, los eventos de salida se crean en la cola de salida.
2. El equipo MH se conecta al servicio de equipos MH, sondea cualquier evento nuevo que sea relevante para él y procesa esos eventos.
3. Cuando el equipo MH está listo para informar, se conecta nuevamente al servicio y envía eventos entrantes. Estos eventos son procesados inmediatamente por el procesador de cola.
4. Según los datos de eventos entrantes, el procesador de cola puede ejecutar el trabajo existente, modificarlo o crear un nuevo trabajo.

## <a name="turn-on-the-mhax-feature"></a>Activar la característica MHAX

Antes de poder utilizar la función MHAX, debe activar tanto su función como su clave de configuración.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
2. En el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**, active la función que se denomina *Interfaz del equipo de manipulación de materiales*.
3. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
4. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
5. Expanda **Comercio \> Gestión de almacén y transporte** y luego seleccione la casilla de verificación **Interfaz del equipo de manipulación de materiales**.
6. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Establecer parámetros MHAX

Debe establecer algunos parámetros generales en la página **Parámetros de la interfaz del equipo de manipulación de materiales** para configurar la función.

1. Vaya a **Interfaz del equipo de manipulación de materiales \> Configuración \> Parámetros de la interfaz del equipo de manipulación de materiales**.
2. En la pestaña **General**, establezca los campos siguientes:

    - **ID de usuario** - Seleccione un trabajador. Este trabajador se utilizará para ejecutar todas las operaciones de trabajo (selecciones y colocaciones) que se procesan a través de la cola de entrada.
    - **Habilitar ID de mensaje entrante** - Cuando esta opción se establece en *Sí*, si se recibe un ID de mensaje entrante duplicado, el mensaje será rechazado y un mensaje de error indicará que el mensaje ya existe. Cuando esta opción se establece en *No*, se permitirán ID de mensajes entrantes duplicados.

3. Sobre la pestaña **Secuencias numéricas**, seleccione las secuencias numéricas de todo el sistema que se deben usar para generar ID únicos para los elementos de la cola de entrada, los elementos de la cola de salida y los pares de líneas de trabajo.

## <a name="outbound-events"></a>Eventos salientes

En puntos específicos durante la creación o ejecución del trabajo, el sistema determina si debe generar eventos de salida para enviar al sistema MH. Si se configura una suscripción para un punto específico durante el procesamiento del almacén, el sistema genera el evento de acuerdo con la configuración de la suscripción.

### <a name="structure-of-outbound-events"></a>Estructura de eventos salientes

Cada evento de salida se identifica de forma única mediante un ID de cola de salida. El tipo de transacción saliente determina el tipo de evento. El almacén y el ID de la suscripción que generó el evento también se registran en el evento.

Para llevar datos al sistema MH, el evento de salida contiene 10 campos para datos (de **data01** a **data10**). Estos campos de datos tienen una asignación de uno a uno (1: 1) a los campos de la base de datos existente. Específicamente, se extraen de los campos de la línea de trabajo y de las tablas de encabezado de trabajo. Los campos se pueden seleccionar libremente. Los configura cuando crea la suscripción.

Además de los 10 campos de datos que tienen una asignación 1: 1 a los campos de la base de datos existente, el evento puede contener un campo de datos adicional que se conoce como *carga útil*. El contenido de este campo se genera mediante un código X ++ personalizado que se conoce como *generador de carga útil*. Cualquier generador de carga útil que deba utilizarse se configura en la suscripción.

Para garantizar que el sistema MH reciba cada ID de cola de salida solo una vez, se utiliza un campo de estado para especificar si un evento está listo para enviarse al sistema externo o si ya se ha enviado.

### <a name="outbound-queue-subscriptions"></a>Suscripciones de cola de salida

Antes de que se genere cualquier evento, se debe configurar una suscripción para indicarle a la función MHAX si debe generar eventos y cómo. Los eventos generados están etiquetados por el identificador de suscripción. Por lo tanto, varios sistemas MH pueden conectarse al mismo sistema WMS pero mantienen sus eventos separados. Cuando se consulta el servicio MHAX en busca de nuevos eventos, una suscripción es una de las opciones disponibles para recuperar los eventos.

Para crear una suscripción, vaya a **Interfaz del equipo de manipulación de materiales \> Configuración \> Suscripciones**. Para cada suscripción, están disponibles los siguientes parámetros:

- **ID de suscripción** - Un nombre único que identifica la suscripción.
- **Descripción** - Escriba una descripción de texto libre de la suscripción.
- **Depósito** - Los almacenes específicos por los que se deben filtrar los eventos.
- **Tipo de transacción saliente** - El tipo de eventos que debe contener la suscripción.
- **Generador de carga útil** - Una extensión de código opcional que puede ingresar información adicional en el campo **Carga útil** del evento saliente.

Se puede asociar una consulta a cada suscripción. Esta consulta filtra líneas de trabajo y encabezados para limitar aún más el trabajo que utilizará la suscripción para generar eventos. Para agregar una consulta a una suscripción, seleccione la casilla **Ejecutar consulta** de la suscripción correspondiente en la página **Suscripciones** y luego seleccione **Editar consulta** en el Panel de acciones. Aparece el editor de consultas estándar de Supply Chain Management.

Además, la suscripción incluye un *mapa de suscripción* que asigna campos desde el encabezado de trabajo o la línea de trabajo a algunos o todos los 10 campos de datos libres del evento de salida, según sea necesario. Para devolver información al servicio MHAX, normalmente incluirá el ID de registro de la línea de trabajo o el *ID de par de línea de trabajo*. (El ID de par de línea de trabajo es una nueva propiedad que permite al sistema usar un solo comando de retorno para procesar líneas de selección y colocación). Los campos restantes dependen del caso de uso. Más adelante en este tema se proporcionan algunos ejemplos.

Para configurar un mapa de suscripción, seleccione la suscripción correspondiente en la página **Suscripciones** y luego seleccione **Mapa de suscripción** en el Panel de acciones. En el cuadro de diálogo **Mapa de suscripción** que aparece, puede asignar una tabla y un campo para cada campo de datos disponible según lo requiera.

### <a name="outbound-event-types"></a>Tipos de eventos salientes

Esta sección describe los distintos tipos de eventos que están disponibles. (Los tipos de eventos también se conocen como *tipos de transacciones*). También explica cuándo se crea cada tipo de evento en el sistema WMS.

#### <a name="work-creation-events"></a>Eventos de creación de obra

Los eventos de creación de trabajo se crean después de que la aplicación genera el trabajo. Este comportamiento se aplica a la mayoría de los tipos de procesos de creación de trabajos, sobre todo a la creación de trabajos de selección y reabastecimiento. En general, si el trabajo se crea en un estado *Abierto*, que indica que el trabajo está listo para ser ejecutado por un trabajador, se generará un evento de creación de trabajo. Además, se generarán eventos de creación de obra para el trabajo de movimiento básico (no el trabajo de movimiento por plantilla), aunque ese trabajo no se crea como trabajo abierto.

Una excepción notable a este comportamiento es el trabajo de recuento cíclico, que actualmente no es compatible. Los recuentos de existencias en el sistema MH están fuera del alcance de MHAX y los resultados de los recuentos deben importarse a un diario de recuento de inventario.

Una vez creado el trabajo, el servicio MHAX procesa las líneas de trabajo que se generan y asigna un ID de par de líneas de trabajo a todas las líneas de trabajo generadas para cada encabezado de trabajo. El objetivo es agrupar todas las líneas de trabajo de picking con los puestos sucesivos bajo un ID de par de líneas de trabajo. (Los grupos corresponden a pares de picking / put en plantillas de trabajo). De esta manera, se puede utilizar una única ID para informar la finalización del trabajo para todas las líneas de pick and put relacionadas. El proceso de agrupación comienza con la primera línea y luego continúa con el mismo ID hasta que encuentra un par sucesivo de líneas de trabajo de colocación / selección. La ID de ejecución se asigna a la línea de venta de ese par. Una nueva ID que luego usó para la línea de selección del par en adelante. Este proceso continúa hasta que haya procesado todas las líneas que pertenecen al encabezado de trabajo.

Como característica especial de los eventos de creación de obra, si la opción **Ola bloqueada** está configurada en *Sí* en el encabezado del trabajo, los eventos que se generen tendrán un estado de *Obstruido* en lugar del estado habitual de *Listo* que se utiliza para enviarlos al sistema MH. La marca **Ola bloqueada** en el encabezado del trabajo indica que el encabezado del trabajo aún no está listo para que los trabajadores lo ejecuten, tal vez debido a un trabajo de reabastecimiento sin terminar. Cuando la marca **Ola bloqueada** se borra el indicador, los eventos que ya se han generado se desbloquean y están disponibles para que el sistema MH los recupere de la cola.

#### <a name="work-initiation-events"></a>Eventos de inicio de obra

Los eventos de inicio del trabajo se activan cuando el estado del trabajo cambia de *Abierto* a *En proceso* durante la actualización del trabajo.

#### <a name="work-completion-events"></a>Eventos de finalización de obra

Los eventos de finalización del trabajo se activan cuando el estado del trabajo cambia de *En proceso* a *Cerrado* durante la actualización del trabajo.

#### <a name="work-cancellation-events"></a>Eventos de cancelación de trabajo

Los eventos de cancelación del trabajo se activan cuando el estado del trabajo cambia de cualquier estado excepto *Cancelado* a *Cancelado* durante la actualización del trabajo. Además, todos los demás eventos relacionados con el encabezado del trabajo se eliminan de la cola de todas las suscripciones. De esta manera, se evita que los sistemas externos procesen eventos que no son necesarios.

#### <a name="pickput-completion-events"></a>Seleccionar / colocar eventos de finalización

Los eventos de finalización de selección/ubicación se activan cuando el estado de la línea de selección/ubicación cambia de *En proceso* a *Cerrado* durante la actualización de la línea de trabajo.

### <a name="monitor-the-outbound-queue"></a>Supervisar la cola de salida

Para revisar su cola de salida, vaya a **Interfaz del equipo de manipulación de materiales \> Común \> Cola de salida**. La página **Cola de salida** enumera todos los elementos de la cola de salida y su estado. Seleccione un elemento de la cola para ver sus detalles. Estos detalles incluyen el tipo de transacción del artículo, la suscripción que utilizó y los valores para cada campo de datos (de **data01** a **data10**) y la carga útil.

### <a name="clean-up-the-outbound-queue"></a>Limpiar la cola de salida

Eventualmente, su cola de salida comenzará a llenarse de elementos de cola que ya se han enviado. Para eliminar estos elementos, vaya a **Interfaz del equipo de manipulación de materiales \> Tareas periódicas \> Limpiar \> Limpieza de la cola de salida**.

## <a name="inbound-events"></a>Eventos entrantes

Esta sección describe los diversos tipos de eventos entrantes que el sistema MH puede informar al sistema WMS. También explica los datos que debe proporcionar el sistema MH y lo que hace cada evento entrante en el sistema WMS.

### <a name="structure-of-inbound-events"></a>Estructura de eventos entrantes

Cuando se envía un evento entrante, el sistema externo debe proporcionar el tipo de transacción entrante junto con hasta 10 parámetros (de **data01** a **data10**). La validación opcional puede garantizar que el servicio MHAX no haya recibido el mismo evento entrante más de una vez. Para habilitar esta validación, cada evento entrante debe tener un ID de mensaje único. Si se recibe un ID de mensaje duplicado, y si la opción **Habilitar ID de mensaje entrante** está configurada en *Sí* sobre la página **Parámetros de la interfaz del equipo de manipulación de materiales**, el mensaje será rechazado. Un mensaje de error indicará que el mensaje ya existe.

Además de los campos de datos entrantes, el sistema asigna un ID de cola de entrada único al evento.

### <a name="inbound-event-types"></a>Tipos de eventos entrantes

Esta sección describe los tipos de eventos entrantes (tipos de transacciones) que son compatibles y los datos que deben proporcionarse para que se procesen los eventos.

#### <a name="work-confirm-events"></a>Eventos de confirmación de trabajo

Los eventos de confirmación de trabajo requieren que los campos de datos entrantes incluyan la siguiente información:

- **data01** - El ID del par de líneas de trabajo.
- **data02** - El ID de registro de la línea de trabajo (`RecId` valor).

    > [!NOTE]
    > *Bien* el campo **data01** *o* el campo **data02** debe estar presente.

- **data03** - La identificación de la matrícula para elegir.
- **data04** - ID de la matrícula de destino del encabezado de trabajo.

Si se proporciona el ID del par de líneas de trabajo, todas las líneas de trabajo de picking, put o personalizadas que están marcadas por el ID del par de líneas de trabajo y que tienen un estado de *Abierto* o *En proceso*, se ejecutan secuencialmente. Si un ID de registro de línea de trabajo (valor `RecId`), la línea de trabajo debe ser una línea de trabajo de selección, colocación o personalizada que tenga un estado de *Abierto* o *En proceso*.

Las líneas de selección de ubicaciones controladas por matrículas requieren que **data03** especifique la placa de la que se debe elegir, independientemente de si las líneas están marcadas por el ID del registro de la línea de trabajo o el ID del par de la línea de trabajo. El campo **data04** debe especificar la matrícula de destino del encabezado de trabajo para la selección.

Poner líneas no acepta más información. Se ejecutan basándose únicamente en la ubicación de la línea de trabajo actual y la placa de matrícula de destino del trabajo. Si la colocación debe realizarse en una ubicación diferente, cambie la ubicación de la línea de trabajo como se describe en la sección [Anular eventos](#override-events) más adelante en este tema.

Las líneas de trabajo personalizadas no requieren, ni admiten, ninguna información adicional en el evento entrante.

#### <a name="short-pick-events"></a>Eventos de selección corta

Los eventos de selección corta requieren que los campos de datos entrantes incluyan la siguiente información:

- **data02** - El ID de registro de trabajo (`RecId` valor).
- **data03** - La identificación de la matrícula para elegir.
- **data04** – Cantidad para seleccionar.
- **data05** - El código de excepción de selección corta.
- **data06** - ID de la matrícula de destino del encabezado de trabajo.

> [!NOTE]
> El campo **data01** no se usa para eventos de selección cortos.

Este evento se parece al evento de confirmación de trabajo, pero solo se aplica a las líneas de picking.

#### <a name="override-events"></a><a id="override-events"></a>Anular eventos

Los eventos de anulación requieren que los campos de datos entrantes incluyan la siguiente información:

- **data01** - El ID de registro de trabajo (valor `RecId`).
- **data02** - El nuevo ID de ubicación.

La línea de trabajo debe tener un estado de *Abierto* o *En proceso* y la nueva ubicación debe existir.

#### <a name="license-plate-receipt-events"></a>Eventos de recibo de matrículas

Los eventos de recibo de matrículas requieren que los campos de datos entrantes incluyan la siguiente información:

- **data01** - La identificación de la matrícula de entrada para recibir.

El sistema realiza una operación de recepción de matrículas, basada en la matrícula que se pasa como el valor del campo **data01**.

### <a name="monitor-the-inbound-queue"></a>Supervisar la cola de entrada

Para revisar su cola de entrada, vaya a **Interfaz del equipo de manipulación de materiales \> Común \> Cola de entrada**. La página **Cola de entrada** enumera todos los elementos de la cola de entrada y su estado. Seleccione un elemento de la cola para ver sus detalles. Estos detalles incluyen el tipo de transacción del artículo, el ID de mensaje y los valores para cada campo de datos (de **data01** a **data10**).

Si se produjo un error u otro tipo de elemento de registro mientras se procesaban los eventos entrantes, puede inspeccionar el registro seleccionando **Registro de errores** en el Panel de acciones.

### <a name="inbound-event-processing"></a>Procesamiento de eventos de entrada

Los eventos entrantes se escriben primero en la base de datos y luego se ejecutan inmediatamente (sincrónicamente). Si ocurre un error durante el procesamiento, el evento aún se escribe en la cola, pero el estado se establece en *Con errores*. El servicio MHAX devuelve un mensaje de error al sistema MH y almacena el registro de errores en el registro de eventos entrantes para una investigación posterior.

Los eventos que tienen un estado de *Con errores* se pueden reprocesar más tarde si se corrige la condición de error. Para volver a procesarlos, siga uno de estos pasos:

- Vaya a **Interfaz del equipo de manipulación de materiales \> Común \> Cola de entrada**. Seleccione la cola entrante relevante y luego seleccione **Reprocesar** en el Panel de acciones.
- Vaya a **Interfaz del equipo de manipulación de materiales \> Común \> Volver a procesar cola de entrada con errores**. Aparece un cuadro de diálogo de trabajo por lotes estándar. Allí, puede configurar un filtro de registros y programar o ejecutar un trabajo por lotes para volver a procesar la cola.

Todas las operaciones de trabajo (selecciones y ubicaciones) se ejecutan utilizando el trabajador que se selecciona en el campo **ID de usuario** de la página **Parámetros de la interfaz del equipo de manipulación de materiales**.

### <a name="clean-up-the-inbound-queue"></a>Limpiar la cola de entrada

Eventualmente, su cola de entrada comenzará a llenarse de elementos de cola que ya se han procesado. Para eliminar estos elementos, vaya a **Interfaz del equipo de manipulación de materiales \> Tareas periódicas \> Limpiar \> Limpieza de la cola de entrada**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Obtenga una descripción general rápida utilizando el administrador de colas

Para obtener una descripción general rápida de toda la actividad relacionada con sus colas entrantes y salientes, vaya a **Interfaz del equipo de manipulación de materiales \> Espacios de trabajo \> Gestor de colas**. La página **Gestor de colas** proporciona un conjunto de pestañas e iconos que puede usar para monitorear y explorar sus colas. También proporciona enlaces útiles a la mayoría de las otras páginas que se mencionan en este tema.

## <a name="connect-to-the-mhax-service"></a>Conectar al servicio MHAX

MHAX se implementa como un servicio personalizado. Por lo tanto, es accesible a través de llamadas SOAP y REST. Aquí están las direcciones de los puntos finales SOAP y REST:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Recuperar mensajes de la cola de salida

Para recuperar mensajes de la cola de salida, utilice uno de los siguientes métodos:

- Use `readOutboundSubscriptionQueue` para recuperar los eventos basados en el ID de suscripción.
- Use `readOutboundWarehouseQueue` para recuperar los eventos según el tipo de evento y el ID del almacén en varias suscripciones.
