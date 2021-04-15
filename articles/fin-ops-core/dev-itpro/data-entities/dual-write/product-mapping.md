---
title: Experiencia unificada del producto
description: Este tema describe la integración de datos de productos entre aplicaciones de Finance and Operations y Dataverse.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 3087ab8853b14308da9496eead7478822cec86b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750749"
---
# <a name="unified-product-experience"></a>Experiencia unificada del producto

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cuando un ecosistema de negocio está compuesto de aplicaciones de Dynamics 365, como Finance, Supply Chain Management y Sales, los negocios a menudo usan estas aplicaciones en los datos del producto de origen. Esto se debe a que estas aplicaciones proporcionan una infraestructura robusta de producto complementada con conceptos sofisticados de precios y datos de inventario disponibles exactos. Las empresas que usan un sistema externo de (PLM) de administración del ciclo de vida del producto para abastecer los datos del producto pueden pasar productos de Finance and Operations a otras aplicaciones de Dynamics 365. La experiencia unificada de producto lleva el modelo de datos del producto integrado a Dataverse, de modo que todos los usuarios de aplicación incluidos los usuarios de Power Platform puedan aprovechar la riqueza de datos de producto que procede de aplicaciones de Finance and Operations.

A continuación se indica el modelo de datos del producto de Sales.

![Modelo de datos para productos de CE](media/dual-write-product-4.jpg)

A continuación se indica el modelo de datos de productos de las aplicaciones de Finance and Operations.

![Modelo de datos para productos de Finance and Operations](media/dual-write-products-5.jpg)

Estos dos modelos de datos se han integrado en Dataverse como se indica a continuación.

![Modelo de datos para productos de aplicaciones de Dynamics 365](media/dual-write-products-6.jpg)

Los mapas de tabla de escritura dual para productos se diseñaron para que los datos fluyan solo en una dirección y es una experiencia de tiempo casi real desde las aplicaciones de Finance and Operations hasta Dataverse. Sin embargo, la infraestructura del producto se ha creado abierta para hacerla bidireccional si procede. Aunque pueda personalizarla, este planteamiento es por su cuenta y riesgo, ya que Microsoft no recomienda este planteamiento.

## <a name="templates"></a>Plantillas

