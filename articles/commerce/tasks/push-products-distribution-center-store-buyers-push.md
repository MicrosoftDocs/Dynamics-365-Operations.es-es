---
title: Insertar productos del centro de distribución al almacén mediante estrategia de presión
description: Este procedimiento le guía por los pasos para crear y procesar una estrategia de presión para distribuir productos desde una ubicación a una o varias tiendas.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3720945823cf127f776a9ea6a6ad75a72ceec00c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012350"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a>Insertar productos del centro de distribución al almacén mediante estrategia de presión

[!include [banner](../includes/banner.md)]

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

