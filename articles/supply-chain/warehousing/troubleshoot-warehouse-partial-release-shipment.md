---
title: Solucionar problemas de lanzamientos parciales y envíos parciales
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con liberaciones parciales y envíos parciales en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 33323a8aed44cf19db6c2c937abcb09f7e05b6c1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993962"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Solucionar problemas de lanzamientos parciales y envíos parciales

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con liberaciones parciales y envíos parciales en Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>El estado de liberación de un pedido de cliente permanece Liberado parcialmente incluso después de facturar el pedido de cliente.

### <a name="issue-description"></a>Descripción del problema

Una orden de venta es una orden de entrega, pero uno o más artículos tienen un modo de entrega diferente. Después de facturar el pedido, todavía tiene un estado de liberación de *Liberado parcialmente*.

Por ejemplo, una orden de venta tiene dos artículos: uno para entrega y otro para recolección. Tanto la entrega como la recogida se han realizado. Por tanto, se han facturado ambas líneas. Sin embargo, el estado de la versión todavía se muestra como *Liberado parcialmente*, que es engañoso.

### <a name="issue-resolution"></a>Solución del problema

El estado de liberación se aplica solo a las líneas de pedido donde los artículos están habilitados para la gestión del almacén. Por lo tanto, el estado de publicación sigue siendo *Liberado parcialmente* en este escenario. Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Se podría agregar una extensión como parte del albarán y el proceso de facturación para actualizar el estado de liberación.
