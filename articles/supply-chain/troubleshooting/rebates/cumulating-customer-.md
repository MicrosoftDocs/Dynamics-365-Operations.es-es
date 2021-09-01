---
title: La acumulación de devoluciones de clientes falla cuando se utilizan grupos de devoluciones de artículos
description: Cuando utiliza acuerdos de devoluciones para clientes en combinación con grupos de devolución de artículos, se calculan las devoluciones, pero la acumulación falla.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760379"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>La acumulación de devoluciones de clientes falla cuando se utilizan grupos de devoluciones de artículos

Número de KB: 4611372

## <a name="symptoms"></a>Síntomas

Cuando utiliza acuerdos de devoluciones para clientes (del tipo *importe*) en combinación con grupos de devolución de artículos, se calculan las devoluciones, pero la acumulación falla.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. Los grupos de artículos agrupan solo los artículos que tienen la misma condición de umbral. La condición de devolución (umbral) se establece en función del importe de cada artículo, no del importe acumulado de cualquier artículo del grupo de artículos.
