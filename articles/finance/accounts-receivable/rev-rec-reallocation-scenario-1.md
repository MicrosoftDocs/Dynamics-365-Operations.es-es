---
title: 'Reasignación de reconocimiento de ingresos: escenario 1'
description: En este tema se repasa un escenario de reasignación en el que se introducen dos pedidos de ventas pero solo se confirman. El mismo escenario producirá resultados similares si más de dos pedidos de ventas se encuentran en estado confirmado.
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
ms.openlocfilehash: d63082553f8625a9953b0a85d59a4949a37c92770ce2a41a43d78cf0266f3b85
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770722"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Reasignación de reconocimiento de ingresos: escenario 1

[!include [banner](../includes/banner.md)]

En este tema se repasa un escenario de reasignación en el que se introducen dos pedidos de ventas pero solo se confirman. El mismo escenario producirá resultados similares si más de dos pedidos de ventas se encuentran en estado confirmado.

En este escenario, la opción **Registrar correcciones de factura en clientes al reasignar** se establece en **No** en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**).

[![Opción Registrar correcciones de factura en clientes al reasignar establecida en No.](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Se crea un pedido de ventas para el cliente US\_SI\_0003. El cliente está comprando un portátil (código de artículo S0012) y un plan de soporte técnico para este (código de artículo S0008, "Servicio de ingeniería sostenido"). Los ingresos del portátil se reconocen inmediatamente (no hay una programación de reconocimiento de ingresos). Los ingresos del plan de soporte técnico se diferirán y reconocerán durante 12 meses, según se define en el intervalo de fechas del contrato.

[![Líneas de pedido de ventas para el ordenador portátil y el plan de soporte.](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

El pedido de ventas se confirma. Puesto que los dos artículos están configurados para la asignación de precios de ingresos, el precio de ingresos se calcula cuando se confirma el pedido de ventas. Puede ver los ingresos que se reconocerán en la página **Asignación de precios de ingresos** (en la página **Pedidos de ventas**, en el panel de acciones, en la pestaña **Administrar**, en el grupo **Reconocimiento de ingresos**, seleccione **Asignación de precios de ingresos**). Los ingresos por el portátil se registrarán en la cuenta de ingresos por un importe de 1008,01 USD. Los ingresos por el plan de soporte técnico se registrarán en la cuenta de ingresos diferidos por un importe de 190,99 USD. La suma de los precios de ingresos debe ser igual a la suma de las líneas que se configuraron para capturar la asignación de precios de ingresos (1199,00 $).

[![Página Asignación de precios de ingresos.](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

El cliente decidió no comprar servicios de instalación (código de artículo S0001) en el momento de la venta, pero luego cambió de opinión. Por lo tanto, se introduce un segundo pedido de ventas para el mismo cliente.

[![Línea de pedido de ventas para servicios de instalación.](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

El segundo pedido de ventas se confirma. Debido a que este pedido de ventas contiene solo una línea, la asignación de precios de ingresos no se realiza cuando se confirma el pedido de ventas. La asignación de precios de ingresos solo se produce si hay dos o más artículos únicos y si estos están configurados para la asignación de precios de ingresos.

Si este nuevo pedido de ventas es el único cambio en el contrato del cliente, el proceso de reasignación se puede ejecutar ahora. En uno de los dos pedidos de ventas, seleccione **Reasignar precio con nuevas líneas de pedido** para abrir la página **Reasignar precio con nuevas líneas de pedido**. Alternativamente, vaya a **Reconocimiento de ingresos \> Tareas periódicas \> Reasignar precio con nuevas líneas de pedido**. Seleccione los dos pedidos de ventas y las líneas de pedido de ventas correspondientes, y luego seleccione **Actualizar reasignación**. La columna **Importe reasignado** muestra el nuevo precio de ingresos para cada línea de pedido de ventas.

[![Nuevos precios de ingresos en la página Reasignar precio con nuevas líneas de pedido.](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Si selecciona **Asiento esperado**, no se muestra nada, porque no se han registrado facturas.

Para completar la reasignación, seleccione **Procesar**. Se le solicita una fecha de registro, aunque no se registre nada. Una vez completada la reasignación, la página **Asignación de precios de ingresos** de cada pedido de ventas mostrará la asignación de precios de todos los artículos en ambos pedidos de ventas. En otras palabras, la página **Asignación de precios de ingresos** de cada pedido de ventas incluirá un artículo que no existe en ese pedido de ventas, porque es parte del mismo contrato pero en un pedido de ventas diferente.

> [!TIP]
> Para ofrecer contexto sobre el motivo por el cual se muestran estos artículos adicionales, puede agregar otras columnas a la cuadrícula, como **Id. de reasignación** y **Pedido de ventas**.
> 
> [![Columnas adicionales en la página Asignaciones de precios de ingresos.](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]