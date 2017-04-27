---
title: "Jerarquías comerciales"
description: "Este artículo describe jerarquías comerciales en Microsoft Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 5fed76e09ef2a64bc2aad2cf6ad7dcfa290acab1
ms.lasthandoff: 03/31/2017


---

# <a name="retail-hierarchies"></a>Jerarquías comerciales

[!include[banner](includes/banner.md)]


Este artículo describe jerarquías comerciales en Microsoft Dynamics AX.

Puede crear una jerarquía de categoría comercial para organizar los productos que vende a través de los canales comerciales. Puede usar jerarquías de productos comerciales para categorizar o agrupar productos. Puede usar estos productos para crear selecciones de productos y programas de fidelización de clientes. También puede asignar propiedades y atributos de productos, asignar una estructura de precios, incluir los productos en las promociones de producto y usar los productos para crear informes. Puede crear una jerarquía de categoría comercial que represente todos los productos y categorías de la organización y, a continuación, utilizar dicha jerarquía de categoría con distintos fines. Como alternativa, puede crear varias jerarquías de categoría comercial para fines especiales, tales como promociones de productos. Al crear una jerarquía de productos comerciales, debe asignar un tipo de jerarquía de categoría para identificar el propósito de la jerarquía de categoría. Por ejemplo, solo se hace referencia a las jerarquías de productos que tienen el tipo **Jerarquía de navegación comercial** asignado al examinar productos por categoría en línea o en el punto de venta (POS).

## <a name="retail-hierarchy-types"></a>Tipos de jerarquía comercial
La siguiente tabla enumera los tipos de jerarquías de categorías comerciales disponibles y los fines generales de cada tipo.

| Tipo de jerarquía de categorías       | Propósito                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jerarquía de productos comerciales      | Use este tipo de jerarquía para definir la jerarquía de productos general para su organización. Puede utilizar este tipo de jerarquía para comercialización, precios y promociones, informes y planificación de selecciones. Solo se puede asignar una jerarquía de productos comerciales a este tipo de la jerarquía.                                       |
| Jerarquía comercial complementaria | Utilice este tipo de la jerarquía para cualquier jerarquía de categoría comercial adicional que desee crear. Por ejemplo, en primavera, tiene una promoción de bañadores. Por lo tanto, incluye sus productos de baño en una jerarquía de categoría independiente y aplica el precio promocional a las distintas categorías de productos. |
| Jerarquía de navegación comercial   | Use este tipo de jerarquía para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta.                                                                                                                                                                                       |

Si utiliza una jerarquía de categorías comerciales para dar estructura a sus productos, podrá configurar y mantener las propiedades y los atributos de los productos en el nivel de la categoría. Estas propiedades y atributos incluyen valores para la configuración del punto de venta y las dimensiones de productos. Cualquier producto que asigne a las categorías heredará automáticamente las propiedades y los atributos definidos. También puede copiar la configuración de propiedad de cualquier producto en varios productos de una categoría seleccionada al mismo tiempo.




