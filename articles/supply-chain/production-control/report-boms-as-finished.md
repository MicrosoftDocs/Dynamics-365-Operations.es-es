---
title: Informar que la L. MAT. ha terminado
description: Este artículo proporciona información acerca de las notificaciones de lista de materiales terminadas.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax, BOMSetupReportFinish
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0010740de764f7b9e7797cc95e2b9187cea2695b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011041"
---
# <a name="report-boms-as-finished"></a>Informar que la L. MAT. ha terminado

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las notificaciones de lista de materiales terminadas.

Las páginas **Notificar como terminado** y **Máx. notificado como terminado** se usan para notificar la finalización de las listas de materiales (L. MAT.). Desde un punto de vista teórico, el proceso para notificar una lista de materiales como terminada es el mismo que el proceso para notificar un pedido de producción como terminado. Este proceso se puede usar en, por ejemplo, procesos sencillos de montaje y de kitting, donde no se necesitan las capacidades más avanzadas de los pedidos de producción. La página **Notificar como terminado** permite notificar varias listas de materiales como terminadas en un lote. La página **Máx. notificado como terminado** permite notificar solo una lista de materiales como terminada a la vez. La página **Notificar como terminado** está disponible desde un elemento de menú en Gestión del inventario, y ambas páginas están disponibles como elementos de menú en la página **Productos emitidos**.

## <a name="report-as-finished-page"></a>Página Notificar como terminado
Si abre la página **Notificar como terminado** desde un producto emitido, la página sugiere que notifique la cantidad predeterminada de inventario estándar como terminada. De forma predeterminada, se muestra la versión de la lista de materiales activa, pero puede cambiar la versión de la lista de materiales si hay otras versiones aprobadas. La página también le permite eliminar registros y crear nuevos registros para productos emitidos que se deban notificar como terminados. Para usar una consulta para seleccionar productos, haga clic en el elemento de menú **Seleccionar**. Puede confirmar manualmente la notificación como terminado para los productos seleccionados haciendo clic en **Aceptar**. También puede configurar el proceso para que se ejecute en un lote. Cuando el informe como proceso terminado se confirma, el sistema genera un diario de lista de materiales donde se procesa el registro en el inventario. Este diario consta de un elemento de línea para el producto terminado y un elemento de línea para cada línea de lista de materiales. Puede controlar si el diario se registra automáticamente o si se deja abierto para realizar más ajustes.

## <a name="max-report-as-finished-page"></a>Página Máx. notificado como terminado
En la página **Máx. notificado como terminado**, cada línea de lista de materiales indica el número de piezas del producto que se pueden notificar como terminadas. Este cálculo se basa en el inventario físico disponible de cada línea de material. En el siguiente ejemplo, una pieza del número de artículo FG consume dos piezas de materia prima RM10 y una pieza de materia prima RM20. Dado que solo hay 10 piezas RM10 disponibles, la cantidad máxima de FG que se puede notificar como terminada es de cinco piezas. Este valor se muestra en el campo **Máx. notificado como terminado**.

| Nivel | Número de artículo | Cantidad | Disponible | Máx. Notificar como terminado |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>Listas de materiales con varios niveles
Cuando una lista de materiales tiene varios niveles, puede controlar la manera en que los materiales se contabilizan en todos los niveles mediante el campo **Expansión**. Este campo solo está disponible en la página **Notificar como terminado** y la página **Máx. notificado como terminado**. Están disponibles las siguientes opciones:

-   **Nunca**: las listas de materiales subyacentes no se expanden si existe escasez de material.
-   **Siempre**: todas las listas de materiales subyacentes se expanden completamente. Por lo tanto, no se usa el inventario libre disponible para los artículos componentes semielaborados.
-   **Escasez**: las listas de materiales subyacentes se expanden solamente si la cantidad total deseada del material no está disponible.

### <a name="example"></a>Ejemplo

En este ejemplo, tres piezas del producto terminado (número de artículo FG) están listas para notificarse como terminadas. Hay una lista de materiales de dos niveles, como se muestra aquí.

| Nivel | Número de artículo | Cantidad en línea de lista de materiales | Disponible |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

En las siguientes tablas se muestra cómo el valor del campo **Expansión** afecta a la forma en que se generan las líneas del diario de lista de materiales. **Expansión: Nunca**

| Nivel | Número de artículo | Cantidad |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Como la tabla anterior muestra, solo el número de artículo COMP se considera restado en el diario. El número de artículo RM, que forma parte de COMP, no se expande a la línea del diario, y las dos piezas disponibles de COMP no se tienen en cuenta. **Expansión: Siempre**

| Nivel | Número de artículo | Cantidad |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

En este caso, el número de artículo COMP se expande a su materia prima, número de artículo RM. Los dos piezas disponibles de COMP no se tienen en cuenta en la cantidad RM que consumir. **Expansión: Escasez**

| Nivel | Número de artículo | Cantidad |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

En este caso, los dos piezas disponibles del número de artículo COMP sí se tienen en cuenta. Sin embargo, dado que hacen falta tres piezas del número de artículo FG, también hace falta una pieza del número de artículo RM para sumar la pieza adicional de COMP.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]