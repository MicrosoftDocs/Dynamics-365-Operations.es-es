---
title: "Análisis del coste del pedido de producción"
description: "Este artículo proporciona información acerca del análisis de costes que puede realizar para pedidos de producción finalizados y actuales. Puede analizar los costes estimados y reales mediante la página Cálculo de precios o el informe Estimaciones y gestión de costes. Puede ver la información acerca de los costes y la cantidad estimados y reales para cada artículo de componente, la operación de enrutamiento y el coste indirecto."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 40ac5108216fd6d9eb5cd6e76fefd66828a7da84
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="production-order-cost-analysis"></a>Análisis del coste del pedido de producción

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca del análisis de costes que puede realizar para pedidos de producción finalizados y actuales. Puede analizar los costes estimados y reales mediante la página Cálculo de precios o el informe Estimaciones y gestión de costes. Puede ver la información acerca de los costes y la cantidad estimados y reales para cada artículo de componente, la operación de enrutamiento y el coste indirecto.

Los costes reales de un pedido de producción se basan en el consumo notificado de material y operaciones de enrutamiento. Puede obtener acceso a las transacciones detalladas acerca del consumo de material, las operaciones de enrutamiento y los costes indirectos notificados de un pedido de producción en la página **Registro de producción**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Análisis de desviaciones de un pedido de producción completado
Las desviaciones reflejan la comparación de las actividades de producción notificadas y el cálculo de costes estándar del artículo de producción. Las desviaciones no reflejan una comparación con los costes estimados del pedido de producción. Las actividades de producción notificadas incluyen el consumo de materiales y las operaciones de ruta (con los costes indirectos asociados) y la cantidad que ha sido notificada como finalizada. Se calculan los siguientes cuatro tipos de desviaciones:

-   Desviación de tamaño de lote
-   Desviación en la cantidad de producción
-   Desviación en el precio de producción
-   Desviación de sustitución de producción

En el siguiente diagrama se muestran las cuatro desviaciones que justifican la diferencia entre los costes reales de un pedido de producción y los costes calculados en el registro de costes del artículo en el momento de finalizar el pedido de producción. 

![Desviaciones que explican las diferencias en un pedido de producción completado](./media/control.jpg) 

Puede analizar las desviaciones de producción mediante la página **Desviación** o el informe **Desviación de producción** . Use las opciones de visualización para ver las desviaciones detalladas por artículo y recurso de operaciones, o por grupo de costes. La directiva de análisis de costes de los parámetros del inventario determina si se realizará un seguimiento de las desviaciones por grupo de costes. También puede usar las opciones de visualización **única**, **múltiple** y **total** para ver las desviaciones resumidas. La información sobre las desviaciones detalladas puede ayudarlo a comprender el origen de cada desviación. Con el fin de poder anticipar las desviaciones antes de que finalice el pedido de producción, analice la información detallada que se proporciona en el informe **Estimaciones y gestión de costes**.

## <a name="cost-analysis-for-current-production-orders"></a>Análisis de costes para los pedidos de producción en curso
Los informes individuales proporcionan información acerca de cada tipo de transacción. Estos informes se pueden utilizar para analizar los costes de actividades de producción notificadas. La información solo se muestra para los pedidos de producción actuales cuyo estado es **Iniciado** o **Notificado como finalizado**.

-   **Materiales en proceso**: este informe muestra las transacciones de la lista de selección notificadas según los pedidos producción actuales a partir de la fecha de transacción especificada. El informe indica la cantidad emitida de un componente que se emitió y el importe de coste físico para cada transacción. Use los criterios de selección para un único artículo de componente. Por ejemplo, puede imprimir información sobre la cantidad emitida del componente en pedidos de producción aplicables. La cantidad emitida no se actualiza con las cantidades finalizadas para el artículo principal. Por lo tanto, la cantidad real de las materias primas en curso se puede exagerar.
-   **Trabajo en curso**: este informe muestra las transacciones de ruta (o transacciones de trabajo) notificadas según los pedidos producción actuales a partir de la fecha de transacción especificada. El informe indica las horas, el importe y la cantidad (tanto la cantidad sin errores como cantidad con errores) que se notifican para cada transacción. También incluye información como el número de operación, el id. de la operación y el recurso de operaciones. Además, este informe muestra el tiempo y cantidad totales para todas las transacciones del pedido de producción y la cantidad notificada como terminada.
-   **Costes indirectos en curso**: este informe muestra los costes indirectos en los que se ha incurrido según los pedidos de producción. Estos datos se basan en el consumo notificado de operaciones de enrutamiento y los componentes a partir de la fecha de transacción especificada. El informe indica el tipo de coste indirecto (suplemento o tasa), el código de la hoja de gestión de costes para el coste indirecto y el importe de coste de cada transacción. Este informe no proporciona información sobre la tarjeta de ruta o la transacción de lista de selección que generó el coste indirecto.
-   **Costes de producción en curso**: este informe muestra el consumo combinado de material, operaciones de enrutamiento y costes indirectos contra los pedidos de compra a partir de la fecha de transacción especificada.
-   **Artículos terminados en proceso**: este informe muestra los pedidos de producción actuales y las transacciones "notificar como terminado" a partir de la fecha de transacción especificada.


<a name="additional-resources"></a>Recursos adicionales
--------

[Orígenes comunes de desviaciones de producción](common-sources-of-production-variances.md)




