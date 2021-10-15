---
title: Productos de tránsito directo del almacén de recepción a las tiendas
description: Este procedimiento le guía por los pasos para crear y procesar un tránsito directo para distribuir productos desde la ubicación de recepción de un pedido de compra a una o varias tiendas.
author: Mirzaab
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e65535a1879eab229f185e0e97d81a304fd292d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572970"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Productos de tránsito directo del almacén de recepción a las tiendas

[!include [banner](../../includes/banner.md)]

Este procedimiento le guía por los pasos para crear y procesar un tránsito directo para distribuir productos desde la ubicación de recepción de un pedido de compra a una o varias tiendas. El usuario puede definir varias configuraciones y hacer que el sistema sugiera cómo distribuir los productos, o especificar manualmente a dónde se distribuyen los productos y qué cantidad se distribuye a cada almacén. El procedimiento no incluye la configuración de datos que se puede usar en el tránsito directo, como reglas de reabastecimiento, jerarquías organizativas y pesos de tiendas. El procedimiento usa la empresa de demostración USRT.

1. Vaya a Todos los pedidos de compra.
2. Seleccione un pedido de compra en la lista y haga clic en el vínculo para abrir el pedido.
3. En el panel de acciones, haga clic en Retail y Commerce.
4. Haga clic en Tránsito directo.
5. Haga clic en Editar.
    * La categoría se puede usar para filtrar los artículos en la sección Líneas.  
6. En la lista, busque y seleccione el registro deseado.
7. En el campo Cantidad en tránsito directo, escriba un valor para especificar cuánto se debe distribuir de la cantidad que se compra del producto seleccionado.
8. En el campo adicional de la cantidad en tránsito directo, especifique un valor para especificar las cantidades que se distribuirán para los productos disponibles que se están adquiriendo
9. En el campo Distribución, especifique el “Peso en la ubicación”.
    * Puede seleccionar los demás tipos para usar diferentes reglas para la distribución.  
10. En el campo Jerarquía de reabastecimiento, seleccione un valor.
11. Seleccione Sí en el campo Respetar selecciones.
12. Haga clic en Calcular cantidades.
13. Haga clic en Crear pedido.
14. Haga clic en Sí.
15. En la lista, busque y seleccione un almacén que recibió productos.
16. Haga clic en Pedido para ver los pedidos que se crearon para el almacén seleccionado



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]