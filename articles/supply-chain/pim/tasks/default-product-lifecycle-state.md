--- 
title: Crear un estado de ciclo de vida de producto predeterminado
description: "Este procedimiento muestra cómo crear un estado de ciclo de vida de producto predeterminado además de cómo asociar el estado predeterminado con los productos emitidos."
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
ms.openlocfilehash: 06a6c7c8fa767edf6fdf50c3c971b6d767f8755f
ms.contentlocale: es-es
ms.lasthandoff: 02/08/2018

---
# <a name="create-a-default-product-lifecycle-state"></a>Crear un estado de ciclo de vida de producto predeterminado

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un estado de ciclo de vida de producto predeterminado además de cómo asociar el estado predeterminado con los productos emitidos.


## <a name="create-a-default-lifecycle-state"></a>Crear un estado de ciclo de vida predeterminado
1. Vaya a Gestión de información de productos > Configuración > Estado de ciclo de vida de producto.
2. Haga clic en Nuevo.
3. En el campo Estado, escriba un valor.
4. Seleccione Sí en el campo Predeterminado cuando se libera a entidad jurídica.
5. En el campo Descripción, escriba un valor.
6. Seleccione No en el campo Es activo para planificación.

> [!NOTE]
> Si no debe incluirse un nuevo producto liberado en la planificación maestra, seleccione No. Si debe incluirse en la planificación maestra, deje el control en el valor predeterminado Sí.  

## <a name="create-a-new-released-product"></a>Crear un nuevo producto liberado
1. Cierre la página.
2. Vaya a Gestión de información de productos > Productos > Productos emitidos.
3. Haga clic en Nuevo.
4. En el campo Número de producto, escriba un valor.
5. En el campo Nombre de producto, escriba un valor.
6. En el campo Nombre de búsqueda, introduzca un valor.
7. En el campo Grupo de modelos de artículo, especifique o seleccione un valor.
8. En el campo Grupo de artículos, especifique o seleccione un valor.
9. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
10. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
11. Haga clic en Aceptar

> [!NOTE]
> El estado del ciclo de vida del producto predeterminado es una definición global.  

## <a name="change-the-product-to-an-active-state"></a>Cambiar el producto a un estado activo
1. En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.

> [!NOTE]
> Supongamos que ha configurado un estado activo, ahora puede seleccionar el estado activo para permitir que el producto se use en el cálculo de la planificación maestra y del nivel de L.MAT. Obviamente, esto solo tiene sentido si se especifican todos los detalles del producto que se necesitan para una planificación coherente.  


