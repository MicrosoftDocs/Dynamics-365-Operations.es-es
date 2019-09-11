---
title: Visión general de la configuración de producto basada en dimensiones
description: La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales.
author: cvocph
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca7e5555a242c10d2268182ed440e686a1dc46ad
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865361"
---
# <a name="dimension-based-product-configuration-overview"></a>Visión general de la configuración de producto basada en dimensiones

[!include [banner](../includes/banner.md)]

La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales.

La configuración de producto basada en dimensiones es una de las tres tecnologías de configuración de producto integradas. Las otras dos tecnologías son variantes predefinidas y configuración basada en restricciones. Las tres tecnologías usan un producto maestro como punto de partida y permiten al usuario crear muchas variantes del producto para un producto maestro.

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
La secuencia natural para crear un modelo de producto para un producto basado en dimensiones comienza con la definición de los grupos de configuración pertinentes. Es importante garantizar que todos los productos que se usarán en la L. MAT se han liberado a la empresa para la que se crea el modelo de producto. Con estos bloques de creación implementados, el usuario puede crear la L. MAT y asignar grupos de configuración a todas las líneas de L. MAT pertinentes. Cuando se completa la L. MAT, se puede definir una ruta de configuración para solicitar los grupos de configuración en la secuencia adecuada. [![Proceso de modelado de productos basado en dimensiones](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Si hay determinados productos de diferentes grupos de configuración que deben o no deben usarse juntos, puede crear reglas de configuración que se aplicarán a estas relaciones de productos. Después de que la L. MAT. se haya vinculado a un producto maestro basado en dimensiones a través de una versión de L. MAT y se hayan tanto aprobado como activado, puede crear configuraciones de productos y especificar un nombre para cada configuración. Las configuraciones se pueden definir antes de que se genere cualquier transacción o se pueden realizar cuando se produzca la necesidad de una configuración determinada.

### <a name="suggested-use"></a>Uso sugerido

La tecnología de configuración basada en dimensiones se puede usar para productos con variabilidad limitada y la combinación del tamaño de las dimensiones de producto estándar, color, estilo y configuración es inadecuada para identificar una variante del producto específica. Un ejemplo podría ser la bicicleta con el alto del marco de la bicicleta, el tamaño de la rueda, los tipos de freno y las distintas marchas.

### <a name="next-step"></a>Paso siguiente 

Las siguientes ocho guías de taras se muestran en el orden en que debe completarlas. 

1.  [Creación de un producto maestro basado en dimensiones (Guía de tareas)](tasks/create-dimension-based-product-master.md)
2.  [Liberar un producto maestro basado en dimensiones (Guía de tareas)](tasks/release-dimension-based-product-master.md)
3.  [Completar la configuración básica de un producto maestro liberado (Guía de tareas)](tasks/complete-basic-setup-released-product-master.md)
4.  [Definir grupos de configuración (Guía de tareas)](tasks/define-configuration-groups.md)
5.  [Crear una lista de materiales para un producto maestro basado en dimensiones (Guía de tareas)](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [Definir rutas de configuración (Guía de tareas)](tasks/define-configuration-route.md)
7.  [Crear reglas de configuración (Guía de tareas)](tasks/create-configuration-rules.md)
8.  [Crear configuraciones basadas en dimensiones (Guía de tareas)](tasks/create-dimension-based-configurations.md)

