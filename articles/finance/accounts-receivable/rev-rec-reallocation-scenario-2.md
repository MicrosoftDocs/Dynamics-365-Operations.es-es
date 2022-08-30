---
title: 'Reasignación de reconocimiento de ingresos: escenario 2'
description: En este artículo se aborda un escenario de reasignación en el que se introducen dos pedidos de ventas y luego el cliente agrega un artículo al contrato después de facturar el primer pedido de ventas. Cuando se agrega un nuevo artículo a un contrato, se puede agregar a un nuevo pedido de ventas o al pedido de ventas existente.
author: bking
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5f8dac2991b309bb91faaa3107480ca3860af008
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348393"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Reasignación de reconocimiento de ingresos: escenario 2

[!include [banner](../includes/banner.md)]

En este artículo se aborda un escenario de reasignación en el que se introducen dos pedidos de ventas y luego el cliente agrega un artículo al contrato después de facturar el primer pedido de ventas. Cuando se agrega un nuevo artículo a un contrato, se puede agregar a un nuevo pedido de ventas o al pedido de ventas existente.

En este escenario, la opción **Registrar correcciones de factura en clientes al reasignar** se establece en **No** en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**).

[![Opción Registrar correcciones de factura en clientes al reasignar establecida en No.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Se crea un pedido de ventas para el cliente US\_SI\_0003. El cliente está comprando servicios de instalación (código de artículo S0001) y un plan de soporte (código de artículo S0008) para un ordenador portátil, pero aún no ha seleccionado el ordenador portátil. Los ingresos por los servicios de instalación se diferirán hasta la fecha de compra del ordenador portátil. Los ingresos del plan de soporte técnico se diferirán y reconocerán durante 12 meses, según se define en el intervalo de fechas del contrato.

[![Líneas de pedido de ventas para los servicios de instalación y el plan de soporte.](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

El pedido de ventas se confirma. Puesto que los dos artículos están configurados para la asignación de precios de ingresos, el precio de ingresos se calcula cuando se confirma el pedido de ventas. Puede ver los ingresos que se reconocerán en la página **Asignación de precios de ingresos** (en la página **Pedidos de ventas**, en el panel de acciones, en la pestaña **Administrar**, en el grupo **Reconocimiento de ingresos**, seleccione **Asignación de precios de ingresos**). Los ingresos por los servicios de instalación se registrarán en una cuenta de ingresos diferidos por un importe de 250,00 $. Los ingresos por el plan de soporte también se registrarán en una cuenta de ingresos diferidos por un importe de 150,00 $. La suma de los precios de ingresos debe ser igual a la suma de las líneas que se configuraron para capturar la asignación de precios de ingresos (400,00 $).

[![Página Asignación de precios de ingresos.](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

El pedido de ventas está completamente facturado. En la siguiente ilustración se muestra el asiento contable que se registra para la factura.

[![Asiento contable para el pedido de ventas completamente facturado.](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

También se crea la programación de reconocimiento de ingresos, pero aún no se reconoce ninguno de los ingresos.

[![Página de programación de reconocimiento de ingresos.](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Unos días después, el cliente selecciona un ordenador portátil. Se introduce un segundo pedido de ventas para el cliente.

[![Línea de pedido de ventas para el ordenador portátil.](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

El segundo pedido de ventas se confirma. Debido a que este pedido de ventas contiene solo una línea, la asignación de precios de ingresos no se realiza cuando se confirma el pedido de ventas. La asignación de precios de ingresos solo se produce si hay dos o más artículos únicos y si estos están configurados para la asignación de precios de ingresos.

Si este nuevo pedido de ventas es el único cambio en el contrato del cliente, el proceso de reasignación se puede ejecutar ahora. En uno de los dos pedidos de ventas, seleccione **Reasignar precio con nuevas líneas de pedido** para abrir la página **Reasignar precio con nuevas líneas de pedido**. Alternativamente, vaya a **Reconocimiento de ingresos \> Tareas periódicas \> Reasignar precio con nuevas líneas de pedido**. Seleccione los dos pedidos de ventas y las líneas de pedido de ventas correspondientes, y luego seleccione **Actualizar reasignación**. La columna **Importe reasignado** muestra el nuevo precio de ingresos para cada línea de pedido de ventas.

[![Nuevos precios de ingresos en la página Reasignar precio con nuevas líneas de pedido.](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

A continuación, seleccione **Asiento esperado** para ver los asientos contables que se registrarán solo en la Contabilidad general. Puesto que la opción **Registrar correcciones de factura en clientes** está establecida en **No** en la página **Parámetros de Contabilidad general**, no se cambiará nada en Clientes cuando se procese la reasignación.

[![Asientos contables en la página Asiento esperado.](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

En la página **Asiento esperado**, las últimas tres líneas invierten el asiento contable original de la factura registrada. Las primeras cuatro líneas constituyen el nuevo asiento contables que se registra para la factura. Es importante que comprenda que no se presenta una nueva factura al cliente. Después de la reasignación, el cliente aún debe 426,00 $, que es el importe que debe registrarse en Clientes en el nuevo asiento contable. El impuesto de compensación y los ingresos diferidos son iguales a 188,69 $ + 314,48 $ + 26,00 $ = 529,17 $. El importe de ingresos diferidos ha cambiado debido a la reasignación. La diferencia de 103,17 $ se registra en una cuenta de compensación de ingresos de factura parcial. Este saldo se liquidará cuando se registre la factura del segundo pedido de ventas que se incluyó en la reasignación.

Para completar la reasignación, seleccione **Procesar**. Se le solicita una fecha de registro, aunque no se registre nada. Una vez completada la reasignación, la página **Asignación de precios de ingresos** de cada pedido de ventas mostrará la asignación de precios de todos los artículos en ambos pedidos de ventas. En otras palabras, la página **Asignación de precios de ingresos** de cada pedido de ventas incluirá un artículo que no existe en ese pedido de ventas, porque es parte del mismo contrato pero en un pedido de ventas diferente.

> [!TIP]
> Para ofrecer contexto sobre el motivo por el cual se muestran estos artículos adicionales, puede agregar otras columnas a la cuadrícula, como **Id. de reasignación** y **Pedido de ventas**.
> 
> [![Columnas adicionales en la página Asignaciones de precios de ingresos.](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

En el pedido de ventas 00036, también se actualizó la programación de reconocimiento de ingresos, en función del nuevo precio de reasignación de ingresos. Desde este pedido de ventas, abra la página **Programación de reconocimiento de ingresos**. Anteriormente, había 13 líneas para el artículo S0008 (se asignó una programación de 12 meses a este artículo). Ahora hay 39 líneas: las 13 líneas de programación originales, 13 líneas de programación de inversión y 13 líneas que se basan en el nuevo precio de ingresos.

[![Página actualizada Programación de reconocimiento de ingresos con 39 líneas para el artículo S0008.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Del mismo modo, anteriormente había dos líneas para el artículo S0001, pero ahora hay seis.

[![Página actualizada Programación de reconocimiento de ingresos con seis líneas para el artículo S0001.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Cuando seleccione **Asiento** en el pedido de ventas 000036, el diario de facturas muestra el asiento contable original. Para ver el asiento de inversión y el nuevo asiento contable del pedido de ventas, seleccione **Ajustes de ingresos** en el panel de acciones y luego **Asiento**.

[![Pedido de ventas 000036.](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

A continuación, abra la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**), seleccione cliente **US\_SI\_0003** y luego **Transacciones**. Se mostrará la factura abierta del pedido de ventas 000036. Si selecciona el asiento, verá el asiento contable original, no el nuevo asiento contable de la reasignación. El asiento de inversión y el nuevo asiento contable no se pueden ver desde Clientes.

El segundo pedido de ventas está ahora facturado. La factura total que se presenta al cliente es de 1.099,00 $ + 71,44 $ de impuestos = 1.170,44 $. En la siguiente ilustración se muestra el asiento contable que se registra.

[![Página Transacciones de asiento con el asiento contable que se registra.](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Puesto que la suma de los ingresos y las ventas es superior a 1170,44 $, la diferencia se registra por -130,17 $. Este importe borra el saldo de la cuenta de compensación de ingresos de factura parcial. Ese saldo se registra en el nuevo asiento contable después de la reasignación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
