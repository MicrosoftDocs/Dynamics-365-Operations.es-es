---
title: Crear una nomenclatura de números de producto para las variantes de producto predefinidas
description: Este artículo explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887323"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto predefinidas

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño. Esta tarea normalmente la realiza un diseñador de productos.


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