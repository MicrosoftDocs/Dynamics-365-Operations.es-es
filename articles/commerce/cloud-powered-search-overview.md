---
title: Visión general de la búsqueda con tecnología de nube
description: Este tema ofrece una visión general de la búsqueda con tecnología de nube en Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c78af42313d83ebec5a56f83682f394c5e9d21f08851aaa0493563163d76046b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722039"
---
# <a name="cloud-powered-search-overview"></a>Información general de la búsqueda con tecnología de nube

[!include [banner](includes/banner.md)]

Este tema ofrece una visión general de la búsqueda con tecnología de nube en Microsoft Dynamics 365 Commerce.

La detectabilidad de productos ayuda a garantizar que los clientes pueden encontrar productos rápida y fácilmente examinando categorías, buscando y filtrando. Los minoristas consideran el descubrimiento de productos una herramienta principal para la interacción de clientes en todos los canales.

Los clientes se acostumbran a tiempos de respuesta casi instantáneos de los motores de búsqueda web, sitios web sofisticados de correo electrónico, aplicaciones sociales, sugerencias automáticas que aparecen conforme escriben términos de búsqueda, navegación por facetas y resaltado. Si los clientes no encuentran el producto que buscan lo suficientemente rápido en una tienda de comercio electrónico, no dudan en ir a una tienda diferente de comercio electrónico.

La detectabilidad de productos con tecnología de nube en Dynamics 365 Commerce continúa aumentando los tipos de conversión y retención de consumidor en todos los canales, tanto en los canales de comercio electrónico como en los canales de punto de venta (PDV).

La experiencia de búsqueda de Dynamics 365 Commerce ha mejorado las capacidades de ayudar a los minoristas a lograr una mejor detectabilidad del producto. Al mismo tiempo, estas capacidades ofrecen la escalabilidad y el rendimiento necesarios para el tráfico de comercio electrónico.

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

La funcionalidad de sugerencia automática actual solo muestra las palabras clave que desencadenan una búsqueda para la palabra clave coincidente. Debido a las nuevas mejoras de Dynamics 365 Commerce, los clientes pueden detectar a menudo vínculos a productos antes de terminar de escribir.

Dynamics 365 Commerce también admite la funcionalidad para coincidencias de palabra clave en diversas categorías. Esta función permite a los clientes ver el número de palabras clave coincidentes en categorías y desencadenar una búsqueda de una palabra clave en otras categorías.

La ilustración siguiente muestra un ejemplo en el que se usa la sugerencia automática inmersiva.

![sugerencia automática inmersiva.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Ordenar

La ordenación mejorada en Dynamics 365 Commerce permite a los clientes ordenar, buscar y examinar resultados de la búsqueda, así como limitarlos por criterios como precio, nombre de producto y número de producto. Los clientes también pueden ordenar los resultados en función de si un producto es nuevo, más vendido o se ha agregado recientemente.

>[!NOTE]
>Estas capacidades de búsqueda basadas en la nube están disponibles a partir de la versión 10.0.8. Asegúrese de que en **Parámetros de Commerce > Parámetros de configuración** hay una entrada para "ProductSearch.UseAzureSearch establecido en 'true'". 
![Parámetros de configuración para búsqueda en la nube.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general de la página de aterrizaje de la categoría predeterminada y la página de resultados de la búsqueda](category-search-page-overview.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
