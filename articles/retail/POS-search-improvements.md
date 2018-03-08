---
title: "Búsqueda de productos y clientes en el sistema PDV"
description: "En este tema se proporciona una visión general de las mejoras que se han realizado en la funcionalidad de búsqueda de productos y clientes en Dynamics 365 for Retail."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 5f6f9a02b20549a75941d367c1b46e3439360078
ms.contentlocale: es-es
ms.lasthandoff: 01/19/2018

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Información general de la búsqueda de productos y clientes en un punto de venta

[!include[banner](includes/banner.md)]

El punto de venta moderno (MPDV) y el punto de venta (CPDV) en la nube proporcionan funcionalidades de búsqueda fáciles de usar que permiten que los empleados de las tiendas busquen rápidamente los productos y clientes que necesiten. La barra de búsqueda siempre se muestra en la parte superior del MPDV y el CPDV, de modo que los empleados pueden buscar rápidamente productos y clientes.

Los empleados pueden buscar productos en los surtidos y los catálogos asociados a su propia tienda, y en los surtidos y catálogos asociados a otra tienda de la empresa. Así pues, los cajeros pueden vender y devolver productos que estén fuera del surtido de su tienda. Del mismo modo, los empleados pueden buscar clientes que estén asociados con la tienda actual o con cualquier otra tienda de la empresa. Además, los empleados pueden buscar clientes que estén relacionados con diferentes empresas de la organización principal.

## <a name="product-search"></a>Búsqueda de productos 

De forma predeterminada, una búsqueda de producto se realiza en el surtido de la tienda. Este tipo de búsqueda se conoce como *búsqueda de producto local*. Sin embargo, los empleados pueden cambiar fácilmente a los catálogos que están asociados a la tienda actual o bien, pueden realizar la búsqueda en otra tienda diferente. Este tipo de búsqueda se conoce como *búsqueda de producto remota*. Para cambiar el catálogo, seleccione el botón **Categorías** en el lado izquierdo de la página. En la parte superior del panel, seleccione el botón **Cambiar catálogo** y, a continuación, seleccione uno de los catálogos disponibles para examinarlo. El sistema buscará el catálogo de productos seleccionado.

En la página **Cambiar catálogo**, los empleados pueden seleccionar cualquier forma de manera sencilla, o pueden buscar productos en todas las tiendas.

![Cambiar el catálogo](./media/Changecatalog.png "Cambiar el catálogo")
 
Si realiza una búsqueda local de un producto, el sistema buscará según las siguientes propiedades de producto:

- Código de producto
- Nombre del producto
- Descripción
- Dimensiones
- Código de barras
- Nombre de búsqueda

### <a name="enhancements-to-local-product-searches"></a>Mejoras en las búsquedas de producto locales

La experiencia de la búsqueda de producto local es más sencilla. Se realizaron las mejoras siguientes:

- Los menús desplegables de productos y clientes se han agregado a la barra de búsqueda, de modo que los empleados pueden seleccionar **Producto** o **Cliente** antes de realizar la búsqueda. De forma predeterminada, se selecciona **Producto** tal y como se muestra en la siguiente ilustración.
- Si va a realizar una búsqueda con varias palabras clave (esto es, una búsqueda que usa términos de búsqueda), los distribuidores pueden configurar los resultados de búsqueda para que incluyan opciones que coincidan con cualquier término de búsqueda o todos los términos de búsqueda. Esta configuración está disponible en el perfil de funcionalidad de PDV, en un nuevo grupo denominado **Búsqueda de producto**. La configuración predeterminada es **Coincidencias con cualquier término de búsqueda**. Le recomendamos que use esta configuración. Cuando use la configuración **Coincidencias con cualquier término de búsqueda**, todos aquellos productos que coincidan parcialmente con uno o varios términos de búsqueda vuelven como resultados, y esos resultados se ordenan automáticamente por orden ascendente de productos que tengan la mayoría de palabras clave (parciales o completas).

    La configuración **Coincidencias con todos los términos de búsqueda** sólo devuelve aquellos productos que coincidan con todos los términos de búsqueda (parcial o completa). Esta opción resulta útil cuando los nombres de producto son muy largos y los empleados solo quieren encontrar ciertos productos en los resultados de búsqueda. Sin embargo, este tipo de búsqueda tiene dos limitaciones:

    - La búsqueda se realiza en propiedades de producto individuales. Por ejemplo, solo se devuelven productos que tengan todas las palabras clave buscadas en al menos una propiedad del producto.
    - No se busca en las dimensiones.

