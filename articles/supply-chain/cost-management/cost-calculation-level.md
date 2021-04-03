---
title: Nivel de cálculo de costes
description: Este tema describe el nivel de lista de materiales (BOM) que se denomina Nivel de cálculo de costes. Este nivel BOM excluye los pedidos de producción y lote de sus cálculos.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1cfbbb6aadbd24a0352776285f6c60ff10f59549
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251035"
---
# <a name="cost-calculation-level"></a>Nivel de cálculo de costes

El nivel de lista de materiales (BOM) que se denomina **Nivel de cálculo de costes** excluye pedidos de producción y pedidos por lotes de sus cálculos. El sistema usa este nivel cuando ejecuta cálculos de costes en versiones de costes. En procesos como el recálculo y el cierre del inventario, el sistema utiliza en su lugar el nivel BOM **Nivel de costes**.

El siguiente escenario simple muestra las diferencias entre Nivel BOM de **Nivel de cálculo de costes** y el nivel BOM **Nivel de costes**.

Tiene tres productos: A, B y C. El producto C es el componente del producto B, y el producto B es el componente del producto A.

- **Nivel de costes** asigna los siguientes niveles de lista de materiales:

    - **Producto A:** 0
    - **Producto B:** 1
    - **Producto C:** 2

- **Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:

    - **Producto A:** 0
    - **Producto B:** 1
    - **Producto C:** 2

Luego se crea una orden de producción para el producto C, y el producto A se agrega a la lista de materiales de la orden de producción. Una vez estimado el pedido, los niveles de la lista de materiales se actualizan de la siguiente manera:

- **Nivel de costes** asigna los siguientes niveles de lista de materiales:

    - **Producto B:** 1
    - **Producto C:** 2
    - **Producto A:** 3

- **Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:

    - **Producto A:** 0
    - **Producto B:** 1
    - **Producto C:** 2

Este comportamiento garantiza que los cambios en las listas de materiales de órdenes de producción no afecten los cálculos de costes posteriores.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]