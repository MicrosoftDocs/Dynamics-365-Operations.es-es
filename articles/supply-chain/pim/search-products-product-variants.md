---
title: Buscar los productos y variantes de producto durante la entrada de pedidos
description: "Utilice el campo <strong>Número de artículo</strong> para buscar los productos y las variantes del producto cuando cree una línea de pedido de ventas o de pedido de compras manualmente.  Esto le permite buscar rápidamente variantes de producto cuando solo dispone de la cadena de configuración o de una de las dimensiones del producto."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a834cb513d95c0244a29e1f9ec196020698c5983
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>Permite buscar los productos y variantes de producto durante la entrada de pedidos

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]

Utilice el campo <strong>Número de artículo </strong>para buscar los productos y las variantes del producto cuando cree una línea de pedido de ventas o de pedido de compras manualmente.  Esto le permite buscar rápidamente variantes de producto cuando solo dispone de la cadena de configuración o de una de las dimensiones del producto.

A veces, tener demasiado de algo no es lo mejor, y eso se cumple especialmente si vende varios productos que son similares e intenta recordar los números de artículo o los nombres de búsqueda del producto para encontrar el producto correcto para un pedido de ventas. Puede utilizar el campo **Número de artículo** en una línea de pedido de ventas o una línea de pedido de compra como campo de búsqueda. Puede especificar cualquier parte de un nombre de producto, un número o de una dimensión y obtener una búsqueda que muestra todos los artículos que coinciden con la palabra de búsqueda.

## <a name="how-search-works"></a>Funcionamiento de la búsqueda
Al buscar productos o variantes de producto, es importante comprender cómo encuentra la función de búsqueda los productos que coinciden con el texto que escribe. Las reglas de búsqueda principales en la entrega de resultados de búsqueda son:

-   Los resultados de búsqueda devolverán cualquier registro coincidente, sin hacer caso del campo en el que el texto de búsqueda se especifica.
-   Es necesario que el texto de búsqueda esté presente íntegramente en el registro coincidente.
-   Habrá coincidencia incluso si el texto de búsqueda se encuentra en medio de una cadena de texto en el registro coincidente. No tiene que aparecer al principio de una cadena de texto.
-   El texto de la búsqueda se trata como una sola cadena de texto incluso si contiene un espacio en blanco.

### <a name="examples"></a>Ejemplo

Los siguientes ejemplos usan productos y variantes de producto para mostrar cómo se administra la búsqueda en distintas situaciones. **Requisito previo:** En **Ventas y marketing &gt; Configuración &gt; Buscar &gt; Parámetros de búsqueda** &gt; **Tipo de búsqueda**, seleccione la opción **Coincidencia total**.

| Tipo de producto     | Nombre del producto    | Mostrar número de producto | código de artículo | Configuración |
|------------------|-----------------|------------------------|-------------|---------------|
| Producto único | SpeakerMidRange | D0001                  | D0001       | N/D            |
| Variante del producto  | Altavoz activo  | D0010:::Negro:         | D0010       | 000005        |
| Variante del producto  | Altavoz activo  | D0010:::Blanco:         | D0010       | Blanco         |

Si escribe “altavoz” en el campo **Número de artículo**, obtendrá todos los productos que se muestran arriba como consecuencia de la búsqueda. Si escribe “negro” en el campo **Número de artículo**, obtendrá como resultado el segundo producto, ya que tiene el texto “negro” en el número de producto. Estos dos ejemplos muestran que la búsqueda no solo se realiza al principio del campo, habrá coincidencia incluso si el texto de búsqueda se encuentra en el medio de una cadena de texto en el registro coincidente.  

Si escribe "05" obtendrá únicamente la segunda variante del producto como resultado, porque tiene "05" en la configuración. Esto muestra que la búsqueda se realiza entre todos los campos habilitados de la página **Criterios de búsqueda**.  

Si escribe “altavoz 05" no obtendrá ningún resultado. Esto se debe a que la búsqueda busca el texto completo que se introduce. La búsuqeda no intentará encontrar “altavoz” y después reducirá los resultados a aquellos que contienen "05".  

