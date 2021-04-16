---
title: Crear un nuevo producto
description: En este tema se describe cómo crear un producto compartido nuevo.
author: ShylaThompson
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d33a13920e1881cdc69ad7c100180d3b3b441d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820043"
---
# <a name="create-a-new-product"></a>Crear un nuevo producto

[!include [banner](../../includes/banner.md)]

En este tema se describe cómo crear un producto compartido nuevo. Normalmente se lleva a cabo por un diseñador de producto. La empresa de datos de prueba utilizada para crear esta tarea es USMF.


## <a name="create-a-product"></a>Crear un producto
1. En el panel de exploración, vaya a **Módulos > Gestión de información de productos > Productos > Productos**.
2. Seleccione **Nuevo**.
3. En el campo **Número de producto**, escriba un valor. Si no se ha configurado una secuencia numérica para el número de producto, debe especificarse manualmente.  
4. En el campo **Nombre de producto**, escriba un valor. El nombre del producto se establece de forma predeterminada como el nombre de búsqueda. Si es necesario, se puede modificar.  
5. Seleccione **Aceptar**.

## <a name="set-up-dimension-groups"></a>Configurar grupos de dimensiones
1. Seleccione **Grupos de dimensiones** para abrir el cuadro de diálogo.
2. En el campo **Grupo de dimensiones de almacenamiento**, especifique o seleccione un valor. El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento debe especificar en cada transacción para el producto y cómo se realizará su seguimiento en el inventario.  
3. En el campo **Grupo de dimensiones de seguimiento**, especifique o seleccione un valor. El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento debe especificar para cada transacción para el producto y cómo se controlará en el inventario.  
4. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]