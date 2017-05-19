---
title: "Corrección de una factura de servicios"
description: "Este artículo explica cómo corregir una factura de servicios que se ha registrado y cómo reenviarla como factura corregida."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: df94cf12accd2b18c1f8cfd43d7de5dff16e7aea
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="correct-a-free-text-invoice"></a>Corrección de una factura de servicios

[!include[banner](../includes/banner.md)]


Este artículo explica cómo corregir una factura de servicios que se ha registrado y cómo reenviarla como factura corregida.

Para corregir una factura de servicios que ya se ha registrado, ábrala. En la página **Factura**, seleccione **Cancelar** y, a continuación seleccione **Corregir factura**. Seleccione un código de razón, agregue comentarios y seleccione la fecha para la nueva factura corregida. Puede modificar la factura corregida y registrarla. 

Al registrar la factura corregida, se crea una factura de cancelación por un importe de crédito que sea igual al importe de la factura original. Por lo tanto, el saldo combinado de las facturas original y de cancelación es igual a 0 (cero). La factura de cancelación se liquida con la factura original. 

Después de registrar la factura corregida, tendrá tres facturas:

-   **Factura original**: factura que contiene la información que está corrigiendo.
-   **Factura de cancelación**: factura de crédito que genera el sistema para cancelar la factura corregida más recientemente.
-   **Factura corregida**: factura que contiene la información de factura corregida.

Puede identificar la cancelación y la corrección de facturas de dos maneras:

-   La página **Todas las facturas de servicios** incluye una columna **Corrección** donde puede ver qué facturas se han cancelado y qué facturas se han corregido.
-   El encabezado de la factura de servicios muestra un estado de **Factura de cancelación '\[número de factura\]'** o **Factura corregida '\[número de factura\]'**.

> [!NOTE]
> Esta característica solo está disponible si se selecciona la clave de configuración **Corrección de factura de servicios**.




