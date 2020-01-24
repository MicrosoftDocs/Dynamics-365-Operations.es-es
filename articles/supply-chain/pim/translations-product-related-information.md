---
title: Preguntas más frecuentes sobre traducciones relacionadas con el producto
description: En este tema se describe cómo administrar las traducciones para los productos, los valores de la dimensión del producto y los atributos del producto.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3d7405af3d0de08cb376164f4ecf59b1d0ef3d4
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934732"
---
# <a name="product-related-translations-faq"></a>Preguntas más frecuentes sobre traducciones relacionadas con el producto

[!include [banner](../includes/banner.md)]

En este tema se describe cómo administrar las traducciones para los productos, los valores de la dimensión del producto y los atributos del producto. 

<a name="what-product-related-data-can-be-translated"></a>¿Qué datos relacionados con el producto se pueden traducir?
--------------------------------------------

Puede crear traducciones para la información relacionada con el producto siguiente:
-   Nombres y descripciones de productos.
-   Descripciones, nombres descriptivos y texto de ayuda de los valores de atributo del producto.
-   Nombres y descripciones de los valores de la dimensión del producto.

Puede traducir la información relacionada con el producto a cualquier idioma disponible de la página **de Traducción de texto**. Para obtener más información, consulte la siguiente sección sobre **“Cómo creo traducciones para la información relacionada con el producto”**.

## <a name="where-can-i-view-the-translated-information"></a>¿Dónde puedo ver la información traducida?
Puede ver las traducciones de la información relacionada con el producto en cualquier documento de origen externo, como una factura, que usa un idioma en el que las traducciones están disponibles.

## <a name="how-do-i-create-translations-for-product-related-information"></a>¿Cómo creo traducciones para la información relacionada con el producto?
Para crear traducciones para un producto, siga estos pasos:
1.  Haga clic en **Gestión de información de productos** &gt; **Común** &gt; **Productos emitidos**.
2.  Seleccione un producto y, en el panel de acciones del grupo **Idiomas** haga clic en **Traducciones**.
3.  En la página **Traducción de texto** del campo de **Idioma** , seleccione un idioma. Para agregar más idiomas, expanda el campo **Idioma** y luego haga clic en **Aceptar**.
4.  En el grupo de **Texto traducido,** introduzca las traducciones en los campos de **Descripción** y **Nombre del producto**.

Para crear traducciones para atributos del producto, siga estos pasos:
1.  Haga clic en **Gestión de información de productos** &gt; **Común** &gt; **Productos emitidos**.
2.  En **Configuración**, haga clic en **Atributos** y, a continuación en **Atributos**.
3.  En la página de **Atributos,** haga clic en **Traducir**.
4.  En la página **Traducción de texto** del campo de **Idioma** , seleccione un idioma. Para agregar más idiomas, expanda el campo **Idioma** y luego haga clic en **Aceptar**.
5.  En el grupo de **Texto traducido,** introduzca las traducciones en los campos de **Descripción**, **Nombre descriptivo** y **Texto de ayuda**.

Para crear traducciones para valores de dimensión del producto, siga estos pasos:
1.  Haga clic en **Gestión de información de productos** &gt; **Común** &gt; **Productos emitidos**.
2.  Seleccione un producto y, a continuación, haga clic en **Dimensiones del producto**.
3.  Seleccione uno de los vínculos para dimensiones de producto: **Configuraciones**, **Tamaños**, **Colores** o **Estilo**.
4.  Seleccione un valor de dimensión y, a continuación, haga clic en **Traducir**.
5.  En la página **Traducción de texto** del campo de **Idioma** , seleccione un idioma. Para agregar más idiomas, expanda el campo **Idioma** y luego haga clic en **Aceptar**.
6.  En el grupo de **Texto traducido**, introduzca las traducciones en los campos de **Nombre** y **Descripción**.

## <a name="can-the-names-of-product-variants-be-translated"></a>¿Se pueden traducir los nombres de las variantes del producto?
Las variantes del producto se basan en las dimensiones de un producto emitido. Los nombres de las variantes del producto se basan en una combinación de valores de la dimensión. Cuando se traducen los valores de dimensión asociados a una variante del producto, el nombre de la variante del producto aparece en la versión traducida.  

