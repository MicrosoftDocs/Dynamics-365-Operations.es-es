---
title: Realizar el seguimiento de un artículo o una materia prima
description: Este procedimiento muestra cómo usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas o dónde se están usando.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c39d34773a2b36cbf9477e4bdda8e45491d9c03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437109"
---
# <a name="trace-an-item-or-raw-material"></a>Realizar el seguimiento de un artículo o una materia prima

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas o dónde se están usando. Con este procedimiento, puede identificar un artículo, realizar un seguimiento de él hasta el origen y después, hacia la producción y la venta del producto terminado. El proceso se puede usar para investigar los clientes y los pedidos de ventas afectados, entre otros. Este procedimiento usa la empresa de datos de demostración USP2.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Realizar un seguimiento hacia de un artículo con un número de lote conocido
1. En el **Panel de navegación**, vaya a **Módulos > Gestión del inventario > Consultas e informes > Dimensiones de seguimiento > Seguimiento de artículos**.
2. En el campo **Código de artículo**, seleccione 'P9100'.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo **Adelante o atrás**, seleccione 'Atrás'.
5. En el campo **Número de lote**, seleccione 'as-12-344-01'.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en **Aceptar**.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identificar un artículo, realizar un seguimiento de él hacia adelante y hacer un análisis

El nodo superior del árbol representa la cantidad disponible del artículo y del lote seleccionados. Necesita expandir los nodos del árbol para encontrar el artículo en el que se debe ejecutar el seguimiento progresivo.   
1. En el árbol, expanda "los nodos descritos a continuación y después seleccione el último nodo".
    
    Expanda: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal  \P9100 ● Seleccionado ● Pedido de venta 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Sitio=1, Almacén=10, Número de lote=as-12-344-01  \P9100 ● Producción B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Sitio=1,Almacén=10,Número de lote=as-12-344-01 ● Productos asociados: P9101' y después seleccione ese nodo.     
2. En el árbol, expanda "el nodo descrito a continuación y después seleccione ese nodo".
    
    Empezando por el nodo que acaba de seleccionar, expanda "M9103 ● Línea de producción B-000050 ● 12/9/2015 ● -160,00 lb ● Tamaño=70, Color=Aceptar, Sitio=1, Almacén=10, Número de lote=App01" y a continuación seleccione ese nodo.  
3. Haga clic en **Hacer seguimiento a partir del nodo**.
4. Haga clic en **Hacia adelante.**
5. En el **Panel de acciones**, haga clic en **Seguimiento**.
    
    Hay varias opciones de seguimiento que proporcionan información acerca de los clientes afectados por el artículo del que está realizando el seguimiento y los pedidos de ventas relacionados con el artículo que se han enviado y que no se han enviado.   
6. Haga clic en **Clientes**.
7. Cierre la página.
8. En el **Panel de acciones**, haga clic en **Seguimiento**.
9. Haga clic en **Pedidos de ventas enviados**.
10. Cierre la página.

