---
title: Calcular y ajustar los impuestos en una factura de proveedor
description: En este tema se explica cómo ajustar los impuestos para una factura de proveedor en Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03313d875d23489b3293376dd94f808c73a4bd15
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983558"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calcular y ajustar los impuestos en una factura de proveedor

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo ajustar los impuestos para una factura de proveedor. Si el documento de origen inicial muestra diferentes importes de impuestos según los calcula, puede ajustar dichos importes antes del registro. Esta tarea usa la empresa de demostración DEMF.

1. En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Diario de facturas**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre** de la nueva fila, seleccione una opción en el menú desplegable.
4. En el panel de acciones, seleccione **Líneas**.
5. En el campo **Cuenta**, especifique los valores deseados.
6. En el campo **Factura**, escriba un valor.
7. En el campo **Crédito**, escriba un número.
8. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
9. Seleccione **Impuestos**.
10. En el campo **Importe total real de impuestos**, escriba un número.
11. En la ficha **Ajuste**, los importes de impuestos se pueden ajustar por código de impuestos.
12. Seleccione **Restablecer importes reales a partir de los importes calculados**.
13. Seleccione **Aceptar**.
14. Seleccione **Guardar**.

