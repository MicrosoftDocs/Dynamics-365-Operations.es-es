---
title: Administración de precio de ventas minoristas
description: En este tema se describen los conceptos para crear y administrar precios de ventas en Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1eb0b218b9008b255cc5a09eefb8c7fa35836cd7
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057496"
---
# <a name="retail-sales-price-management"></a>Administración de precios de venta minorista

[!include [banner](includes/banner.md)]

Este tema proporciona información acerca del proceso de creación y la administración de precios de ventas en Dynamics 365 Commerce. Se centra en los conceptos implicados en este proceso y en los efectos de las distintas opciones de configuración para los precios de venta.

## <a name="terminology"></a>Terminología

En este tema se utilizan los siguientes términos:

| Condición | Definición, uso y notas |
|---|---|
| Precio | El importe de unidad única por el que se vende un producto a un cliente de punto de venta (PDV) o en un pedido de ventas. En este tema, el término *precio* hace referencia siempre al precio de venta, no al precio de inventario ni al precio de coste. |
| Precio base | El precio que se establece en el campo **Precio** en un producto liberado. |
| Precio de acuerdo comercial | El precio que se establece en un producto o una variante mediante un acuerdo comercial del tipo **Precio (ventas)** . |
| Mejor precio | Cuando se puede aplicar más de un precio o descuento a un producto, el menor importe del precio y/o el mayor importe de descuento que genera el menor importe neto posible que el cliente debe pagar. En este tema, el concepto de mejor precio siempre se conoce como "el mejor precio". Este mejor precio es diferente y no debe confundirse con el valor de enumeración **Mejor precio** para el modo de concurrencia de un descuento. |

## <a name="price-groups"></a>Grupos de precio

Los grupos de precios se encuentran en el centro de la administración de precios y descuentos en Commerce. Los grupos de precios se utilizan para asignar precios y descuentos para entidades comerciales (es decir, canales, catálogos, afiliaciones y programas de fidelización). Puesto que los grupos de precios se utilizan para todos los precios y descuentos, es muy importante que planifique cómo los utilizará antes de comenzar.

Por sí mismo, un grupo de precios es solo un nombre, una descripción y, de forma opcional, una prioridad de precios. La cuestión principal a recordar acerca de los grupos de precios es que se utilizan para gestionar las relaciones de varios a varios que los descuentos y precios tienen con las entidades comerciales.

La siguiente ilustración muestra cómo se utilizan los grupos de precios. En esta ilustración, observe que el "Grupo de precios" se encuentra literalmente en el centro de la gestión de precios y descuentos. Las entidades comerciales que puede utilizar para gestionar precios y descuentos diferenciales se encuentran a la izquierda, y los registros reales de precios y descuentos están a la derecha.

![Grupos de precios](./media/PriceGroups.png "Grupos de precios")

Al crear grupos de precios, no debe utilizar un único grupo de precios para varios tipos de entidades comerciales. De lo contrario, puede resultar difícil determinar por qué un precio o descuento específico se está aplicando a una transacción.

Como muestra la línea discontinua roja en la ilustración, Commerce no admite la funcionalidad principal de Microsoft Dynamics 365 de un grupo de precios que se establece directamente en un cliente. Sin embargo, en este caso, solo obtiene acuerdos comerciales de precios de venta. Si desea aplicar los precios específicos del cliente, le recomendamos que no establezca grupos de precio directamente en el cliente. En su lugar, debe utilizar afiliaciones.

Las secciones siguientes proporcionan más información acerca de las entidades comerciales que puede usar para establecer precios distintos cuando se utilizan grupos de precios. La configuración de precios y descuentos para todas estas entidades es un proceso de dos pasos. Estos pasos se pueden realizar en cualquier pedido. Sin embargo, el pedido lógica es establecer primero los grupos de precios en las entidades, ya es probable que este paso sea una configuración única que se realiza durante la implementación. A continuación, cuando se crean los precios y descuentos, puede establecer de manera individual los grupos de precios en estos precios y descuentos.

### <a name="channels"></a>Canales

En el sector comercial, es muy habitual tener diferentes precios en distintos canales. Los dos factores principales que afectan a los precios específicos de un canal son costes y condiciones empresariales locales.