**Ejemplo**  

El producto es una camiseta que se encuentra en tamaños y colores distintos y los nombres de las variantes se basan en los siguientes detalles:
-   Número de producto: \#3
-   Dimensiones: tamaño y color
-   Valores de la dimensión de tamaño: pequeño, medio, grande
-   Valores de dimensión de color: rojo, verde, negro

El nombre de una variante del producto que se basa en los valores de dimensión pequeños y rojos es **\#3:Pequeño:Rojo**.  

Un cliente desea comprar algunas camisetas pequeñas, rojas y el nombre de la camiseta debe aparecer en francés en la factura. Se traducen los valores de dimensión, pequeño y rojo, al francés, y el nombre de la variante del producto es **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Sugerencia</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Para configurar el idioma preferido de un cliente, siga estos pasos:
<ol><br/><li>Haga clic en <strong>Ventas y marketing</strong> &gt; <strong>Clientes</strong> &gt; <strong>comunes</strong> &gt; <strong>Todos</strong> <strong>los clientes</strong>.</li>
<li>Haga doble clic en una cuenta de cliente para abrir la página de <strong>Clientes</strong>. En la ficha <strong>General</strong>, en el campo <strong>Idioma</strong>, seleccione el <strong>idioma</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>¿Qué sucede si un cliente tiene un idioma preferido para el que no hay traducciones disponibles?
Si las traducciones no están disponibles en el idioma preferido del cliente, los nombres y las descripciones se muestran en el idioma global de su propia empresa.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>¿Se pueden gestionar las traducciones para una serie de valores de dimensión al mismo tiempo?
Los valores de dimensión son específicos del producto y puede gestionar las traducciones de los valores de dimensión para cada producto. Sin embargo, si crea un grupo de valores de dimensión y crea traducciones para los valores del grupo de valores, resulta más fácil gestionar las traducciones.   

**Ejemplo**  

Su empresa fabrica camisetas de diferentes estilos y cada estilo se encuentra disponible en la talla Pequeña, Mediana y Grande. Los tamaños se recogen en un grupo del valor de dimensión. Cuando se agrega un nuevo estilo de camiseta, puede asociarlo al grupo del valor de dimensión que se usa para tamaños, de modo que todos los tamaños estén disponibles para el producto. También puede agregar o cambiar las traducciones de los tamaños del grupo de valor de dimensión en cualquier momento.  

Un valor de dimensión que está asociado a un producto a través de un grupo de variantes de la dimensión se debe mantener des del grupo de la variante del producto.   
Para crear un grupo de valores de dimensión, siga estos pasos:
1.  Haga clic en **Gestión de información de productos** &gt; **Configuración** &gt; **Grupos de variantes**.
2.  Seleccione **Grupos de** **talla**, **Grupos de color**, o **Grupos de estilo**.
3.  Haga clic en **Nuevo**, a continuación introduzca un nombre para el grupo en el campo de **Grupo** **de talla**, **Grupo de color**, o **Grupo de estilo**. Haga clic en **Tallas**, **Colores**, o **Estilos** para crear líneas para esos grupos.
4.  En la página de **Líneas** **de grupo** de talla, **Líneas** **de grupo** **de color**, o **Líneas de grupo de estilo**, haga clic en **Nuevo** y a continuación cree las tallas, los colores y los estilos para esos grupos.

Para gestionar las traducciones para los valores de un grupo de valores de dimensión, siga estos pasos:
1.  Siga los pasos del procedimiento anterior para crear un grupo de valor de dimensión para abrir la página de las **Líneas de grupo de tallas**, **Líneas de grupo de color** o **Líneas de grupo de estilo**.
2.  Haga clic en **Traducción de texto**. En la página de **Traducción de texto**, en el grupo de **Texto traducido**, introduzca las traducciones en los campos **Nombre** y **Descripción**.

## <a name="when-can-translations-of-product-related-information-be-managed"></a>¿Cuándo se pueden gestionar las traducciones de la información relacionada con el producto?
Las traducciones de la información relacionada con el producto se pueden gestionar en cualquier momento. Cuando las traducciones se actualizan para un valor de dimensión asociado a un producto, la información de productos se actualiza, independientemente de si el producto tiene transacciones.





