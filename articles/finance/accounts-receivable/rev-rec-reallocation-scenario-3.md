---
title: 'Reasignación de reconocimiento de ingresos: escenario 3'
description: En este tema se aborda un escenario de reasignación en el que se agrega una nueva línea a un pedido de ventas facturado y existente. Cuando se agrega un nuevo artículo a un contrato, se puede agregar a un nuevo pedido de ventas o al pedido de ventas existente.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca61a64199d9a61d0ddaa95c49e847e4be35c07b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238337"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Reasignación de reconocimiento de ingresos: escenario 3

[!include [banner](../includes/banner.md)]

En este tema se aborda un escenario de reasignación en el que se agrega una nueva línea a un pedido de ventas facturado y existente. Cuando se agrega un nuevo artículo a un contrato, se puede agregar a un nuevo pedido de ventas o al pedido de ventas existente. En este escenario también se muestra lo que ocurre cuando se actualiza Clientes debido a la reasignación.

En este escenario, la opción **Registrar correcciones de factura en clientes al reasignar** se establece en **Sí** en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**).

[![Opción Registrar correcciones de factura en clientes al reasignar establecida en Sí](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Se crea un pedido de ventas para el cliente US\_SI\_0003. El cliente está comprando un portátil (código de artículo S0012) y un plan de soporte técnico para este (código de artículo S0008, "Servicio de ingeniería sostenido"). Los ingresos por el ordenador portátil se reconocen de inmediato. Los ingresos del plan de soporte técnico se diferirán y reconocerán durante 12 meses, según se define en el intervalo de fechas del contrato.

[![Líneas de pedido de ventas para el ordenador portátil y el plan de soporte](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

El pedido de ventas se confirma. Puesto que los dos artículos están configurados para la asignación de precios de ingresos, el precio de ingresos se calcula cuando se confirma el pedido de ventas. Puede ver los ingresos que se reconocerán en la página **Asignación de precios de ingresos** (en la página **Pedidos de ventas**, en el panel de acciones, en la pestaña **Administrar**, en el grupo **Reconocimiento de ingresos**, seleccione **Asignación de precios de ingresos**). Los ingresos por el ordenador portátil se registrarán en la cuenta de ingresos por un importe de 1008,01 $. Los ingresos por el plan de soporte técnico se registrarán en la cuenta de ingresos diferidos por un importe de 190,99 USD. La suma de los precios de ingresos debe ser igual a la suma de las líneas que se configuraron para capturar la asignación de precios de ingresos (1199,00 USD).

[![Página Asignación de precios de ingresos](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

El pedido de ventas está completamente facturado. En la siguiente ilustración se muestra el asiento contable que se registra para la factura.

[![Entrada contable para el pedido de ventas completamente facturado](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

La programación de reconocimiento de ingresos también se crea. Después de un tiempo, dos de los meses han reconocido ingresos para el plan de soporte.

[![Página Programación de reconocimiento de ingresos después de dos meses](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

Llegado este punto, el cliente decide agregar servicios de instalación (código de artículo S0001). Este artículo se agrega al pedido de ventas existente. El cliente tendrá que confirmar que desea modificar el pedido de ventas completamente facturado y seleccionar **Sí**.

[![Pedido de ventas después de que se agregue la línea para servicios de instalación](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Si este nuevo artículo es el único cambio en el contrato del cliente, el proceso de reasignación se puede ejecutar ahora. En el pedido de ventas, seleccione **Reasignar precio con nuevas líneas de pedido** para abrir la página **Reasignar precio con nuevas líneas de pedido**. Seleccione todas las líneas de pedido de ventas para este pedido de ventas y luego seleccione **Actualizar reasignación**. La columna **Importe reasignado** muestra el nuevo precio de ingresos para cada línea de pedido de ventas.

[![Nuevos precios de ingresos en la página Reasignar precio con nuevas líneas de pedido](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

A continuación, seleccione **Asiento esperado** para ver los asientos contables. Puesto que la opción **Registrar correcciones de factura en clientes** está establecida en **Sí** en la página **Parámetros de Contabilidad general**, estos asientos contables se registrarán en la Contabilidad general a través del documento de crédito y se creará una nueva factura en Clientes.

[![Asiento contables en la página Asiento esperado](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

En la página **Asiento esperado**, las últimas cuatro líneas invierten el asiento contable original de la factura registrada. Las primeras cinco líneas son los nuevos asientos contables que se registran para la factura. Es importante que comprenda que no se presenta una nueva factura al cliente. Después de la reasignación, el cliente aún debe 1.276,94 $, que es el importe que debe registrarse en Clientes en el nuevo asiento contable. El impuesto de compensación y los ingresos o ingresos diferidos son iguales a 995,83 $ + 188,69 $ + 77,94 $ = 1262,46 $. El importe de ingresos o ingresos diferidos ha cambiado debido a la reasignación. La diferencia de -14,48 $ se registra en una cuenta de compensación de ingresos de factura parcial. Este saldo se liquidará cuando se registre la factura del nuevo artículo que se agregó al pedido de ventas.

Para completar la reasignación, seleccione **Procesar**. Se introduce una fecha de registro. Una vez completada la reasignación, la página **Asignación de precios de ingresos** muestra la reasignación de precios para los tres artículos.

[![Reasignación de precios para los tres artículos en la página Asignación de precios de ingresos](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

También se actualizó la programación de reconocimiento de ingresos, en función del nuevo precio de reasignación de ingresos. Desde el pedido de ventas, abra la página **Programación de reconocimiento de ingresos**. Anteriormente, había 13 líneas para el artículo S0008 (se asignó una programación de 12 meses a este artículo). Ahora hay 39 líneas: las 13 líneas de programación originales, 13 líneas de programación de inversión y 13 líneas que se basan en el nuevo precio de ingresos.

[![Página actualizada Programación de reconocimiento de ingresos con 39 líneas para el artículo S0008](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Cuando seleccione **Asiento**, el diario de facturas muestra el asiento contable original. Para ver el asiento de inversión y el nuevo asiento contable del pedido de ventas, seleccione **Ajustes de ingresos** en el Panel de acciones y luego **Asiento**.

A continuación, abra la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**), seleccione cliente **US\_SI\_0003** y luego **Transacciones**. La página **Transacciones del cliente** muestra la factura original (000006), el documento de inversión (000006-1) y la nueva factura (000006-2). La factura original y el documento de inversión se liquidan entre sí y tienen un saldo de 0 (cero). Vea el asiento para cada documento para ver el impacto en la Contabilidad general.

[![Factura original, documento de inversión y nueva factura en la página Transacciones del cliente](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

El pedido de ventas se factura de nuevo para el artículo que se agregó. La factura total que se presenta al cliente es de 300,00 $ + 19,50 $ de impuestos = 319,50 $. En la siguiente ilustración se muestra el asiento contable que se registra.

[![Página Transacciones de asiento con el asiento contable que se registra](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Puesto que la suma de los ingresos y las ventas es superior a 319,50 $, la diferencia se registra por 14,48 $. Este importe borra el saldo de la cuenta de compensación de ingresos de factura parcial. Ese saldo se actualizó en el nuevo asiento contable que se registró después de la reasignación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]