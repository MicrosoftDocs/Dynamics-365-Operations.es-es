---
title: Configurar productos comerciales
description: Este artículo describe cómo configurar productos al por menor en Dynamics 365 Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 74fa3a87ac2993adca3edf003bbc39371ce8e289
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024784"
---
# <a name="set-up-retail-products"></a>Configurar productos comerciales

[!include [banner](includes/banner.md)]

Este artículo describe cómo configurar productos al por menor en Dynamics 365 Retail.

Para poder ofrecer productos para la reventa en sus canales comerciales, debe crear y configurar los productos en Dynamics 365 Retail. Retail crea productos en toda la organización en el producto maestro. Puede crear los productos, definir sus atributos y propiedades y asignar los productos a las jerarquías de categorías comerciales. Para hacer que los productos estén disponibles para los canales comerciales y agregarlos a un surtido activo, debe liberar los productos a las entidades jurídicas donde están disponibles. Para configurar los productos que vende mediante canales comerciales, lleve a cabo las tareas siguientes.

1. Defina una jerarquía de productos comerciales. Mediante las características de la jerarquía de categoría en Retail, puede definir las jerarquías de categoría comercial para agrupar y clasificar los productos que distribuye en sus canales comerciales. Se pueden definir atributos del sistema y definidos por el usuario en el nivel de categoría. A continuación, todos los productos asignados a la categoría heredan dichos atributos. Se pueden definir varias jerarquías de categoría, y cada producto puede asignarse a varias jerarquías. Sin embargo, en una sola jerarquía, cada producto puede asignarse a una única categoría.
2. Agregue productos y variantes del producto al producto maestro. Los productos que se agregan al producto maestro representan una lista global de productos. Puede agregar productos manualmente, uno por uno o importar los datos del producto de los proveedores.
3. Emitir productos a entidades jurídicas. Solo los productos que se han liberado a las entidades jurídicas pueden hacerse disponibles para los canales comerciales. Al definir en primer lugar un producto, lo define en un nivel de toda la organización. A continuación, puede seleccionar una o varias entidades jurídicas a las que liberar el producto. El producto quedará entonces disponible para varios canales comerciales en su organización. Puede usar esta funcionalidad para crear un producto cada vez, agregar y actualizar atributos de productos y propiedades en un solo lugar y, a continuación, distribuir el producto a través de su organización a los canales comerciales en los que está disponible.
4. Agregar productos a selecciones. Una selección representa una colección de productos que ofrece en sus canales comerciales. Puede definir una o varias selecciones, y cada producto puede asignarse a una o varias selecciones. Para asignar productos a los canales comerciales, asigne las selecciones a dichos canales comerciales. Cuando se crea un surtido, puede agregar productos que aún no se hayan liberado a una entidad jurídica. Sin embargo, debe liberar los productos a una entidad jurídica antes de que dichos productos puedan estar disponibles para los canales comerciales.
5. Agregue los productos a las jerarquías de navegación. Para que los productos se puedan buscar en línea o en el punto de venta (POS), deben estar clasificados en una jerarquía de navegación comercial.
6. Agregue productos a catálogos Aunque este paso es opcional para el PDV, las tiendas en línea requieren que los productos estén incluidos al menos en un catálogo.
