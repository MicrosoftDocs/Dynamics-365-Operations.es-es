---
title: Búsqueda de productos y de clientes en el punto de venta (PDV)
description: En este tema se proporciona una visión general de las mejoras que se han realizado en la funcionalidad de búsqueda de productos y clientes en Microsoft Dynamics 365 for Retail.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: b2f1d522a60721c746d03e477615265f9a8ba9a0
ms.sourcegitcommit: 3d8c951898e05febc160515127c1bcc5de5882a1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "1625651"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Búsqueda de productos y de clientes en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

El punto de venta moderno (MPDV) y el punto de venta (CPDV) en cloud proporcionan funcionalidades de búsqueda fáciles de usar para los productos y clientes. Gracias a que la barra de búsqueda siempre se muestra en la parte superior de las ventanas de MPDV y el CPDV, los empleados pueden buscar rápidamente productos y clientes.

Los empleados pueden buscar los productos en los surtidos y catálogos que están asociados a la tienda actual. También pueden buscar en los surtidos y catálogos que están asociados a la cualquier otra tienda de la empresa. Así pues, los cajeros pueden vender y devolver productos que estén fuera del surtido de su tienda. Del mismo modo, los empleados pueden buscar clientes que estén asociados con la tienda actual o con cualquier otra tienda de la empresa. Además, los empleados pueden buscar clientes que estén relacionados con diferentes empresas de la organización principal.

## <a name="product-search"></a>Búsqueda de productos

De forma predeterminada, las búsquedas de producto se realizan en el surtido de la tienda. Este tipo de búsqueda se conoce como *búsqueda de producto local*. Sin embargo, los empleados pueden cambiar fácilmente a los catálogos que están asociados a la tienda actual o bien, pueden realizar la búsqueda en otra tienda diferente. Este tipo de búsqueda se conoce como *búsqueda de producto remota*. Para cambiar el catálogo, seleccione el botón **Categorías** en el lado izquierdo de la página. En la parte superior del panel, seleccione el botón **Cambiar catálogo** y, a continuación, seleccione uno de los catálogos disponibles para examinarlo. El sistema buscará el catálogo de productos seleccionado.

En la página **Cambiar catálogo**, los empleados pueden seleccionar cualquier forma de manera sencilla, o pueden buscar productos en todas las tiendas.

![Cambiar el catálogo](./media/Changecatalog.png "Cambiar el catálogo")

Una búsqueda de producto local realiza búsquedas en las siguientes propiedades de producto:

- Código de producto
- Nombre del producto
- Descripción
- Dimensiones
- Código de barras
- Nombre de búsqueda

### <a name="enhancements-to-local-product-searches"></a>Mejoras en las búsquedas de producto locales

La experiencia de la búsqueda de producto local es ahora más sencilla. Se realizaron las mejoras siguientes:

- Los menús desplegables de productos y clientes se han agregado a la barra de búsqueda, de modo que los empleados pueden seleccionar **Producto** o **Cliente** antes de realizar la búsqueda. De forma predeterminada, se selecciona **Producto** tal y como se muestra en la siguiente ilustración.
- Si va a realizar una búsqueda con varias palabras clave (esto es, una búsqueda que usa términos de búsqueda), los distribuidores pueden configurar los resultados de búsqueda para que incluyan opciones que coincidan con *cualquier* término de búsqueda o *todos* los términos de búsqueda. La configuración para esta funcionalidad está disponible en el perfil de funcionalidades de PDV, en un nuevo grupo denominado **Búsqueda de producto**. La configuración predeterminada es **Coincidencias con cualquier término de búsqueda**. Le recomendamos que use esta configuración. Cuando se usa la configuración **Coincidir con cualquier término de búsqueda**, todos los productos que coinciden total o parcialmente con uno o varios términos de búsqueda se devuelven como resultados. Esos resultados se ordenan automáticamente en orden ascendente de productos que tienen la mayoría de las coincidencias de la palabra clave (parcial o completa).

    La configuración **Coincidencias con todos los términos de búsqueda** sólo devuelve aquellos productos que coincidan con todos los términos de búsqueda (parcial o completa). Esta opción resulta útil cuando los nombres de producto son muy largos y los empleados solo quieren encontrar ciertos productos en los resultados de búsqueda. Sin embargo, este tipo de búsqueda tiene dos limitaciones:

    - La búsqueda se realiza en propiedades de producto individuales. Por ejemplo, solo se devuelven productos que tengan todas las palabras clave buscadas en al menos una propiedad del producto.
    - No se busca en las dimensiones.

