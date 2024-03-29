---
title: Jerarquías de Commerce
description: Este artículo describe jerarquías de Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.industry: Retail
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
ms.openlocfilehash: ce196acc8c4bced865b983b12d72f8bc6e4d02a0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271887"
---
# <a name="commerce-hierarchies"></a>Jerarquías de Commerce

[!include [banner](includes/banner.md)]

Este artículo describe jerarquías de Dynamics 365 Commerce.

Puede crear una jerarquía de categoría para organizar los productos que vende a través de los canales. Puede usar jerarquías de productos para categorizar o agrupar productos. Puede usar estos productos para crear selecciones de productos y programas de fidelización de clientes. También puede asignar propiedades y atributos de productos, asignar una estructura de precios, incluir los productos en las promociones de producto y usar los productos para crear informes. Puede crear una jerarquía de categoría para representar todos los productos y categorías de la organización y, a continuación, usar esa jerarquía de categoría para varios propósitos. Como alternativa, puede crear varias jerarquías de categoría para fines especiales, tales como promociones de productos. Al crear una jerarquía de productos, debe asignar un tipo de jerarquía de categoría para identificar el propósito de la jerarquía de categoría. Por ejemplo, solo se hace referencia a las jerarquías de productos que tienen el tipo **Jerarquía de navegación de Commerce** asignado al examinar productos por categoría en línea o en el punto de venta (POS).

## <a name="hierarchy-types"></a>Tipos de jerarquía

La siguiente tabla enumera los tipos de jerarquías de categorías disponibles y los fines generales de cada tipo.

| Tipo de jerarquía de categorías       | Propósito |
|-------------------------------|---------|
| Jerarquía de productos      | Use este tipo de jerarquía para definir la jerarquía de productos general para su organización. Puede utilizar este tipo de jerarquía para comercialización, precios y promociones, informes y planificación de selecciones. Solo se puede asignar una jerarquía de productos a este tipo de la jerarquía. |
| Jerarquía complementaria | Utilice este tipo de la jerarquía para cualquier jerarquía de categoría adicional que desee crear. Por ejemplo, en primavera, tiene una promoción de bañadores. Por lo tanto, incluye sus productos de baño en una jerarquía de categoría independiente y aplica el precio promocional a las distintas categorías de productos. |
| Jerarquía de navegación   | Use este tipo de jerarquía para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta. |

Si utiliza una jerarquía de categorías para dar estructura a sus productos, podrá configurar y mantener las propiedades y los atributos de los productos en el nivel de la categoría. Estas propiedades y atributos incluyen valores para la configuración del punto de venta y las dimensiones de productos. Cualquier producto que asigne a las categorías heredará automáticamente las propiedades y los atributos definidos. También puede copiar la configuración de propiedad de cualquier producto en varios productos de una categoría seleccionada al mismo tiempo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
