--- 
title: "Crear una nomenclatura de números de producto para las variantes de producto predefinidas"
description: "Esta guía muestra cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto predefinidas

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


