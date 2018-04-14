--- 
title: Asignar un estado del ciclo de vida del producto a un producto maestro
description: "Este procedimiento muestra cómo asignar un estado de ciclo de vida de producto a un producto maestro liberado y sus variantes."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: f476c1b2585ce0b5b67cd0d91684c86f7d3bda36
ms.contentlocale: es-es
ms.lasthandoff: 02/08/2018

---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Asignar un estado del ciclo de vida del producto a un producto maestro

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo asignar un estado de ciclo de vida de producto a un producto maestro liberado y sus variantes. Requisito previo: Necesita reproducir primero la guía de tareas “Crear un nuevo estado de ciclo de vida de producto” para asegurarse de que al menos tiene un estado de ciclo de vida del producto antes de reproducir esta guía de tareas.


## <a name="find-a-released-product-master"></a>Buscar un producto maestro liberado
1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, busque y seleccione el registro deseado.

> [!NOTE]
> Un producto maestro tiene el producto maestro del subtipo producto.  

## <a name="update-the-lifecycle-state"></a>Actualice el estado del ciclo de vida
1. Haga clic en Editar.
2. En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.
3. Haga clic en Guardar.
4. Haga clic en Sí.

> [!NOTE]
> Si se selecciona Sí, todas las variantes del producto liberado relacionado con el mismo estado original que el producto maestro liberado también se actualizan al nuevo estado de ciclo de vida de producto. Si se selecciona No, todas las variantes conservan su estado real. Las variantes cuyo estado del ciclo de vida de producto es diferente al del producto maestro liberado no se actualizan.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Compruebe el estado del ciclo de vida de las variantes
1. Haga clic en Variantes del producto emitidas.

> [!NOTE]
> Tenga en cuenta que todas las variantes han heredado el estado de ciclo de vida seleccionado del producto maestro.  

2. En la lista, marque la fila seleccionada.
3. En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.