- **Costes**: cuanto más lejos esté un canal del origen del producto, más cuesta almacenar un producto. Por ejemplo, el producto fresco tiene una vida útil limitada y unos requisitos de producción específicos (por ejemplo, una temporada de cultivo). Durante el invierno, la lechuga fresca probablemente cuesta más en climas septentrionales que en climas meridionales. Si establece precios para canales en un área geográfica grande, probablemente querrá establecer diferentes precios en distintos canales.
- **Condiciones empresariales locales**: una tienda que tiene un competidor directo al otro lado de la calle será mucho más sensible a los precios que una tienda que no tiene un competidor directo cerca.

### <a name="affiliations"></a>Afiliaciones

La definición general de una afiliación es un vínculo o la asociación a un grupo. En Commerce, las afiliaciones son grupos de clientes. Las afiliaciones son una herramienta mucho más flexible para precios y descuentos de cliente que el concepto básico de Microsoft Dynamics 365 de grupos de clientes y grupos de descuento. En primer lugar, una afiliación se puede utilizar para precios y descuentos, mientras que el precio que no es para minoristas tiene un grupo diferente para cada tipo de descuento y precio. A continuación, un cliente puede pertenecer a varias afiliaciones pero solo puede pertenecer a un único grupo de precios no para minoristas de cada tipo. Finalmente, aunque las afiliaciones pueden configurarse para que se vinculen a un cliente, no es necesario hacerlo. Una afiliación ad hoc se puede utilizar para clientes anónimos en el PDV. Un ejemplo típico de un descuento de afiliación anónimo es un descuento para antiguos alumnos o estudiantes, donde un cliente puede recibir un descuento con solo mostrar una tarjeta de miembro del grupo.

Aunque las afiliaciones suelen asociarse más a descuentos, también puede utilizarlas para establecer precios diferenciales. Por ejemplo, cuando un minorista vende a un empleado, es posible que desee cambiar el precio de venta en lugar de aplicar un descuento sobre el precio normal. Como otro ejemplo, un minorista que vende a los clientes consumidores y clientes comerciales pueden ofrecer mejores precios a los clientes comerciales, en función del volumen de compra. Las afiliaciones permiten estas situaciones.

### <a name="loyalty-programs"></a>Programas de fidelización

En relación con los precios y descuentos, los programas de fidelidad son básicamente una afiliación que tiene un nombre especial. Pueden establecerse precios y descuentos para un programa de fidelidad, al igual que pueden establecerse para una afiliación. Sin embargo, la manera en que los clientes obtienen precios de fidelidad durante una transacción o un pedido difiere de la forma en que obtienen precios de afiliación. Los clientes pueden obtener precios de fidelidad solamente si se agrega una tarjeta de fidelización a una transacción. Cuando una tarjeta de fidelización se añade a una transacción, también se agrega el programa de fidelidad. El programa de fidelidad permite precios y descuentos especiales.

Los programas de fidelidad pueden tener varios niveles, y los descuentos pueden ser diferentes para distintos niveles. De esta manera, los minoristas pueden dar mayores recompensas a clientes frecuentes sin tener que meter manualmente a estos clientes en un grupo especial.

Además de los precios y descuentos, los programas de fidelidad tienen funciones adicionales. Sin embargo, desde la perspectiva de los precios y descuentos, son las mismas que las afiliaciones.

### <a name="catalogs"></a>Catálogos

Algunos minoristas utilizan catálogos físicos o virtuales para comercializar productos, y asignarles precios, a grupos de clientes específicos. Como parte de su modelo empresarial para marketing de segmentos a través de un catálogo, estos minoristas pueden establecer precios diferenciales en sus distintos catálogos. Microsoft Dynamics 365 admite esta capacidad al permitirle definir descuentos y precios específicos del catálogo, de la misma manera que puede definir descuentos específicos del canal y de la afiliación. Al editar un catálogo, puede asociar grupos de precios al catálogo, al igual que puede asociarlos a un canal, una afiliación o un programa de fidelidad.

### <a name="best-practices-for-price-groups"></a>Prácticas recomendadas para grupos de precios

