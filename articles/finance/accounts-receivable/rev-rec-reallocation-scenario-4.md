---
title: 'Reasignación de reconocimiento de ingresos: escenario 4'
description: En este tema se aborda un escenario de reasignación en el que se eliminar una línea de un pedido de ventas existente y facturado parcialmente. Este escenario produce el mismo resultado, independientemente de si la línea se elimina del pedido de ventas o se establece en un estado cancelado.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b9aada2c110ea3b7e70157e6edce9647bbfd28fe307654e10f6d38585090563
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758954"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Reasignación de reconocimiento de ingresos: escenario 4

[!include [banner](../includes/banner.md)]

En este tema se aborda un escenario de reasignación en el que se eliminar una línea de un pedido de ventas existente y facturado parcialmente. Este escenario produce el mismo resultado, independientemente de si la línea se elimina del pedido de ventas o se establece en un estado cancelado.

En este escenario, la opción **Registrar correcciones de factura en clientes al reasignar** se establece en **No** en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**).

[![Opción Registrar correcciones de factura en clientes al reasignar establecida en No.](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Se crea un pedido de ventas para el cliente US\_SI\_0003. El cliente está comprando un ordenador portátil (código de artículo S0012), servicios de instalación (código de artículo S0001) y un plan de soporte para el portátil (código de artículo S0008, "Servicio de ingeniería sostenido"). Los ingresos por el ordenador portátil y los servicios de instalación se reconocen de inmediato. Los ingresos del plan de soporte técnico se diferirán y reconocerán durante 12 meses, según se define en el intervalo de fechas del contrato.

[![Líneas de pedido de ventas para el portátil, los servicios de instalación y el plan de soporte.](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

El pedido de ventas se confirma. Puesto que los tres artículos están configurados para la asignación de precios de ingresos, el precio de ingresos se calcula cuando se confirma el pedido de ventas. Puede ver los ingresos que se reconocerán en la página **Asignación de precios de ingresos** (en la página **Pedidos de ventas**, en el panel de acciones, en la pestaña **Administrar**, en el grupo **Reconocimiento de ingresos**, seleccione **Asignación de precios de ingresos**). Los ingresos por el ordenador portátil se registrarán en la cuenta de ingresos por un importe de 995,84 $. Los ingresos por los servicios de instalación también se registrarán en una cuenta de ingresos por un importe de 314,47 $. Los ingresos por el plan de soporte se registrarán en una cuenta de ingresos diferidos por un importe de 188,69 $. La suma de los precios de ingresos debe ser igual a la suma de las líneas que se configuraron para capturar la asignación de precios de ingresos (1499,00 $).

[![Página Asignación de precios de ingresos.](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

Se factura al cliente por el ordenador portátil y el plan de soporte, pero no por los servicios de instalación. En la siguiente ilustración se muestra el asiento contable que se registra para la factura.

[![Asiento contable para el pedido de ventas facturado.](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

El asiento contable registra 1276,94 $ en Clientes. Sin embargo, puesto que esta factura es una factura parcial, los ingresos o ingresos diferidos más impuestos no equivalen al importe de Clientes. La diferencia de -14,47 $ se registra en la cuenta de compensación de ingresos de factura parcial.

La programación de reconocimiento de ingresos también se crea.

[![Página de programación de reconocimiento de ingresos para la factura parcial.](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

Posteriormente, el cliente decide no adquirir los servicios de instalación. Por lo tanto, esa línea se elimina del pedido de ventas. Tenga en cuenta que el pedido de ventas no se puede confirmar de nuevo, ya que solo quedan líneas facturadas en el pedido de ventas.

[![Pedido de ventas después de que se elimine la línea para servicios de instalación.](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Aunque el pedido de ventas no se puede confirmar, se puede reasignar. En el pedido de ventas, seleccione **Reasignar precio con nuevas líneas de pedido** para abrir la página **Reasignar precio con nuevas líneas de pedido**. Seleccione las dos líneas de pedido de ventas restantes y luego seleccione **Actualizar reasignación**. La columna **Importe reasignado** muestra el nuevo precio de ingresos para cada línea de pedido de venta restante.

[![Nuevos precios de ingresos en la página Reasignar precio con nuevas líneas de pedido.](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

A continuación, seleccione **Asiento esperado** para ver los asientos contables.

[![Asientos contables en la página Asiento esperado.](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

En la página **Asiento esperado**, las últimas cinco líneas invierten el asiento contable original de la factura registrada. Las primeras cuatro líneas son los nuevos asientos contables que se registran para la factura. Es importante que comprenda que no se presenta una nueva factura al cliente. Después de la reasignación, el cliente aún debe 1.276,94 $, que es el importe que debe registrarse en Clientes en el nuevo asiento contable. Los nuevos ingresos o ingresos diferidos más impuestos equivalen a 1276,94 $. Por lo tanto, no tiene que registrarlo en la cuenta de compensación de ingresos de factura parcial.

Para completar la reasignación, seleccione **Procesar**. Se introduce una fecha de registro. Una vez completada la reasignación, la página **Asignación de precios de ingresos** muestra la reasignación de precios para los dos artículos restantes.

[![Reasignación de precios para los artículos restantes en la página Asignación de precios de ingresos.](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

También se actualizó la programación de reconocimiento de ingresos, en función del nuevo precio de reasignación de ingresos. Desde el pedido de ventas, abra la página **Programación de reconocimiento de ingresos**. Anteriormente, había 13 líneas para el artículo S0008 (se asignó una programación de 12 meses a este artículo). Ahora hay 39 líneas: las 13 líneas de programación originales, 13 líneas de programación de inversión y 13 líneas que se basan en el nuevo precio de ingresos.

[![Página actualizada Programación de reconocimiento de ingresos con 39 líneas para el artículo S0008.](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Cuando seleccione **Asiento**, el diario de facturas muestra el asiento contable original. Para ver el asiento de inversión y el nuevo asiento contable del pedido de ventas, seleccione **Ajustes de ingresos** en el Panel de acciones y luego **Asiento**.

A continuación, abra la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**), seleccione cliente **US\_SI\_0003** y luego **Transacciones**. La página **Transacciones del cliente** muestra solo la factura original (000008), junto con el asiento contable original. Puesto que la opción **Registrar correcciones de factura en clientes** está establecida en **No** en la página **Parámetros de Contabilidad general**, solo se actualiza la Contabilidad general. Por lo tanto, no se muestran los asientos contables actualizados y de inversión. Tenga en cuenta que se muestran las transacciones de ajuste de ingresos que se crearon en el [escenario 3](rev-rec-reallocation-scenario-3.md).

[![Asiento contable original en la página Transacciones del cliente.](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]