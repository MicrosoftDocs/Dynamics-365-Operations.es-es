--- 
title: Crear un nuevo producto
description: "Esta tarea muestra cómo crear un nuevo producto compartido."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 56ce5d965952d0cb41278915e4631ae9d920f5f9
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-product"></a>Crear un nuevo producto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea muestra cómo crear un nuevo producto compartido. Normalmente se lleva a cabo por un diseñador de producto. La empresa de datos de prueba utilizada para crear esta tarea es USMF.

1. Vaya a Gestión de información de productos > Productos > Productos.

## <a name="create-a-product"></a>Crear un producto
1. Haga clic en Nuevo.
2. En el campo Número de producto, escriba un valor.
    * Si no se ha configurado una secuencia numérica para el número de producto, debe especificarse manualmente.  
3. En el campo Nombre de producto, escriba un valor.
    * El nombre del producto se establece de forma predeterminada como el nombre de búsqueda. Si es necesario, se puede modificar.  
4. Haga clic en Aceptar

## <a name="set-up-dimension-groups"></a>Configurar grupos de dimensiones
1. Haga clic en Grupos de dimensiones para abrir el cuadro de diálogo.
2. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
    * El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento debe especificar en cada transacción para el producto y cómo se realizará su seguimiento en el inventario.  
3. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
    * El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento debe especificar para cada transacción para el producto y cómo se controlará en el inventario.  
4. Haga clic en Aceptar


