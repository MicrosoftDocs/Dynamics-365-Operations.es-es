---
title: Escenarios de límite de crédito
description: Este artículo describe cómo se comprueba el límite de crédito del cliente cuando el cliente pertenece a un grupo de límite de crédito de clientes.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130265"
---
# <a name="credit-limit-scenarios"></a>Escenarios de límite de crédito

En Gestión de créditos se puede asignar un límite de crédito a clientes en el nivel de cliente. Cada cliente puede ser asignado a un *grupo de límite de crédito del cliente*, y cada grupo tiene un límite de crédito. Por tanto, también se puede asignar un límite de crédito a clientes en el nivel de grupo. Todos los clientes que están asignados al mismo grupo de crédito del cliente tienen el mismo límite de crédito.

En general, los límites de crédito del grupo se verifican antes que los límites de crédito individuales. El límite de crédito individual no siempre anula el límite de crédito del grupo.

Este artículo describe cinco escenarios relacionados con grupos de crédito de clientes y límites de crédito individuales.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>El límite de crédito del grupo del cliente es mayor que el límite de crédito individual

Por ejemplo, el cliente tiene un límite de crédito individual de 10 000 $. El cliente está asignado a un grupo de crédito de cliente y el límite de crédito del grupo es 15 000 $. En este caso, el "límite de crédito efectivo" del cliente es 10 000 $, porque ese importe es menor que el límite del grupo. Las reglas de bloqueo verifican primero el límite del grupo. Luego verifican el límite individual. Se bloqueará cualquier pedido de venta superior a 10 000 $.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>El límite de crédito individual es mayor que el límite de crédito del grupo del cliente

Por ejemplo, el cliente tiene un límite de crédito individual de 20 000 $. El cliente está asignado a un grupo de crédito de cliente y el límite de crédito del grupo es 15 000 $. En este caso, el límite de crédito efectivo del cliente es 15 000 $, porque las reglas de bloqueo siempre verifican primero el límite del grupo. Se bloquearán pedidos de venta superiores a 15 000 $.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>El límite de crédito individual se establece en 0,00 y el límite de crédito obligatorio se establece en Sí

Si el cliente tiene un límite de crédito individual establecido en **0,00** y la opción **Límite de crédito obligatorio** se configura como **Sí**, el límite de crédito efectivo del cliente es 0,00 $, incluso si el cliente está asignado a un grupo de crédito del cliente. De esta forma, el cliente puede formar parte de un grupo, pero todos los pedidos irán a Gestión de crédito.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>El límite de crédito individual se establece en 0,00 y el límite de crédito ilimitado se establece en Sí

Si el cliente tiene un límite de crédito individual establecido en **0,00**, pero la opción **Límite de crédito ilimitado** se configura como **Sí**, el cliente tendrá crédito ilimitado, incluso si está asignado a un grupo de crédito del cliente.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>El límite de crédito individual se establece en 0,00 y el cliente forma parte de un grupo de crédito de clientes

Por ejemplo, el cliente tiene un límite de crédito individual establecido en **0,00**, la opción **Crédito ilimitado** está configurada en **No** y la opción **Límite de crédito obligatorio** está configurada en **No**. El cliente está asignado a un grupo de crédito de cliente y el límite de crédito del grupo es 15 000 $. En este caso, el límite de crédito efectivo del cliente es el límite del grupo, 15 000 $. Por tanto, cualquier pedido de venta que supere ese importe será bloqueado. Este comportamiento permite que el límite de crédito se gestione en el nivel de grupo de crédito del cliente en lugar de en el nivel de cliente individual. Todos los clientes que están asignados al mismo grupo tienen el mismo límite de crédito.
