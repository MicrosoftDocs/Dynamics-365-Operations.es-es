--- 
title: "Crear un número de producto para las variantes de producto predefinidas"
description: "Esta guía muestra cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
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
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: f14ee57564ad70bb7f28cd9274fc97d07974ec32
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a>Crear un número de producto para las variantes de producto predefinidas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía muestra cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño. Esta tarea normalmente la realiza un diseñador de productos.


## <a name="create-a-product-number-nomenclature"></a>Crear una nomenclatura de número de producto
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Nomenclatura de producto.
3. Haga clic en Nuevo.
4. En el campo Nombre, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, ColorSize.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Agregar.
7. Haga clic en Número de producto maestro.
8. Haga clic en Agregar.
9. Haga clic en Constante de texto.
10. En el campo Texto, escriba un valor.
11. Haga clic en Agregar.
12. Haga clic en Color.
13. Haga clic en Agregar.
14. Haga clic en Constante de texto.
15. En el campo Texto, escriba un valor.
16. Haga clic en Agregar.
17. Haga clic en Tamaño.
18. Cierre la página.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Asignar la nomenclatura a un producto maestro
1. Haga clic en Grupos de dimensiones de productos.
2. Seleccione el grupo de dimensiones de productos SizeCol.
3. Haga clic en Editar.
4. Seleccione Sí en el campo Usar nomenclatura.
5. En el campo Nomenclatura del número de variante del producto, especifique o seleccione un valor.
6. Cierre la página.


