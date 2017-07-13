---
title: "Opciones de letras de cambio españolas"
description: "Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 264644
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 457077edb4162b65b125c49b864556bc196d488b
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Opciones de letras de cambio españolas
<a id="spanish-bill-of-exchange-options" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para las entidades jurídicas en España.

Para las entidades jurídicas en España, la funcionalidad de letra de cambio tiene opciones adicionales:

-   Validación de los diarios de letra de cambio
-   Fechas de los diarios de letra de cambio

## Parámetros de clientes para letras de cambio españolas
<a id="accounts-receivable-parameters-for-spanish-bills-of-exchange" class="xliff"></a>
Para configurar los parámetros para letras de cambio de entidades jurídicas en España, vaya a **Parámetros de clientes** &gt; **Letra de cambio ES**.

## Validación de los diarios de letra de cambio
<a id="validation-for-bill-of-exchange-journals" class="xliff"></a>
Si el parámetro **Validación del diario de letra de cambio** está establecido en **Sí**, no se registra una letra de cambio cuando las transacciones tienen el mismo número de asiento y distintas fechas de transacción. Este parámetro se aplica a las transacciones del diario contable. Este parámetro solo se utiliza cuando el diario admite un número de asiento y cuando la opción **Validación del diario de letra de cambio** está seleccionada en la página **Parámetros de clientes**. El parámetro **Validación del diario de letra de cambio** afecta a los siguientes documentos:

-   Diario de creación de letra de cambio
-   Diario de envíos
-   Diario de impago de letras de cambio
-   Diario de renegociación de letras de cambio
-   Diario de liquidación de letra de cambio
-   Diario de pagos

## Fechas de los diarios de letra de cambio
<a id="dates-in-bill-of-exchange-journals" class="xliff"></a>
Si el parámetro **Tratamiento de fecha en diario de letra de cambio** está establecido en **Sí**, la fecha de transacción de los diarios de letra de cambio se actualiza a la fecha de vencimiento cuando se usa una propuesta de pago. El parámetro **Tratamiento de fecha en diario de letra de cambio** afecta a los siguientes documentos:

-   Diario de envíos
-   Diario de impago de letras de cambio
-   Diario de renegociación de letras de cambio





