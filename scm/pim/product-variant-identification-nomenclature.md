---
title: "Nomenclatura de número de producto"
description: "Este tema describe cómo puede configurar una nomenclatura del número de producto para reemplazar el formato fijo, [Número de producto maestro: Configuración: Talla: Color: Estilo], con un formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección. También puede crear una nomenclatura para identificar las configuraciones que crea el configurador de producto basado en restricciones. Estas nomenclaturas pueden contener atributos de su elección."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 58afcd62e7ef317e624fd26d198c2606bf53e6a5
ms.lasthandoff: 03/31/2017


---

# <a name="product-number-nomenclature"></a>Nomenclatura de número de producto

[!include[banner](../includes/banner.md)]


Este tema describe cómo puede configurar una nomenclatura del número de producto para reemplazar el formato fijo, [Número de producto maestro: Configuración: Talla: Color: Estilo], con un formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección. También puede crear una nomenclatura para identificar las configuraciones que crea el configurador de producto basado en restricciones. Estas nomenclaturas pueden contener atributos de su elección.

La nueva nomenclatura del número de la variante del producto permite incluir segmentos en sus identificadores de variantes del producto. Estos segmentos pueden incluir el número de producto principal, las dimensiones de producto, las secuencias numéricas, las constantes de texto y los atributos. Dicha función permite encontrar rápidamente una variante del producto específica al crear un pedido de ventas o un pedido de compra.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura de variantes del producto predefinidas
Las variantes del producto se generan para los productos principales de acuerdo a una de estas tres tecnologías de configuración:

-   Variantes predefinidas
-   Basada en restricciones
-   Basada en dimensiones

Cada variante del producto tiene un número y la nomenclatura de identificación de la variante del producto permite seleccionar los segmentos que se incluirán en cada número de variante del producto. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**.

-   Número de producto maestro
-   Valor de secuencia numérica
-   Constante de texto
-   Dimensiones de producto
    -   Configuración
    -   Color
    -   Tamaño
    -   Estilo

Después de que se haya definido una nomenclatura de identificación de la variante del producto, puede asociarse a un grupo de dimensiones de producto. Por lo tanto, a todos los productos principales que hagan referencia a este grupo de dimensión de producto se les asignarán números de variante del producto de acuerdo a la nomenclatura. También se puede asignar una nomenclatura de identificación de la variante del producto directamente a un producto maestro, en este caso las variantes del producto que pertenecen a este maestro se asignarán de acuerdo a la nomenclatura.

### <a name="example"></a>Ejemplo

Una camiseta (TS1234) se fabrica en 3 tallas diferentes (S, M, L), 4 colores distintos (Rojo, Verde, Azul, Amarillo) y 2 estilos (Polo, V) que dan un total de 24 variantes de producto posibles. Una nomenclatura de identificación de la variante del producto se crea con los segmentos siguientes:

1.  Número de producto maestro
2.  Constante de texto: '-'
3.  Color
4.  Constante de texto: '-'
5.  Tamaño
6.  Constante de texto: '-'
7.  Estilo

El número de variante de producto para el Rojo, Pequeño, Polo será: TS1234-Rojo-Pequeño-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Configuraciones de nomenclatura basada en restricciones
Para las configuraciones basadas en restricciones, se puede crear una nomenclatura dedicada para la dimensión del producto de configuración. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**.

-   Valor de secuencia numérica
-   Constante de texto
-   Valor de atributo 

Cada componente de un modelo de configuración de productos puede tener su propia nomenclatura de configuración. Solo pueden usarse los atributos que pertenecen al componente. Los atributos de subcomponentes o de requisitos de usuario no están disponibles.

### <a name="example"></a>Ejemplo

El modelo de confuguración del producto tiene un componente raíz con dos atributos.

-   Material (Plástico, Madera, Acero)
-   Longitud (10...100)

Una nomenclatura de configuración se define mediante los segmentos siguientes:

1.  Valor de atributo: Material
2.  Constante de texto: 'AAA'
3.  Valor de atributo: Longitud

El identificador de configuración para el material de madera con una longitud de 78 obtendrá el identificador de configuración siguiente: MaderaAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Configuraciones de nomenclatura basadas en dimensiones
Para las configuraciones basadas en dimensiones, se puede crear una nomenclatura dedicada para la dimensión del producto de configuración. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**.

-   Valor de secuencia numérica
-   Constante de texto
-   Elemento de grupo de configuración

Se puede definir una nomenclatura de configuración para la lista de materiales (L.M.)

### <a name="example"></a>Ejemplo

Una lista de materiales tiene 4 líneas de L.M. divididas en 2 grupos de configuración.

