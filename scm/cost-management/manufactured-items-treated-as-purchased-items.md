---
title: "Productos de instalación que se pueden generar o ser adquiridos"
description: "Los productos se pueden originarios de varias maneras - puede generarlos () o fabricado ser adquiridos (adquirido). Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5360c7b1475763b8e33205bff560393e9ee51882
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-products-that-can-be-produced-or-procured"></a>Productos de instalación que se pueden generar o ser adquiridos

Los productos se pueden originarios de varias maneras - puede generarlos () o fabricado ser adquiridos (adquirido). Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple. 

El abastecimiento múltiple se usa normalmente para un artículo comprado que a veces se fabrica, o cuando se modifica un artículo era principalmente un artículo fabricado de modo que pase a ser principalmente un artículo comprado. El artículo se designa primero como artículo fabricado para definir la información de ruta y de lista de materiales y para admitir pedidos de producción para el artículo. El tipo de producción debe establecerse en **L. MAT.** (o, en fabricación de procesos,**Fórmula** o **Coproducto**).

Cuando se usan costes estándar, se puede calcular el registro de costes de artículo para el artículo fabricado. No obstante, es posible que el registro de coste de artículo no coincida con el coste estándar que desee asignar a los artículos de compra. En este caso, deberá especificar manualmente el coste estándar que desee asignar y activarlo en el registro de costes de artículos. Para calcular los costes, puede usar una lista de materiales y una ruta especiales que representan la combinación de suministro del producto a lo largo de un período fiscal, para minimizar las desviaciones en el tiempo. Además, un artículo fabricado en un sitio se puede transferir a otro sitio. Por tanto, el coste del artículo se debe especificar y activar manualmente para el sitio al que se transfiere el artículo. Cuando usa un artículo fabricado como componente de productos de alto nivel, los costes del componente deben tratarse como un artículo comprado. Esta directriz se aplica independientemente de si los costes del componente se calcularon o se especificaron manualmente. En otras palabras, un cálculo de lista de materiales debe tratar los costes del artículo como un componente comprado en lugar de calcular los costes basándose en la información de ruta y la lista de materiales del artículo. Para evitar el cálculo, seleccione el indicador **Detener la expansión** incrustado en el grupo de cálculo de lista de materiales asignado al artículo. Para evitar que se utilicen los requisitos de expansión en los cálculos de la programación maestra a través del artículo, defina el indicador de límite de expansión en 0 (cero) días en la cobertura del artículo o en el grupo de cobertura. El cálculo de la programación maestra tratará el artículo como un artículo comprado y no realizará más cálculos en cuanto a información de ruta y lista de materiales del artículo.




