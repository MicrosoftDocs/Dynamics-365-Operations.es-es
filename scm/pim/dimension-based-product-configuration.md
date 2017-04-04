---
title: "Configuración de producto basada en dimensiones"
description: "La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7fbf69dc217a2f61ec3aeda952ff221491e9385a
ms.lasthandoff: 03/31/2017


---

# <a name="dimension-based-product-configuration"></a>Configuración de producto basada en dimensiones

La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales.

la configuración de productos Dimensión-basada es una de las tres tecnologías integradas de la configuración de productos. Las otras dos tecnologías son variantes predefinidas y configuración basada en restricciones. Las tres tecnologías usan un producto maestro como punto de partida y permiten al usuario crear muchas variantes del producto para un producto maestro.

## <a name="key-concepts"></a>Conceptos clave
La configuración de producto basada en dimensiones se basa en los siguientes conceptos clave:

-   Productos maestros
-   Dimensión del producto de configuración
-   Grupos de configuración
-   Lista de materiales (L. MAT)
-   Ruta de configuración
-   Reglas de configuración

### <a name="product-masters"></a>Productos maestros

Un producto maestro es el punto de partida para cualquier proceso de configuración de producto. Para la configuración de producto basada en dimensiones, necesita un producto maestro con esta tecnología de configuración concreto y un grupo de dimensiones de producto que incluye la dimensión del producto de configuración.

### <a name="configuration-product-dimension"></a>Dimensión del producto de configuración

La dimensión del producto de configuración se usa para identificar las variantes del producto para un producto maestro con la tecnología de configuración basada en dimensiones. El usuario especifica el valor de dimensión de configuración y debe ayudar a identificar las variantes de producto individuales.

### <a name="configuration-groups"></a>Grupos de configuración

Los grupos de configuración se definen en un repositorio central y se pueden usar para todos los modelos de configuración de productos basada en dimensiones. Los grupos de configuración se asocian a las líneas de L. MAT individuales y mantienen unidas un grupo de líneas que son mutuamente exclusivas. Esto significa que solo se puede seleccionar una línea de un grupo para una única variante del producto.

### <a name="bill-of-materials-bom"></a>Lista de materiales (L. MAT)

La L. MAT representa los bloques de creación para una configuración de producto basada en dimensiones. Debe incluir todos los productos diferentes que se pueden usar en cualquier variante del producto. Cada línea de la L. MAT. puede hacer referencia a un grupo de configuración. Si una línea no hace referencia a un grupo de configuración, se incluirá en todas las variantes del producto.

### <a name="configuration-route"></a>Ruta de configuración

La ruta de configuración determina la secuencia de los grupos de configuración, como se mostrarán al usuario durante el proceso de configuración de producto.

### <a name="configuration-rules"></a>Reglas de configuración

Las reglas de configuración representan un mecanismo para garantizar que un producto incluido en un grupo de configuración de una L. MAT fuerza una inclusión o una exclusión de un producto en un grupo de configuración diferente en la misma L. MAT.

## <a name="product-modeling-process"></a>Proceso de modelos del producto
La secuencia natural para crear un modelo de producto para un producto basado en dimensiones comienza con la definición de los grupos de configuración pertinentes. Es importante garantizar que todos los productos que se usarán en la L. MAT se han liberado a la empresa para la que se crea el modelo de producto. Con estos bloques de creación en el lugar, el usuario puede crear la L y los grupos de configuración a todas las líneas pertinentes de L. MAT Una vez finalizada la lista de materiales, una ruta de configuración se puede definir para pedir grupos de configuración en la secuencia correspondiente. \_datos adjuntos de 282671 " id= de\[" width= " axtable= " alignnone de align=” 1187 "\][proceso Dimensión- basado![de modelo de producto (]. /media/dimension-based-product-modeling-process-v1.png])(. proceso Dimensión- basado\[/caption\] si hay determinados productos de grupos de configuración diferentes que debe o no debe para usarse junto, se de modelo de producto de /media/dimension-based-product-modeling-process-v1.png) puede crear reglas de configuración que se aplicarán estas relaciones de productos. Después de que la L. MAT. se haya vinculado a un producto maestro basado en dimensiones a través de una versión de L. MAT y se hayan tanto aprobado como activado, puede crear configuraciones de productos y especificar un nombre para cada configuración. Las configuraciones se pueden definir antes de que se genere cualquier transacción o se pueden realizar cuando se produzca la necesidad de una configuración determinada.

### <a name="suggested-use"></a>Uso sugerido

La tecnología de configuración basada en dimensiones se puede usar para productos con variabilidad limitada y la combinación del tamaño de las dimensiones de producto estándar, color, estilo y configuración es inadecuada para identificar una variante del producto específica. Un ejemplo podría ser la bicicleta con el alto del marco de la bicicleta, el tamaño de la rueda, los tipos de freno y las distintas marchas.


