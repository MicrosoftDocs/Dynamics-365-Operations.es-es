---
title: Visión general de llegadas
description: Este tema proporciona información acerca de la función de visión general de llegadas. La página de la visión general de llegadas forma parte de esta característica y proporciona una visión general de todos los artículos que se espera que se reciban como artículos entrantes.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 43e49fb6e8deead7c6dfe24a25337aeb35f1fcc0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "356010"
---
# <a name="arrival-overview"></a>Visión general de llegadas

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de la función de visión general de llegadas. La página de la visión general de llegadas forma parte de esta característica y proporciona una visión general de todos los artículos que se espera que se reciban como artículos entrantes.

La página **Visión general de llegadas** proporciona una visión general de todos los artículos entrantes esperados. También muestra las llegadas que pueden ser inicializadas según la información general. Este tema se centra en el proceso de recepción.

## <a name="business-scenario"></a>Escenario empresarial
Considere el escenario siguiente en los procesos de entrada.

[![Escenario empresarial](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sammy, empleado de recepción, desea saber qué se espera que sea recibido en el día actual. En la página **Visión general de llegadas** , Sammy puede obtener una visión general de las tareas actuales, y obtener una estimación somera de cantidades, volumen, peso, diversos tipos de pedido, y así sucesivamente. Más adelante, una entrega llega a uno de los muelles de llegada, y Sammy recibe una lista de entrega. En la página **Visión general de llegadas**, puede realizar las siguientes tareas:

-   Identificar el pedido de conciliación de recepción, y registrar la recepción como **En proceso**. Las líneas que se necesitan para el registro se generan automáticamente, y la recepción pueden ser controlada, aunque las transacciones todavía no se hayan registrado como **Registrado**.
-   Obtenga acceso a la referencia de diario de recepción adecuada (es decir, el diario **Recepción de artículos** o el diario **Entrada desde producción** ), e identifique los diarios que están listos para la actualización de la recepción de producto.

## <a name="arrival-overview-page"></a>Página Visión general de llegadas
Para abrir la página **Visión general de llegadas** , haga clic en **Gestión del inventario** &gt; **Pedidos de entrada** &gt; **Visión general de llegadas**. Puede ver una lista de los pedidos que se espera que sean recibidos. La visión general se divide en un encabezado y las líneas. La información de encabezado se agrupa por el tipo de pedido, la fecha de recepción esperada, y el destino de entrega. Si una línea de encabezado se selecciona para la llegada, todas las líneas de detalle relacionadas con la referencia de recepción se seleccionan para la llegada en la parte de los detalles de línea de la página. Cuando se han registrado todas las líneas de diario relacionadas, esta información no se muestra.

### <a name="arrival-overview-profiles"></a>Perfiles de visión general de llegadas

La página **Visión general de llegadas** proporciona una visión general de los artículos que se espera que se reciban y la fecha en que está previsto que se reciban. Como parte del proceso de llegada, múltiples conjuntos de configuración personal pueden usarse. Los usuarios individuales pueden definir su configuración personal en la página **Perfiles de visión general de llegadas** .

### <a name="set-up-item-arrival"></a>Configurar la recepción de artículos

En nuestro ejemplo, Sammy desea configurar un equipo nuevo en una ubicación que se usará para recibir productos terminados que proceden de la producción en el sitio 1. En la página **Perfiles de visión general de llegadas** , Sammy crea una nueva configuración que se denomina **Producción del sitio 1** y especifica los valores siguientes.

1.  En la ficha desplegable **Opciones de llegada** , en el grupo de campos **Intervalo** , especifique información sobre un intervalo diario y los almacenes para incluirla en la visión general.
2.  En la ficha desplegable **Opciones de llegada** , en el grupo de campos **Diario** , especifique un almacén de recepción, una ubicación, y un nombre de diario (recepción de artículos o entrada desde producción).
3.  En la ficha desplegable **Detalles de consulta de llegada** , en el grupo de campos **Sitio**, en el campo **Restringir a sitio** , especifique un sitio para limitar la vista del área de la visión general.
4.  En la ficha desplegable **Detalles de consulta de llegada** , en el grupo de campos **Tipos de transacciones mostradas**, establezca la opción **Pedidos de producción** en **Sí**.
5.  En la ficha desplegable **Detalles de consulta de llegada** , en el grupo **Varios**, establezca la opción **Actualizar al iniciar** en **Sí**, si la vista debe actualizarse automáticamente en el inicio. Establezca la opción **Actualizar al cambiar el intervalo** en **Sí** si la vista debe actualizarse automáticamente cuando se modifican los valores de intervalo.

Para este ejemplo, el campo **Nombre de perfil de visión general de llegadas** de la ficha desplegable **Opciones de llegada** de la página **Visión general de llegadas** se establece en **Producción del sitio 1**.

### <a name="prerequisites-for-arrival-journals"></a>Requisitos previos para los diarios de recepción

Para crear automáticamente los diarios de recepción de la página **Visión general de llegadas** , debe definir la información adecuada en el grupo de campos **Diario** en la ficha desplegable **Opciones de llegada** .

-   Debe especificar un nombre de diario para crear un nuevo diario.

[![Especificar un nombre de diario](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Si especifica valores en los campos **Almacén** y **Ubicación** , estos valores se aplican en las líneas de diario. Si no especifica valores, el sistema utiliza los valores de la dimensión que se especifica en las transacciones de inventario.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Artículos que se reciben desde un pedido de recepción esperado

En la ficha desplegable **Recibos**, Sammy selecciona una línea y después hace clic en **Iniciar llegada**. Todas las líneas relacionadas que se encuentran en el intervalo especificado y con una cantidad para registrar se seleccionan automáticamente. Se genera un diario de recepción de artículos que tiene una coincidencia entre el pedido de recepción previsto y el diario. La cantidad se inicializa automáticamente en todas las líneas que se creen.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Artículos que se reciben desde más de un pedido de recepción esperado

En la ficha desplegable **Recibos**, Sammy selecciona varias líneas y después hace clic en **Iniciar llegada**. Se genera un diario de recepción de artículos que tiene una coincidencia entre todos los pedidos de recepción previstos y el diario. Todas las líneas se crean en un encabezado del diario de recepción de artículos, y la cantidad se inicializa automáticamente.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Recepción de artículos desde uno o varios pedidos de recepción esperados

#### <a name="view-information"></a>Ver información

Para obtener una visión general de las recepciones previstas en un intervalo de fechas, Sammy especifica la siguiente información en los campos de la ficha desplegable **Opciones de llegada** en la página **Visión general de llegadas** y después hace clic en **Actualización** para actualizar la vista:

-   Nombre del perfil de la visión general de llegadas: **Consulta**
-   Mostrar líneas: **Todas**
-   Días hacia atrás: (en blanco)
-   Días hacia adelante: **0**
-   Almacenes: **GW, MW**

Sammy puede ver la siguiente información:

-   Todos los pedidos de recepción relacionados de la fecha del sistema y un número infinito de días atrás desde esta (el intervalo **InventTrans.StatusDate** ) y recepciones a los almacenes GW y MW, independientemente de su estado.
-   Información de línea detallada para más de un pedido. Sammy puede seleccionar varias líneas de encabezado en la visión general y después hacer clic en **Mostrar todos los seleccionados** para ver toda la información de detalle de línea correspondiente para todos los pedidos seleccionados.
-   Información relativa a un pedido de compra específico. Para mostrar solo la información que está relacionada con un número de referencia específico en la visión general, Sammy puede especificar un número de cuenta en el campo **Número de cuenta** y un número de pedido en el campo **Número de referencia** .
-   Una visión general de las tareas de registro que están pendientes de todas las líneas de pedido para las que se ha creado un diario de recepción de artículos pero que todavía no se han enviado. Para ver esta información, Sammy puede seleccionar **En proceso** en el campo **Mostrar líneas** .

### <a name="update-journals"></a>Actualizar diarios

Para registrar una o más líneas de pedido que deben ser procesadas, Sammy puede seleccionar las líneas en la cuadrícula de visión general o en la cuadrícula de líneas y a continuación hacer clic en **Diarios** &gt; **Mostrar llegadas a partir de recepciones**. Se mostrarán los encabezados de la recepción de artículos que coincidan con las líneas. Para actualizar la recepción de productos del pedido de compra para los artículos registrados, Sammy puede tener acceso a los encabezados del diario de recepción de artículos que están listos para la actualización. Para obtener acceso a estas cabeceras del diario de llegadas de artículos, hace clic en **Diarios** &gt; **Diarios listos para recepción de productos**. Se muestran todas las líneas de encabezado que están listas para la actualización de la recepción de productos en el intervalo especificado de almacenes. (Las líneas de encabezado que se muestran no están relacionadas con el intervalo de días).

### <a name="start-an-arrival-registration"></a>Iniciar un registro de llegada

Seleccionando varias líneas en la página **Visión general de llegadas**, Sammy puede iniciar una llegada de más de una referencia de recepción. Cuando selecciona una línea de la visión general de recepciones, los detalles de línea correspondientes se seleccionan. Si existe una cantidad para el registro, el botón **Iniciar llegada** está disponible. Sammy puede utilizar dos métodos para iniciar el registro de llegada:

-   Para filtrar la página para que muestre solo registros que cumplan criterios específicos, en el campo **Referencia del proveedor** , digitalice un número de referencia de un proveedor, como el código de barras para una nota de entrega.
-   En la parte de la información general o la parte de detalles de la página **Visión general de llegadas** seleccione o cancele manualmente la selección de registros para el registro de llegada. Posteriormente, cuando Sammy hace clic en **Iniciar llegada**, los registros seleccionados se crean automáticamente en un diario de recepción de artículos. Los registros incluyen información de línea, y se asigna toda la información de campo única.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Actualizar la información de llegada y procesar una recepción de producto
Una vez que se hayan registrado todas las mercancías, el responsable del almacén o el director de compras pueden actualizar los artículos recibidos con una recepción de producto para agregar el coste físico. Para actualizar la información de llegada y enviar una recepción de producto, siga estos pasos.

1.  Haga clic en **Gestión del inventario** &gt; **Pedidos de entrada** &gt; **Visión general de llegadas**.
2.  En la página **Visión general de llegadas**, haga clic en **Diarios** &gt; **Diarios listos para recepción de productos** para mostrar una lista de los diarios que están listos para una actualización de la recepción de productos.
3.  Seleccione los diarios que es necesario actualizar y, a continuación, haga clic en **Funciones** &gt; **Recepción de producto**.
4.  En la página **Registro** , especifique el número de la recepción de producto, si no está ya disponible en el diario y, a continuación. haga clic en **Aceptar** para procesar la recepción de producto.

## <a name="summary"></a>Resumen
La página **Visión general de llegadas** puede ayudar al responsable del almacén y a los trabajadores de almacén a obtener una visión general del trabajo previsto que se debe hacer como parte de un proceso de entrada. La página se puede usar también para iniciar el proceso de recepción de artículos, para ayudar a garantizar que se realiza un seguimiento de los artículos en la primera entrada en el almacén.
