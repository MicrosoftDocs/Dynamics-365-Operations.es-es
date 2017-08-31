--- 
title: Crear un pedido de ventas para un producto configurable
description: "Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas."
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6546d504a2fda255cb5183408dfe84a3074543ab
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Crear un pedido de ventas para un producto configurable

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas. Este ejemplo usa el modelo de altavoz D0006 en la empresa de datos de demostración USMF. Normalmente, un procesador del pedido de ventas utiliza este procedimiento.


## <a name="create-a-sales-order"></a>Crear un pedido de ventas
1. Haga clic en Consulta y procesamiento de pedido de ventas.
2. Haga clic en Nuevo.
3. Haga clic en Pedido de ventas.
4. En el campo Cuenta de cliente, seleccione US-001. 
5. Haga clic en Aceptar
6. En el campo Código de artículo, seleccione D0006.
    * Para esta tarea, debe seleccionar un producto configurable.  
7. Haga clic en Producto y suministro.
8. Haga clic en Configurar la línea.
    * Tenga en cuenta que el precio ha cambiado, en función de la configuración seleccionada, y que ahora el campo Incluir cable se ha establecido como Verdadero.  
    * Anote el precio predeterminado y la configuración que se selecciona para el cable.  
9. Haga clic en Cargar plantilla.
    * Este ejemplo muestra cómo puede aplicar una plantilla para seleccionar una configuración predefinida. Si utiliza este procedimiento como una guía de la tarea y desea ver los otros valores de atributo que están disponibles, debe hacer clic en el botón Desbloquear.  
10. Haga clic en Aceptar
11. Haga clic en Aceptar
12. Expanda la sección Detalles de línea.
13. Haga clic en la ficha Producto.
    * La configuración del artículo se enumera ahora bajo las dimensiones del producto.  
14. Cierre la página.

## <a name="select-the-product-configuration"></a>Seleccione la configuración del producto


