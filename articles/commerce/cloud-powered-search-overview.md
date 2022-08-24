---
title: Información general de la búsqueda con tecnología de nube
description: Este artículo ofrece una visión general de la búsqueda con tecnología de nube en Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273676"
---
# <a name="cloud-powered-search-overview"></a>Información general de la búsqueda con tecnología de nube

[!include [banner](includes/banner.md)]

Este artículo ofrece una visión general de la búsqueda con tecnología de nube en Microsoft Dynamics 365 Commerce.

La detectabilidad de productos ayuda a garantizar que los clientes pueden encontrar productos rápida y fácilmente examinando categorías, buscando y filtrando. Los minoristas consideran que el descubrimiento de productos es una herramienta principal para la interacción con el cliente en todos los canales impulsados por Cloud Scale Unit (CSU), como el comercio electrónico y el punto de venta (PDV).

Los clientes se acostumbran a tiempos de respuesta casi instantáneos de los motores de búsqueda web, sitios web sofisticados de correo electrónico, aplicaciones sociales, sugerencias automáticas que aparecen conforme escriben términos de búsqueda, navegación por facetas y resaltado. Si los clientes no encuentran el producto que buscan rápidamente en una tienda de comercio electrónico, no dudan en ir a una tienda diferente de comercio electrónico.

La detectabilidad de productos con tecnología de nube en Commerce ayuda a los minoristas a continuar aumentando los tipos de conversión y retención de consumidor en todos los canales con tecnología de CSU.

La experiencia de búsqueda de Commerce ha mejorado las capacidades de ayudar a los minoristas a lograr una mejor detectabilidad del producto. Al mismo tiempo, estas capacidades ofrecen la escalabilidad y el rendimiento necesarios para el tráfico de comercio electrónico.

## <a name="browse-and-search"></a>Examinar y buscar

El rendimiento y la relevancia de la búsqueda son factores clave en la experiencia de omnicanal, ya que la detección de productos depende principalmente de la funcionalidad de búsqueda para la recuperación de información y la navegación de contenido. Una experiencia de búsqueda y exploración eficaz y eficiente ayuda a aumentar la conversión.

La ilustración siguiente muestra un ejemplo de la funcionalidad de búsqueda y exploración típica.

![Página de aterrizaje de búsqueda.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Resumen de opciones y navegación por facetas 

La navegación por facetas ayuda a los clientes a examinar con mayor facilidad contenido al permitirles filtrar por refinadores vinculados a términos de un conjunto de términos. Una vez que ha seleccionado y aplicado refinadores, se muestra un resumen de las opciones. 

Al usar la navegación por facetas, puede configurar diferentes refinadores para diferentes términos en un conjunto de términos, sin tener que crear páginas adicionales. 

La ilustración siguiente muestra un ejemplo donde se usa la navegación por facetas en una búsqueda.

![Resumen de opciones.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Sugerencia automática inmersiva

La funcionalidad de sugerencia automática actual muestra las palabras clave que desencadenan una búsqueda para la palabra clave coincidente. Debido a las nuevas mejoras de Commerce, los clientes pueden detectar a menudo vínculos a productos antes de terminar de escribir.

Commerce también admite la funcionalidad para coincidencias de palabra clave en diversas categorías. Esta función permite a los clientes ver el número de palabras clave coincidentes en categorías y desencadenar una búsqueda de una palabra clave en otras categorías.

La ilustración siguiente muestra un ejemplo en el que se usa la sugerencia automática inmersiva.

![sugerencia automática inmersiva.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Ordenar

La funcionalidad de ordenación permite a los clientes ordenar, buscar y examinar por categoría, así como limitarlos por criterios como precio, nombre de producto y número de producto. Si habilita [Recomendaciones de productos](product-recommendations.md)en su entorno, los clientes también pueden clasificar los resultados en función de criterios de clasificación avanzados, como nuevos, más vendidos y tendencias.


> [!NOTE]
> Estas capacidades de búsqueda basadas en la nube están disponibles a partir de la versión 10.0.8. Asegúrese de que hay una entrada para "ProductSearch.UseAzureSearch" establecido en "true" en **Parámetros de Commerce > Parámetros de configuración**. 
![Parámetros de configuración para búsqueda en la nube.](./media/CloudPoweredSearchConfigurationParameters.png)
>Las opciones de clasificación avanzadas como nuevo, más vendido y tendencia están disponibles con la versión 9.35+ de Commerce SSK y Dynamics 365 Commerce versión 10.0.20.  


## <a name="additional-resources"></a>Recursos adicionales

[Información general de la página de aterrizaje de la categoría predeterminada y la página de resultados de la búsqueda](category-search-page-overview.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
