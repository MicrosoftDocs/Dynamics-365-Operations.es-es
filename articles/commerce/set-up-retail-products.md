---
title: Configurar productos comerciales
description: Este artículo describe cómo configurar productos en Dynamics 365 Commerce.
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
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
ms.openlocfilehash: 22a3ecb235b21e239b23e5450ca4a2f12f9a41ac
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276084"
---
# <a name="set-up-retail-products"></a>Configurar productos comerciales

[!include [banner](includes/banner.md)]

Este artículo describe cómo configurar productos en Dynamics 365 Commerce.

Para poder ofrecer productos para la reventa en sus canales de Commerce, debe crear y configurar los productos. Commerce crea productos en toda la organización en el producto maestro. Puede crear los productos, definir sus atributos y propiedades y asignar los productos a las jerarquías de categorías de Commerce. Para que los productos estén disponibles para los canales y agregarlos a una selección activa, deberá lanzarlos para las entidades jurídicas en las que estén disponibles. Para configurar los productos que vende mediante canales, lleve a cabo las tareas siguientes.

1. **Defina una jerarquía de productos**. Mediante las características de la jerarquía de categoría en Commerce, puede definir las jerarquías de categoría comercial para agrupar y clasificar los productos que distribuye en sus canales. Se pueden definir atributos del sistema y definidos por el usuario en el nivel de categoría. A continuación, todos los productos asignados a la categoría heredan dichos atributos. Se pueden definir varias jerarquías de categoría, y cada producto puede asignarse a varias jerarquías. Sin embargo, en una sola jerarquía, cada producto puede asignarse a una única categoría.
2. **Agregue productos y variantes del producto al producto maestro.** Los productos que se agregan al producto maestro representan una lista global de productos. Puede agregar productos manualmente, uno por uno o importar los datos del producto de los proveedores.
3. **Emitir productos a entidades jurídicas.** Solo los productos liberados para entidades jurídicas pueden estar disponibles para los canales. Al definir en primer lugar un producto, lo define en un nivel de toda la organización. A continuación, puede seleccionar una o varias entidades jurídicas a las que liberar el producto. El producto quedará entonces disponible para varios canales en su organización. Puede usar esta funcionalidad para crear un producto cada vez, agregar y actualizar atributos de productos y propiedades en un solo lugar y, a continuación, distribuir el producto a través de su organización a los canales en los que está disponible.
4. **Agregar productos a selecciones.** Una selección representa una colección de productos que ofrece en sus canales. Puede definir una o varias selecciones, y cada producto puede asignarse a una o varias selecciones. Para asignar productos a los canales, asigne las selecciones a dichos canales. Cuando se crea un surtido, puede agregar productos que aún no se hayan liberado a una entidad jurídica. Sin embargo, debe liberar los productos a una entidad jurídica antes de que dichos productos puedan estar disponibles para los canales.
5. **Agregue los productos a las jerarquías de navegación.** Para que los productos se puedan buscar en línea o en el punto de venta (POS), deben estar clasificados en una jerarquía de navegación de Commerce.
6. **Agregue productos a catálogos** Aunque este paso es opcional para el PDV, las tiendas en línea requieren que los productos estén incluidos al menos en un catálogo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
