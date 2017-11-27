---
title: Configurar productos que pueden fabricarse o suministrarse
description: "Los productos se pueden suministrar de distintas maneras: se pueden producir (fabricar) o adquirir (comprar). Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b5ed8c93c13746249605ad8742549c23bb1e0e10
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-products-that-can-be-produced-or-procured"></a>Configurar productos que pueden fabricarse o suministrarse

[!include[banner](../includes/banner.md)]


Los productos se pueden suministrar de distintas maneras: se pueden producir (fabricar) o adquirir (comprar). Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple. 

El abastecimiento múltiple se usa normalmente para un artículo comprado que a veces se fabrica, o cuando se modifica un artículo era principalmente un artículo fabricado de modo que pase a ser principalmente un artículo comprado. El artículo se designa primero como artículo fabricado para definir la información de ruta y de lista de materiales y para admitir pedidos de producción para el artículo. El tipo de producción debe establecerse en **L. MAT.** (o, en fabricación de procesos,**Fórmula** o **Coproducto**).

Cuando se usan costes estándar, se puede calcular el registro de costes de artículo para el artículo fabricado. No obstante, es posible que el registro de coste de artículo no coincida con el coste estándar que desee asignar a los artículos de compra. En este caso, deberá especificar manualmente el coste estándar que desee asignar y activarlo en el registro de costes de artículos. Para calcular los costes, puede usar una lista de materiales y una ruta especiales que representan la combinación de suministro del producto a lo largo de un período fiscal, para minimizar las desviaciones en el tiempo. Además, un artículo fabricado en un sitio se puede transferir a otro sitio. Por tanto, el coste del artículo se debe especificar y activar manualmente para el sitio al que se transfiere el artículo. Cuando usa un artículo fabricado como componente de productos de alto nivel, los costes del componente deben tratarse como un artículo comprado. Esta directriz se aplica independientemente de si los costes del componente se calcularon o se especificaron manualmente. En otras palabras, un cálculo de lista de materiales debe tratar los costes del artículo como un componente comprado en lugar de calcular los costes basándose en la información de ruta y la lista de materiales del artículo. Para evitar el cálculo, seleccione el indicador **Detener la expansión** incrustado en el grupo de cálculo de lista de materiales asignado al artículo. Para evitar que se utilicen los requisitos de expansión en los cálculos de la programación maestra a través del artículo, defina el indicador de límite de expansión en 0 (cero) días en la cobertura del artículo o en el grupo de cobertura. El cálculo de la programación maestra tratará el artículo como un artículo comprado y no realizará más cálculos en cuanto a información de ruta y lista de materiales del artículo.






