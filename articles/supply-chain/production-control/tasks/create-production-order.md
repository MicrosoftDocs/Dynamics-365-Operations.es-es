---
title: "Crear un pedido de producción"
description: "Este procedimiento muestra cómo crear un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 4db56f76c7f8ce0cccf85ab04024d9a1e88a8822
ms.contentlocale: es-es
ms.lasthandoff: 02/06/2018

---
# <a name="create-a-production-order"></a>Crear un pedido de producción

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un pedido de producción. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el primer procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="create-a-production-order"></a>Crear un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
2. Haga clic en Nuevo pedido de producción.
3. En el campo Código de artículo, escriba 'D0001'.
4. En el campo Entrega, especifique una fecha.
    * La fecha de entrega indica si el pedido de producción debe completarse para entregarlo a tiempo. Esta fecha se puede usar en el proceso de programación. Por ejemplo, puede programar el pedido hacia atrás a partir de la fecha de entrega.  
5. Establezca el valor de cantidad en '20'.
    * Nota: el campo de número de L. MAT. muestra automáticamente el número de las L. MAT. activa para el artículo actual, pero puede cambiar la L. MAT. para el pedido de producción seleccionando una L. MAT. activa de la lista de versiones de L. MAT. aprobadas.    El campo Número de ruta muestra automáticamente el número de la ruta activa para el artículo actual, pero puede cambiar la ruta del pedido de producción seleccionando una ruta activa de la lista de versiones de ruta aprobadas.  
6. Haga clic en Crear.

## <a name="validate-the-production-order"></a>Validar el pedido de producción
1. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Haga clic en el vínculo para el número de pedido de producción que acaba de crear. Esto permite abrir la página de detalles del pedido.  
2. Haga clic en Editar.
3. En el campo Entrega, especifique una fecha.
    * Por ejemplo, puede cambiar la fecha de entrega para el pedido de producción.  
4. Haga clic en Guardar.
5. Cierre la página.

## <a name="update-the-bom"></a>Actualizar la L. MAT.
1. En el panel de acciones, haga clic en Pedido de producción.
2. Haga clic en L. MAT.
    * Abrir la página L. MAT. para validar los datos de la L. MAT. que se copiaron de los datos predeterminados al crear el pedido de producción. En este procedimiento, es necesario actualizar la cantidad de una L. MAT.  
3. Haga clic en Editar.
4. En el campo Cantidad, especifique un número.
    * Cambiar la cantidad de la línea de L. MAT. afecta a la estimación de coste de consumo de material para el pedido de producción.  
5. Haga clic en Guardar.
6. Cierre la página.

## <a name="update-the-production-route"></a>Actualizar la ruta de producción
1. En el panel de acciones, haga clic en Pedido de producción.
2. Haga clic en Ruta.
    * Abra la página Ruta para validar los datos de la ruta de producción que se copiaron de los datos predeterminados al crear el pedido. En este procedimiento, es necesario actualizar la cantidad de una de las operaciones de la ruta de producción.  
3. En la lista, busque y seleccione el registro deseado.
4. Haga clic en Editar.
5. En el campo Cantidad de proceso, especifique un número.
    * El cambio del tiempo de proceso afecta al consumo de ruta estimado y al coste del pedido de producción.  
6. Haga clic en Guardar.
7. Cierre la página.

