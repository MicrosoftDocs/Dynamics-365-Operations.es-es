---
title: "Opciones españolas de la letra de cambio"
description: "Este tema describe opciones y cambios específicos en el proceso básico de la letra de cambio implementado en Microsoft Dynamics 365 para las operaciones para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264644
ms.assetid: 67e8f90e-5522-4631-96c5-62d193eab72f
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: fb4c2f5d4b0f2b952fadc2163b2250c0fd0b9e5d
ms.lasthandoff: 03/31/2017


---

# <a name="spanish-bill-of-exchange-options"></a>Opciones españolas de la letra de cambio

Este tema describe opciones y cambios específicos en el proceso básico de la letra de cambio implementado en Microsoft Dynamics 365 para las operaciones para las entidades jurídicas en España.

Para las entidades jurídicas en España, las funciones de la letra de cambio tiene opciones adicionales:

-   Validación para los diarios de letras de cambio
-   Fechas de los diarios de letra de cambio

## <a name="accounts-receivable-parameters-for-spanish-bills-of-exchange"></a>Parámetros de clientes para letras de cambio españolas
Para configurar los parámetros para las letras de cambio para las entidades jurídicas en España, vaya ** los parámetros de clientes ** &gt; ** la letra de cambio ES **.

## <a name="validation-for-bill-of-exchange-journals"></a>Validación para los diarios de letras de cambio
Si ** validación en diario de letra de cambio ** el parámetro se establece ** Sí **, una letra de cambio no se registra cuando las transacciones tienen las mismas fechas el número de asiento y de transacción distintas. Este parámetro se aplica a las transacciones del diario contable. Se utiliza este parámetro si el diario permite un número de asiento y, cuando ** validación de los diarios de letra de cambio ** la opción se selecciona en ** los parámetros de clientes ** la página. ** Validación de los diarios de letra de cambio ** el parámetro afecta a los siguientes documentos:

-   Diario de creación de letra de cambio
-   Diario de envíos
-   Diario de impago de letras de cambio
-   Diario de renegociación de letras de cambio
-   Diario de liquidación de letra de cambio
-   Diario de pagos

## <a name="dates-in-bill-of-exchange-journals"></a>Fechas de los diarios de letra de cambio
Si ** tratamiento de la fecha en diario de letra de cambio ** el parámetro se establece ** Sí **, la fecha de transacción en el diario de letras de cambio se actualizará a la fecha de vencimiento en que se usa una propuesta de pago. ** Tratamiento de fecha en diario de letra de cambio ** el parámetro afecta a los siguientes documentos:

-   Diario de envíos
-   Diario de impago de letras de cambio
-   Diario de renegociación de letras de cambio