- Ahora los distribuidores pueden configurar la búsqueda de productos para que se muestren sugerencias a medida que el usuario escribe el nombre del producto. Una nueva configuración para esta funcionalidad está disponible en el perfil de funcionalidades de PDV, en un grupo denominado **Búsqueda de producto**. Esta configuración se llama **Mostrar las sugerencias de búsqueda mientras se escribe**. Esta función puede ayudar a sus empleados a buscar rápidamente el producto que quieran, ya que no tienen que escribir todo el nombre de forma manual.
- El algoritmo de búsqueda de productos también busca términos en la propiedad de producto **Nombre de búsqueda**.

![Sugerencias de producto](./media/Productsuggestions.png "Sugerencias de producto")

## <a name="customer-search"></a>Búsqueda de clientes

La búsqueda de clientes se utiliza para buscar clientes para distintos fines. Por ejemplo, es posible que los cajeros quieran ver la lista de solicitudes o el historial de compra de algún cliente o agregar al cliente a alguna transacción. El algoritmo de búsqueda coincide con los términos de búsqueda con los valores que están presentes en las siguientes propiedades del cliente:

- Nombre
- Dirección de correo electrónico
- Número de teléfono
- Número de tarjeta de fidelización
- Dirección
- Número de cuenta

Entre estas propiedades, el nombre proporciona la mayor flexibilidad para búsquedas de múltiples palabras clave, ya que el algoritmo devuelve todos los clientes que coincidan con cualquiera de las palabras clave buscadas. Los clientes que coinciden con la mayoría de las palabras clave aparecen en la parte superior de los resultados. Este comportamiento ayuda a los cajeros en situaciones en las que buscan escribiendo el nombre completo, pero el apellido y el nombre fueron intercambiados durante la entrada de datos inicial. Sin embargo, por motivos de rendimiento, el resto de propiedades conservan el orden de las palabras clave de la búsqueda. Por lo tanto, si el orden de las palabras clave de la búsqueda no coincide con el orden en el que se almacenan los datos, no se mostrará ningún resultado.

De forma predeterminada, una búsqueda de clientes se realiza en los libros de direcciones de cliente que están asociados a la tienda. Este tipo de búsqueda se conoce como *búsqueda de cliente local*. Asimismo, los empleados también pueden buscar clientes de manera global. Es decir, pueden buscar en las tiendas de la empresa y a través de las demás entidades jurídicas. Este tipo de búsqueda se conoce como *búsqueda de cliente remota*.

Para realizar búsquedas globales, los empleados pueden seleccionar el botón **Filtrar resultados** en la parte inferior de la página y seleccionar la opción **Buscar en todas las tiendas**, tal y como se muestra en la siguiente ilustración. En este caso, no sólo se devuelven los clientes. También se muestran todos los tipos de grupos que forman parte de la libreta de direcciones de la sede central. Entre estos grupos podemos encontrar trabajadores, proveedores, contactos y competidores.

> [!NOTE]
> Debe escribir un mínimo de cuatro caracteres para que la búsqueda de cliente remota devuelva algún resultado.

En una búsqueda de cliente remota, no se muestra el id. del cliente si este forma parte de otras entidades jurídicas, ya que no se creó ningún identificador de cliente para dichos grupos en la empresa actual. Sin embargo, si un empleado abre la página de detalles del cliente, el sistema genera automáticamente un identificador de cliente para el grupo y también lo asocia a las libretas de direcciones de clientes de la tienda. Por lo tanto, el cliente será visible en las búsquedas de tienda locales que se hagan posteriormente.

![Búsqueda global de cliente](./media/Globalcustomersearch.png "Búsqueda global de cliente")

### <a name="enhancements-to-local-customer-search"></a>Mejoras en la búsqueda de cliente locales

Se han simplificado las búsquedas que se basan en el número de teléfono. Estas búsquedas ahora omiten caracteres especiales, como espacios, guiones y corchetes, lo que se puedan haber agregado cuándo se creó el cliente. Por lo tanto, los cajeros no tienen que preocuparse del formato de número de teléfono al realizar una búsqueda. También pueden buscar por cliente escribiendo un número de teléfono parcial. Si un número de teléfono incluye caracteres especiales, también se puede encontrar buscando los números que aparecen después de caracteres especiales. Por ejemplo, si un número de teléfono de cliente se escribió como **123-456-7890**, un cajero puede buscar el cliente escribiendo **123**, **456**, **7890** o **1234567890** o simplemente escribiendo los primeros números del teléfono.

