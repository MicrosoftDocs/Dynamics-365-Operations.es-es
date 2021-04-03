---
title: Actualizar costes estándar en un entorno de fabricación
description: Este artículo proporciona orientación acerca de cómo actualizar los costes estándar en un entorno de no fabricación.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 726eccdc8a9350a292ba719784b5db99afdfad4f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262438"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Actualizar costes estándar en un entorno de fabricación

[!include [banner](../includes/banner.md)]

Este artículo proporciona orientación acerca de cómo actualizar los costes estándar en un entorno de no fabricación. 

Las actualizaciones pueden reflejar nuevos artículos, categorías de coste o fórmulas de cálculo de costes indirectos. También pueden reflejar correcciones y cambios de coste. El tipo de actualización afecta a los pasos que debe completar para actualizar los costes estándar, tal como se muestra en los casos siguientes:

-   Especifica los cambios en el coste estándar esperados para los artículos comprados y, a continuación, cambia el estado de los registros de costes de artículos a **Activo** en la fecha adecuada. Sin embargo, no vuelve a calcular los costes de los artículos fabricados que usan artículos comprados.
-   Especifica los costes estándar para un nuevo artículo comprado, pero no vuelve a calcular los costes de los artículos fabricados que tienen una versión de la lista de materiales (L. MAT) que contiene el nuevo artículo comprado como componente.
-   Corrige o cambia el coste de un artículo comprado o cambia el grupo de costes asignado a un artículo comprado y vuelve a calcular el coste de todos los artículos fabricados que tienen una versión de L. MAT que contiene el artículo comprado como componente.
-   Cambia el coste de una categoría de coste y calcula el coste de todos los artículos fabricados que tienen una versión de ruta que contiene operaciones de enrutamiento que usan la categoría de coste.
-   Cambia las categorías de costes asignadas a las operaciones de rutas o el grupo de costes asignado a las categorías de costes. A continuación calcula el coste de todos los artículos fabricados que tienen una versión de ruta que contiene operaciones de enrutamiento que usan la categoría de coste.
-   Cambia una fórmula de cálculo de costes indirectos y calcula el coste de todos los artículos fabricados que se verán afectados por el cambio.
-   Cambia o agrega un sitio de fabricación para un artículo fabricado y calcula el coste fabricado del artículo para el sitio.
-   Calcula, o vuelve a calcular, el coste de un artículo fabricado y vuelve a calcular el coste de todos los artículos fabricados que tienen una versión de L. MAT que contiene el artículo fabricado como componente.
-   Calcula los costes de un nuevo artículo fabricado en función de su información de L. MAT y ruta definidas, aprobadas y activas.

Cada caso requiere una consideración cuidadosa sobre cómo se deben actualizar los costes estándar.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]