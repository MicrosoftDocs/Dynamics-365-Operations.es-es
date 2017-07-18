---
title: "Confirmación de lote y matrícula"
description: "Este tema describe cómo configurar y aplicar confirmación de lote y matrícula desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 70a8c18560f0cfc7a44625520f2f035a6004618a
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

# <a name="batch-and-license-plate-confirmation"></a>Confirmación de lote y matrícula

[!include[banner](../includes/banner.md)]

La confirmación de lote le permite confirmar que se eligió el lote correcto en el dispositivo móvil. En la selección inicial del trabajo solo para los artículos superiores al lote, donde *superior al lote* indica que el lote supera a la ubicación en la jerarquía de la búsqueda, debe comprobar que el lote elegido se corresponde con el lote en la línea del trabajo. 

La confirmación de matrícula le permite confirmar que se eligió la matrícula correcta en el dispositivo móvil. Al seleccionar el trabajo en una ubicación de la etapa, debe comprobar que la matrícula elegida coincide con la matrícula que está asociada al trabajo. Si el trabajo se ha iniciado con la digitalización de una matrícula, este paso de confirmación se omitirá.

## <a name="where-it-applies"></a>Dónde se aplica
La confirmación se aplica en los casos siguientes:

- La confirmación de lote se aplica a las selecciones iniciales de trabajo para los artículos superiores al lote.
- La confirmación de la matrícula se aplica a las selecciones de ubicaciones de la etapa.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurara la confirmación de lote y matrícula
Puede configurar la confirmación del lote y de matrícula desde los elementos de menú del dispositivo móvil.  
1.  En los elementos de menú del dispositivo móvil, especifique la configuración de la confirmación del trabajo.  
2.  Seleccione la opción para la confirmación de lote o matrícula. Ambas opciones están disponibles para las selecciones del tipo de trabajo que no tengan habilitada la confirmación automática.  

