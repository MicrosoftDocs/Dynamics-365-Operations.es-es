---
title: Ajuste de valores de coste de inventario disponible
description: Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62122454b2fe0f6a9f04f073057156603e66bb22
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673309"
---
# <a name="adjust-on-hand-inventory-cost-values"></a>Ajuste de valores de coste de inventario disponible

[!include [banner](../includes/banner.md)]

Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.

Puede usar la página **Ajuste del inventario disponible** para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario. **Nota**: para abrir la página **Ajuste del inventario disponible**, en la página **Cierre y ajuste**, seleccione el registro de un proceso de cierre de inventario finalizado y haga clic en **Ajuste** &gt; **Disponible**. **Ejemplo:** Tiene las siguientes transacciones en febrero:

-   1 de febrero: recepción financiera de inventario para una cantidad de 2 a un coste de 10,00 USD
-   5 de febrero: una recepción financiera de inventario para una cantidad de 1 a un coste de 13,00 USD
-   19 de febrero: una emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 11,00

Este artículo se ha configurado con el modelo de inventario FIFO, y el cierre de inventario se ha efectuado con fecha de 28 de febrero. La transacción de emisión financiera de 11,00 USD se liquidará con la recepción financiera del 1 de febrero, y se efectuará un ajuste de 1,00 USD. Las siguientes recepciones de inventario contendrán cantidades de inventario abiertas:

-   1 de febrero: una cantidad de 1 a un coste de 10,00 dólares
-   5 de febrero: una cantidad de 1 a un coste de 13,00 dólares

Para definir el coste de estos dos artículos en 15,00 USD, utilice la opción de ajuste disponible para ajustar las cantidades abiertas disponibles como del último período de cierre del inventario. **Nota**: la fecha de contabilización de la transacción de ajuste disponible será la fecha del último cierre de inventario. Este valor de fecha no se podrá modificar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]