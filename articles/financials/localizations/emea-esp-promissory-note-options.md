---
title: "Opciones de pagaré español"
description: "Este tema describe opciones y cambios en la funcionalidad básica de pagarés implementada en Microsoft Dynamics 365 for Finance and Operations para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendParameters, BankPromissoryNoteTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264624
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c9c759270ae17e4ea2162e2fd6ec8bb493ddca57
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="spanish-promissory-note-options"></a>Opciones de pagaré español

[!include [banner](../includes/banner.md)]

Este tema describe opciones y cambios en la funcionalidad básica de pagarés implementada en Microsoft Dynamics 365 for Finance and Operations para las entidades jurídicas en España.

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