La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento. Como la tabla siguiente muestra, una colección de mapas de la tabla se crea para sincronizar los productos y la información relacionada.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365 | Descripción
-----------------------|--------------------------------|---
Productos liberados V2 | msdyn\_sharedproductdetails | La tabla **msdyn\_sharedproductdetails** contiene las columnas de las aplicaciones de Finance and Operations que definen el producto y que contienen la información de administración y financiera del producto. 
Productos únicos emitidos por Dataverse | Producto | La tabla **Producto** contiene las columnas que definen el producto. Incluye productos individuales (productos con producto del subtipo) y las variantes de producto. La tabla siguiente muestra las correlaciones.
Código de barras identificado por número de producto | msdyn\_productbarcodes | Los códigos de barras de producto se usan para identificar de forma única productos.
Configuración predeterminada de pedido | msdyn\_productdefaultordersettings
Configuración de pedido predeterminada específica del producto | msdyn_productdefaultordersettings
Grupos de dimensiones de producto | msdyn\_productdimensiongroups | El grupo de dimensiones de producto define qué dimensiones de producto definen el producto. 
Grupos de dimensiones de almacenamiento | msdyn\_productstoragedimensiongroups | El grupo de dimensiones de almacenamiento de producto representa el método usado para definir la ubicación del producto en el almacén.
Grupos de dimensiones de seguimiento | msdyn\_producttrackingdimensiongroups | El grupo de dimensiones de seguimiento del producto representa el método usado para seguir el producto en el inventario.
Colores | msdyn\_productcolors
Tamaños | msdyn\_productsizes
Estilos | msdyn\_productsytles
Configuraciones | msdyn\_productconfigurations
Colores de producto maestro | msdyn_sharedproductcolors | La tabla **Color del producto compartido** indica los colores que un producto maestro específico puede tener. Este concepto se migra a Dataverse para mantener los datos coherentes.
Tamaños de producto maestro | msdyn_sharedproductsizes | La tabla **Tamaño del producto compartido** indica el tamaño que un producto maestro específico puede tener. Este concepto se migra a Dataverse para mantener los datos coherentes.
Estilos de producto maestro | msdyn_sharedproductstyles | La tabla **Estilo del producto compartido** indica los estilos que un producto maestro específico puede tener. Este concepto se migra a Dataverse para mantener los datos coherentes.
Configuraciones de producto maestro | msdyn_sharedproductconfigurations | La tabla **Configuración del producto compartido** indica las configuraciones que un producto maestro específico puede tener. Este concepto se migra a Dataverse para mantener los datos coherentes.
Todos los productos | msdyn_globalproducts | La tabla Todos los productos contiene todos los productos disponibles en las aplicaciones de Finance and Operations, tanto los productos lanzados como los no lanzados.
Unidad | uoms
Conversiones de unidades | msdyn_ unitofmeasureconversions
Conversión de unidad de medida específica del producto | msdyn_productspecificunitofmeasureconversion
Categorías de productos | msdyn_productcategories | Cada una de las categorías de productos e información acerca de su estructura y funciones se incluyen en la tabla de categoría de producto. 
Jerarquías de categorías de producto | msdyn_productcategoryhierarhies | Use jerarquías de productos para categorizar o agrupar productos. Las jerarquías de categorías están disponibles en Dataverse utilizando la tabla de jerarquía de categoría de producto. 
Roles de jerarquía de categorías de producto | msdyn_productcategoryhierarchies | Las jerarquías de producto se pueden usar para distintos roles en D365 Finance and Operations. Especifican qué categoría se usa en cada rol en que la tabla de rol de categoría de producto se utiliza. 
Asignaciones de categorías de producto | msdyn_productcategoryassignments | Para asignar un producto a una categoría se puede usar la tabla de asignaciones de categorías de producto.

## <a name="integration-of-products"></a>Integración de productos

En este modelo, el producto se representa con la combinación de dos tablas en Dataverse: **Producto** y **msdyn\_sharedproductdetails**. Mientras que la primera tabla contiene la definición de un producto (el identificador único para el producto, el nombre del producto y la descripción), la segunda tabla contiene las columnas almacenadas en el nivel de producto. Se usará la combinación de estas dos tablas para definir el producto de acuerdo con el concepto de la referencia de almacén (SKU). Cada producto emitido tendrá su información en las tablas mencionadas (producto y detalles del producto compartido). Para realizar un seguimiento de todos los productos (lanzados y no lanzados), se utiliza la tabla **Productos globales**. 

Dado que el producto se representa como SKU, los conceptos de productos únicos, de productos maestros y de variantes de producto se pueden capturar en Dataverse de la siguiente manera:

- **Productos con producto de subtipo** son productos que se definen por sí mismos. No hay que definir dimensiones. Un ejemplo es un libro específico. Para estos productos, se crea una fila en la tabla **Producto** y se crea una fila en la tabla **msdyn\_sharedproductdetails**. No se crea ninguna fila de familia de productos.
- Los **productos maestros** se usan como productos genéricos bloqueo que contienen la definición y las reglas que determinan el comportamiento en procesos empresariales. Según estas definiciones, los productos únicos que se conozcan como variantes de producto pueden generarse. Por ejemplo, si camiseta es el producto maestro, puede tener Color y Tamaño como dimensiones. Se pueden lanzar variantes que tienen diferentes combinaciones de estas dimensiones, como una pequeña camiseta azul o una camiseta verde de tamaño mediano. En la integración, se crea una fila por variante en la tabla del producto. Esta fila contiene información específica de las variantes, como las diferentes dimensiones. La información genérica del producto se almacena en la tabla **msdyn\_sharedproductdetails**. (Esta información genérica se conserva en el producto maestro). La información de producto maestro se sincroniza con Dataverse tan pronto como se crea el producto maestro lanzado (pero antes de que se lancen variantes).
- **Productos únicos** hace referencia a todos los productos de subtipo de productos y a todas las variantes de producto. 

