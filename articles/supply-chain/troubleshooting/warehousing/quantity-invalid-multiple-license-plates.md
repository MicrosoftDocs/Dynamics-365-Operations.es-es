---
title: Cantidad no válida para trabajos de picking con varios LP
description: Cuando hay trabajo de recolección con varias placas en un solo lugar, la cantidad no es válida para la unidad ea. Verifique que los siguientes campos sean correctos.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477483"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>Cantidad no válida cuando hay trabajo de picking con varios LP en una ubicación

## <a name="symptoms"></a>Síntomas

Cuando hay trabajo de recolección con varias placas en un solo lugar, la cantidad no es válida para la unidad *ea* y recibe el siguiente mensaje de error:

> La cantidad no es válida para la unidad 1%.

## <a name="resolution"></a>Resolución

Verifique que los campos **ID de grupo de secuencia de unidad** y **Conversiones de unidades** del producto lanzado o la variante del producto están configurados correctamente.

Tenga en cuenta que el mensaje de error se ha mejorado en la versión 10.0.15 para mostrar la cantidad esperada (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). El nuevo mensaje de error es:

> La cantidad no es válida. Se esperaba %1 %2.
