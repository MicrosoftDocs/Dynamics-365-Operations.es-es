---
title: Calcular un pedido de producción
description: Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58a0f8e9247e5885b1f148b3b28b7e67b1fa292d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240326"
---
# <a name="estimate-a-production-order"></a>Calcular un pedido de producción

[!include [banner](../../includes/banner.md)]

Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. En ambos casos, debe tener un pedido de producción abierto con estado Creado. Este es el segundo procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="estimate-a-production-order"></a>Calcular un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
2. Seleccione un pedido con estado Creado en la cuadrícula.
3. En el panel de acciones, haga clic en Pedido de producción.
4. Haga clic en Estimación.
    * En este paso, se calculan los costes estimados de un único pedido de producción.   
5. Haga clic en Aceptar

## <a name="view-the-calculation-details"></a>Visualización de los detalles de cálculo
1. En el panel de acciones, haga clic en Gestionar costes.
2. Haga clic en Ver detalles de cálculo.
    * Esta página muestra el análisis de costes. Por ejemplo, puede ver el precio de coste total por unidad para el producto terminado en la primera fila. Las filas posteriores contienen costes según la lista de materiales, la ruta de producción y los costes indirectos.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]