No utilice un grupo de precios para varios tipos de entidades. En su lugar, utilice un conjunto de grupos de precios para canales, un conjunto distinto de grupos de precios para afiliaciones o programas de fidelidad, etc. Puede utilizar un prefijo o un sufijo en el nombre del grupo de precios para agrupar visualmente los distintos tipos de grupos de precios que utiliza.

Evite configurar grupos de precios directamente en un cliente. En su lugar, utilice una afiliación. De esta manera, puede asignar todos los tipos de precios y descuentos a los clientes, no solo acuerdos comerciales de precios de venta.

## <a name="pricing-priority"></a>Prioridad de precios

Por sí misma, una prioridad de precios es solo un número y una descripción. Las prioridades de precios se pueden aplicar grupos de precios, o se pueden aplicar directamente a descuentos. Cuando se utilizan prioridades de precios, estas permiten a un minorista anular el principio del mejor precio al controlar el orden en el que se aplican los precios y los descuentos a los productos. Un número mayor de prioridad de precios se evalúa antes que un número menor de prioridad de precios. Además, si un precio o descuento se encuentra en cualquier número de prioridad, se ignoran todos los precios o descuentos que tienen números más bajos de prioridad.

El precio y un descuento pueden proceder de dos prioridades de precios diferentes, ya que las prioridades de precios se aplican de forma independiente a precios y descuentos.

Para utilizar una prioridad de precios para los precios, debe asignar una prioridad de precios a un grupo de precios y luego crear un acuerdo comercial de precio de ventas para ese grupo de precios.

La función de prioridad de precios se introdujo para admitir el escenario en el que un minorista desea aplicar precios mayores en un conjunto específico de tiendas. Por ejemplo, un minorista ha definido precios regionales para la costa este de los Estados Unidos, pero desea precios mayores para algunos productos en las tiendas de Nueva York, ya que cuesta más vender algunos productos en la ciudad, y/o porque el mercado local tendrá un precio más alto.

Como se describió en la sección "Mejor precio" de este tema, el motor de precios selecciona normalmente el precio más bajo de los dos. Por lo tanto, normalmente se impide al minorista usar el precio más alto de los dos en una tienda que tiene los grupos de precios del Nordeste y de Nueva York. Para resolver este problema antes de que se introduzca la función de prioridad de precios, el minorista tenía que definir los precios para cada producto dos veces y no asignar ambos grupos de precios. De manera alternativa, el minorista tuvo que crear grupos de precios adicionales para aislar los productos con precios más altos que los productos que tienen los precios habituales y más bajos.

Sin embargo, la función de prioridad de precios permite al minorista crear una prioridad de precios para precios de tienda que sea mayor que la prioridad de precio para precios regionales. De manera alternativa, el minorista puede crear una prioridad de precios solo para precios de tienda y dejar los precios regionales en la prioridad de precios predeterminada, que es 0 (cero). Ambas configuraciones ayudan a garantizar que los precios de tienda se utilizan siempre antes que los precios regionales.

### <a name="pricing-priority-example"></a>Ejemplo de prioridad de precios

Veamos un ejemplo en el que los precios de tienda anulan otros precios.

Un minorista nacional establece la mayoría de precios por región, y tiene cuatro regiones: Nordeste, Sureste, Medio Oeste y Oeste. Ha identificado varios mercados de alto coste que admiten precios más altos. Estos mercados se encuentran en Nueva York, Chicago y la zona de la bahía de San Francisco.

Para este ejemplo, profundizaremos en la región del Nordeste. La tienda 1 se encuentra en Boston y la tienda 2 está en Manhattan. Para la tienda de Boston, se vinculan dos grupos de precios al canal: Nordeste y Tienda 1. Para la tienda de Manhattan, se vinculan tres grupos de precios al canal: Nordeste, Nueva York y Tienda 2.

El minorista configura dos prioridades de precio: Alto coste tiene un número de prioridad de 5 y Precios de tienda tiene un número de prioridad de 10. (Recuerde que, de forma predeterminada, la prioridad de precios es 0, \[cero\] y un precio o descuento con un número de prioridad mayor se utiliza antes que un precio o descuento con un número de prioridad menor.) Para el grupo de precios del Nordeste, la prioridad de precios se deja en el valor predeterminado de **0** (cero). Para el grupo de precios de Nueva York, la prioridad de precios se establece en **5**, ya que Nueva York es un mercado de alto coste. Para los grupos de precios Tienda 1 y Tienda 2, la prioridad de precios se establece en **10**.