Puede limitar el número de resultados de búsqueda mediante el campo **Número de resultados** en la página **Ventas y marketing &gt; Configuración &gt; Búsqueda &gt; Parámetros de búsqueda**. Si establece este campo en 0, se incluirán todos los resultados de la búsqueda. Si lo establece en 10, por ejemplo, incluirá un máximo de 10 resultados.

## <a name="configure-the-product-search"></a>Configurar la búsqueda de producto
Para poder usar la función de búsqueda del producto y de la variante del producto, siga estos pasos para configurar la búsqueda de producto. [![3 pasos para configurar la búsqueda de productos\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>Paso 1: Incluir todos los identificadores del producto y de la variante del producto, y las dimensiones relevantes en los criterios de búsqueda

Algunos ejemplos de identificadores de producto y de la variante del producto y de las dimensiones por las que puede buscar son **Nombre de producto, número de artículo**,**Ver número de producto, Configuración, Color, Tamaño, Estilo, Nombre de búsuqeda, etc**.  

Vaya a la página **Ventas y marketing &gt; Configuración &gt; Buscar &gt; Criterios de búsqueda**. La página **Criterios de búsqueda** le permite definir los criterios para el cliente, el cliente potencial y la búsqueda de producto. Asegúrese de filtrar la página mediante el uso de criterios de búsqueda del producto. Puede hacerlo cambiando a **Producto** en el menú de la página.  

Para agregar el número de producto a los criterios de búsqueda, haga clic en **Nuevo** en el menú de la página. Esto añadirá un nuevo registro en la cuadrícula **Criterios de búsqueda**. Abra la búsqueda de la columna **Nombre de campo** y elija **DisplayProductNumber**. Para añadir la configuración del producto a los criterios de búsqueda, cree un nuevo registro en la cuadrícula **Criterios de búsqueda** y elija **configId** en la columna **Nombre de campo**. De la misma manera, cree un registro con **Nombre de campo** **InventColorId** para la dimensión de color, **InventSizeId** para la dimensión de tamaño y **InventStyleId** para la dimensión del estilo.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>Paso 2: Rellene la tabla de la base de datos usada para la búsqueda de producto

En la página **Criterios de búsqueda**, haga clic en el botón **Actualizar datos de búsqueda**. En el cuadro de diálogo **Actualizar datos de búsqueda**, asegúrese de que **Origen** esté establecido en **Producto**, y haga clic en **Aceptar**. El sistema agregará en una tabla todos los criterios de búsqueda seleccionados especificados en el paso 1. Si tiene muchos productos y variantes de producto, esta operación puede ser bastante larga y puede que reciba un aviso. Se recomienda que programe el rellenado de la tabla de búsqueda en el servidor por lotes en un momento en el que el servidor no esté muy ocupado.  

Hasta que se haya rellenado la tabla, la búsqueda de producto no proporcionará los resultados correctos. Si no obtiene ningún resultado de búsqueda, asegúrese de que la tabla se ha rellenado.  

La tabla solo tiene que rellenarse cuando se modifican los criterios de búsqueda. Los productos y variantes emitidos nuevamente se añaden a la tabla automáticamente. Los productos y variantes eliminados se quitan de la tabla automáticamente.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>Paso 3: Habilite la búsqueda para los productos en líneas de pedidos de ventas y de compras

Puede habilitar esta función en **Ventas y marketing &gt; Configuración &gt; Búsqueda &gt; Parámetros de búsqueda** y configurando **Habilitar búsqueda** a **Sí** en la pestaña **General**.  

Para la entrada de la línea de pedido de ventas, el comportamiento predeterminado es abrir la página **Búsqueda de producto** cuando empieza a escribir en el campo **Número de artículo**y, a continuación pulsar la tecla **Ficha**. La página **Búsqueda de producto** cambia el contexto durante la creación de la línea de pedido y se puede considerar demasiado intrusiva. Si prefiere obtener los resultados de la búsqueda en una búsqueda y no perder contexto durante la entrada de la línea de pedido, puede usar la consulta de la búsqueda en su lugar. Si busca un producto o una variante del producto, pero no selecciona nada en la búsqueda y pulsa la tecla **Ficha**, se mostrará la página **Búsqueda de producto**.




