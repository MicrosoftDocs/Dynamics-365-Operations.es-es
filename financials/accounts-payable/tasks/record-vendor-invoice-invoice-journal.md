--- 
title: Registrar una factura de proveedor en el diario de facturas
description: "Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 127875443da1d43783440083b11afd423f2a12fe
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrar una factura de proveedor en el diario de facturas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra. Algunos ejemplos de este tipo de factura incluyen los gastos para suministros o servicios.  Esta grabación usa la empresa de demostración USMF.

1. Vaya a Proveedores > Áreas de trabajo > Entrada de factura de proveedor.
2. Haga clic en Diario de facturas nuevas.
3. Haga clic en Nuevo.
4. En el campo Nombre, escriba el nombre del diario o haga clic en el botón desplegable para abrir la búsqueda.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Líneas.
    * En el campo Fecha, especifique la fecha de registro que va a actualizar la contabilidad general.  
7. En el campo Cuenta, especifique la cuenta del proveedor.
8. En el campo Factura, especifique el número de factura.
9. En el campo Descripción, escriba un valor.
10. En el campo Crédito, escriba un número.
11. En el campo Cuenta de contrapartida, escriba el número de cuenta o haga clic en el botón desplegable para abrir la búsqueda.
    * El valor predeterminado del grupo de impuestos proviene de la cuenta de proveedor  
    * El valor predeterminado proviene del campo Grupo de impuestos de artículos de la cuenta principal especificada en el campo Cuenta de contrapartida.  
    * La fecha de vencimiento se calculará según las condiciones de pago.  
    * El descuento por pronto pago proviene de la cuenta de proveedor  
12. Haga clic en Registrar.
13. Cierre la página.


