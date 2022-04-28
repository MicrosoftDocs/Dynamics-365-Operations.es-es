---
title: Mensajes de acción
description: Un mensaje de acción es una sugerencia generada por el sistema para cambiar una orden de planificada o en firme existente.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570265"
---
# <a name="action-messages"></a>Mensajes de acción

[!include [banner](../includes/banner.md)]

Un mensaje de acción es una sugerencia generada por el sistema para cambiar una orden planificada, aprobada o confirmada.

Los mensajes de acción se generan por el cálculo de planificación maestra en respuesta a los requisitos modificados. Por ejemplo, la fecha de envío o la cantidad se cambian en un pedido de ventas después de crear un pedido de compra para satisfacer la demanda del pedido de venta. En este caso, el cálculo de la planificación maestra generan uno o más mensajes de acción que sugieren actualizar el pedido de compra. Puede decidir si desea aplicar los cambios sugeridos.

Configure la forma de calcular mensajes de acción para un grupo de cobertura que vincule a un artículo.

## <a name="select-action-messages"></a>Seleccione los mensajes de acción

En la página **Grupos de cobertura** puede seleccionar los mensajes de acción que desea que el sistema genere, y los grupos de cobertura o los artículos a los que se aplican los mensajes. La siguiente tabla enumera el mensaje de acción que puede seleccionar.

| Mensaje | Description |
|---|---|
| Adelantar | El sistema generará mensajes de acción, conforme sean necesarios, para mover los pedidos a una fecha anterior. En el campo **Margen anticipado** también puede especificar el número máximo de días que pueden transcurrir entre una recepción y una emisión sin la acción de anticipación. |
| Retrasar | El sistema generará mensajes de acción, conforme sean necesarios, para mover los pedidos a una fecha posterior. En el campo **Retrasar margen** puede especificar el número máximo de días que pueden transcurrir entre una recepción y una emisión sin acción de retraso. |
| Disminuir | El sistema generará mensajes de acción cuando los pedidos de producción, los pedidos de compra y otras transacciones de recepción se deban disminuir para evitar el exceso de niveles de inventario. |
| Aumentar | El sistema generará mensajes de acción cuando los pedidos de producción, los pedidos de compra y otras transacciones de recepción se deban incrementar para evitar la escasez en el inventario. |
| Acciones derivadas | Los mensajes de acción que se crean para las transacciones de recepción se propagarán a cualquier requisito derivado y se generarán los mensajes de acción necesarios para las transacciones de recepción que satisfagan esos requisitos. |

Las siguientes secciones proporcionan algunos escenarios detallados.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Aumentar y disminuir acciones con cantidades de pedido predeterminadas de productos

En la página **Configuración de pedido predeterminada** de un artículo, puede configurar una cantidad mínima de pedido, una cantidad máxima de pedido y varios valores. Luego, el sistema tiene en cuenta esta configuración cuando sugiere acciones, para garantizar que las sugerencias nunca causen un suministro insuficiente.

Por ejemplo, tiene un artículo con la siguiente configuración en su página **Configuración de pedido predeterminada**:

- **Cantidad mínima de pedido:** *0*
- **Cantidad máxima de pedido:** *90*
- **Múltiple:** *20*

Si hay una demanda de una cantidad de 60 de este artículo, la planificación maestra creará un pedido de compra planificado para una cantidad de 60. Si la demanda se aumenta en 30, el plan maestro sugerirá un aumento de 40, porque respetará el múltiplo de 20 y nunca causará falta de suministro.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Mensajes de acción para pedidos relacionados con las existencias de seguridad

Los mensajes de acción para pedidos que suministren existencias de seguridad nunca sugerirán disminuir la cantidad por debajo de la cantidad que se necesita para las existencias de seguridad. En otras palabras, si hay un pedido que suministra existencias de seguridad y demanda del cliente, y la demanda disminuye o se cancela, la planificación maestra sugerirá disminuir el pedido planificado en la disminución de la demanda. Sin embargo, nunca sugerirá un valor inferior a las existencias de seguridad que se necesitan.

El sistema no sugerirá la postergación de acciones para el abastecimiento de las existencias de seguridad, ya que se asume que las existencias de seguridad deben suministrarse en el momento y la fecha requeridos.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Adelantar y posponer acciones relacionadas con las listas de materiales

Las acciones que están relacionadas con los componentes de las listas de materiales (BOM) deben aplicarse antes que las acciones de sus artículos primarios, ya que es posible que se vean afectadas otros pedidos relacionados con listas de materiales de nivel superior. A continuación, debe volver a ejecutar la planificación maestra para volver a calcular y sugerir las acciones adecuadas.

Por ejemplo, se encuentra en la siguiente situación:

- La mercancía final *FG* de tipo *producción* tiene una lista de materiales que incluye la materia prima *RM*.
- La fecha de hoy es el 21 de enero.
- Un pedido de producción liberado existente para *FG* está previsto para el 25 de enero.
- Para respaldar el pedido de producción existente, la planificación maestra ha creado un pedido de compra planificado para la materia prima requerida *RM*. Este pedido tiene como fecha requerida el 25 de enero.
- Se crea hoy un nuevo pedido de ventas para el cliente *FG*. Tiene una fecha requerida de hoy (21 de enero).
- El 21 de enero está cerrado para la entrega en el calendario *RM*, pero el 22 de enero está abierto.

Cuando se ejecuta la planificación maestra, genera mensajes de acción anticipada que sugieren aumentar la producción programada previamente para que pueda cumplir con el pedido de hoy.

- Para satisfacer la nueva demanda, sugiere mover el pedido de producción para *FG* hasta el 21 de enero. (Hace esta sugerencia sin considerar la fecha de cierre para *RM*).
- Como *RM* aún se requiere para la orden de producción, sugiere subir también el pedido de compra planificado. Sin embargo, esta vez, comprueba el calencario *RM*. Por lo tanto, sugiere mover el pedido de compra planificado para *RM* al 22 de enero (porque el 21 de enero está cerrado).

Como puede ver, la materia prima requerida *RM* ahora llegará demasiado tarde para la producción programada de *FG*. Por lo tanto, primero debe aplicar la acción de avance al pedido de compra planificado para *RM* y luego vuelva a ejecutar la planificación maestra. En ese momento, la planificación maestra generará un nuevo mensaje de acción que sugiere mover el pedido de producción para *FG* al 22 de enero.
