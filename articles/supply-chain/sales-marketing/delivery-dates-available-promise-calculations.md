---
title: Compromisos de pedidos
description: En este artículo se proporciona información acerca de los compromisos de entrega. Los compromisos de entrega le ayuda a comprometer fechas de entrega de manera confiable a sus clientes y le ofrecen flexibilidad para que pueda cumplir esas fechas.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228278"
---
# <a name="order-promising"></a>Compromisos de pedidos

[!include [banner](../includes/banner.md)]

En este artículo se proporciona información acerca de los compromisos de entrega. Los compromisos de entrega le ayuda a comprometer fechas de entrega de manera confiable a sus clientes y le ofrecen flexibilidad para que pueda cumplir esas fechas.

Los compromisos de pedidos calculan las fechas de envío y recepción más tempranas, y se basan en el método de control de fecha de entrega y los días de transporte. Puede seleccionar entre los siguientes métodos de control de fecha de entrega:

- **Plazo de ventas**: el plazo de ventas es el tiempo entre la creación del pedido de ventas y el envío de los artículos. El cálculo de la fecha de entrega se basa en un número predeterminado de días y no considera la disponibilidad de existencias, la demanda conocida o el suministro planificado.
- **NNC (neto no comprometido)**: el NNC es la cantidad de un artículo que esté disponible y se pueda prometer a un cliente en una fecha específica. El cálculo del NNC incluye inventario no comprometido, fechas disponibles, recepciones planificadas y emisiones.
- **ATP + Días de emisión**: la fecha de envío es igual que la fecha de neto no comprometido (NNC) más el margen de emisión del artículo. El margen de emisión es el tiempo que necesario para preparar los artículos para el envío.
- **CTP (capaz de comprometer)**: la disponibilidad se calcula a través de la expansión. Si utiliza la Optimización de la planificación, el método de control de fecha de entrega *CTP* no está permitido y, si se selecciona, provocará un error cuando se ejecute el cálculo. Para obtener más información sobre cómo configurar y usar CTP, consulte [Calcule las fechas de entrega de pedidos de ventas usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP para la optimización de la planificación** – Utilice el cálculo de CTP proporcionado por Planning Optimization. Esta opción no tiene efecto si está utilizando el motor de planificación maestra integrado, se admiten los productos controlados por lotes. Para obtener más información sobre cómo configurar y usar CTP, consulte [Calcule las fechas de entrega de pedidos de ventas usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Cuando se actualiza una orden de venta, la información de la promesa de la orden solo se actualiza si la fecha de la promesa de la orden existente no se puede cumplir, como se ilustra en los siguientes ejemplos:
>
> - **Ejemplo 1**: La fecha prometedora del pedido actual es el 20 de julio, pero debido al aumento de la cantidad, no podrá realizar la entrega hasta el 25 de julio. Debido a que la fecha actual ya no se puede cumplir, se activa la promesa de pedido.
> - **Ejemplo 2**: La fecha prometedora del pedido actual es el 20 de julio, pero debido a la reducción de la cantidad, ahora es posible realizar la entrega el 15 de julio. Sin embargo, debido a que la fecha actual aún se puede cumplir, la promesa de pedido no se activa y el 20 de julio sigue siendo la fecha de promesa de pedido.

## <a name="atp-calculations"></a>Cálculos de NNC

La cantidad de NNC se calcula mediante el método “NNC acumulativo con previsión futura”. La principal ventaja de este cálculo de NNC es que permite controlar las ocasiones en las que la suma de las emisiones entre recepciones supera la última recepción; por ejemplo, cuando es necesario usar una cantidad de una recepción anterior para satisfacer un requisito. El método de cálculo "NNC acumulativo con previsión futura" incluye todas las emisiones hasta que la cantidad acumulativa que se recibe excede la cantidad acumulada que se emite. Por lo tanto, este método de cálculo de NNC evalúa si parte de la cantidad de un período anterior se puede utilizar en un período posterior.

La cantidad de NNC es el saldo no comprometido de inventario en el primer período. Normalmente, se calcula para cada período en el que se programa una recepción. El programa calcula el período de NNC en días y la fecha actual como la primera fecha para la cantidad de NNC. En el primer período, NNC incluye el inventario disponible menos los pedidos de cliente vencidos.

La ATP se calcula mediante la fórmula siguiente:

ATP = ATP para el período anterior + Recepciones del período actual - Emisiones del período actual - Cantidad neta de emisión para los períodos futuros hasta el período en el que la suma de las recepciones de todos los períodos futuros (hasta el período futuro, incluido éste) sea superior a la suma de las emisiones (hasta el período futuro, incluido este).

Tenga en cuenta que el cálculo de ATP no incluye información sobre la fecha de vencimiento y más allá del límite de tiempo ATP que el sistema espera cuando se puede prometer cualquier cantidad.

Cuando ya no queden emisiones o recepciones para tener en cuenta, la cantidad ATP de las fechas siguientes será la misma que la última cantidad ATP calculada.

Si no se proporcionan todas las dimensiones que se usan para un artículo a la hora de realizar la comprobación NNC, es posible que aún se especifiquen en la emisión y las recepciones. En este caso, el cálculo de NNC, las recepciones y las emisiones deberán agregarse a las dimensiones existentes con el fin de reducir el número de líneas de recepción y emisión que se usan en el cálculo de NNC.

La cantidad de NNC que se muestra siempre es mayor o igual que 0 (cero). Si el cálculo devuelve una cantidad negativa de NNC (por ejemplo, si la cantidad que se prometió anteriormente excede la cantidad disponible), la cantidad se establece automáticamente en 0.

### <a name="example"></a>Ejemplo

El campo **Límite de tiempo para demanda regresiva de NNC** controla hasta qué momento anterior se buscan pedidos de demanda o emisiones de inventario retrasados. El campo **Límite de tiempo para suministro regresivo de NNC** controla hasta qué momento anterior se buscan pedidos de suministro o recepciones de inventario retrasados. Por ejemplo, si los pedidos que se retrasan solo siete días deben considerarse en el cálculo de NNC, ambos campos se deben establecer en **7**.

Los campos **Tiempo de compensación para demanda retrasada de NNC** y **Tiempo de compensación para suministro retrasado de NNC** controlan cuándo se tendrán en cuenta la demanda o el suministro retrasados en el cálculo de NNC. Por ejemplo, si la demanda y el suministro retrasados deben considerarse en el cálculo de NNC de pasad mañana, ambos campos se deben establecer en **2**. Un valor de **2** significa que la cantidad de un artículo en un pedido de compra retrasado que se debe tener en cuenta en el cálculo de NNC se considerará disponible dos días después de la fecha actual.

En el siguiente ejemplo, **7** se especifica en los campos **Límite de tiempo para demanda regresiva de NNC** y **Límite de tiempo para suministro regresivo de NNC** y **1** se especifica en los campos **Tiempo de compensación para demanda retrasada de NNC** y **Tiempo de compensación para suministro retrasado de NNC**.

Un pedido de compra de 200 piezas de un producto que se debería haber recibido hace tres días todavía no se recibió. Por consiguiente, una línea de pedido de ventas de 75 piezas del mismo producto que se debería haber enviado ayer no se ha enviado.

Un cliente llama y desea pedir 150 piezas del mismo producto. Cuando se comprueba la disponibilidad del producto, se descubre que hay otro pedido de compra de 100 piezas del producto que se entregará 10 días más tarde.

Se crea una línea de pedido de ventas para el producto y se especifica **150** como cantidad.

Dado que el control de fecha de entrega es el método NNC, se calculan los datos de NNC para buscar la fecha de envío más temprana posible. De acuerdo con los parámetros, se consideran el pedido de compra y el pedido de ventas retrasados, y la cantidad resultante de NNC para la fecha actual es 0. Mañana, cuando se espera recibir el pedido de compra retrasado, la cantidad de NNC se calcula como más de 0 (en este caso, se calcula como 125). Sin embargo, 10 días de ahora en adelante, cuando se espera que se reciba el pedido de compra adicional de 100 piezas, la cantidad de NNC se convierte en más de 150.

Por lo tanto, la fecha de envío se establece en 10 días a partir de ahora, según el cálculo de NNC. Por consiguiente, comenta al cliente que la cantidad pedida se puede entregar en 10 días.

## <a name="ctp-calculations"></a>Cálculos de CTP

La funcionalidad CTP le permite dar a los clientes fechas realistas para cuando puede prometer productos específicos. Para cada línea de ventas, puede proporcionar una fecha que tenga en cuenta el inventario disponible existente, la capacidad de producción y los tiempos de transporte.

CTP se extiende la funcionalidad ATP teniendo en cuenta la información de capacidad. Mientras que ATP considera solo la disponibilidad de materiales y asume recursos de capacidad infinita, CTP considera la disponibilidad tanto de materiales como de capacidad. Por lo tanto, proporciona una imagen más realista de si la demanda se puede satisfacer dentro de un marco de tiempo determinado.

La página Requisitos netos se comporta de forma ligeramente diferente en función de si está utilizando Optimización de planificación o el motor de planificación maestra integrado. Actualmente, CTP para la optimización de la planificación solo admite un subconjunto de los escenarios de CTP que son compatibles con el motor integrado.

Para obtener información detallada sobre cómo configurar y usar CTP para cada motor, consulte [Calcule las fechas de entrega de pedidos de ventas usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