La búsqueda tradicional de clientes puede ser larga, porque buscar en varios campos. En su lugar, los cajeros pueden ahora buscar en una única propiedad de cliente, como el nombre, dirección de correo electrónico o número de teléfono. Las propiedades que el algoritmo de búsqueda del cliente usa se conocen colectivamente como *criterios de búsqueda del cliente*. La administración del sistema puede configurar fácilmente uno o más criterios como métodos abreviados que aparecen en PDV. Dado que la búsqueda se limita a un único criterio, solo se muestran los resultados relevantes de la búsqueda y el rendimiento es mucho mejor que el rendimiento de una búsqueda estándar del cliente. La ilustración siguiente muestra los métodos abreviados de búsqueda del cliente en el PDV.

![Métodos abreviados de búsqueda del cliente](./media/SearchShortcutsPOS.png "Métodos abreviados de búsqueda del cliente")

Para establecer criterios de búsqueda como métodos abreviados, la administración debe abrir la página **Parámetros de Retail** en Microsoft Dynamics 365 for Finance and Operations y, a continuación, en la pestaña **Criterios de búsqueda de PDV**, seleccionar todos los criterios que se deben mostrarse como métodos abreviados.

![Configurar métodos abreviados de búsqueda](./media/ConfigureShortcutsAX.png "Configurar métodos abreviados de búsqueda")

> [!NOTE]
> Si agrega demasiados métodos abreviados, el menú desplegable de la barra de la búsqueda en el PDV se desordenará y la experiencia de búsqueda del empleado se puede ver afectada. Es recomendable solo agragar tantos métodos abreviados como le sean necesarios.

El campo **Visualizar orden** determina el orden en que los accesos directos se muestran en PDV. Los criterios que se muestran son propiedades que el algoritmo de búsqueda del cliente usa para buscar clientes Sin embargo, los asociados pueden agregar propiedades personalizadas como métodos abreviados de búsqueda. Para agregar propiedades personalizadas como métodos abreviados de búsqueda, la administración del sistema debe remitir enumeración extensible (enum) que se usa para los criterios de búsqueda del cliente y después marcar las propiedades personalizadas de los asociados como métodos abreviados. Los socios son responsables de escribir el código para encontrar resultados cuando sus métodos abreviados personalizados se usan para las búsquedas.

> [!NOTE]
> Una propiedad personalizada que se agrega al enum no afecta al algoritmo de búsqueda estándar del cliente. Es decir, el algoritmo de búsqueda del cliente no buscará en la propiedad personalizada. Los usuarios pueden usar una propiedad personalizada para las búsquedas si dicha propiedad personalizada se agrega como método abreviado o si el algoritmo de búsqueda predeterminado ha sido reemplazado.

En una próxima versión de Microsoft Dynamics 365 for Retail, los minoristas podrán establecer el modo de búsqueda de clientes predeterminado en el PDV en **Buscar en todas las tiendas**. Esta configuración puede resultar útil en escenarios en los que los clientes que se crearon fuera del PDV deben buscarse de inmediato (por ejemplo, incluso antes de que se ejecute el trabajo de distribución). Una nueva opción **Modo de búsqueda de clientes predeterminado** estará disponible en el perfil de funcionalidad de PDV. Establézcala en **Activa** para establecer el modo de búsqueda predeterminado en **Buscar en todas las tiendas**. Cada intento de búsqueda de clientes hará una llamada en tiempo real a la sede.

Para ayudar a evitar problemas de rendimiento inesperados, esta configuración se oculta detrás de un indicador que se denomina **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Por tanto, para mostrar el **Modo de búsqueda de clientes predeterminado** que configura la interfaz de usuario (IU), el minorista debe crear una incidencia de soporte técnico para su prueba de aceptación del usuario (UAT) y los entornos de producción. Una vez que se reciba la incidencia, el equipo de ingeniería trabajará con el minorista para garantizar que este último realiza la prueba en sus entornos que no son de producción a fin de evaluar el rendimiento e implementar cualquier optimización que sea necesaria.
