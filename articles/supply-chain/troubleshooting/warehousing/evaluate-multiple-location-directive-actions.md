---
title: Evaluar todas las acciones para directivas de ubicación de SKU múltiples
description: Una nueva característica se ha agregado para evaluar todas las acciones para directivas de ubicación de múltiples SKU. Esta página lo guía a información sobre cómo encenderlo.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d5f7cf548eb6c18d9700c73ef084f197b78542e
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102972"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>La opción de SKU múltiple no evalúa múltiples acciones de directiva de ubicación

## <a name="symptoms"></a>Síntomas

Las directivas de ubicación del tipo de orden de trabajo *Ordenes de venta* y del tipo de trabajo *Ubicación* no evalúan múltiples acciones de directiva de ubicación cuando está seleccionada la opción **Varios SKU** . Solo se evalúa la primera acción directiva de ubicación.

## <a name="resolution"></a>Resolución

Una nueva característica, *Evaluar todas las acciones para las directivas de ubicación de múltiples SKU*, se ha agregado en la versión 10.0.15 (ver [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Esta función evalúa todas las acciones para las directivas de ubicación de varios SKU. A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada.  A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Los administradores pueden usar la página [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla o deshabilitarla si es necesario.
