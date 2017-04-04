---
title: "Opciones españolas de pagaré"
description: "Este tema describe opciones y los cambios para la funcionalidad básica de pagarés que se implementa en Microsoft Dynamics 365 para las operaciones para las entidades jurídicas en España."
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
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 82baf809cf691e7a3a7a9e51547a0c2ab9c9f843
ms.lasthandoff: 03/31/2017


---

# <a name="spanish-promissory-note-options"></a>Opciones españolas de pagaré

Este tema describe opciones y los cambios para la funcionalidad básica de pagarés que se implementa en Microsoft Dynamics 365 para las operaciones para las entidades jurídicas en España.

Para las entidades jurídicas en España, la funcionalidad de pagaré tiene opciones adicionales:

-   Validación para los diarios de pagarés
-   Fechas en los diarios de pagarés
-   Confirmación de la factura

## <a name="accounts-payable-parameters-for-spanish-promissory-notes"></a>Parámetros de proveedores para los pagarés españoles
Para configurar los parámetros para los pagarés para las entidades jurídicas en España, vaya ** los parámetros de proveedores ** &gt; ** los pagarés ** ES.

## <a name="validation-for-promissory-notes-journals"></a>Validación para los diarios de pagarés
Si ** validación en el diario de pagarés ** el parámetro se establece ** Sí **, se valida el número de identificación fiscal del proveedor a las líneas se suman y se realizan en un diario de liquidación de pagarés. Si se establece este parámetro ** ningún **, y si ** nacional + los estados miembros ** se selecciona en ** requisito de número de identificación fiscal ** campo, el número de identificación fiscal no se valida.

## <a name="dates-in-promissory-notes-journals"></a>Fechas en los diarios de pagarés
Si ** tratamiento de fecha (diarios de pagarés) ** el parámetro se establece ** Sí **, ** fecha mínima ** se borra el campo cuando cree propuestas de pago para diarios y diarios de remesas de diario de creación de pagarés. Por lo tanto, se usa la fecha de vencimiento como la fecha de transacción, aunque la fecha de vencimiento es anterior a la fecha del sistema. Si ** tratamiento de fecha (diarios de pagarés) ** se establece el parámetro ** ningún **, la fecha del sistema es la fecha predeterminada en ** fecha mínima ** el campo.

## <a name="invoice-confirmation"></a>Confirmación de la factura
Si ** confirmando factura el tratamiento ** el parámetro se establece ** Sí **, una línea independiente se crea para cada número de factura cuando cree propuestas de pago para los diarios de pagarés de diarios de remesas y de Liquidar. Se crean líneas independientes, independientemente de la selección en ** período ** campo para la forma de pago. Cada importe de factura puede comprobar en el diario de envíos. Si ** confirmando factura el tratamiento ** se establece el parámetro ** ningún **, las líneas de diario pueden incluir importes para varias facturas, en función de la selección en ** período ** el campo.


