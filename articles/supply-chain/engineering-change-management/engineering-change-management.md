---
title: Administrar cambios en productos de ingeniería
description: Este tema proporciona información acerca de la gestión de cambios de ingeniería. La gestión de cambios de ingeniería proporciona procesos estructurados para gestionar los cambios en los productos de ingeniería, desde proponer, solicitar y realizar cambios, hasta revisar y aprobar cambios, evaluar su impacto en las transacciones existentes y darles seguimiento.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 93f5c3e4951784a6c4925b8f9026816bfaf551ee
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102922"
---
# <a name="manage-changes-to-engineering-products"></a>Administrar cambios en productos de ingeniería

[!include [banner](../includes/banner.md)]

La gestión de cambios de ingeniería proporciona procesos estructurados para gestionar los cambios en los productos de ingeniería. Puede usar el proceso *solicitud de cambio de ingeniería* para proponer y solicitar cambios, y luego usar el proceso *orden de cambio de ingeniería* para realizar esos cambios. Los usuarios pueden crear solicitudes de cambio de ingeniería u órdenes de cambio de ingeniería, y luego hay un proceso para revisarlas y aprobarlas, evaluar su impacto en las transacciones existentes y hacer un seguimiento de ellas.

## <a name="engineering-change-requests"></a>Solicitudes de cambio de ingeniería

El proceso de solicitud de cambio de ingeniería le permite capturar solicitudes de cambios de todos los departamentos relevantes de su empresa. No importa si trabaja como ingeniero o en el departamento de Fabricación, Abastecimiento, Almacén o Ventas: cualquiera puede utilizar una solicitud de cambio de ingeniería para solicitar un cambio. Este cambio puede ser una idea para un nuevo producto, un problema que descubrió mientras trabajaba con un producto existente, una sugerencia para mejorar un producto existente u otra cosa.

Después de que alguien envía una solicitud de cambio, el proceso *revisión y aprobación* se gestiona mediante un flujo de trabajo que identifica quién debe aprobar el cambio (por ejemplo, el propietario del producto).

Para configurar un flujo de trabajo para órdenes de cambio de ingeniería o solicitudes de cambio de ingeniería, vaya a **Gestión de cambios de ingeniería \> Flujos de trabajo de ingeniería**. Seleccione **Nuevo**, seleccione si el flujo de trabajo se utilizará para revisar órdenes de cambio de ingeniería o solicitudes de cambio de ingeniería, y luego configure el flujo de trabajo.

