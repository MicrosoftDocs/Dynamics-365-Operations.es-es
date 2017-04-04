---
title: Ajuste de valores de coste de inventario disponible
description: "Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d1ef775c9783b975fd0f852dc7112506d3897605
ms.lasthandoff: 03/31/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Ajuste de valores de coste de inventario disponible

Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.

Puede usar la página **Ajuste del inventario disponible** para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario. ** Nota: ** Para abrir ** ajuste del inventario disponible ** la página, en ** el cierre y ajuste ** la página, seleccione el registro de un proceso de cierre de inventario completado, y haga clic en ** ajuste ** &gt; ** ** disponible. **Ejemplo:** Tiene las siguientes transacciones en febrero:

-   1 de febrero: recepción financiera de inventario para una cantidad de 2 a un coste de 10,00 USD
-   5 de febrero: una recepción financiera de inventario para una cantidad de 1 a un coste de 13,00 USD
-   19 de febrero: una emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 11,00

Este artículo se ha configurado con el modelo de inventario FIFO, y el cierre de inventario se ha efectuado con fecha de 28 de febrero. La transacción de emisión financiera de 11.00 USD se liquidará con la recepción financiera que se con fecha del 1 de febrero, y un ajuste de 1.00 dólares USD. Las siguientes recepciones de inventario contendrán cantidades de inventario abiertas:

-   1 de febrero: una cantidad de 1 a un coste de 10,00 dólares
-   5 de febrero: una cantidad de 1 a un coste de 13,00 dólares

Para definir el coste de estos dos artículos en 15,00 USD, utilice la opción de ajuste disponible para ajustar las cantidades abiertas disponibles como del último período de cierre del inventario. **Nota**: la fecha de contabilización de la transacción de ajuste disponible será la fecha del último cierre de inventario. Este valor de fecha no se podrá modificar.