![Modelo de datos para productos](media/dual-write-product.png)

Con la función de doble escritura habilitada, los productos de Finance and Operations se sincronizarán en otros productos de Dynamics 365 en el estado **Borrador**. Se agregan a la primera lista de precios con la misma divisa. Es decir se agregan a la primera lista de precios de una aplicación de Dynamics 365 que coincida con la divisa de la tabla jurídica donde el producto se lance en una aplicación de Finance and Operations. Si no hay una lista de precios para la moneda dada, se creará automáticamente una lista de precios y se le asignará el producto. 

La implementación actual de los complementos de escritura dual que asocian la lista de precios predeterminada a la unidad busca la moneda asociada con la aplicación Finance and Operations y busca la primera lista de precios en la aplicación de interacción con el cliente, utilizando el orden alfabético en el nombre de la lista de precios. Para establecer una lista de precios predeterminada para una divisa específica cuando tiene varias listas de precios para esa divisa, debe actualizar el nombre de la lista de precios a un nombre que sea anterior en orden alfabético a cualquier otra lista de precios para esa misma divisa.

De forma predeterminada los productos de las aplicaciones de Finance and Operations se sincronizan con otras aplicaciones de Dynamics 365 en el estado **Borrador**. Para sincronizar el producto con el estado **Activo** para que pueda utilizarlo directamente en presupuestos de pedidos de ventas, por ejemplo, es necesario elegir la siguiente configuración: **Sistema > Administración > Administración del sistema > ventas** y seleccionar **Crear productos en estado activo = sí**. 

Cuando los productos están sincronizados, debe ingresar un valor para el campo **Unidad de ventas** en la aplicación Finance and Operations, porque es un campo obligatorio en Sales.

La creación de familias de productos desde Dynamics 365 Sales no es compatible con la sincronización de productos de escritura dual.

La sincronización de productos se produce de las aplicaciones de Finance and Operations a Dataverse. Esto significa que los valores de las columnas de la tabla del producto se pueden cambiar en Dataverse, pero cuando se activa la sincronización (cuando una columna de producto se modifica en una aplicación de Finance and Operations), se sobrescribirán los valores de Dataverse. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Dimensiones de producto 

Las dimensiones de un producto son las características que identifican una variante del producto. Las cuatro dimensiones de producto (El color, tamaño, estilo, y configuración) también se asignan a Dataverse para definir las variantes de producto. La ilustración siguiente muestra el modelo de datos para la dimensión del producto Color. El mismo modelo se aplica a los tamaños, a los estilos y a las configuraciones. 

