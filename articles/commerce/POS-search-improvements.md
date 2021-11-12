---
title: Búsqueda de productos y de clientes en el punto de venta (PDV)
description: En este tema se proporciona una visión general de las mejoras que se han realizado en la funcionalidad de búsqueda de productos y clientes en Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 022dcaca9bb3c9e7e749ee143702325367e5149b
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700098"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Búsqueda de productos y de clientes en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

El punto de venta moderno (MPDV) y el punto de venta (CPDV) en cloud proporcionan funcionalidades de búsqueda fáciles de usar para los productos y clientes. Gracias a que la barra de búsqueda siempre se muestra en la parte superior de las ventanas de MPDV y el CPDV, los empleados pueden buscar rápidamente productos y clientes.

Los empleados pueden buscar los productos en los surtidos y catálogos que están asociados a la tienda actual. También pueden buscar en los surtidos y catálogos que están asociados a la cualquier otra tienda de la empresa. Así pues, los cajeros pueden vender y devolver productos que estén fuera del surtido de su tienda. Del mismo modo, los empleados pueden buscar clientes que estén asociados con la tienda actual o con cualquier otra tienda de la empresa. Además, los empleados pueden buscar clientes que estén relacionados con diferentes empresas de la organización principal.

## <a name="product-search"></a>Búsqueda de productos

De forma predeterminada, las búsquedas de producto se realizan en el surtido de la tienda. Este tipo de búsqueda se conoce como *búsqueda de producto local*. Sin embargo, los empleados pueden cambiar fácilmente a los catálogos que están asociados a la tienda actual o bien, pueden realizar la búsqueda en otra tienda diferente. Este tipo de búsqueda se conoce como *búsqueda de producto remota*. Para cambiar el catálogo, seleccione el botón **Categorías** en el lado izquierdo de la página. En la parte superior del panel, seleccione el botón **Cambiar catálogo** y, a continuación, seleccione uno de los catálogos disponibles para examinarlo. El sistema buscará el catálogo de productos seleccionado.

En la página **Cambiar catálogo**, los empleados pueden seleccionar cualquier forma de manera sencilla, o pueden buscar productos en todas las tiendas.

![Cambio del catálogo.](./media/Changecatalog.png "Cambio del catálogo")

Una búsqueda de producto local realiza búsquedas en las siguientes propiedades de producto:

- Código de producto
- Nombre del producto
- Descripción
- Dimensiones
- Código de barras
- Nombre de búsqueda

### <a name="additional-local-product-search-capabilities-conventional-sql-full-text-search"></a>Capacidades adicionales de búsqueda de productos locales (búsqueda de texto completo SQL convencional) 

- Si va a realizar una búsqueda con varias palabras clave (esto es, una búsqueda que usa términos de búsqueda), los distribuidores pueden configurar los resultados de búsqueda para que incluyan opciones que coincidan con *cualquier* término de búsqueda o *todos* los términos de búsqueda. La configuración para esta funcionalidad está disponible en el perfil de funcionalidades de PDV, en un nuevo grupo denominado **Búsqueda de producto**. La configuración predeterminada es **Coincidencias con cualquier término de búsqueda**. Le recomendamos que use esta configuración. Cuando se usa la configuración **Coincidir con cualquier término de búsqueda**, todos los productos que coinciden total o parcialmente con uno o varios términos de búsqueda se devuelven como resultados. Esos resultados se ordenan automáticamente en orden ascendente de productos que tienen la mayoría de las coincidencias de la palabra clave (parcial o completa).

    La configuración **Coincidencias con todos los términos de búsqueda** sólo devuelve aquellos productos que coincidan con todos los términos de búsqueda (parcial o completa). Esta opción resulta útil cuando los nombres de producto son muy largos y los empleados solo quieren encontrar ciertos productos en los resultados de búsqueda. Sin embargo, este tipo de búsqueda tiene dos limitaciones:

    - La búsqueda se realiza en propiedades de producto individuales. Por ejemplo, solo se devuelven productos que tengan todas las palabras clave buscadas en al menos una propiedad del producto.
    - No se busca en las dimensiones.