Dos productos que el minorista vende son el producto 1, una camiseta, y el producto 2, unos pantalones vaqueros modernos específicos de una marca.

| Producto | Precio del Nordeste | Precio de Nueva York | Precio de tienda |
|---|---|---|---|
| Camiseta | 15 $ | Sin establecer | Sin establecer |
| Pantalones vaqueros modernos | 50 $ | 70 $ | Sin establecer |

La camiseta se vende por el mismo precio (es decir, 15 $) en las tiendas de Boston y Manhattan, ya que solo se establece un precio en el grupo de precios del Nordeste que se vincula a ambos canales. Los pantalones vaqueros modernos se venden a 50 $ en la tienda de Boston, ya que dicho precio es el único precio disponible en esa tienda. Sin embargo, en la tienda de Manhattan están disponibles dos precios : 50 $ y 70 $. Puesto que la prioridad de precios de 5 para el grupo de precios de Nueva York es mayor que la prioridad de precios de 0 (cero) para el grupo de precios del Nordeste, el precio se elevará a 70 $ en el sistema PDV.

> [!NOTE]
> Para cada prioridad de precios, se requiere un paso completo a través de la lógica para el motor de precios al por menor. Por lo tanto, para ayudar a mantener el rendimiento del precio y el cálculo del descuento, debe utilizar con moderación las prioridades de precios.

## <a name="types-of-prices"></a>Tipos de precios

En Microsoft Dynamics 365, puede establecer el precio de un producto en tres ubicaciones:

- Directamente en el producto (precio base)
- En un acuerdo comercial de precio de ventas
- En un ajuste de precios

El precio base y el precio del acuerdo comercial forman parte de Dynamics 365, y está disponible incluso si no utiliza Commerce. La funcionalidad de ajuste de precios solo está disponible en Commerce. La siguiente sección proporciona más información sobre cada una de estas opciones para establecer los precios y explica cómo funcionan juntas las opciones.

## <a name="setting-prices"></a>Configuración de precios

### <a name="base-price"></a>Precio base

El lugar más fácil para establecer el precio de un producto se encuentra directamente en el producto. El valor que establece directamente en un producto suele denominarse como precio base para el producto. Establece el precio base en el campo **Precio** en la pestaña **Vender** de la página **Detalles de producto emitido**. El valor que introduce está en la divisa de la empresa. De forma predeterminada, el precio es para una cantidad de 1 de la unidad de medida (UdM) definida en el campo **Unidad** en la pestaña **Vender**. El precio real por unidad de un producto se basa en la UdM, la cantidad del precio y la divisa.

Si un producto tiene un precio para todos, el precio base ofrece la forma más eficaz de administrar el precio de dicho producto. Incluso si utiliza acuerdos comerciales para establecer precios, es posible que también establezca el precio base en un producto. A continuación, si no utiliza un acuerdo comercial **Todos**, tendrá un precio de reserva que se usa cuando no se aplica ningún acuerdo comercial.

Si la divisa de un canal se diferencia de la divisa de la empresa, el precio base en dicho canal se determina mediante la conversión de divisas en el precio que se establece en el producto.

Aunque la unidad de precio no es una situación común de comercio, el motor de precios la admite. Si la unidad de precio se establece en un valor distinto a **0** (cero), el precio por unidad es igual a Precio ÷ Unidad de precio. Por ejemplo, si el precio de un producto es $10,00 y la unidad de precio es 50, el precio para una cantidad de 1 es 0,20 $ (= 10,00 $ ÷ 50).

### <a name="sales-price-trade-agreement"></a>Acuerdo comercial de precio de ventas

Al utilizar el diario de acuerdos comerciales, puede crear acuerdos comerciales de precio de ventas para cada producto. En Microsoft Dynamics 365, existen tres ámbitos del cliente para acuerdos comerciales de precio de ventas: **Tabla**, **Grupo** y **Todos**. El ámbito del cliente determina los clientes a los que se aplica un acuerdo comercial de precio de ventas determinado.

