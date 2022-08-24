---
title: Actualizar el presupuesto de traspaso después de reducciones en pedidos de compra y facturas
description: En este artículo se describe cómo controlar lo que sucede con el traspaso de presupuesto cuando se cancelan o reducen los pedidos de compra y cuándo se reducen las facturas.
author: TaylorVH
ms.date: ''
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: Version 1611
ms.search.form: LedgerFund
ms.openlocfilehash: f51839b6890e39a2f2c5867977f3935ab43e2c5d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280541"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Actualizar el presupuesto de traspaso después de reducciones en pedidos de compra y facturas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se describe cómo controlar lo que sucede con el traspaso de presupuesto cuando se cancelan o reducen los pedidos de compra y cuándo se reducen las facturas.

Para obtener información sobre cómo se procesan los pedidos de compra al final del año, consulte [Procesar pedidos de compra al final del año](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Activar o desactivar las reducciones presupuestarias de traspaso para desviaciones de facturas

El sistema siempre puede actualizar el presupuesto de traspaso cuando se cancela o reduce un pedido de compra. Sin embargo, si desea actualizar el presupuesto de traspaso cuando se reduce una factura, debe activar la característica *Reducir el presupuesto de traspaso cuando una factura contra un pedido de compra se reduce con una desviación*. Los administradores pueden activar o desactivar esta característica buscándola en el área de trabajo **[Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Reducciones y cancelaciones de pedidos de compra

Independientemente de si está activada la característica *Reducir el presupuesto de traspaso cuando una factura contra un pedido de compra se reduce con una desviación*, el presupuesto de traspaso se actualizará cuando se cancele o reduzca un pedido de compra. Puede configurar cada fondo de contabilidad general para que responda de una de las siguientes maneras:

- Conservar el presupuesto traspasado tal y como se creó.
- Ajuste automáticamente el presupuesto de traspaso para eliminar el importe cancelado o reducido.

Solo las líneas de pedido de compra que tienen distribuciones que incluyen un fondo están disponibles para el ajuste presupuestario automático. El ajuste presupuestario automático ocurre cuando se finaliza el pedido de compra o se confirma una reducción del pedido de compra.

## <a name="invoice-reductions"></a>Reducciones de facturas

Cuando se activa la característica *Reducir el presupuesto de traspaso cuando una factura contra un pedido de compra se reduce con una desviación*, puede especificarse si cada fondo debe reducir el presupuesto de traspaso cuando se reduce una factura, además de cuando se cancele o reduzca un pedido de compra. La factura debe corresponder a un pedido de compra que tenga un presupuesto de traspaso. Las reducciones incluyen desviaciones de precios, desviaciones de cargos y desviaciones de impuestos. Cuando se reduce un pedido de compra de traspaso durante la facturación, se crea una desviación. Cuando se registra la factura, la reserva de gasto del pedido de compra se reducirá en el importe de la desviación. La característica también creará el ajuste presupuestario automático para el importe de la desviación.

Sin embargo, si se desactiva la característica *Reducir el presupuesto de traspaso cuando una factura contra un pedido de compra se reduce con una desviación*, el presupuesto de traspaso no se reduce en este escenario. Por lo tanto, se deja atrás el presupuesto de arrastre restante en el importe de la desviación.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Configurar las opciones de presupuesto de traspaso para cada fondo

Siga estos pasos para cada fondo de contabilidad general que debería poder reducir el presupuesto de traspaso rrastrado cuando se reduce un pedido de compra o una factura.

1. Vaya a **Contabilidad general \> Plan contable \> Fondos \> Fondos**.
1. Seleccione el fondo que quiera configurar.
1. En **Proceso de fin de año de pedidos de compra**, asegúrese de que la opción **Anular la opción de fin de año seleccionada** esté configurada en *Sí*.
1. En **Estado del presupuesto de traspaso**, seleccione el campo **Restablecer el presupuesto cuando se cancela o reduce un pedido de compra transferible** como mejor le convenga. Los ajustes tienen efectos ligeramente diferentes, dependiendo de si la característica *Reducir el presupuesto de traspaso cuando una factura contra un pedido de compra se reduce con una desviación* está activada en su sistema.

    - Cuando la característica está desactivada, el sistema reacciona solo a los pedidos de compra cancelados o reducidos. La configuración de opciones funciona de la siguiente manera:

        - *No*: el sistema crea un asiento de registro presupuestario para el saldo restante de los pedidos de compra que han sido cancelados o reducidos.
        - *Sí*: el sistema permite cancelar o reducir pedidos de compra, pero no crea un asiento de registro presupuestario. El presupuesto de traspaso permanece disponible para el consumo por parte de otros documentos.

    - Cuando la característica está activada, el sistema reacciona a las desviaciones de facturas y a los pedidos de compra cancelados o reducidos. La configuración de opciones funciona de la siguiente manera:

        - *No*: para las desviaciones de facturas, el sistema crea un asiento de registro presupuestario contra el pedido de compra por el importe de reducción de desviación. Para pedidos de compra cancelados o reducidos, esta configuración tiene el mismo efecto que cuando la función está desactivada.
        - *Sí*: para desviaciones de facturas, el sistema permite la reducción de facturas pero no crea un asiento de registro de presupuesto. El presupuesto de traspaso permanece disponible para el consumo por parte de otros documentos. Para pedidos de compra cancelados o reducidos, esta configuración tiene el mismo efecto que cuando la función está desactivada.

## <a name="additional-resources"></a>Recursos adicionales

- [Procesar pedidos de compra al final del año](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Mantener reservas de presupuesto generales](general-budget-reservation-tasks.md)
- [Fondos en el sector público](funds-public-sector.md)
- [Configurar un fondo en el sector público](tasks/set-up-fund-public-sector.md)
