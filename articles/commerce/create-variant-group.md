---
title: Crear un grupo de variantes
description: En este artículo se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
ms.openlocfilehash: 507076259c2d9dfe97a0e24d253b5ac0a8325fe2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270110"
---
# <a name="create-a-variant-group"></a>Crear un grupo de variantes


[!include [banner](includes/banner.md)]

En este artículo se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Dynamics 365 Commerce admite múltiples variantes para productos. Es ideal para configurar grupos de variantes para diferentes categorías de productos. Por ejemplo, se puede crear un grupo de tallas de camisetas, con tallas extra pequeñas, pequeñas, medianas, grandes y extra grandes, o se puede crear un grupo de colores para incluir todos los colores disponibles de un producto. Se deben agregar los grupos de variantes antes de agregar los productos.

En este artículo vamos a crear y configurar un grupo de tamaños. Se pueden usar procedimientos similares para agregar y configurar grupos de estilos y grupos de colores.

## <a name="create-a-size-group"></a>Crear un grupo de tamaños

Para crear un grupo de tamaños, siga estos pasos.
 
1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Grupo de tamaños**, especifique un nombre único para el grupo de tamaños.
1. Especifique una descripción adecuada en el cuadro **Descripción**.
1. En el panel de acciones, seleccione **Guardar**.

## <a name="add-attributes-to-the-size-group"></a>Agregar atributos al grupo de tamaños

Para agregar atributos a un grupo de tamaños, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.
1. En el panel de navegación, seleccione un grupo de tamaños.
1. En **Líneas de grupo de tamaños**, seleccione **Agregar**.
1. En el cuadro **Talla**, especifique una cadena que represente el tamaño (por ejemplo, "XL").
1. En el cuadro **Nombre del tamaño**, escriba un nombre para el tamaño (por ejemplo, "Extra grande").
1. En el cuadro **Peso de reabastecimiento**, escriba un número que represente el peso de reabastecimiento.
1. En el cuadro **Número del código de barras**, escriba un número que represente el código de barras.
1. En el cuadro **Orden de visualización**, escriba un número que represente el orden de visualización.
1. Cuando haya terminado de agregar tamaños, seleccione **Guardar** en el panel de acciones.

La siguiente imagen muestra un ejemplo de grupo de tamaños para "tallas de camisetas informales".

![Crear grupo de tamaños.](media/Size-Groups.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general del producto](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Configurar productos comerciales](set-up-retail-products.md)

[Dimensiones de producto](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