Un acuerdo comercial de precio de ventas **Tabla** es para un único cliente que se establece directamente en el acuerdo comercial. Este escenario no es un escenario habitual empresa-consumidor (B2C). Sin embargo, si se produce, el motor de precios utiliza los acuerdos comerciales **Tabla** cuando se determina el precio.

Un acuerdo comercial de precio de ventas **Grupo** es el tipo que se utiliza con mayor frecuencia. Fuera de Commerce, los acuerdos comerciales de precio de ventas **Grupo** son para un grupo de clientes simple. Sin embargo, en Commerce, el concepto de un grupo de clientes se ha ampliado de modo que sea un grupo de precios más genérico. Un grupo de precios se puede vincular a un canal, una afiliación, un programa de fidelidad o un catálogo. Para obtener información detallada sobre los grupos de precios, consulte la sección "Grupos de precios" que se descrige anteriormente en este tema.

> [!NOTE]
> Un precio de acuerdo comercial siempre se utiliza antes que el precio base.

### <a name="price-adjustment"></a>Ajuste de precios

Como el nombre implica, un ajuste de precios se utiliza para modificar el precio que se estableció directamente en el producto o mediante un acuerdo comercial. Un ajuste de precios solo se puede usar para reducir el precio, no para elevarlo. Un ajuste de precios es la forma recomendada para que los minoristas creen, supervisen y administren las reducciones de precios para sus productos a lo largo del tiempo.

Existen tres tipos de ajustes de precios: el porcentaje de reducción, el importe de reducción y el precio. Un ajuste de precios del tipo porcentaje de reducción o importe de reducción siempre se aplica a una transacción de venta. Sin embargo, un ajuste de precios del tipo precio solo se aplica si el precio ajustado es menor que el precio que se estableció mediante el precio base o el precio del acuerdo comercial. Por lo tanto, si el precio que se establece en un ajuste de precios es mayor que el precio sin ajustar, el ajuste de precios no se utiliza.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Determinar el precio de un producto en una transacción

El cálculo del precio y el descuento en una transacción utiliza el principio de encontrar el mejor precio para el cliente. De acuerdo con este principio, si se encuentra más de un precio, se utiliza el precio más bajo. Además, se utiliza la combinación de descuentos que genera el importe de descuento mayor para toda la transacción. En algunos casos, debe utilizarse un descuento inferior en un único producto, de manera que se puedan aplicar descuentos adicionales a otros productos en la transacción.

La única excepción al principio de encontrar el mejor precio para el cliente es una opción para descuentos combinados menos caros. Esta opción habilita los descuentos menos caros que favorecen al minorista cuando se seleccionan y agrupan los productos. Por lo tanto, cuando una transacción incluye más productos que se requieren para habilitar el descuento menos caro, el motor de precios selecciona los productos que generan el menor importe de descuento posible para el cliente.

El motor de precios devuelve tres precios para cada producto: el precio base, el precio de acuerdo comercial y el precio activo.

El precio base es solo la propiedad del producto y es el mismo para todos en cualquier parte.

En el acuerdo comercial del precio de venta, si la opción **Buscar siguiente** se establece en **Sí**, el precio más bajo que se encuentra para los acuerdos comerciales del precio de ventas aplicable se utiliza como el precio del acuerdo comercial. Los acuerdos comerciales se pueden encontrar mediante el uso de grupos de precios o el código de cuenta **ALL** . De forma alternativa, los acuerdos comerciales se pueden asignar directamente a un cliente. Si la opción **Buscar siguiente** se establece en **No**, se utiliza el primer precio del acuerdo comercial que se encuentra. Si no se encuentra ningún acuerdo comercial del precio de ventas, el precio del acuerdo comercial es igual al precio base.

El precio activo se calcula tomando el precio del acuerdo comercial y aplicando el ajuste de precios mayor que se aplica al producto. Si no se encuentra ningún ajuste de precios, o si el precio activo calculado es mayor que el precio del acuerdo comercial, el precio activo es igual al precio del acuerdo comercial. Recuerde que no podrá subir el precio de un producto mediante un ajuste de precios. Los ajustes de precios aplicables se pueden encontrar solo mediante grupos de precios que se asignan a un canal, catálogo, afiliación o programa de fidelidad.

