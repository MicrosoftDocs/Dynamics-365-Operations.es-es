---
title: MX-00010 Cancelar facturas electrónicas
description: Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC.
author: AdamTrukawka
ms.date: 06/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EInvoiceCFDIJournal_AR
ms.openlocfilehash: 3cf007d0d40f9240fd8eea0c0437cb1a60c2d700
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270550"
---
# <a name="mx-00010-cancel-an-electronic-invoice"></a>MX-00010 Cancelar facturas electrónicas

[!include [banner](../../includes/banner.md)]

Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC. También puede cancelar una factura electrónica CFDI mediante el proceso manual.

## <a name="cancel-a-cfdi-electronic-invoice"></a>Cancelación de una factura electrónica CFDI

1. Vaya a **Clientes** \> **Consultas e informes** \> **CFDI (facturas electrónicas)**.
2. Seleccione una factura electrónica con estado **Aprobada**.
3. Seleccione el número de factura para ver los detalles.
4. En el panel de acciones, seleccione **Funciones** \> **Cancelar CFDI**.
5. Cierre la página.
6. Vaya a **Clientes** \> **Facturas** \> **Facturas electrónicas** \> **Proceso de exportar/importar factura electrónica**.
7. Seleccione **Aceptar**. Cuando se confirma la cancelación, el estado de la factura electrónica cambia a **Cancelada**.
8. Vaya a **Clientes** \> **Consultas e informes** \> **CFDI (facturas electrónicas)**.
9. Seleccione la factura cancelada para comprobar el estado.

> [!NOTE]
> No puede cancelar un documento CFDI si existe un documento asociado. Por ejemplo, no puede cancelar un pago por adelantado si una factura hace referencia a ese pago. Cancele los documentos asociados y luego cancele el documento CFDI.

A continuación, especifique el motivo de la cancelación. Cuando selecciona **Funciones** \> **Cancelar CFDI** en el Panel de acciones, puede seleccionar un motivo de cancelación. Si selecciona **01** como motivo, complete un documento de reemplazo para reemplazar el documento actual.

## <a name="manually-cancel-a-cfdi-electronic-invoice"></a>Cancelación manual de una factura electrónica CFDI

1. Seleccione una factura con estado **Aprobada**.
2. En el panel de acciones, seleccione **Funciones** \> **Cancelación manual**.
3. Especifique la fecha de cancelación.
4. En el campo **Nombre de clave de cancelación**, escriba el motivo de la cancelación.
5. Seleccione **Aceptar** para confirmar la cancelación de la factura electrónica. El estado de la factura electrónica cambia a **Cancelación manual**.

## <a name="manually-update-the-status-of-a-cfdi-document-that-is-in-progress-after-cancellation"></a>Actualizar manualmente el estado de un documento CFDI que está en proceso luego de la cancelación

Puede usar la tarea periódica **Actualizar estado de documento electrónico** para actualizar el estado de un documento CFDI que está **En curso** durante mucho tiempo después de la cancelación, si el documento fue cancelado en una aplicación PAC.

1. Vaya a **Clientes** \> **Facturas** \> **Facturas electrónicas** \> **Actualizar el estado de la factura electrónica**.
2. Filtre los registros para encontrar aquellos en los que se debe actualizar el estado.

> [!NOTE]
> No se pueden actualizar los campos **Estado a** y **Estado al mensaje**. Solo se pueden actualizar documentos CFDI que tengan un estado de **En curso**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