![Modelos de datos para dimensiones de producto](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Cuando un producto tiene distintas dimensiones de producto (por ejemplo, un producto maestro tiene el tamaño y el color como dimensiones de producto), cada producto único (es decir, cada variante del producto) se define como una combinación de dichas dimensiones del producto. Por ejemplo, el número de producto B0001 es una camiseta negra extrapequeña, y el número de producto B0002 es una pequeña camiseta negra. En este caso, se definen las combinaciones de dimensiones de producto existentes. Por ejemplo, la camiseta del ejemplo anterior puede ser extrapequeña y negra, pequeña y negra, mediana y negra, o grande y negra, pero no puede ser extragrande y negra. Es decir las dimensiones de producto que un producto maestro puede tomar se especifican, y las variantes se pueden lanzar en función de estos valores.

Para realizar un seguimiento de las dimensiones de producto que un producto maestro puede aceptar, se crean y se asignan las tablas siguientes en Dataverse para cada dimensión de producto. Para obtener más información, consulte [Visión general de la información de producto](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Configuración predeterminada de pedido y Configuración de pedido predeterminada específica del producto

Los configuración de pedido predeterminada define el sitio y el almacén de dónde se originan o almacenan los artículos, las cantidades mínimas, máximas, múltiples y estándar que se usarán en la gestión de comercio o de inventario, los plazos, el indicador de detención y el método prometedor del pedido. Este información está disponible en Dataverse mediante la configuración de pedido predeterminada y la entidad de configuración de pedido predeterminada específica del producto. Puede leer más información sobre la funcionalidad en el [Tema de la configuración de pedido predeterminada](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unidad de medida y conversiones de unidad de medida

Las unidades de medida y sus conversiones respectivas están disponibles en el Dataverse según se indica en el modelo de datos indicado en el diagrama.

![Modelo de datos para unidad de medida](media/dual-write-product-three.png)

El concepto de unidad de medida está integrado entre aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365. Para cada clase de unidad en una aplicación de Finance and Operations se crea un grupo de unidades en una aplicación de Dynamics 365, que contiene las unidades que pertenecen a la clase de unidad. Una unidad base predeterminada también se crea para cada grupo de unidad. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Sincronización inicial de datos de unidades coincidentes entre Finance and Operations y Dataverse

### <a name="initial-synchronization-of-units"></a>Sincronización inicial de unidades

Cuando la doble escritura está habilitada, las unidades de las aplicaciones de Finance and Operations se sincronizan con otras aplicaciones de Dynamics 365. Los grupos de unidades sincronizados desde aplicaciones de Finance and Operations con Dataverse tienen un indicador establecido que indica que se “mantienen externamente”.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Conciliación de unidades y datos de clases de unidades/grupos de Finance and Operations y otras aplicaciones de Dynamics 365

En primer lugar, es importante tener en cuenta que la clave de la integración de la unidad es msdyn_symbol. Por lo tanto, este valor debe ser único en Dataverse u otras aplicaciones de Dynamics 365. Dado que en otras aplicaciones de Dynamics 365 es el par “identificación del grupo de unidades” y “Nombre” el que define la exclusividad de una unidad, es necesario que tenga en cuenta diferentes escenarios para conciliar datos entre aplicaciones de Finance and Operations y Dataverse.

Para las unidades que concilian/se superponen en aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365:

+ **La unidad pertenece a un grupo de unidades en otras aplicaciones de Dynamics 365 que corresponde a la clase de unidad asociada en aplicaciones de Finance and Operations**. En este caso, la columna msdyn_symbol de otras aplicaciones de Dynamics 365 se debe rellenar con el símbolo de unidad de aplicaciones de Finance and Operations. Por lo tanto, cuando los datos se concilien, el grupo de unidades se establecerá como “externamente mantenido” en otras aplicaciones de Dynamics 365.
+ **La unidad pertenece a un grupo de unidades en otras aplicaciones de Dynamics 365 que no corresponde a la clase de unidad asociada en las aplicaciones de Finance and Operations (no hay ninguna clase de unidad en las aplicaciones de Finance and Operations para la clase de unidad en las otras aplicaciones de Dynamics 365).** En este caso, el msdyn_symbol se debe rellenar con una cadena aleatoria. Tenga en cuenta que este valor debe ser único en otras aplicaciones de Dynamics 365.

Para las unidades y clases de unidades de Finance and Operations que no existan en otras aplicaciones de Dynamics 365:

Como parte de la doble escritura, los grupos de unidades de aplicaciones de Finance and Operations y sus correspondientes unidades se crean y sincronizan en otras aplicaciones de Dynamics 365 y Dataverse y el grupo de unidades se establecerá como “externamente mantenido”. No se requiere ningún esfuerzo de arranque adicional.

Para unidades de otras aplicaciones de Dynamics 365 que no existan en aplicaciones de Finance and Operations:

La columna msdyn_symbol se debe completar para todas las unidades. Las unidades se pueden crear siempre en aplicaciones de Finance and Operations en la clases de unidad correspondiente (si existe). Si no existe la clase de unidad, primero debe crearse la clase de unidad (tenga en cuenta que no puede crear una clase de unidad en aplicaciones de Finance and Operations, excepto a través de la extensión si está extendiendo la enumeración) que corresponda con el otro grupo de unidad de aplicaciones de Dynamics 365. A continuación, podrá crear la unidad. Tenga en cuenta que el símbolo de unidad en las aplicaciones de Finance and Operations tiene que ser el msdyn_symbol especificado previamente en otras aplicaciones de Dynamics 365 para la unidad.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Directivas de productos: grupos de dimensionies, seguimiento y almacenamiento

Las directivas de producto son conjuntos de directivas que se usan para definir productos y sus funciones de inventario. El grupo de dimensiones de producto, el grupo de dimensiones de seguimiento del producto y el grupo de dimensiones de almacenamiento pueden encontrarse como directivas de producto. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Jerarquías de productos

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Clave de integración para los productos 

Para identificar de forma única productos entre Dynamics 365 for Finance and Operations y productos de Dataverse las claves de integración se usan. Para los productos, **(productnumber)** es la clave única que identifica un producto en Dataverse. Está compuesto por la concatenación de: **(empresa, msdyn_productnumber)**. **empresa** indica la entidad jurídica en Finance and Operations y **msdyn_productnumber** indica el número de producto del producto específico en Finance and Operations. 

Para usuarios de otras aplicaciones de Dynamics 365, el producto se identifica en la interfaz de usuario con **msdyn_productnumber** (tenga en cuenta que la etiqueta de la columna es **Número de producto**). En el formulario de producto se muestran la empresa y el msydn_productnumber. Sin embargo, la columna (productnumber), la clave única para un producto, no se muestra. 

Si construye aplicaciones en Dataverse, debe prestar atención al uso de **Número de producto** (el ID de producto único) como clave de integración. No utilice **msdyn_productnumber**, porque no es único. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Sincronización inicial de productos y migración de datos de Dataverse a Finance and Operations

### <a name="initial-synchronization-of-products"></a>Sincronización inicial de productos 

Cuando la doble escritura está habilitada, los productos de las aplicaciones Finance and Operations se sincronizan con Dataverse y con aplicaciones de Customer Engagement. Los productos creados en Dataverse y otras aplicaciones de Dynamics 365 antes de la publicación de la doble escritura no se actualizarán ni se conciliarán con datos de productos de aplicaciones Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Conciliación de datos de producto de Finance and Operations y otras aplicaciones de Dynamics 365

Si los mismos productos se mantienen (solapan/concilian) en Finance and Operations y en Dataverse y otras aplicaciones de Dynamics 365, al habilitar la escritura dual, ocurrirá la sincronización de productos de Finance and Operations y filas duplicadas aparecerán en Dataverse para el mismo producto.
Para evitar la situación anterior, si otras aplicaciones de Dynamics 365 tienen productos que se solapan/coinciden con Finance and Operations, el administrador que habilita la escritura dual debe arrancar las columnas **Empresa** (ejemplo: “USMF”) y **msdyn_productnumber** (ejemplo: “1234:Black:S”) antes de que se produzca la sincronización de productos. Es decir, estas dos columnas del producto en Dataverse se deben rellenar con la empresa respectiva de Finance and Operations con la que el producto debe correlacionarse y con su número de producto. 

A continuación, cuando la sincronización se habilita y tiene lugar, los productos de Finance and Operations se sincronizarán con los productos asignados en Dataverse y otras aplicaciones de Dynamics 365. Esto es aplicable para productos únicos y variantes de producto. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migración de datos de producto de otras aplicaciones de Dynamics 365 a Finance and Operations

Si otras aplicaciones de Dynamics 365 tienen productos que no están presentes en Finance and Operations, el administrador puede usar primero **EcoResReleasedProductCreationV2Entity** para importar los productos a Finance and Operations. Y en segundo lugar, concilie los datos de productos de Finance and Operations y otras aplicaciones de Dynamics 365 como se describe anteriormente. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