## <a name="category-price-rules"></a>Reglas de precios de categoría

La función de reglas de precios de categorías en Commerce le brinda una forma sencilla de crear nuevos acuerdos comerciales para todos los productos en una categoría. Esta función también le permite encontrar automáticamente acuerdos comerciales existentes para los productos de la categoría y caducarlos.

Al seleccionar la opción de caducar los acuerdos comerciales existentes, el sistema crea un nuevo diario de acuerdos comerciales para los productos de la categoría que tenga un acuerdo comercial activo. Sin embargo, el diario debe registrarse manualmente. Además, las reglas del precio de categoría puede encontrar acuerdos comerciales existentes solo si usa la misma regla de precios (es decir, si crea una nueva regla de precios que emplea la misma categoría que antes). Si no utiliza la misma regla de precios, los acuerdos comerciales existentes no caducarán.

Los precios se pueden aumentar o disminuir mediante los campos **Regla de precios** y **Base de precio** de las reglas de precios por categoría.

- En el campo **Regla de precios**, seleccione el tipo de cambio de precio que desea utilizar:

    - **Margen de beneficio**: se usará un porcentaje de la base de precios para calcular el precio de venta. Por ejemplo, un producto que cuesta 10,00 y se vende por 15,00 tiene un margen de beneficio del 50 por ciento.
    - **Margen**: se usará un porcentaje del precio de venta para calcular las ganancias. Por ejemplo, un producto que cuesta 10,00 y se vende por 15,00 tiene un margen del 33,3 por ciento.
    - **Importe fijo**: se usará un importe que se agrega a la base de precio para calcular el precio de venta. Por ejemplo, un producto que cuesta 10,00 y se vende por 15,00 tiene un importe fijo de 5,00.

- En el campo **Base de precio**, seleccione el tipo de precio para modificar:

    - **Coste base**: el importe que ha pagado el minorista al proveedor.
    - **Precio base**: el precio de ventas antes de que los acuerdos comerciales y los ajustes de precios se implementen.
    - **Precio actual**: el precio de ventas después de que los acuerdos comerciales y los ajustes de precios se implementen.

Para actualizar fácilmente los precios de varios productos de distintas categorías de productos, puede usar las categorías de productos adicionales junto con las reglas del precios por categoría.

## <a name="best-practices"></a>Prácticas recomendadas

Microsoft SQL Server Express se suele utilizar para las bases de datos de canales debido al coste (gratuito). Tenga en cuenta que SQL Server Express tiene limitaciones de hardware y límites en el tamaño de los datos. Si no planifica correctamente, puede alcanzar rápidamente los límites de tamaño de datos de SQL Server Express. Esta consideración no solo se aplica a los precios, sino también a otras áreas del producto. Aquí se muestran algunas prácticas recomendadas que pueden ayudarle a reducir el tamaño de los datos:

- Si utiliza acuerdos comerciales y sus precios cambian, debe caducar los acuerdos comerciales antiguos estableciendo una fecha final. Con el tiempo, este enfoque ayuda a reducir el número de acuerdos comerciales que se mantienen en las bases de datos de canales. También ayuda a reducir la cantidad de datos con la que debe trabajar el algoritmo del cálculo de precios.
- Si los precios varían por variante del producto, considere el uso del precio base del producto como el precio de variante más común. A continuación, utilice los acuerdos comerciales solo para los precios variables que sean excepciones. Este enfoque ayuda a reducir el número de registros del acuerdo comercial. Puesto que es muy sencilla importar datos en Microsoft Dynamics 365, es posible que tenga la tentación de importar un acuerdo comercial para cada variante de cada producto. Sin embargo, ese enfoque puede generar muchos acuerdos comerciales con el mismo valor. Por lo tanto, puede aumentar innecesariarmente el tamaño de los datos.
- Commerce procesa precios específicos de las variantes en orden del más al menos específico. Si una dimensión del producto no afecta al precio, no es necesario definir acuerdos comerciales para ella. Por ejemplo, un producto está disponible en tres colores y cuatro tamaños, pero el precio varía solo por tamaño. Si define un acuerdo comercial para cada variante, crea 12 registros. En su lugar, puede definir un acuerdo comercial solo para cada tamaño y dejar en blanco de la dimensión de color. En este caso, puede generar únicamente cuatro registros.

    De forma alternativa, si no todos los valores de una dimensión generan un precio diferente, puede definir un acuerdo comercial para el producto maestro y dejar en blanco todas las dimensiones del producto. A continuación, defina un acuerdo comercial independiente solo para cada valor de dimensión que genere un precio diferente. Por ejemplo, si el tamaño XXL tiene un precio mayor, pero el resto de tamaños tiene el mismo precio, se requieren solo dos acuerdos comerciales: uno para el producto maestro y otro para el tamaño XXL.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Precios que incluyen impuestos frente a precios sin impuestos

