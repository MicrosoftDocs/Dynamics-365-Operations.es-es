---
title: Crear manualmente recomendaciones curadas
description: Este tema explica de qué manera los distribuidores pueden crear y administrar manualmente listas de productos para los clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b00c83355850f6249068749096b011f805b37e3c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154327"
---
# <a name="manually-create-curated-recommendations"></a>Crear manualmente recomendaciones curadas

[!include [banner](includes/banner.md)]

Este tema explica de qué manera los distribuidores pueden crear y administrar manualmente recomendaciones de productos para los clientes de Microsoft Dynamics 365 Commerce.

Las listas mantenidas son colecciones de contenido individual creadas y mantenidas por las personas.  

## <a name="create-a-new-list"></a>Crear una lista nueva

Para crear una lista de recomendaciones de productos mantenida, siga estos pasos.

1. Vaya a **Retail y Commerce &gt; Recomendaciones de producto &gt; Listas de recomendaciones**.
1. Seleccione **Nuevo**.
1. En el campo **Id. de lista**, escriba un valor.
1. En el campo **Nombre de la lista**, escriba un valor.
    - El **Nombre de la lista** es el título de la lista que aparecerá en la sección de listas mantenidas del módulo **Colección de productos**.
1. Para agregar productos a la lista, seleccione **Agregar productos**.
1. Para cambiar el orden de los productos de la lista, especifique un valor en la columna **Orden de visualización**.
    - Si dos productos tienen el mismo valor de orden de visualización, el orden final de estos dos resultados puede ser diferente de la oficina administrativa.
1. Seleccione **Guardar** para guardar la lista.

## <a name="example-list"></a>Lista de ejemplos

![Lista mantenida de ejemplos en oficina administrativa](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar ADLS en un entorno de Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)
