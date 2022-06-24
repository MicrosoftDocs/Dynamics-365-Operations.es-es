---
title: Programación de suministros
description: Este artículo proporciona información sobre la página de programación de suministros y sus capacidades.
author: t-benebo
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0e3937dd4cffc464f38b5770674364579bdb06d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851750"
---
# <a name="supply-schedule"></a>Programación de suministros

[!include [banner](../includes/banner.md)]

La página **Programa de suministro** muestra una descripción general completa de la oferta y la demanda de un producto o familia de productos. La información se filtra por ubicación, plan maestro y períodos. También puede utilizar la página para crear nuevos pedidos, modificar pedidos planificados existentes y ejecutar la planificación maestra.

## <a name="open-the-supply-schedule-page"></a>Abrir la página Programación de suministros

Puede abrir la página **Programación de suministros** de cualquiera de las siguientes formas:

- Vaya a **Planificación maestra \> Planificación maestra \> Programación de suministros**. En el cuadro de diálogo **Modificar filtro**, especifique el plan y el producto que está buscando, introduciendo valores de filtro en los campos que se proporcionan. (En el resto de este artículo, la colección de valores de filtro que introduce se denomina "el filtro" o "el filtro actual"). Cuando haya terminado, seleccione **Aceptar**.
- Vaya a **Gestión de información de productos \> Productos \> Productos despachados**. Seleccione o abra un producto. En el panel Acciones, en la pestaña **Plan** del grupo **Vista**, seleccione **Programación de suministros**.
- Vaya a **Planificacion maestra \> Configuración \> Previsión de demanda \> Claves de asignación de artículos**. Seleccione una clave de asignación de artículos que se utilice como familia de productos. Luego, en el panel de acciones, seleccione **Programación de suministros**.
- Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**. Seleccione o abra un pedido planificado. Luego, en el panel Acciones, en la pestaña **Vista** del grupo **Vista**, seleccione **Programación de suministros**.

> [!NOTE]
> Al abrir la página **Programación de suministros** de un producto, familia de productos o pedido planificado, no es necesario que introduzca valores de filtro. El sistema utilizará la plantilla de período predeterminada.

## <a name="use-the-supply-schedule-page"></a>Usar la página Programación de suministros

La página **Programación de suministros** consta de una sección superior, la ficha desplegable **Inventario de fin de período**, una ficha desplegable adicional que se vuelve visible, según la línea que esté seleccionada en la sección superior y el panel de cuadro informativo. (Para abrir el panel de cuadro informativo y ver un cuadro informativo, seleccione **Información relacionada** en el borde derecho de la página).

### <a name="upper-section"></a>Sección superior

La sección superior de la página **Programación de suministros** contiene una cuadrícula que muestra los siguientes datos para un producto o familia de productos. Estos datos se desglosan por períodos que están definidos por el valor **Plantilla de período** del filtro.

- **Inventario de inicio de período**: esta línea muestra el saldo de inventario esperado al inicio del período si se producen todos los pedidos en el sistema.
- **Inventario de finalización de período**: esta línea muestra el saldo de inventario esperado al final del período si se producen todos los pedidos en el sistema.
- **Inventario vinculado al final del período**: esta línea muestra la cantidad de inventario al final del período que está vinculado a la demanda futura.
- **Suministro neto del período**: esta línea muestra la diferencia entre suministro y demanda en el período.
- **Inventario mínimo**: este nodo muestra las existencias de seguridad para un producto o familia de productos. Para expandir o contraer este nodo, selecciónelo y luego seleccione **Expandir** o **Colapsar** en la barra de herramientas. Este nodo se muestra solo cuando hay stock de seguridad para el producto o la familia de productos.
- **Demanda**: este nodo muestra la demanda de un producto o familia de productos. La demanda se agrupa por tipo de transacción. Para expandir o contraer este nodo, selecciónelo y luego seleccione **Expandir** o **Colapsar** en la barra de herramientas. Los tipos de transacciones de demanda incluyen ventas, transferencias y diarios de inventario. Este nodo se muestra solo cuando hay demanda del producto o de la familia de productos.
- **Suministro**: este nodo muestra el suministro de un producto o familia de productos. El suministro se agrupa por tipo de transacción. Para expandir o contraer este nodo, selecciónelo y luego seleccione **Expandir** o **Colapsar** en la barra de herramientas. Los tipos de transacciones de suministro incluyen producción, compra y transferencias. Este nodo se muestra solo cuando hay suministro del producto o de la familia de productos.

