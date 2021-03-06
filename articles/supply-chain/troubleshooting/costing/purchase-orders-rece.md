---
title: Los pedidos de compra recibidos físicamente no aparecen en el informe de cierre de inventario
description: Los pedidos de compra recibidos físicamente no aparecen en el informe de cierre de inventario Comprobar cantidades abiertas.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026881"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Los pedidos de compra recibidos físicamente no aparecen en el informe de cierre de inventario

Número de KB: 4612595

## <a name="symptoms"></a>Síntomas

Los pedidos de compra recibidos físicamente no aparecen en el informe de cierre de inventario **Comprobar cantidades abiertas**.

## <a name="resolution"></a>Resolución

El informe **Comprobar cantidades abiertas** muestra transacciones de emisión que no se pueden liquidar con recepciones de inventario actualizadas financieramente a partir de la fecha de cierre seleccionada. Puede optar por incluir recepciones físicas en el informe. En ese caso, se mostrarán las recepciones físicas si pueden cubrir las transacciones de emisión que no se pueden liquidar. Para obtener más información, consulte [Preparar para ejecutar el cierre de inventario](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
