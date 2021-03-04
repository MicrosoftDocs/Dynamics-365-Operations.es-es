---
title: Crear una nomenclatura de números de producto para las variantes de producto predefinidas
description: Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6871765a450295a3f308ec7e706f1b126071585f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436849"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto predefinidas

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño. Esta tarea normalmente la realiza un diseñador de productos.


## <a name="create-a-product-number-nomenclature"></a>Crear una nomenclatura de número de producto
1. Seleccione **Definición de modelo de variante del producto**.
2. Seleccione **Nomenclatura de producto**.
3. Seleccione **Nuevo**.
4. En el campo **Nombre**, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, `ColorSize`.
5. En el campo **Descripción**, escriba un valor.
6. Seleccione **Agregar**.
7. Seleccione el número de **Producto maestro**.
8. Seleccione **Agregar**.
9. Seleccione **Constante de texto**.
10. En el campo **Texto**, escriba un valor.
11. Seleccione **Agregar**.
12. Seleccione **Color**.
13. Seleccione **Agregar**.
14. Seleccione **Constante de texto**.
15. En el campo **Texto**, escriba un valor.
16. Seleccione **Agregar**.
17. Seleccione **Tamaño**.
18. Cierre la página.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Asignar la nomenclatura a un producto maestro
1. Seleccione **Grupos de dimensiones de producto**.
2. Seleccione el grupo **Dimensiones de productos SizeCol**.
3. Seleccione **Editar**.
4. Seleccione **Sí** en el campo **Usar nomenclatura**.
5. En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.
6. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]