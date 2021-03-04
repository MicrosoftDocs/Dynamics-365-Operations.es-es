---
title: Estimación del coste del pedido de producción
description: Este artículo proporciona información acerca de la estimación de costes de producción. La estimación de costes de producción proporciona los costes de consumo de capacidad y material previsto de producir un artículo en la cantidad del pedido de producción planificado.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a101f82e60113941d389421b19cddc1ad123ce9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436938"
---
# <a name="production-order-cost-estimation"></a>Estimación del coste del pedido de producción

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la estimación de costes de producción. La estimación de costes de producción proporciona los costes de consumo de capacidad y material previsto de producir un artículo en la cantidad del pedido de producción planificado. 

Después de crear un pedido de producción, debe estimar los costes de producción. El propósito es estimar el consumo de ruta y artículos para el proceso de producción, ya que estas estimaciones se usan como la base de los siguientes procesos de programación y producción.

## <a name="production-cost-estimation"></a>Estimación de costes de producción
Las estimaciones de costes de producción se basan en la siguiente información:

-   La cantidad en el pedido de producción
-   Los componentes de las listas de materiales (L. MAT) de producción
-   Las operaciones de rutas de la ruta de producción
-   Los costes indirectos que se aplican a los componentes y las operaciones
-   Los datos de coste activos a partir de la fecha de cálculo

Si existe un artículo de línea fantasma en las L. MAT de producción, los cálculos reflejan los componentes y operaciones de ruta fantasmas. Puede usar la tarea de estimación para volver a calcular los costes estimados de modo que reflejen información actualizada. Por ejemplo, esta podría referirse a cambios en la cantidad del pedido de producción, los componentes de las L. MAT de producción, las operaciones de enrutamiento de la ruta de producción, los costes indirectos que se aplican a estos componentes y operaciones o los datos de coste activos a partir de la fecha de nuevo cálculo. Además, los cálculos de coste estimado sugieren un precio de venta para un artículo de producción basado en un enfoque de marcado según coste más margen. De manera opcional, los cálculos de coste estimado se pueden aplicar a pedidos de referencia que reflejen otros pedidos de producción vinculados al pedido de producción.

## <a name="view-the-estimated-costs"></a>Ver costes estimados
Tras ejecutar la estimación, puede ver los resultados en la página **Cálculo de precios**. La estimación calcula los valores siguientes:

-   **Coste de producción**: el coste de producción es la línea superior de la estimación. Muestra el coste completo de ejecutar el pedido de producción y el precio de ventas total para la producción. Es la suma de todas las líneas de coste de la estimación.
-   **Costes de recursos o ruta**: los costes de recursos o ruta son los costes de las operaciones de producción. Incluyen el coste de elementos como el tiempo de preparación, el tiempo de ejecución y los gastos generales.
-   **Costes de material**: los costes de materiales son los costes y precios de los componentes de L. MAT necesarios para producir el artículo. Se han establecido y especificado los costes en el sistema anteriormente.

## <a name="other-uses-of-cost-estimation"></a>Otros usos de la estimación de coste
Una estimación de coste también proporciona la siguiente información:

-   Presupuestos de precio significativos
-   Estimaciones de la rentabilidad del pedido
-   Estimaciones del uso de materias primas
-   Comparaciones de coste de producciones anteriores
-   Información de presupuesto y previsión
-   Estimación del tamaño de producción necesario para mantener un coste particular






[!INCLUDE[footer-include](../../includes/footer-banner.md)]