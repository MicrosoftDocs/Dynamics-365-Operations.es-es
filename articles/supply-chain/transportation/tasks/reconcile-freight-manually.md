---
title: Conciliar el flete manualmente
description: Este procedimiento muestra cómo conciliar el flete manualmente.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc4fc51955544df4d0156a4c83bcc5b5a0e13df3
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437227"
---
# <a name="reconcile-freight-manually"></a>Conciliar el flete manualmente

[!include [banner](../../includes/banner.md)]]

Este procedimiento muestra cómo conciliar el flete manualmente. Esto lo hace normalmente el coordinador de transporte. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.


## <a name="select-a-load-to-reconcile"></a>Seleccione una carga para conciliar
1. Vaya a Administración de transporte > Planificación > Área de trabajo de planificación de la carga.
2. Desactive la casilla Ocultar enviado y recibido. 
3. En la lista, seleccione el flete que tiene el identificador de carga 00006.

## <a name="create-a-carrier-invoice"></a>Cree una factura de transportista
Si se concilia el flete manualmente y no recibe facturas de transportista automáticamente, puede crear una factura basada en el albarán de flete.  
1. Haga clic en Información relacionada.
2. Haga clic en Detalles del albarán de flete.
3. Haga clic en Generar factura de albarán de flete.
4. En el campo Factura, escriba un valor.
5. Haga clic en Aceptar

## <a name="reconcile-the-invoice"></a>Concilie la factura
La conciliación de una factura de transportista y un albarán de flete se realiza línea por línea.  
1. Haga clic en Conciliar los albaranes de flete y las facturas.
2. Expanda la sección Detalles de factura.
3. Expanda la sección Detalles del albarán de flete no conciliado.
4. En la lista, marque la fila seleccionada.
5. Haga clic en Conciliar.
6. Expanda la sección Detalles del albarán de flete conciliado.

## <a name="submit-the-invoice-for-approval"></a>Enviar la factura para su aprobación
1. Haga clic en Enviar para aprobación.
2. Cierre la página.
3. Borre la casilla Ocultar elementos aprobados. 
4. Haga clic en Diarios de facturas de proveedor.
5. Haga clic para seguir el vínculo en el campo Número de diario de referencia.
6. Haga clic en Líneas.

