---
title: Crear una nomenclatura de números de producto para las variantes de producto predefinidas
description: Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920666"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto predefinidas

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño. Esta tarea normalmente la realiza un diseñador de productos.


## <a name="create-a-product-number-nomenclature"></a>Crear una nomenclatura de número de producto

1. Vaya a **Gestión de información de productos \> Configuración \> Nomenclatura de productos**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre**, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, `ColorSize`.
1. En el campo **Descripción**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione el número de **Producto maestro**.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Color**.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Tamaño**.
1. Cierre la página.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Asignar la nomenclatura a un producto maestro

1. Seleccione **Grupos de dimensiones de producto**.
2. Seleccione el grupo **Dimensiones de productos SizeCol**.
3. Seleccione **Editar**.
4. Seleccione **Sí** en el campo **Usar nomenclatura**.
5. En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.
6. Cierre la página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]