-   Línea de L.M.: M0007, Armario estándar
    -   Grupo de configuración: Armario
-   Línea de L.M.: M0008, Armario de gama alta
    -   Grupo de configuración: Armario
-   Línea de L.M.: M0021, Tela en rejilla delantera
    -   Grupo de configuración: Rejilla delantera
-   Línea de L.M.: M0022, Metal en rejilla delantera
    -   Grupo de configuración: Rejilla delantera

Una nomenclatura de configuración se define mediante los segmentos siguientes:

1.  Grupo de configuración: Armario
2.  Constante de texto: '&'
3.  Grupo de configuración: Rejilla delantera

El identificador de configuración para un armario estándar con tela en la rejilla delantera será: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nomenclatura de una combinación de variantes del producto y configuraciones
Cuando usa tecnología de configuración basada en restricciones o en dimensiones para configurar las variantes del producto de un producto maestro, las variantes del producto pueden obtener números de la variante del producto que incluyen la nomenclatura de la dimensión de configuración. Siga estos pasos para configurar las variantes:

1.  Definir una nomenclatura del número de la variante del producto que incluye la dimensión de configuración en la página **Nomenclatura de producto**.
2.  Asignar esta nomenclatura un grupo de dimensiones de producto con la dimensión de configuración.
3.  Definir una nomenclatura de la configuración de los componentes o la L.M. que se usará para configurar las variantes de producto.

### <a name="example-for-constraint-based-configurations"></a>Ejemplo de configuraciones basadas en restricciones

En este ejemplo, puede usar una nomenclatura del número de la variante del producto que consta de los segmentos siguientes:

1.  Número de producto maestro
2.  Constante de texto '\_'
3.  Configuración

La nomenclatura de configuración consta de los segmentos siguientes:

1.  Valor de atributo: Material
2.  Constante de texto: 'AAA'
3.  Valor de atributo: Longitud

Puede especificar los siguientes valores de los segmentos:

-   Número de producto maestro = M0099
-   Material = Plástico
-   Longitud = 12

El número de la variante del producto se convertirá en: M0099\_PlásticoAAA12.

### <a name="example-for-dimension-based-configurations"></a>Ejemplo de configuraciones basadas en dimensiones

En este ejemplo, puede usar una nomenclatura del número de la variante del producto que consta de los segmentos siguientes:

1.  Número de producto maestro
2.  Constante de texto '//'
3.  Configuración

La nomenclatura de configuración consta de los segmentos siguientes:

1.  Grupo de configuración: Armario
2.  Constante de texto: '&'
3.  Grupo de configuración: Rejilla delantera

Puede especificar los siguientes valores de los segmentos:

-   Número de producto maestro = D0123
-   Armario = M0008
-   Rejilla delantera = M0022

El número de la variante del producto se convertirá en: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Numeración de conflictos
Es posible configurar la nomenclatura del número de la variante del producto que no se convierte en números únicos de la variante del producto. Por ejemplo, esto puede suceder si una dimensión de producto activo no se incluye en la nomenclatura para un producto maestro que utilice la tecnología de configuración de variantes predefinida. Los conflictos se gestionan de forma distinta para las diferentes tecnologías de configuración.

### <a name="predefined-variants"></a>Variantes predefinidas

Aparecerá un error si intenta generar manual o automáticamente las variantes del producto en el que uno o más terminan con el mismo número de variante del producto. Para evitar esto, debe usar todas las dimensiones de producto activo del grupo de dimensiones de producto, o incluir una secuencia numérica para asegurarse de que los números de la variante del producto son únicos.

### <a name="constraint-based-configurations"></a>Configuraciones basadas en restricciones

En función de la nomenclatura, el sistema puede intentar asignar un número de la variante del producto no único a una configuración. En este caso, el sistema utilizará la secuencia numérica para la dimensión de configuración en lugar del número de la variante del producto. Si esto sucede, recibirá un aviso. Para evitar esto, debe incluir suficientes atributos en la nomenclatura para proteger la singularidad y para asegurarse de que la opción **Reutilización** está activada para el componente.

### <a name="dimension-based-configurations"></a>Configuraciones basadas en dimensiones

El proceso de configuración incluye un paso en el que el sistema sugerirá un valor de configuración según la nomenclatura. En dicho paso, puede cambiar manualmente el valor de la configuración. Cuando guarde la configuración, el sistema comprobará si el valor de configuración es único. En caso contrario, se mostrará un error. Debe especificar un valor de configuración único para guardar la configuración.



<a name="see-also"></a>Consulte también
--------

[Crear una nomenclatura del número de producto para las variantes de producto predefinidas (Guía de tareas)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Crear una nomenclatura del número de producto para las variantes de producto configuradas (Guía de tareas)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)




