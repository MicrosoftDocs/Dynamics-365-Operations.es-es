---
title: "Opciones de pagaré español"
description: "Este tema describe opciones y cambios en la funcionalidad básica de pagarés implementada en Microsoft Dynamics 365 for Operations para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264624
ms.assetid: a4925301-e193-49ce-814d-a0b71899118d
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5cb67f3352b1adc41aaae191585d80a128a64c31
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="spanish-promissory-note-options"></a>Opciones de pagaré español

[!include[banner](../includes/banner.md)]


Este tema describe opciones y cambios en la funcionalidad básica de pagarés implementada en Microsoft Dynamics 365 for Operations para las entidades jurídicas en España.

Para las entidades jurídicas en España, la funcionalidad de pagaré tiene opciones adicionales:

-   Validación de los diarios de pagarés
-   Fechas en los diarios de pagarés
-   Confirmación de facturas

## <a name="accounts-payable-parameters-for-spanish-promissory-notes"></a>Parámetros de proveedor para pagarés españoles
Para configurar los parámetros de los pagarés para las entidades jurídicas en España, vaya a **Parámetros de proveedores** &gt; **Pagarés ES**.

## <a name="validation-for-promissory-notes-journals"></a>Validación de los diarios de pagarés
Si el parámetro **Validación del diario de pagarés** se establece en **Sí**, el número de identificación fiscal del proveedor se valida al agregar líneas y rellenarlas en un diario de liquidación de pagarés. Si este parámetro está establecido en **No**, y está activado **Nacional + estados miembros de la UE** en el campo **Requisito de NIF**, el número de identificación fiscal (NIF) no se valida.

## <a name="dates-in-promissory-notes-journals"></a>Fechas en los diarios de pagarés
Si el parámetro **Tratamiento de datos (diarios de pagarés)** está establecido en **Sí**, el campo **Fecha mínima** se vacía al crear propuestas de pagos para Diarios de creación de pagarés y Diarios de remesa. Por tanto, se usa la fecha de vencimiento como la fecha de transacción, aunque la fecha de vencimiento sea anterior a la del sistema. Si el parámetro **Tratamiento de datos (diarios de pagarés)** se establece en **No**, la fecha del sistema es la fecha predeterminada en el campo **Fecha mínima**.

## <a name="invoice-confirmation"></a>Confirmación de facturas
Si el parámetro **Confirmando tratamiento de facturas** se establece en **Sí**, se crea una línea independiente para cada número de factura al crear propuestas de pago para diarios de remesa y diarios de liquidación de pagarés. Se crean líneas independientes, sea cual sea la selección en el campo **Periodo** para el método de pago. Cada importe de factura puede comprobarse en el diario de remesas. Si el parámetro **Confirmando tratamiento de facturas** se establece en **No**, las líneas de diario pueden incluir importes para varias facturas, en función de la selección del campo **Período**.




