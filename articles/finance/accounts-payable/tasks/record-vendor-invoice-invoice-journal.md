---
title: Registrar una factura de proveedor en el diario de facturas
description: Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971837"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrar una factura de proveedor en el diario de facturas

[!include [banner](../../includes/banner.md)]

Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra. Algunos ejemplos de este tipo de factura incluyen los gastos para suministros o servicios.  Esta grabación usa la empresa de demostración USMF.

1. Vaya a **Panel de navegación > Módulos > Proveedores > Espacios de trabajo > Entrada de factura de proveedor**.
2. En el **Panel de acciones**, haga clic en **Nuevo diario de facturas**.
3. Haga clic en **Nuevo**.
4. En el campo **Nombre**, escriba el nombre del diario o haga clic en el botón desplegable para abrir la búsqueda.
5. En el campo **Descripción**, escriba un valor.
6. En el **panel de acciones**, haga clic en **Líneas**. En el campo **Fecha**, especifique la fecha de registro que va a actualizar la contabilidad general.  
7. En el campo **Cuenta**, especifique la **cuenta del proveedor**.
8. En el campo **Factura**, especifique el número de factura.
9. En el campo **Descripción**, escriba un valor.
10. En el campo **Crédito**, escriba un número.
11. En el campo **Cuenta de contrapartida**, escriba el número de cuenta o haga clic en el botón desplegable para abrir la búsqueda.
    * El valor predeterminado del **grupo de impuestos** proviene de la cuenta de proveedor  
    * El valor predeterminado proviene del campo **Grupo de impuestos de artículos** de la cuenta principal especificada en el campo **Cuenta de contrapartida**.  
    * La **fecha de vencimiento** se calculará según las condiciones de pago.  
    * El **descuento por pronto pago** proviene de la cuenta de proveedor
12. Si ha habilitado el flujo de trabajo del diario de facturas de proveedores, haga clic en **Flujo de trabajo > Enviar**.
    * Cuando se aprueba su envío, la fecha se adelantará al primer día del próximo período abierto, si la fecha de contabilización de la transacción cae dentro de un período que está En espera o Cerrado para la contabilización del libro mayor.
12. Haga clic en **Registrar**.
13. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]