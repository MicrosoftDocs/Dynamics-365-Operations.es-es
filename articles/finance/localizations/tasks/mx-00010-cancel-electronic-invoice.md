---
title: MX-00010 Cancelar facturas electrónicas
description: Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EInvoiceCFDIJournal_AR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63769dc6eabdfc782020014a8ef3177c6591454c
ms.sourcegitcommit: f717439a228358e85c99dfc97fd9fcc68d98b986
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "4407830"
---
# <a name="mx-00010-cancel-an-electronic-invoice"></a>MX-00010 Cancelar facturas electrónicas

[!include [banner](../../includes/banner.md)]

Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC. También puede cancelar una factura electrónica CFDI mediante el proceso manual.

## <a name="cancel-a-cfdi-electronic-invoice"></a>Cancelación de una factura electrónica CFDI
1. Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).
2. Seleccione una factura electrónica con estado Aprobada.
3. Haga clic en el vínculo del número de factura para ver los detalles.
4. En el panel de acciones, haga clic en Funciones.
5. Haga clic en Cancelar CFDI.
6. Cierre la página.
7. Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.
8. Haga clic en Aceptar
    * Cuando se confirma la cancelación, el estado de la factura electrónica cambia a Cancelada.  
9. Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).
10. Seleccione la factura cancelada para comprobar el estado.

>[!NOTE] 
> No puede cancelar un documento CFDI si existe un documento asociado. Por ejemplo, no puede cancelar un pago por adelantado si una factura hace referencia a ese pago. Primero debe cancelar los documentos asociados y luego cancelar el documento CFDI.

## <a name="manually-cancel-a-cfdi-electronic-invoice"></a>Cancelación manual de una factura electrónica CFDI
1. Seleccione una factura con estado Aprobada.
2. En el panel de acciones, haga clic en Funciones.
3. Haga clic en Cancelación manual.
4. Especifique la fecha de cancelación.
5. En el campo Nombre de clave de cancelación, escriba el motivo de la cancelación.
6. Haga clic en Aceptar para confirmar la cancelación de la factura electrónica.
    * El estado de la factura electrónica es Cancelación manual.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]