Para obtener más información sobre los flujos de trabajo, consulte [Visión general del sistema de flujos de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) Para obtener más información acerca de propietarios de productos, vea [Propietarios de productos](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Crear nueva solicitud de cambio de ingeniería

Para crear una solicitud de cambio de ingeniería, siga uno de estos pasos.

- Vaya a **Gestión de cambios de ingeniería \> Común \> Gestión de cambios de ingeniería \> Solicitudes de cambio de ingeniería** y luego seleccione **Nuevo** en el Panel de acciones.
- Abra la página **Detalles de producto** de un producto de ingeniería existente. Luego, en el Panel de acciones, en la pestaña **Ingeniero**, en el grupo **Gestión de cambios de ingeniería**, seleccione **Solicitud de cambio de ingeniería \> Nueva solicitud de cambio de ingeniería**.

Se crea una nueva solicitud de cambio. Ahora puede configurar los campos en cada ficha desplegable como se describe en las siguientes subsecciones.

#### <a name="general-fasttab"></a>Ficha desplegable General

La ficha desplegable **General** le permite proporcionar una descripción básica de la solicitud de cambio. En la tabla siguiente se describen los campos de esa ficha desplegable.

| Campo | Descripción |
|---|---|
| Cambiar solicitud | Permite especificar un nombre para la solicitud de cambio de ingeniería. |
| Cargo | Ingrese texto que describa o identifique brevemente los cambios en la solicitud. |
| Prioridad | Seleccione un valor para indicar qué tan alta es la prioridad del cambio. Puede personalizar los valores disponibles para su empresa, según sea necesario. (Para más información, vea [Establecer valores comunes para la gestión de cambios de ingeniería](engineering-change-management-setup.md)). |
| Categoría | Seleccione un valor para describir el tipo de cambio que solicita. Puede personalizar los valores disponibles para su empresa, según sea necesario. (Para más información, vea [Establecer valores comunes para la gestión de cambios de ingeniería](engineering-change-management-setup.md)). |
| Gravedad | Seleccione un valor para indicar la gravedad del problema que debe solucionarse implementando la solicitud. Puede personalizar los valores disponibles para su empresa, según sea necesario. (Para más información, vea [Establecer valores comunes para la gestión de cambios de ingeniería](engineering-change-management-setup.md)). |
| Solicitado por | Nombre del usuario que creó la solicitud. |
| En | Fecha de creación de la solicitud. |
| Estado | El estado de la solicitud. Cuando se crea una solicitud por primera vez, el estado es *Creado*. Cuando se aprueba la solicitud, el estado cambia a *Aprobado*. Si se ha creado una orden de cambio relacionada para la solicitud, el estado cambia a *Seguimiento*. |
| Cambiar pedido | El número de orden de cambio, si la solicitud de cambio se siguió mediante una orden de cambio. |

#### <a name="information-fasttab"></a>Ficha desplegable Información

La ficha desplegable **Información** le permite agregar más información sobre la solicitud.

Para agregar una fila a la cuadrícula, seleccione **Nuevo** en la barra de herramientas sobre la cuadrícula y luego seleccione una de las siguientes opciones:

- **Archivo** – Cargar un archivo.
- **Imagen** - Subir un archivo de imagen.
- **Nota** - Introduzca una nota directamente en la cuadrícula.
- **URL** - Introduzca una URL directamente en la cuadrícula.

En la tabla siguiente se describen los campos de cada fila.

| Campo | Descripción |
|---|---|
| Fecha y hora de creación | La fecha y hora de creación de la fila. |
| Tipo | El tipo de información para la que se creó la fila (archivo, imagen, nota o URL). |
| Descripción | Especifique una descripción para la fila. |
| Restricción | Un valor que indica si la información que se ha agregado proviene de una fuente interna o externa. |
| Vinculado | Una casilla de verificación seleccionada indica que la fila incluye un archivo adjunto (archivo o imagen). Para descargar el archivo adjunto, seleccione la fila y luego seleccione **Abierto** en la barra de herramientas sobre la cuadrícula. |

#### <a name="products-fasttab"></a>Ficha desplegable Productos

La ficha desplegable **Productos** le permite enumerar cada producto afectado por la solicitud de cambio. Puede utilizar los botones de la barra de herramientas para agregar productos a la cuadrícula o eliminar productos.

La lista es meramente informativa. Por lo tanto, puede agregar tantos productos relacionados como considere relevantes. Si crea una solicitud de cambio desde la página **Detalles de producto** de un producto existente, ese producto debe aparecer en la ficha desplegable **Productos** después de guardar el registro de solicitud.

#### <a name="source-fasttab"></a>Ficha desplegable Origen

La ficha desplegable **Origen** le permite realizar un seguimiento del punto de inicio de la solicitud de cambio. Es útil si, por ejemplo, desea ver si la solicitud de cambio se creó a partir de un pedido de cliente, quién la creó y en qué empresa se creó.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Evaluar el impacto comercial de una solicitud de cambio y enviar notificaciones

Cuando revisa una solicitud de cambio, puede buscar dependencias. De esta manera, puede evaluar el impacto del cambio solicitado en transacciones abiertas, como pedidos de venta, pedidos de producción e inventario disponible. A medida que revisa las solicitudes de cambios, puede enviar notificaciones a las personas responsables de cumplir con los distintos tipos de pedidos relacionados.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Revise las transacciones afectadas, bloquee las transacciones seleccionadas y envíe notificaciones

Para revisar las transacciones afectadas, bloquear las transacciones seleccionadas y enviar notificaciones relacionadas, siga estos pasos.

1. Vaya a **Gestión de cambios de ingeniería \> Común \> Gestión de cambios de ingeniería \> Solicitudes de cambio de ingeniería**.
1. Abra una solicitud de cambio existente o seleccione **Nuevo** en el Panel de acciones para crear una nueva solicitud de cambio.
1. En el panel de acciones, en la pestaña **Solicitud de cambio**, en el grupo **Impacto de negocios**, seleccione uno de los siguientes botones:

    - **Buscar** - Analiza todas las transacciones abiertas y luego abre el cuadro de diálogo **Impacto empresarial en transacciones abiertas**, que enumera todas las transacciones que se verán afectadas por el cambio.
    - **Ver búsqueda anterior** - Abre el cuadro de diálogo **Impacto empresarial en transacciones abiertas**, que enumera los resultados de la búsqueda anterior. (No se realiza una nueva búsqueda).

1. El cuadro de diálogo **Impacto empresarial en las transacciones abiertas** proporciona un conjunto de pestañas, cada una de las cuales muestra una lista de transacciones afectadas de un tipo específico (**Pedidos de ventas**, **Pedidos de compras**, **Pedidos de producción**, **Inventario** y similares). Cada pestaña también muestra un número que indica el número de transacciones afectadas de ese tipo. Seleccione una pestaña para ver la lista relevante.
1. Para trabajar con una transacción en la lista, selecciónela y luego seleccione uno de los siguientes botones en la barra de herramientas:

    - **Ver transacción**: abre el registro de transacción seleccionado.
    - **Bloquear pedido**: este botón está disponible solo en la pestaña **Pedidos de ventas**. Selecciónelo para bloquear el pedido de ventas seleccionado.
    - **Bloquear línea**: este botón está disponible solo en la pestaña **Pedidos de compras**. Selecciónelo para bloquear la línea de pedido de compras seleccionada.
    - **Notificar al responsable**: este botón está disponible solo en la pestaña **Pedidos de ventas**. Selecciónelo para enviar una notificación de cambio al usuario que está configurado como responsable del pedido de ventas seleccionado. Para obtener más información sobre quién puede ver las notificaciones y cómo puede verlas, consulte [Revisar y procesar notificaciones de cambios para transacciones](#review-notifications).
    - **Notificar pedido**: este botón está disponible solo en la pestaña **Pedidos de compras**. Selecciónelo para enviar una notificación de cambio al usuario que está configurado como el que pide el pedido de ventas seleccionado. Para obtener más información sobre quién puede ver las notificaciones y cómo puede verlas, consulte [Revisar y procesar notificaciones de cambios para transacciones](#review-notifications).
    - **Notificar producción**: este botón está disponible solo en la pestaña **Pedidos de producción**. A diferencia de los pedidos de ventas y los pedidos de compras, los pedidos de producción no tienen un solo usuario que se establezca como responsable de ellas de principio a fin. En cambio, varios supervisores o planificadores suelen tomar posesión de un sitio específico o de una parte específica de la producción (por ejemplo, para recursos o grupos de recursos específicos). Por lo tanto, cuando selecciona este botón, todos los usuarios responsables de cualquier recurso relacionado con la orden de producción seleccionada reciben una notificación de cambio. Para obtener más información sobre quién puede ver las notificaciones y cómo puede verlas, consulte [Revisar y procesar notificaciones de cambios para transacciones](#review-notifications).
    - **Notificar preparador**: este botón está disponible solo en la pestaña **Solicitud de compra**. Selecciónelo para enviar una notificación de cambio al usuario que está configurado como el preparador de la solicitud de compra seleccionada. Para obtener más información sobre quién puede ver las notificaciones y cómo puede verlas, consulte [Revisar y procesar notificaciones de cambios para transacciones](#review-notifications).
    - **Notificar al responsable de ventas**: este botón está disponible solo en la pestaña **Presupuestos**. Selecciónelo para enviar una notificación de cambio al usuario que está configurado como responsable del presupuesto seleccionado. Para obtener más información sobre quién puede ver las notificaciones y cómo puede verlas, consulte [Revisar y procesar notificaciones de cambios para transacciones](#review-notifications).
    - **Rechazar**: este botón está disponible solo en la pestaña **Inventario**. Selecciónelo para rechazar el inventario seleccionado.
    - **Ver historial**: abre un historial de acciones que se han realizado en la transacción seleccionada utilizando el cuadro de diálogo **Impacto empresarial en las transacciones abiertas**. (Por ejemplo, el historial muestra si se han enviado notificaciones o si se han bloqueado transacciones). 
    - **Ver todas las transacciones**: abre la lista completa de todas las transacciones, no solo las transacciones abiertas.

> [!IMPORTANT]
> El botón **Notificar producción** está disponible solo si la función *Notificaciones de ingeniería para producción* está activada en su sistema. Para obtener instrucciones sobre cómo activar o desactivar esta característica y sus requisitos previos, consulte [Información general de la gestión de cambios de ingeniería](product-engineering-overview.md).

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>Revisar y procesar notificaciones de cambios para transacciones

Puede leer y procesar las notificaciones de cambio que recibe de las siguientes formas:

- Excepto en el caso de las órdenes de producción, las notificaciones de cambios para las transacciones de las que es responsable aparecen en el Centro de actividades. El botón **Mostrar mensajes** (símbolo de campana) en el lado derecho de la barra de navegación indica cuando un mensaje del Centro de actividades está disponible para usted. Seleccione el botón **Mostrar mensajes** para abrir el Centro de actividades y revisar los mensajes.
- Para ver todas los pedidos de producción para los que se ha enviado una notificación de ingeniería, vaya a **Pedidos de producción \> Pedidos de producción \> Todos los pedidos de producción**. Luego, en el panel de acciones, en la pestaña **Pedido de producción**, en el grupo **Solicitar cambio de ingeniería**, seleccione **Notificaciones de ingeniería** para abrir la página **Notificaciones de ingeniería**.
- Para los pedidos de producción, puede optar por revisar solo las notificaciones de cambios que se aplican a los recursos de producción que administra. En el espacio de trabajo **Gestión de planta de producción**, en el Panel de acciones, seleccione **Configurar mi espacio de trabajo** para filtrar la página para que muestre solo información sobre las unidades de producción, grupos y / o recursos que administra. En la sección **Resumen**, un mosaico que se llama **Pedidos de producción con productos modificados** muestra un recuento de notificaciones que coinciden con la configuración de su filtro. Seleccione este mosaico para abrir la página **Notificaciones de ingeniería**, que muestra la lista completa de transacciones que cumplen con los criterios de su filtro.

Mientras revisa las notificaciones de órdenes de producción en la página **Notificaciones de ingeniería**, puede seguir enlaces a órdenes de cambio u órdenes de producción relacionadas seleccionando valores de columna o utilizando los comandos relacionados en el Panel de acciones. Una vez que haya terminado de evaluar un cambio y después de haber cancelado o modificado los pedidos de producción según sea necesario, puede marcar una notificación como resuelta. Seleccione la notificación y luego, en el Panel de acciones, seleccione **Resolver**. La notificación se elimina de las vistas de todos los usuarios.

> [!IMPORTANT]
> La capacidad de enviar notificaciones para órdenes de producción requiere que la función *Notificaciones de ingeniería para producción* esté activada en su sistema. Para obtener instrucciones sobre cómo activar o desactivar esta característica y sus requisitos previos, consulte [Información general de la gestión de cambios de ingeniería](product-engineering-overview.md).

### <a name="create-a-change-order-from-a-change-request"></a>Crear una orden de cambio a partir de una solicitud de cambio

Un ingeniero que está revisando una solicitud de cambio de ingeniería puede crear una orden de cambio de ingeniería directamente desde la página **Solicitudes de cambio de ingeniería**. En el panel de acciones, en la ficha **Solicitud de cambio**, en el grupo **Orden de cambio de ingeniería**, seleccione **Copiar enlace y productos**.

## <a name="engineering-change-orders"></a>Pedidos de cambio de ingeniería

Los pedidos de cambios de ingeniería proporcionan un proceso estructurado para realizar cambios en los productos de ingeniería. Proponga cambios utilizando una copia de los datos relevantes para la ingeniería. Los datos maestros reales no se ven afectados. Para obtener más información sobre datos relevantes para la ingeniería, consulte [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

Puede crear una orden de cambio de ingeniería que se base en una solicitud de cambio de ingeniería aprobada. Los ingenieros también pueden crear órdenes de cambio de ingeniería desde cero. Puede incluir varios productos en una sola orden de cambio de ingeniería siguiendo cualquiera de estos pasos:

- Seleccionar productos manualmente.
- Utilice la lista de materiales (BOM) para incluir productos que se encuentran en un nivel inferior en la estructura del producto (es decir, los hijos).
- Utilice una búsqueda de dónde se usa para incluir productos que estén más arriba en la estructura del producto (es decir, los padres).

Una vez completada la propuesta de cambios, el proceso de revisión y aprobación se gestionará mediante un flujo de trabajo. Puede configurar diferentes flujos de trabajo, según la prioridad y la gravedad.

Para configurar un flujo de trabajo para órdenes de cambio de ingeniería o solicitudes de cambio de ingeniería, vaya a **Gestión de cambios de ingeniería \> Flujos de trabajo de ingeniería**. Seleccione **Nuevo**, seleccione si el flujo de trabajo se utilizará para revisar órdenes de cambio de ingeniería o solicitudes de cambio de ingeniería, y luego configure el flujo de trabajo.

Para obtener más información sobre los flujos de trabajo, consulte [Visión general del sistema de flujos de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md)

A continuación, se muestran algunas partes interesadas típicas que podrían tener que aprobar una orden de cambio de ingeniería:

- **Propietarios de productos** – Para obtener más información acerca de propietarios de productos, vea [Propietarios de productos](product-owner.md).
- **Líder del equipo responsable** – El campo **Ingeniero** en la vista **Encabezamiento** de la orden de cambio de ingeniería muestra al ingeniero que creó la orden de cambio de ingeniería. Si el ingeniero pertenece a un equipo definido en el sistema, el campo **Responsable** muestra el líder de ese equipo.
- **Departamento de Finanzas** - El departamento de Finanzas podría tener que revisar los casos en los que el cambio implica altos costos.

Puede elegir si la orden de cambio de ingeniería debe procesarse directamente después de su aprobación, como parte del flujo de trabajo, o si el procesamiento debe realizarse más tarde, como un paso manual. Durante el procesamiento de una orden de cambio de ingeniería, se actualizan los datos de ingeniería del producto real.

Mientras revisa una solicitud de cambio, en el Panel de acciones, en la pesetaña **Solicitud de cambio**, en el grupo **Impacto de negocios**, seleccione **Buscar** para evaluar el impacto del cambio propuesto en transacciones abiertas, como pedidos de venta, pedidos de producción e inventario disponible. Los resultados se muestran en el cuadro de diálogo **Impacto empresarial en transacciones abiertas**, donde puede seleccionar las transacciones afectadas y luego usar comandos en la barra de herramientas para ver más información, notificar al usuario responsable o bloquear la transacción.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Órdenes de cambio de ingeniería en empresas de ingeniería u operativas

Como se describe en [Empresas de ingeniería y reglas de propiedad de datos](engineering-org-data-ownership-rules.md), los datos de productos que puede editar varían, según el tipo de entidad jurídica en la que trabaja (una empresa de ingeniería frente a una empresa operativa). Las reglas de propiedad de datos también se aplican a las órdenes de cambio de ingeniería. Por lo tanto, según la entidad jurídica en la que cree una orden de cambio de ingeniería, se pueden realizar diferentes tipos de cambios. A continuación, encontrará algunos ejemplos:

- Para las órdenes de cambio de ingeniería en una *compañía de ingeniería*, puede realizar cambios básicos en los datos de ingeniería. Por ejemplo, puede crear nuevas versiones de un producto, cambiar la estructura de un producto a través de la lista de materiales y cambiar los valores de los atributos de ingeniería. Para cada producto afectado, seleccione uno de los siguientes valores en el campo **Impacto**:

    - **Ninguna** - Actualice la versión del producto existente (actualización en versión).
    - **Nueva versión** - Cree una nueva versión basada en la versión del producto seleccionado.
    - **Nuevo producto**: cree un producto completamente nuevo que se base en la versión del producto seleccionada.
    - **Nueva variante**: cree una nueva variante basada en la versión del producto seleccionado. Se copiará su L. MAT. y la información de ruta.

- Para órdenes de cambio de ingeniería en una *empresa operativa*, puede cambiar los datos logísticos del producto. Por ejemplo, puede enriquecer la lista de materiales existente con configuraciones para el abastecimiento, agregar rutas locales o listas de materiales locales e incluso enriquecer una lista de materiales agregando nuevas líneas de lista de materiales para materiales de embalaje locales, fluidos de lubricación o instrucciones en el idioma local. Los enriquecimientos que hagan los usuarios en la empresa operativa se conservarán cuando se envíen nuevas actualizaciones desde la empresa de ingeniería. Para más información, vea [Empresas de ingeniería y reglas de propiedad de datos](engineering-org-data-ownership-rules.md).

    Cuando las órdenes de cambio de ingeniería se procesan en la empresa de ingeniería, los productos se crean o actualizan solo en la empresa de ingeniería. Por lo tanto, si los datos maestros del producto también deben actualizarse, también debe liberar los productos a las empresas operativas.

- Puede liberar productos directamente desde órdenes de cambio de ingeniería. Abra la orden de cambio y luego, en el Panel de acciones, en la pestaña **Cambia el orden**, en el grupo **Lanzamientos de productos**, seleccione **Estructura del producto de liberación**. El proceso funciona igual que cuando libera productos de la página **Productos lanzados**. Para obtener más información, consulte [Liberar estructuras de productos](release-product-structure.md).
- Puede hacer que los productos se liberen automáticamente de las órdenes de cambio de ingeniería, en función de los siguientes factores:

    - Relanzamientos a empresas donde los productos se lanzaron anteriormente. Seleccione **Buscar** para escanear todas las versiones anteriores y luego seleccione **Ver** para ver los resultados. La página **Ver** muestra los lanzamientos de productos anteriores y puede seleccionar qué productos desea volver a lanzar. Luego cierre la página **Ver** y seleccione **Proceso** para relanzar los productos seleccionados.
    - Configuración de liberación automática en el control de liberación de la categoría de productos de ingeniería. Puede realizar esta versión como parte del flujo de trabajo. Cuando se usa **recopilar propuesta de lanzamiento**, la propuesta de lanzamiento se completará con propuestas de relanzamiento (consulte el elemento de la lista anterior), y los productos se lanzarán a las empresas si la casilla **Liberación automática** está seleccionada en el control de liberación de la categoría de productos de ingeniería. Puede seleccionar **Ver** para ver los resultados, como se describe en el elemento de la lista anterior. Los productos también se lanzarán cuando se usa el bloque de la **propuesta de liberación del proceso**. Si elige recopilar solo la propuesta de lanzamiento como parte del flujo de trabajo, puede iniciar el lanzamiento manualmente seleccionando **Proceso**, como se describe en el elemento de la lista anterior.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Dar seguimiento a una solicitud de cambio de ingeniería a través de una orden de cambio de ingeniería

Tan pronto como se apruebe una solicitud de cambio de ingeniería, puede realizar un seguimiento a través de una orden de cambio de ingeniería. Puede combinar varias solicitudes de cambio de ingeniería en una sola orden de cambio de ingeniería. Una sola orden de cambio de ingeniería puede incluso incluir varios productos. (Por lo general, utiliza este enfoque cuando se debe aplicar el mismo cambio a varios productos). Sin embargo, no puede crear varias órdenes de cambio de ingeniería a partir de una única solicitud de cambio de ingeniería.

Para dar seguimiento a una solicitud de cambio a través de una orden de cambio, abra la solicitud de cambio y luego, en el Panel de acciones, en la pestaña **Cambia el orden**, en el grupo **Orden de cambio de ingeniería**, seleccione **Copiar enlace y productos**. Luego puede seleccionar una orden de cambio de ingeniería existente para conectar la solicitud de cambio, o puede crear una nueva orden de cambio de ingeniería para esa solicitud específica.

## <a name="engineering-change-order-report"></a>Informe de pedido de cambio de ingeniería

Los informes de órdenes de cambio de ingeniería describen los cambios que se realizaron en una orden de cambio de ingeniería. Son útiles tanto durante como después del proceso de revisión y aprobación.

Para ver un informe de orden de cambio de ingeniería, abra la orden de cambio relevante y luego, en el Panel de acciones, en la pestaña **Cambia el orden**, en el grupo **Ver**, seleccione **Informe de orden de cambio de ingeniería**.

## <a name="fields-on-an-engineering-change-order"></a>Campos en una orden de cambio de ingeniería

La mayoría de los campos de las órdenes de cambio de ingeniería son los mismos que los campos para productos lanzados, versiones de ingeniería, documentos, listas de materiales (líneas) y rutas (operaciones). Sin embargo, los campos de la siguiente tabla son exclusivos para cambiar órdenes.

| Campo | Descripción |
|---|---|
| Motivos del cambio de ingeniería | Seleccione el motivo para cambiar el producto afectado. |
| Cambiar descripción | Escriba una descripción del cambio. |
| Herramientas especiales necesarias | Especifique si se requieren herramientas especiales para aplicar el cambio. |
| Disposición de material de ingeniería | Seleccione un código de disposición de material para cualquier residuo que se produzca cuando se aplica el cambio. |
| Se requiere la aprobación del cliente | Especifique si se requiere la aprobación del cliente antes de que se pueda aplicar el cambio. |
| Aprobación del cliente recibida | Especifique el estado de la aprobación del cliente. |
| Salud medioambiental y seguridad | Especifique si las reglas de seguridad y salud ambiental son aplicables al cambio. Si es así, puede seleccionar las reglas aplicables. |

Puede usar el botón **Mantener/copiar información de cambios** para copiar la información de cambio entre los productos afectados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
