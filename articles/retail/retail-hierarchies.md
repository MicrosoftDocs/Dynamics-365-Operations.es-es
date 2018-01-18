---
title: "Jerarquías comerciales"
description: "Este artículo describe jerarquías comerciales en Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: OMHierarchyManager
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e94b59540c9ef188a07e2e24ef4a04829b9d37f8
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="retail-hierarchies"></a>Jerarquías comerciales

[!include[banner](includes/banner.md)]


Este artículo describe jerarquías comerciales en Microsoft Dynamics 365 for Retail.

Puede crear una jerarquía de categoría comercial para organizar los productos que vende a través de los canales comerciales. Puede usar jerarquías de productos comerciales para categorizar o agrupar productos. Puede usar estos productos para crear selecciones de productos y programas de fidelización de clientes. También puede asignar propiedades y atributos de productos, asignar una estructura de precios, incluir los productos en las promociones de producto y usar los productos para crear informes. Puede crear una jerarquía de categoría comercial que represente todos los productos y categorías de la organización y, a continuación, utilizar dicha jerarquía de categoría con distintos fines. Como alternativa, puede crear varias jerarquías de categoría comercial para fines especiales, tales como promociones de productos. Al crear una jerarquía de productos comerciales, debe asignar un tipo de jerarquía de categoría para identificar el propósito de la jerarquía de categoría. Por ejemplo, solo se hace referencia a las jerarquías de productos que tienen el tipo **Jerarquía de navegación comercial** asignado al examinar productos por categoría en línea o en el punto de venta (POS).

## <a name="retail-hierarchy-types"></a>Tipos de jerarquía comercial
La siguiente tabla enumera los tipos de jerarquías de categorías comerciales disponibles y los fines generales de cada tipo.

| Tipo de jerarquía de categorías       | Propósito                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jerarquía de productos comerciales      | Use este tipo de jerarquía para definir la jerarquía de productos general para su organización. Puede utilizar este tipo de jerarquía para comercialización, precios y promociones, informes y planificación de selecciones. Solo se puede asignar una jerarquía de productos comerciales a este tipo de la jerarquía.                                       |
| Jerarquía comercial complementaria | Utilice este tipo de la jerarquía para cualquier jerarquía de categoría comercial adicional que desee crear. Por ejemplo, en primavera, tiene una promoción de bañadores. Por lo tanto, incluye sus productos de baño en una jerarquía de categoría independiente y aplica el precio promocional a las distintas categorías de productos. |
| Jerarquía de navegación comercial   | Use este tipo de jerarquía para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta.                                                                                                                                                                                       |

Si utiliza una jerarquía de categorías comerciales para dar estructura a sus productos, podrá configurar y mantener las propiedades y los atributos de los productos en el nivel de la categoría. Estas propiedades y atributos incluyen valores para la configuración del punto de venta y las dimensiones de productos. Cualquier producto que asigne a las categorías heredará automáticamente las propiedades y los atributos definidos. También puede copiar la configuración de propiedad de cualquier producto en varios productos de una categoría seleccionada al mismo tiempo.




