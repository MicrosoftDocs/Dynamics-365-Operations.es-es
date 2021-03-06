---
title: Orígenes comunes de desviaciones de producción
description: Este artículo explica diversos orígenes de cada tipo de desviación de producción.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f627cb1d15d0fa858abae588d149875967cff97c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813252"
---
# <a name="common-sources-of-production-variances"></a>Orígenes comunes de desviaciones de producción

[!include [banner](../includes/banner.md)]

Este artículo explica diversos orígenes de cada tipo de desviación de producción. 

Estos son algunos orígenes típicos de desviación de **tamaño de lote**:

-   La cantidad sin errores para un pedido de producción difiere de la cantidad de cálculo usada en el cálculo de coste estándar. La cantidad proporciona la base para la amortización de costes constantes.
-   El valor de costes constantes del pedido de producción difiere de los costes constantes usados en el cálculo de coste estándar. Los costes constantes del pedido de producción pueden ser diferentes por varios motivos. Por ejemplo, los costes constantes pueden reflejar los factores siguientes:
    -   Modificaciones efectuadas manualmente en la lista de materiales de producción (L. MAT) o en la ruta
    -   La selección de una versión de L. MAT o versión de ruta diferente al crear el pedido de producción
    -   Modificaciones de ingeniería planificadas en la versión de L. MAT o de ruta asignada al artículo

Estos son algunos orígenes típicos de una desviación de **precio de producción**:

-   La categoría de coste (y el precio de categoría de coste) del consumo notificado de una operación de ruta difiere de la categoría de coste usada en el cálculo de coste estándar.
-   El coste activo para el precio de categoría de coste difiere del precio de categoría de coste usado en el cálculo de coste estándar.

Estos son algunos orígenes típicos de una desviación de **cantidad de producción**:

-   Realiza una emisión excesiva o insuficiente de un componente de material.
-   Especifica un tiempo de informe excesivo o insuficiente para una operación de ruta.
-   Realiza una recepción excesiva o insuficiente de la cantidad sin errores del artículo principal, en relación con la cantidad del pedido. Sin embargo, emite totalmente componentes y operaciones de informes, en función de la cantidad del pedido para el pedido de producción.

Estos son algunos orígenes típicos de una desviación de **sustitución de producción**:

-   Emite un componente de material que no se encuentra en la L. MAT de producción.
-   Agrega manualmente un componente a la L. MAT de producción y notifica ese componente como consumido.
-   Notifica un artículo como consumido pero sin agregarlo manualmente a la L. MAT de producción.
-   Agrega manualmente una operación a la ruta de producción y notifica esa operación como consumida.
-   Al crear el pedido de producción, selecciona una versión de L. MAT difiere de la usada en el cálculo de coste estándar.
-   Al crear el pedido de producción, selecciona una versión de ruta que difiere de la usada en el cálculo de coste estándar.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]