---
title: "Nomenclatura de los nombres y los números de variante de los productos"
description: "En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo]."
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 6a620f2a0105d578d419d3aac816c7d78fbf3e46
ms.contentlocale: es-es
ms.lasthandoff: 03/08/2018

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Nomenclatura de los nombres y los números de variante de los productos

[!INCLUDE [banner](../includes/banner.md)]

En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo]. La nueva nomenclatura tiene el formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección. También puede crear una nomenclatura para los nombres de producto. Por último, también puede crear una nomenclatura para identificar configuraciones creadas por el configurador de producto basado en restricciones. Estas nomenclaturas pueden contener atributos de su elección.

Las nuevas nomenclaturas para números y nombres de variante de producto permiten incluir segmentos en los identificadores de variantes de producto. Estos segmentos pueden incluir el número y el nombre del producto maestro, identificadores y nombres de dimensiones de producto, secuencias numéricas, constantes de texto y atributos. Esta funcionalidad permite encontrar rápidamente una variante de producto específica al crear un pedido de ventas o un pedido de compra. Puede crear nomenclaturas para números y nombres de variante de producto en la página **Nomenclatura de producto** . Para abrir esta página, haga clic en **Gestión de información de productos** &gt; **Configuración**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura de variantes del producto predefinidas
Las variantes del producto se generan para los productos principales de acuerdo a una de estas tres tecnologías de configuración:

-   Variantes predefinidas
-   Basada en restricciones
-   Basada en dimensiones

Cada variante de producto tiene un número y un nombre, y las nomenclaturas de identificación de variante de producto permite seleccionar los segmentos que se incluirán en cada número o nombre de variante del producto. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:

-   Número de producto maestro
-   Nombre del producto maestro
-   Valor de secuencia numérica
-   Constante de texto
-   Dimensiones de producto
    -   Id. o nombre de configuración
    -   Id. o nombre de color
    -   Id. o nombre de tamaño
    -   Id. o nombre de estilo

Trras definir una nomenclatura de identificación de variante de producto, puede asociarla a un grupo de dimensiones de producto. Se asignará a todos los productos maestros que hagan referencia a este grupo de dimensiones de producto un número de variante de producto de acuerdo con la nomenclatura. Sin embargo, las nomenclaturas de nombre de variante de producto no se pueden asociar a los grupos de dimensiones de producto. También puede asignar directamente una nomenclatura de identificación de variante de producto a un producto maestro. En este caso, se asignarán números y nombres de variante de producto a las variantes de producto que pertenecen al producto maestro, de acuerdo con las nomenclaturas.

### <a name="example"></a>Ejemplo

Una camiseta (TS1234) se genera en tres tamaños (S, M, L), cuatro colores (Rojo, Verde, Azul, Amarillo) y dos estilo (Polo, V). Por lo tanto, hay 24 variantes de producto (= 3 × 4 × 2). Va a crear una nomenclatura de número de variante de producto con los segmentos siguientes:

1.  Número de producto maestro
2.  Constante de texto: "-"
3.  Color
4.  Constante de texto: "-"
5.  Tamaño
6.  Constante de texto: "-"
7.  Estilo

En este caso, el número de variante de producto para una camiseta de tipo polo, talla pequeña y color rojo sería TS1234-Rojo-Pequeña-Polo.

## <a name="nomenclature-of-constraint-based-configurations"></a>Configuraciones de nomenclatura basada en restricciones
Para configuraciones basadas en restricciones puede crear una nomenclatura dedicada para la dimensión de producto de configuración. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:

-   Valor de secuencia numérica
-   Constante de texto
-   Valor de atributo

Cada componente de un modelo de configuración de productos puede tener su propia nomenclatura de configuración. Solo pueden usarse atributos que pertenezcan al componente. No se pueden usar atributos de subcomponentes o de requisitos de usuario.

### <a name="example"></a>Ejemplo

Un modelo de confuguración del producto tiene un componente raíz con dos atributos:

-   Material (Plástico, Madera, Acero)
-   Longitud (10...100)

Va a crear una nomenclatura de configuración con los segmentos siguientes:

1.  Valor de atributo: Material
2.  Constante de texto: "AAA"
3.  Valor de atributo: Longitud

En este caso, el identificador de configuración para el material de madera que tiene una longitud de 78 será MaderaAAA78.

## <a name="nomenclature-of-dimension-based-configurations"></a>Configuraciones de nomenclatura basadas en dimensiones
Para configuraciones basadas en dimensiones puede crear una nomenclatura dedicada para la dimensión de producto de configuración. Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:

-   Valor de secuencia numérica
-   Constante de texto
-   Elemento de grupo de configuración

Puede definir una nomenclatura de configuración para una lista de materiales (L.M.)

### <a name="example"></a>Ejemplo

Una lista de materiales tiene cuatro líneas de L.M. que se dividen en dos grupos de configuración:

-   Línea de L.M.: M0007, Armario estándar
    -   Grupo de configuración: Armario
-   Línea de L.M.: M0008, Armario de gama alta
    -   Grupo de configuración: Armario
-   Línea de L.M.: M0021, Tela en rejilla delantera
    -   Grupo de configuración: Rejilla delantera
-   Línea de L.M.: M0022, Metal en rejilla delantera
    -   Grupo de configuración: Rejilla delantera

Va a crear una nomenclatura de configuración con los segmentos siguientes:

1.  Grupo de configuración: Armario
2.  Constante de texto: "&"
3.  Grupo de configuración: Rejilla delantera

En este caso, el identificador de configuración para un armario estándar con tela en la rejilla delantera será: M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Nomenclatura para una combinación de variantes del producto y configuraciones
Cuando usa la tecnología de configuración basada en restricciones o en dimensiones para configurar las variantes de producto de un producto maestro, los números de variante de producto o las variantes del producto pueden incluir la nomenclatura de la dimensión de configuración. Siga estos pasos para configurar las variantes.

1.  En la página **Nomenclatura de producto**, defina una nomenclatura de número de variante de producto que incluya la dimensión de configuración.
2.  Asigne esta nomenclatura un grupo de dimensiones de producto que tenga la dimensión de configuración.
3.  Defina una nomenclatura de configuración para los componentes o L.M. que se usarán para configurar las variantes de producto.

También puede crear nomenclaturas para los nombres de variante de producto. Los nombres de variante de producto se pueden configurar para incluir el identificador de configuración o el nombre.

### <a name="example-for-constraint-based-configurations"></a>Ejemplo de configuraciones basadas en restricciones

En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:

1.  Número de producto maestro
2.  Constante de texto: "\_"
3.  Configuración

La nomenclatura de configuración consta de los siguientes segmentos:

1.  Valor de atributo: Material
2.  Constante de texto: "AAA"
3.  Valor de atributo: Longitud

Puede especificar los siguientes valores de los segmentos:

-   Número de producto maestro = **M0099**
-   Material = **Plástico**
-   Longitud = **12**

En este caso, el número de la variante del producto se convertirá en: M0099\_PlásticoAAA12.

### <a name="example-for-dimension-based-configurations"></a>Ejemplo de configuraciones basadas en dimensiones

En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:

1.  Número de producto maestro
2.  Constante de texto: "//"
3.  Configuración

La nomenclatura de configuración consta de los siguientes segmentos:

1.  Grupo de configuración: Armario
2.  Constante de texto: "&"
3.  Grupo de configuración: Rejilla delantera

Puede especificar los siguientes valores de los segmentos:

-   Número de producto maestro = **D0123**
-   Armario = **M0008**
-   Rejilla delantera = **M0022**

En este caso, el número de la variante del producto será D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Numeración de conflictos
En algunos casos, es posible configurar una nomenclatura de número de variante de producto que no genere números únicos de variante de producto. Por ejemplo, los números de variante de producto no serán únicos si una dimensión de producto activo no se incluye en la nomenclatura para un producto maestro que utilice la tecnología de configuración de variantes predefinida. La forma de solucionar conflictos variará en función de la tecnología de configuración.

### <a name="predefined-variants"></a>Variantes predefinidas

Se producirá un error si intenta generar variantes de producto manualmente o automáticamente, y más de una variante de producto terminará con el mismo número. Para evitar este escenario, debe utilizar todas las dimensiones de producto activo del grupo de dimensiones de producto. Como alternativa, incluya una secuencia numérica para asegurarse de que los números de variante de producto sean únicos.

### <a name="constraint-based-configurations"></a>Configuraciones basadas en restricciones

En función de la nomenclatura, el sistema puede intentar asignar un número de variante de producto que no es único a una configuración. En este caso, el sistema utilizará la secuencia numérica para la dimensión de configuración como número de variante de producto. ESto generará una advertencia. Para evitar este escenario debe incluir suficientes atributos en la nomenclatura para asegurarse de que se generen números de variante de producto únicos. También debe asegurarse de que la opción **Reutilizar** esté activada para el componente.

### <a name="dimension-based-configurations"></a>Configuraciones basadas en dimensiones

En uno de los pasos del proceso de configuración, el sistema sugiere un valor de configuración según la nomenclatura. En dicho paso, puede cambiar manualmente el valor de la configuración. Cuando guarde la configuración, el sistema comprobará si el valor de configuración es único. Si el valor que ha especificado no es único, recibirá un mensaje de error. Para poder guardar la configuración debe especificar un valor de configuración único.

<a name="see-also"></a>Consulte también
--------

[Crear una nomenclatura del número de producto para las variantes de producto predefinidas](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[Crear una nomenclatura del número de producto para las variantes de producto configuradas](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


