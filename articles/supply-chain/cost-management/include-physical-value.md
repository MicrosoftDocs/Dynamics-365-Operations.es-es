---
title: Incluir valor físico en coste
description: Use la casilla Incluir valor físico en coste de la ficha desplegable Modelo de inventario del formulario Grupos de modelos de artículo se utiliza para especificar si las transacciones actualizadas físicamente se incluyen en el cálculo del precio de coste promedio móvil del artículo.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e96d5e2a658a027d66663868329cf4eedcb1d46f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "357321"
---
# <a name="include-physical-value"></a>Incluir valor físico en coste

[!include [banner](../includes/banner.md)]

Use la casilla Incluir valor físico en coste de la ficha desplegable Modelo de inventario del formulario Grupos de modelos de artículo se utiliza para especificar si las transacciones actualizadas físicamente se incluyen en el cálculo del precio de coste promedio móvil del artículo.

La casilla **Incluir valor físico** tiene los siguientes valores.

| Valor    | Resultado                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Seleccionado | Tanto las transacciones actualizadas físicamente como las actualizadas financieramente se usarán para calcular el precio de coste promedio móvil. |
| Desactivada  | Sólo se usarán las transacciones actualizadas financieramente para calcular el precio de coste promedio móvil.                                     |

La casilla tiene efectos ligeramente diferentes, en función del modelo de inventario que use.

-   Si se activa la casilla de verificación **Incluir valor físico en coste** cuando se usa el modelo de inventario de fecha FIFO (primero en entrar, primero en salir), LIFO (el último en entrar es el primero en salir) o Fecha LIFO, el cierre de inventario también realiza ajustes en las transacciones actualizadas físicamente.
-   Si no se activa la casilla de verificación **Incluir valor físico en coste** cuando se usan estos modelos de inventario, el cierre de inventario realiza liquidaciones únicamente en las transacciones actualizadas financieramente.
-   Al usar el modelo de inventario de media ponderada o de fecha media ponderada, el cierre de inventario liquida únicamente las transacciones actualizadas financieramente, independientemente de si se activa la casilla de verificación **Incluir valor físico en coste**.

**Ejemplo 1** Ha activado la casilla**Incluir valor físico en coste** y recibido los siguientes pedidos de compra:

-   Se ha actualizado el albarán para un pedido de compra para una cantidad de 2 y un precio de coste de 10,00 dólares.
-   Se ha actualizado la factura para un pedido de compra para una cantidad de 3 y un precio de coste de 12,00 dólares.

En este caso, el precio de coste promedio móvil será de 11,20 USD, ya que se usan transacciones actualizadas tanto física como financieramente para calcular el precio de coste. **Ejemplo 2** No ha activado la casilla de verificación **Incluir valor físico en coste** y el precio de coste en la configuración del artículo es de 10,00 USD. Recibe un pedido de compra para una cantidad de 20 y un precio de coste de 12,00 dólares del que se ha actualizado el albarán. Cuando se registre un pedido de ventas, se registrará un importe de coste de 10,00 USD, ya que el precio de coste promedio móvil no incluirá las transacciones actualizadas físicamente. **Nota:** A modo de comparación, si activa la casilla **Incluir valor físico** para este artículo, cuando se registre un pedido de ventas, el importe de coste registrado será 12,00 USD.



