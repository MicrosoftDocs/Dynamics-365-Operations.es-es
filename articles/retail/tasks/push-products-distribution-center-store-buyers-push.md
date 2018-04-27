--- 
title: "Insertar productos del centro de distribución al almacén mediante estrategia de presión"
description: "Este procedimiento le guía por los pasos para crear y procesar una estrategia de presión para distribuir productos desde una ubicación a una o varias tiendas."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 9d9a5d4fdece1cfb573224bd54d96ccd281c0f09
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a>Insertar productos del centro de distribución al almacén mediante estrategia de presión

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento le guía por los pasos para crear y procesar una estrategia de presión para distribuir productos desde una ubicación a una o varias tiendas. El usuario puede definir varias configuraciones y hacer que el sistema sugiera cómo distribuir los productos, o especificar manualmente a dónde se distribuyen los productos y qué cantidad se distribuye a cada almacén. Este procedimiento no incluye la configuración de datos que se puede usar en la estrategia de presión, como reglas de reabastecimiento, jerarquías organizativas y pesos de tiendas. Este procedimiento usa la empresa de prueba USRT.

1. Vaya a Estrategia de presión.
2. Haga clic en Nuevo.
3. En el campo Descripción, escriba un valor.
4. En el campo Sitio, especifique o seleccione un valor.
5. En el campo Almacén, especifique o seleccione un almacén que tenga productos con cantidades disponibles.
6. Haga clic en Agregar.
7. En la lista, marque la fila seleccionada.
8. En el campo Número de artículo, especifique o seleccione un producto.
9. Haga clic en Agregar.
10. En la lista, marque la fila seleccionada.
11. En el campo Número de artículo, especifique o seleccione un producto de variante.
    * Al especificar un producto de variante, se crearán líneas para cada variante.  
12. En la lista, marque una fila.
13. En el campo Cantidad insertada, escriba cuánto del producto seleccionado desea distribuir.
14. En el campo Cantidad adicional a la que aplicar la estrategia de presión, especifique la cantidad de los productos que tienen cantidad disponible para distribuir.
15. En el campo Distribución, especifique el “Peso en la ubicación”.
    * Puede seleccionar los demás tipos para usar otras reglas para la distribución.  
16. En el campo Jerarquía de reabastecimiento, seleccione un valor.
17. Seleccione Sí en el campo Respetar selecciones.
18. Haga clic en Calcular cantidades y revise las cantidades que se agregan a las filas en la sección Almacén.
19. Haga clic en Crear pedido.
20. Haga clic en Sí.


