---
title: Crear facturas de pedidos de ventas
description: Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140289"
---
# <a name="create-sales-order-invoices"></a>Crear facturas de pedidos de ventas

[!include [banner](../../includes/banner.md)]

Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes. Este procedimiento usa la empresa de demostración USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Crear una factura a partir de un pedido de ventas
1. Vaya a **Panel de navegación > Módulos > Clientes > Pedidos > Pedidos de ventas enviados pero no facturados**.
2. Seleccione un pedido de ventas en la lista. 
3. En el **panel de acciones**, haga clic en **Factura > Generar > Factura**. Tenga en cuenta que este pedido de ventas tiene varios albaranes asociados con él. Solo mostrará la palabra <multiple> en lugar del número de albarán.  
4. Expanda la sección **Parámetros**.
    - El registro se debe establecer en Sí para registrar la factura. También puede desactivar el registro y solo imprimir la factura. Sin embargo, puede lograr el mismo resultado creando una factura de proforma en lugar de una factura.  
    - Esta opción es la que se usa para trabajos por lotes. El trabajo por lotes se ejecuta al registrar pedidos de ventas.
5. En el campo **Imprimir**, seleccione "Después de".
6. Seleccione **Sí** para **Imprimir factura**. La gestión de impresión puede imprimir varias copias de la factura y también enviar la factura por correo electrónico como archivo PDF.  
7. En el campo **Imprimir costes**, seleccione "Resumir".
8. En el campo **Comprobar límite de crédito**, seleccione "Saldo".
9. Haga clic en **Cancelar**.

## <a name="combine-orders-into-a-single-invoice"></a>Combinar pedidos en una única factura
1. Vaya a **panel de navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.
2. Localice a un cliente que tenga varias facturas abiertas.
3. Seleccione varios pedidos de ventas abiertos del mismo cliente.
4. En el **panel de acciones**, haga clic en **Factura > Generar > Factura**.
5. Expanda la sección **Parámetros**.
6. En el campo **Cantidad**, seleccione "Todo". Tenga en cuenta que hay dos facturas que aparecen en la sección de descripción. Ahora vamos a combinarlas en una única factura.  
7. En el campo **Actualización conjunta para**, seleccione "Cuenta de facturación".
8. Haga clic en **Organizar** para combinar los pedidos de ventas en una única factura. Los dos pedidos de ventas se combinan ahora en una única factura.   
9. Haga clic en **Cancelar**.
10. Haga clic en **Sí**.

## <a name="post-invoices-in-a-batch"></a>Registrar facturas en un lote
1. Vaya a **Panel de exploración >Módulos > Clientes > Facturas > Facturación por lotes > Factura de clientes abiertas**.
2. Haga clic en **Seleccionar**.
3. Haga clic en **Aceptar**.
4. Haga clic en **Lote**.
5. Seleccione **Sí** para el **procesamiento por lotes**.
6. Haga clic en **Periodicidad**.
7. Seleccione **Días**.
8. Haga clic en **Aceptar**.
9. Haga clic en **Aceptar**.
10. Haga clic en **Cancelar**.
11. Haga clic en **Sí**.

