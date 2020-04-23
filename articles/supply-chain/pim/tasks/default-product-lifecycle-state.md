---
title: Crear un estado de ciclo de vida de producto predeterminado
description: Este procedimiento muestra cómo crear un estado de ciclo de vida de producto predeterminado además de cómo asociar el estado predeterminado con los productos emitidos.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd346f338a14476960ab47db2e3013402f4c43af
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213179"
---
# <a name="create-a-default-product-lifecycle-state"></a>Crear un estado de ciclo de vida de producto predeterminado

[!include [banner](../../includes/banner.md)]

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

