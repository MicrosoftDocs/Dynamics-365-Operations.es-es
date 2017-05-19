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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a62d8d453be096dda221415437e78c695f3e5cf7
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Ajuste de valores de coste de inventario disponible

[!include[banner](../includes/banner.md)]


Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.

Puede usar la página **Ajuste del inventario disponible** para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario. **Nota**: para abrir la página **Ajuste del inventario disponible**, en la página **Cierre y ajuste**, seleccione el registro de un proceso de cierre de inventario finalizado y haga clic en **Ajuste** &gt; **Disponible**. **Ejemplo:** Tiene las siguientes transacciones en febrero:

-   1 de febrero: recepción financiera de inventario para una cantidad de 2 a un coste de 10,00 USD
-   5 de febrero: una recepción financiera de inventario para una cantidad de 1 a un coste de 13,00 USD
-   19 de febrero: una emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 11,00

Este artículo se ha configurado con el modelo de inventario FIFO, y el cierre de inventario se ha efectuado con fecha de 28 de febrero. La transacción de emisión financiera de 11,00 USD se liquidará con la recepción financiera del 1 de febrero, y se efectuará un ajuste de 1,00 USD. Las siguientes recepciones de inventario contendrán cantidades de inventario abiertas:

-   1 de febrero: una cantidad de 1 a un coste de 10,00 dólares
-   5 de febrero: una cantidad de 1 a un coste de 13,00 dólares

Para definir el coste de estos dos artículos en 15,00 USD, utilice la opción de ajuste disponible para ajustar las cantidades abiertas disponibles como del último período de cierre del inventario. **Nota**: la fecha de contabilización de la transacción de ajuste disponible será la fecha del último cierre de inventario. Este valor de fecha no se podrá modificar.




