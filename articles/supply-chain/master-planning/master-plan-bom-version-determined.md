---
title: Determinar la versión de L. MAT.
description: En una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L. MAT válida en función del sitio.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf125e2b75c4dfa406f4f05b249e6fdb49c84b7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556930"
---
# <a name="determine-the-bom-version"></a>Determinar la versión de L. MAT.

[!include [banner](../includes/banner.md)]

En una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L. MAT válida en función del sitio. 

La dimensión del sitio se conoce siempre y se indica en la transacción de demanda. El siguiente proceso se usa para determinar la versión de L. MAT que utilizar:

-   Si hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa la L. MAT específica del sitio.
-   Si no hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa una L. MAT general. Una L. MAT general no indica un sitio, y es válida para varios sitios. Si hay una L. MAT general, se utiliza.
-   Si no hay ninguna L. MAT. general que se pueda usar, la expansión de la demanda se detiene en este punto.

Una versión de L. MAT válida, tanto si es específica del sitio como si es general, debe cumplir los criterios necesarios para la fecha y la cantidad.





