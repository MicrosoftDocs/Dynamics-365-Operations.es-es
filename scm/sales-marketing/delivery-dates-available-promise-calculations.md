---
title: Compromisos de pedidos
description: "En este artículo se proporciona información acerca de los compromisos de entrega. Los compromisos de entrega le ayuda a comprometer fechas de entrega de manera confiable a sus clientes y le ofrecen flexibilidad para que pueda cumplir esas fechas."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8aa0a58b03ee18e42ca7770ea3e22311c1ddba67
ms.lasthandoff: 03/31/2017


---

# <a name="order-promising"></a>Compromisos de pedidos

En este artículo se proporciona información acerca de los compromisos de entrega. Los compromisos de entrega le ayuda a comprometer fechas de entrega de manera confiable a sus clientes y le ofrecen flexibilidad para que pueda cumplir esas fechas.

Los compromisos de pedidos calculan las fechas de envío y recepción más tempranas, y se basan en el método de control de fecha de entrega y los días de transporte. Puede seleccionar entre cuatro métodos de control de fecha de entrega:

-   ** Plazo de ventas ** – plazo de ventas es el tiempo entre la creación de pedido de ventas y el envío de los artículos. El cálculo de fecha de entrega se basa en un número predeterminado de días, y no considerará la disponibilidad de existencias, la demanda conozca, la fuente o planificada.
-   ** NNC (neto no comprometido) – ** el NNC es la cantidad de un artículo que esté disponible y se puede comprometer un cliente en una fecha específica. El cálculo del NNC incluye inventario no comprometido, fechas disponibles, recepciones planificadas y emisiones.
-   **NNC + Días de emisión**: la fecha de envío será igual que la fecha de neto no comprometido (NNC) más el margen de emisión del artículo. El margen de emisión es el tiempo que necesario para preparar los artículos para el envío.
-   **CTP (capaz de comprometer)**: la disponibilidad se calcula a través de la expansión.

## <a name="atp-calculations"></a>Cálculos de NNC
La cantidad ATP se calcula mediante “NNC acumulativo con el método de look ahead”. La ventaja principal de este método de cálculo ATP es que puede gestionar casos en los que está más la suma de las emisiones entre recibos que la última recepción (por ejemplo, cuando una cantidad de una recepción anterior se debe usar para satisfacer un requisito). El NNC “acumulativo con el método de cálculo de look ahead” incluye todas las emisiones hasta que la cantidad acumulativa que recibir excede la cantidad acumulativa para su envío. Por lo tanto, este método de cálculo de NNC evalúa si parte de la cantidad de un período anterior se puede utilizar en un período posterior.  

La cantidad de NNC es el saldo no comprometido de inventario en el primer período. Normalmente, se calcula para cada período en el que se programa una recepción. El programa calcula el período de NNC en días y la fecha actual como la primera fecha para la cantidad de NNC. En el primer período, NNC incluye el inventario disponible menos los pedidos de cliente vencidos.  

La ATP se calcula mediante la fórmula siguiente:  

El ATP = ATP para el período anterior + las recepciones del período actual – emisiones del período actual – la cantidad neta de emisión para los períodos futuros hasta el período en que la suma de recepciones de todos los períodos futuros, hasta e incluido el período futuro, supera la suma de emisiones hasta y de incluir el período futuro.  

Cuando ya no queden emisiones o recepciones para tener en cuenta, la cantidad ATP de las fechas siguientes será la misma que la última cantidad ATP calculada.  

Si no se proporcionan todas las dimensiones que se usan para un artículo a la hora de realizar la comprobación NNC, es posible que aún se especifiquen en la emisión y las recepciones. En este caso, el cálculo de NNC, las recepciones y las emisiones deberán agregarse a las dimensiones existentes con el fin de reducir el número de líneas de recepción y emisión que se usan en el cálculo de NNC.  

La cantidad de NNC que se muestra siempre es mayor o igual que 0 (cero). Si el cálculo devuelve una cantidad negativa de NNC (por ejemplo, si la cantidad que se prometió anteriormente excede la cantidad disponible), el programa establece automáticamente la cantidad en **0**.

### <a name="example"></a>Ejemplo

El campo **Límite de tiempo para demanda regresiva de NNC** controla hasta qué momento anterior se buscan pedidos de demanda o emisiones de inventario retrasados. El campo **Límite de tiempo para suministro regresivo de NNC** controla hasta qué momento anterior se buscan pedidos de suministro o recepciones de inventario retrasados. Por ejemplo, si los pedidos que se retrasan solo siete días deben considerarse en el cálculo de NNC, ambos campos se deben establecer en **7**.  

Los campos **Tiempo de compensación para demanda retrasada de NNC** y **Tiempo de compensación para suministro retrasado de NNC** controlan cuándo se tendrán en cuenta la demanda o el suministro retrasados en el cálculo de NNC. Por ejemplo, si la demanda y el suministro retrasados deben considerarse en el cálculo de NNC de pasad mañana, ambos campos se deben establecer en **2**. Un valor de **2** significa que la cantidad de un artículo en un pedido de compra retrasado que se debe tener en cuenta en el cálculo de NNC se considerará disponible dos días después de la fecha actual.  

En el siguiente ejemplo, **7** se especifica en los campos **Límite de tiempo para demanda regresiva de NNC** y **Límite de tiempo para suministro regresivo de NNC** y **1** se especifica en los campos **Tiempo de compensación para demanda retrasada de NNC** y **Tiempo de compensación para suministro retrasado de NNC**.  

Un pedido de compra de 200 piezas de un producto que se debería haber recibido hace tres días todavía no se recibió. Por consiguiente, una línea de pedido de ventas de 75 piezas del mismo producto que se debería haber enviado ayer no se ha enviado.  

Un cliente llama y desea pedir 150 piezas del mismo producto. Cuando se comprueba la disponibilidad del producto, se descubre que hay otro pedido de compra de 100 piezas del producto que se entregará 10 días más tarde.  

Se crea una línea de pedido de ventas para el producto y se especifica **150** como cantidad.  

Dado que el control de fecha de entrega es el método NNC, se calculan los datos de NNC para buscar la fecha de envío más temprana posible. Según los valores, se consideran el pedido de compra y el pedido de ventas retrasados, y la cantidad ATP resultante para la fecha actual es 0. Mañana, si se espera el pedido de compra Retrasado de ser recibido, la cantidad ATP se calcula como más de 0 (en este caso, ha calculado como 125). Sin embargo, 10 días a partir de ahora, si se espera que el pedido de compra adicional de 100 piezas sea recibido, la cantidad ATP se convierte más de 150.  

Por lo tanto, la fecha de envío se establece 10 días a partir de ahora, en función del cálculo de NNC. Por consiguiente, comenta al cliente que la cantidad pedida se puede entregar en 10 días.