- Ahora los distribuidores pueden configurar la búsqueda de productos para que se muestren sugerencias a medida que el usuario escribe el nombre del producto. Esta nueva configuración para esta funcionalidad está disponible en el perfil de funcionalidades de PDV, en un nuevo grupo denominado **Búsqueda de producto**. Esta configuración se llama **Mostrar las sugerencias de búsqueda mientras se escribe**. Esta función puede ayudar a sus empleados a buscar rápidamente el producto que quieran, ya que no tienen que escribir todo el nombre de forma manual.
- El algoritmo de búsqueda de productos también busca términos en la propiedad de producto **Nombre de búsqueda**.

![Sugerencias de producto](./media/Productsuggestions.png "Sugerencias de producto")

## <a name="customer-search"></a>Búsqueda de clientes

La búsqueda de clientes se utiliza para buscar clientes para distintos fines. Por ejemplo, es posible que los cajeros quieran ver la lista de solicitudes o el historial de compra de algún cliente o agregar al cliente a alguna transacción. En el caso de búsquedas con varias palabras clave, el algoritmo de búsqueda de clientes devuelve todos aquellos clientes que coincidan con cualquiera de las palabras clave introducidas. Sin embargo, los clientes que coinciden con la mayoría de las palabras clave aparecen en la parte superior de los resultados. Este comportamiento es análogo al modo que otros motores de búsqueda muestran los resultados. Primero muestran los resultados que coincidan con los términos más buscados y, a continuación, muestran los resultados que coincidan parcialmente con las palabras clave de la búsqueda. Este comportamiento es útil si los cajeros usan varias palabras clave en su búsqueda, pero una de las palabras tiene un error de ortografía.

De forma predeterminada, una búsqueda de clientes se realiza en los libros de direcciones de cliente que están asociados a la tienda. Este tipo de búsqueda se conoce como *búsqueda de cliente local*. Asimismo, los empleados también pueden buscar clientes de manera global. Es decir, pueden buscar en las tiendas de la empresa y a través de las demás entidades jurídicas. Este tipo de búsqueda se conoce como *búsqueda de cliente remota*.

Para realizar búsquedas globales, los empleados pueden seleccionar el botón **Filtrar resultados** en la parte inferior de la página y seleccionar la opción **Buscar en todas las tiendas**, tal y como se muestra en la siguiente ilustración. En este caso, no sólo se devuelven los clientes. También se muestran todos los tipos de grupos que forman parte de la libreta de direcciones de la sede central. Entre estos grupos podemos encontrar trabajadores, proveedores, contactos y competidores.

> [!NOTE]
> Debe escribir un mínimo de cuatro caracteres para que la búsqueda de cliente remota devuelva algún resultado.

En una búsqueda de cliente remota, no se muestra el id. del cliente si este forma parte de otras entidades jurídicas, ya que no se creó ningún identificador de cliente para dichos grupos en la empresa actual. Sin embargo, si un empleado abre la página de detalles del cliente, el sistema genera automáticamente un identificador de cliente para el grupo y también lo asocia a las libretas de direcciones de clientes de la tienda. Por lo tanto, el cliente será visible en las búsquedas de tienda locales que se hagan posteriormente.

![Búsqueda global de cliente](./media/Globalcustomersearch.png "Búsqueda global de cliente")

### <a name="enhancements-to-local-customer-searches"></a>Mejoras en las búsquedas de cliente locales

Gracias a las búsquedas de cliente locales los empleados pueden encontrar rápidamente al cliente según su número de teléfono. Los empleados no tienen que escribir ningún carácter especial que se haya agregado al número de teléfono del cliente como por ejemplo, espacios, guiones o paréntesis. Aunque los cajeros pueden almacenar los números de teléfono en cualquier formato (por ejemplo, pueden incluir paréntesis, guiones, símbolos, etc.) pueden buscar al cliente en cuestión escribiendo el número de teléfono de forma parcial. Si un cajero incluía caracteres especiales cuando guardaba teléfonos, otros cajeros podrán encontrar al cliente escribiendo los números que aparecen tras esos caracteres especiales. Por ejemplo, si un número de teléfono de cliente se escribió como **123-456-7890**, un cajero puede buscar el cliente escribiendo **123**, **456**, **7890** o **1234567890** o simplemente escribiendo de forma parcial los primeros números del teléfono.