Muchos de los botones de la barra de herramientas disponibles, las pantallas de cuadro informativo y las pantallas de ficha desplegable dependen de sus selecciones en la sección superior. Por lo general, elegirá un tipo de transacción seleccionando una de las filas del nodo **Suministro** o **Demanda**. Luego, elegirá un período seleccionando una columna específica para la fila seleccionada.

La barra de herramientas de endima de la cuadrícula en la sección superior de la página **Programa de suministro** ofrece los siguientes botones:

- **Expandir/Contraer**: expandir o contraer un nodo seleccionado, como el nodo **Demanda**, el nodo **Suministro** y sus subnodos. (Los nodos muestran un prefijo **\[+\]** o **\[-\]** para indicar si están actualmente contraídos o expandidos).
- **Nuevo**: abrir un menú donde cada comando, a su vez, abre un cuadro de diálogo o página que le permite agregar un tipo específico de elemento para la selección. Los comandos disponibles incluyen **Suministro de pronóstico**, **Orden planificada**, **Kanban programado**, **Nuevo pedido de producción**, **pedido de compra** y **Pedido de transferencia**.
- **Planificacion maestra**: ejecutar la planificación maestra. Aparece un cuadro de diálogo, donde puede especificar el plan a ejecutar. De manera predeterminada, el campo **Plan maestro** se establece automáticamente para coincidir con el filtro actual.
- **Max. informar como terminado**: abrir la página **Max. informar como terminado** para el producto que se define en el filtro actual.
- **Actualizar pedidos planificados**: abre la página **Pedidos planificados**, que muestra los pedidos planificados para el producto o la familia de productos que se define en el filtro actual.
- **Nivel**: distribuir los pedidos planificados de acuerdo con la configuración del cuadro de diálogo que aparece.
- **Directiva del plan de materiales por ubicación**: abrir la página **Cobertura de artículos** para el producto definido en el filtro actual.
- **Regla Kanban**: abrir la página **Reglas Kanban** para el producto que se define en el filtro actual.

### <a name="fasttabs"></a>Fichas desplegables

La página **Programa de suministro** puede contener las siguientes fichas desplegables:

- **Inventario de final de período**: esta ficha desplegable muestra los datos del inventario al final del período en un formato gráfico.
- **Perfil de suministro**: esta ficha desplegable muestra los datos de suministro en un formato gráfico. Se vuelve visible cuando selecciona un nodo de **Suministro** o una línea de debajo de él en la sección superior.
- **Resumen**: esta ficha desplegable muestra detalles resumidos relacionados con el tipo de transacción que seleccionó en la sección superior. Por ejemplo, si selecciona **Ventas** en el nodo **Demanda**, esta ficha desplegable muestra los campos relacionados con los pedidos de ventas, como **Líneas de pedido de ventas solicitadas** o **Cantidad total**. Si selecciona **Pedidos de producción** en el subnodo **Producción** del nodo **Suministro**, esta ficha desplegable muestra los campos relacionados con los pedidos de producción, como **Pedidos de producción programados** o **Total programado**. Los valores de campo dependen del período que seleccionó en la sección superior. 
- **\[Tipo de transacción\] - \[Período\]**: esta ficha desplegable muestra los pedidos para el tipo de transacción y el período que seleccionó en la sección superior. El nombre de la ficha desplegable refleja esas selecciones. Por ejemplo, podría denominarse **Pedidos de ventas: registro hacia atrás** o **Pedidos de producción: semana 37**.

### <a name="action-pane"></a>Panel de acciones

Los siguientes botones están disponibles en el panel de acciones:

- **Modificar filtro**: abre el cuadro de diálogo **Modificar filtro**, donde puede actualizar los valores de filtro y luego volver a abrir la página **Programa de suministro**, que refleja la configuración de filtro actualizada.
- **Mostrar retrasos**: resalta las líneas relevantes en la sección superior si hay un pedido retrasado de ese tipo de transacción.

### <a name="factbox-pane"></a>Panel de cuadro informativo

Para abrir el panel de cuadro informativo y ver un cuadro informativo, seleccione **Información relacionada** en el borde derecho de la página. Los siguientes cuadros informativos están disponibles en la página **Programa de suministro**:

- **Detalles del artículo**: este cuadro informativo muestra información básica sobre el producto que se define en el filtro actual. Está en blanco si definió una familia de productos en el filtro.
- **Acciones**: este cuadro informativo muestra las acciones para los pedidos del tipo de transacción y el período que seleccionó en la sección superior.
- **Retrasos**: este cuadro informativo muestra los retrasos de los pedidos del tipo de transacción y el período que seleccionó en la sección superior.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