Al establecer precios de venta en Dynamics 365, no especifica si el valor del precio que está configurando incluye o excluye impuestos. El valor es solo el precio. Sin embargo, la configuración **El pecio incluye impuestos** le permite configurar los canales para que incluyan o excluyan los impuestos de los precios. Esta configuración se establece en el canal y puede cambiar incluso en una sola empresa.

Si trabaja con tipos de impuestos incluidos y exclusivos, es muy importante que configure los precios correctamente, ya que el importe total que el cliente paga cambiará si se cambia la configuración **El precio incluye impuestos** en el canal.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>Diferencias entre precios al por menor y precios no al por menor

Un único motor de precios se utiliza para calcular precios en todos los canales: centro de llamadas, tienda y tiendas en línea. Esto ayuda a habilitar los escenarios de comercio unificados.

Los precios están diseñados para trabajar con las entidades minoristas en lugar de con entidades no minoristas. Específicamente, está diseñado para establecer precios por tienda, no por almacén.

El motor de precios **no admite** las siguientes características de precios:

- Establecer precios por sitio o por dimensiones de almacenamiento de sitio o almacén. Si solo especifica la dimensión del sitio en los acuerdos comerciales, el motor de precios omitirá el sitio y aplicará el acuerdo comercial a todos los sitios. Si especifica tanto el sitio como el almacén, el comportamiento será indefinido/no probado porque se espera que los minoristas utilicen los grupos de precios de la tienda para controlar los precios de cada tienda o almacén.
- No se admiten precios basados en atributos.
- No se admite la transferencia de descuentos de proveedor.

Además, el motor de precios **solo** admite las siguientes funciones:

- El precio se basa en dimensiones del producto, en orden desde el precio variable más específico al precio variable menos específico para el precio del producto maestro. Un precio que se establece mediante el uso de dos dimensiones del producto (por ejemplo, Color y Tamaño) se utiliza antes que un precio que se establece usando solo una dimensión del producto (por ejemplo, Tamaño).
- Se puede utilizar el mismo grupo de precios para controlar precios y descuentos.

## <a name="pricing-api-enhancements"></a>Mejoras en los precios de API

El precio es uno de los factores más importantes que controlan las decisiones de compra de muchos clientes, y muchos clientes comparan precios en distintos sitios antes de hacer una compra. Para ayudar a garantizar que proporcionan precios competitivos, los minoristas observan detenidamente a sus competidores y a menudo realizan promociones. Para ayudar a minoristas a atraer a clientes, es muy importante que la búsqueda de producto, la característica de exploración, las listas, y la visualización de la página de detalles de productos muestren los precios más precisos.

En una versión próxima de Commerce, la interfaz de programación (API) de la aplicación **GetActivePrices** devolverá los precios que incluyen descuentos simples (por ejemplo, los descuentos de una línea que no dependen de otros artículos del carro). De esta manera, los precios que aparecen están muy cerca del importe real que los clientes pagan por los artículos. Este API incluirá todos los tipos de descuentos simples: basados en afiliación, fidelidad, catálogo y en el canal. Además, la API devolverá los nombres y la información de la validez para descuentos aplicados, de modo que los minoristas pueden proporcionar una descripción más detallada del precio y crear una sensación urgencia de si la validez del descuento expirará pronto.