> [!NOTE]
> Las siguientes configuraciones de **Coincidir con cualquier término de búsqueda**/**Coincidir con todos los términos de búsqueda** en los perfiles de funcionalidad POS solo son aplicables para **local** experiencias de búsquedas de productos (búsqueda de texto completo SQL convencional). Esta configuración no tiene ningún efecto en las experiencias de búsqueda impulsadas por la nube. El nuevo motor de búsqueda tiene su propio algoritmo avanzado que potencia la relevancia de la búsqueda para los resultados de búsqueda de productos. 

- Los distribuidores pueden configurar la búsqueda de productos para que se muestren sugerencias a medida que el usuario escribe el nombre del producto. Una nueva configuración para esta funcionalidad está disponible en el perfil de funcionalidades de PDV, en un grupo denominado **Búsqueda de producto**. Esta configuración se llama **Mostrar las sugerencias de búsqueda mientras se escribe**. Esta función puede ayudar a sus empleados a buscar rápidamente el producto que quieran, ya que no tienen que escribir todo el nombre de forma manual.
- El algoritmo de búsqueda de productos también busca términos en la propiedad de producto **Nombre de búsqueda**.

![Sugerencias de productos.](./media/Productsuggestions.png "Sugerencias de productos")

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

En la búsqueda de clientes solicitada desde otras entidades jurídicas, no se muestra el id. del cliente,ya que no se creó ningún id. de cliente para dichas partes en la empresa actual. Sin embargo, si un empleado abre la página de detalles del cliente, el sistema genera automáticamente un identificador de cliente para el grupo y también lo asocia a las libretas de direcciones de clientes de la tienda. Por lo tanto, el cliente será visible en las búsquedas de tienda locales que se hagan posteriormente.

![Búsqueda global de cliente.](./media/Globalcustomersearch.png "Búsqueda global de cliente")

### <a name="additional-local-customer-search-capabilities"></a>Capacidades adicionales de búsqueda de clientes locales

Cuando el usuario busca un número de teléfono, el sistema ignora los caracteres especiales (como espacios, guiones y corchetes), lo que se puedan haber agregado al crear el cliente. Por lo tanto, los cajeros no tienen que preocuparse del formato de número de teléfono al realizar una búsqueda. Por ejemplo, si un número de teléfono de cliente se escribió como **123-456-7890**, un cajero puede buscar el cliente escribiendo **1234567890** o simplemente escribiendo los primeros números del teléfono.

> [!NOTE]
> Un cliente puede tener múltiples números de teléfono y múltiples correos electrónicos. El algoritmo de búsqueda de clientes también busca a través de estos correos electrónicos y números de teléfono secundarios, pero la página de resultados de búsqueda de clientes solo muestra el correo electrónico principal y el número de teléfono. Esto puede causar cierta confusión ya que los resultados devueltos del cliente no mostrarían el correo electrónico o el número de teléfono buscado. En una versión futura, planeamos mejorar la pantalla de resultados de búsqueda de clientes para mostrar esta información.

La búsqueda tradicional de clientes puede ser larga, porque buscar en varios campos. En su lugar, los cajeros pueden buscar una única propiedad de cliente, como el nombre, dirección de correo electrónico o número de teléfono. Las propiedades que el algoritmo de búsqueda del cliente usa se conocen colectivamente como *criterios de búsqueda del cliente*. La administración del sistema puede configurar fácilmente uno o más criterios como métodos abreviados que aparecen en PDV. Dado que la búsqueda se limita a un único criterio, solo se muestran los resultados relevantes de la búsqueda y el rendimiento es mucho mejor que el rendimiento de una búsqueda estándar del cliente. La ilustración siguiente muestra los métodos abreviados de búsqueda del cliente en el PDV.

![Métodos abreviados de búsqueda del cliente.](./media/SearchShortcutsPOS.png "Métodos abreviados de búsqueda del cliente")

Para establecer criterios de búsqueda como métodos abreviados, el administrador debe abrir la página **Parámetros de Commerce** en Commerce y, a continuación, en la pestaña **Criterios de búsqueda de PDV**, seleccionar todos los criterios que se deben mostrarse como métodos abreviados.

![Configurar métodos abreviados de búsqueda.](./media/ConfigureShortcutsAX.png "Configurar métodos abreviados de búsqueda")

> [!NOTE]
> Si agrega demasiados métodos abreviados, el menú desplegable de la barra de la búsqueda en el PDV se desordenará y la experiencia de búsqueda del empleado se puede ver afectada. Es recomendable solo agragar tantos métodos abreviados como le sean necesarios.

El campo **Visualizar orden** determina el orden en que los accesos directos se muestran en PDV. Los criterios que se muestran son propiedades que el algoritmo de búsqueda del cliente usa para buscar clientes Sin embargo, los asociados pueden agregar propiedades personalizadas como métodos abreviados de búsqueda. Para agregar propiedades personalizadas como métodos abreviados de búsqueda, la administración del sistema debe remitir enumeración extensible (enum) que se usa para los criterios de búsqueda del cliente y después marcar las propiedades personalizadas de los asociados como métodos abreviados. Los socios son responsables de escribir el código para encontrar resultados cuando sus métodos abreviados personalizados se usan para las búsquedas.

> [!NOTE]
> Una propiedad personalizada que se agrega al enum no afecta al algoritmo de búsqueda estándar del cliente. Es decir, el algoritmo de búsqueda del cliente no buscará en la propiedad personalizada. Los usuarios pueden usar una propiedad personalizada para las búsquedas si dicha propiedad personalizada se agrega como método abreviado o si el algoritmo de búsqueda predeterminado ha sido reemplazado.

Los minoristas también pueden configurar el modo de búsqueda de clientes predeterminado en PDV en **Buscar en todas las tiendas**. Esta configuración puede resultar útil en escenarios en los que los clientes que se crearon fuera del PDV deben buscarse de inmediato (por ejemplo, incluso antes de que se ejecute el trabajo de distribución). Para hacerlo, el minorista debe activar la opción **Modo de búsqueda de clientes predeterminado** en el perfil de funcionalidad de PDV. Una vez establecido en **Sí**, cada intento de búsqueda de clientes hará una llamada en tiempo real a la sede.

Para ayudar a evitar problemas de rendimiento inesperados, esta configuración se oculta detrás de un indicador que se denomina **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Por tanto, para mostrar el **Modo de búsqueda de clientes predeterminado** que configura la interfaz de usuario (IU), el minorista debe crear una incidencia de soporte técnico para su prueba de aceptación del usuario (UAT) y los entornos de producción. Una vez que se reciba la incidencia, el equipo de ingeniería trabajará con el minorista para garantizar que este último realiza la prueba en sus entornos que no son de producción a fin de evaluar el rendimiento e implementar cualquier optimización que sea necesaria.

## <a name="cloud-powered-customer-search"></a>Búsqueda de clientes con tecnología de nube

La versión preliminar pública de la función de búsqueda de clientes mediante el servicio de búsqueda cognitiva de Azure se ha lanzado como parte de la versión 10.0.18 de Commerce. Además de las mejoras de rendimiento, los usuarios del servicio también se benefician de un gran ajuste y capacidades de relevancia mejoradas. Las mejoras de rendimiento son especialmente evidentes cuando se utiliza la función de búsqueda global ("Buscar en todas las tiendas") del PDV. Esto se debe a que los resultados de la búsqueda se obtienen del índice de búsqueda de Azure en lugar de consultar los datos en la sede de Commerce. 

### <a name="enable-the-cloud-powered-search-feature"></a>Habilitar la función de búsqueda con tecnología de la nube

> [!NOTE]
> Se requiere que tanto la sede de Commerce como Commerce Scale Unit estén actualizados a la versión 10.0.18. No es necesario actualizar el PDV.

Para habilitar la característica de búsqueda con tecnología de la nube en la sede de Commerce, siga estos pasos.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Busque y seleccione la característica **(Versión preliminar) Búsqueda de clientes con tecnología de nube** y, a continuación, seleccione **Habilitar ahora**.
1. Vaya a **Comercio minorista y Commerce > Configuración de sede> Programador de comercio> Inicializar el programador de comercio** y seleccione **Aceptar** para mostrar el nuevo trabajo **1010_CustomerSearch** trabajo en el formulario **Programa de distribución**.
1. Vaya a **Comercio minorista y Commerce > TI de Comercio minorista y Commerce > Programación de distribución**.
1. Ejecute el trabajo **1010_CustomerSearch**. Este trabajo publica la fecha en el índice de búsqueda de Azure. Cuando se complete la publicación del índice, el estado del trabajo se establecerá en **Aplicado**.
1. Después de que el estado del trabajo **1010_CustomerSearch** se establece en **Aplicado**, ejecute el trabajo **1110 - Configuración global** para actualizar los canales PDV de la característica recién habilitada en **Administración de funciones**.
1. A continuación, ejecute el trabajo **1010_CustomerSearch** a intervalos regulares para enviar actualizaciones de clientes al índice de búsqueda.

> [!NOTE]
> Para la publicación del índice inicial, el trabajo **1010_CustomerSearch** puede tardar algunas horas en completarse, ya que enviará todos los registros del cliente al índice de búsqueda de Azure. Las actualizaciones posteriores deberían tardar unos minutos. En el período de tiempo en el que la función de búsqueda con tecnología de nube está habilitada pero la publicación del índice aún no se ha completado, la búsqueda del cliente desde el PDV será la búsqueda predeterminada basada en SQL. Esto asegura que no haya interrupciones en las operaciones de la tienda.

### <a name="functional-differences-from-the-existing-search"></a>Diferencias funcionales de la búsqueda existente

La siguiente lista muestra en qué se diferencia la funcionalidad de búsqueda de clientes con tecnología de nube de la funcionalidad de búsqueda existente. 

- Los clientes creados y editados en la sede de Commerce se envían al índice de búsqueda de Azure cuando se ejecuta el trabajo **1010_CustomerSearch**. Estas actualizaciones tardan un mínimo de 15 a 20 minutos en actualizar el índice. Los usuarios de PDV podrán buscar nuevos clientes (o buscar en base a información actualizada) entre 15 y 20 minutos después de que ocurran las actualizaciones en la sede de Commerce. Si su proceso comercial requiere que los clientes creados en la sede de Commerce puedan buscarse inmediatamente en los PDV, es posible que este no sea el servicio adecuado para usted.
- Los nuevos clientes creados en los PDV se envían al índice de búsqueda de Azure desde la Commerce Scale Unit y se pueden buscar inmediatamente en cualquier tienda. Sin embargo, si la función de creación de clientes asincrónicos está activada, los nuevos registros de clientes no se publicarán en el índice de búsqueda de Azure desde la Commerce Scale Unit y no se podrán buscar desde los PDV hasta que la información del cliente se sincronice con la sede de Commerce y se generen los id. de cliente. para los clientes asincrónicos. El trabajo **1010_CustomerSearch** podrá enviar los registros de clientes asincrónicos al índice de búsqueda de Azure. En promedio, pasarán alrededor de 30 minutos antes de que los clientes asincrónicos recién creados puedan buscarse en los PDV. Esta estimación presupone que los trabajos **1010_CustomerSearch**, **P-job**, **Sincronizar clientes y socios comerciales desde el modo asincrónico** están programados para ejecutarse cada 15 minutos.
- La búsqueda basada en la nube también busca los correos electrónicos secundarios y los números de teléfono de los clientes, pero actualmente los resultados de la búsqueda de clientes solo muestran el número de teléfono principal y la dirección de correo electrónico principal de los clientes. A primera vista, puede parecer que se han obtenido resultados de búsqueda irrelevantes, pero el comprobar el correo electrónico secundario y el número de teléfono de un cliente en los resultados de búsqueda puede ayudar a verificar si la palabra clave buscada dio por resultado una coincidencia de cliente. Para evitar tal confusión, hay planes para mejorar la página de resultados de búsqueda para que sea más fácil para los usuarios conocer por qué se devolvió un resultado de búsqueda.
- El requisito de buscar utilizando al menos 4 caracteres en una búsqueda global ("Buscar en todas las tiendas") no es aplicable a este servicio.

> [!NOTE]
> La capacidad de búsqueda de clientes que usa el servicio Azure Cognitive Search está disponible en regiones limitadas en forma de versión preliminar. La capacidad de búsqueda de clientes *no* está disponible en las siguientes regiones:
> - Brasil
> - India

[!INCLUDE[footer-include](../includes/footer-banner.md)]
