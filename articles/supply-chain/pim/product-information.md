---
title: Información general del producto
description: Este tema proporciona información acerca de la gestión de información de productos. La gestión de información de productos funciona con una definición de producto, una clasificación e identificadores compartidos entre todas las entidades jurídicas, y también de configuraciones específicas de un producto que se ajusten a los procesos empresariales.
author: benebotg
manager: tfehr
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c118bc37a26d6d3a65905f2fd955ceb3554e9557
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980897"
---
# <a name="product-information-overview"></a>Información general del producto

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de la gestión de información de productos. La gestión de información de productos funciona con una definición de producto, una clasificación e identificadores compartidos entre todas las entidades jurídicas, y también de configuraciones específicas de un producto que se ajusten a los procesos empresariales. 

La información de producto es la base de la cadena de suministro y de las aplicaciones de Commerce en todos los sectores. Hace referencia a los procesos y las tecnologías que se centran en gestionar la información de productos de forma centralizada (por ejemplo, en varias cadenas de suministros). Es esencial que se utilicen las definiciones de producto, la documentación, los atributos y los identificadores compartidos. En los varios módulos de una solución empresarial, la información y la configuración específicas de un producto son necesarias para administrar procesos de negocio relacionados con productos, familias de productos o categorías de productos específicas.

## <a name="product-definition"></a>Definición de producto

Un producto se define principalmente con un número de producto, un nombre y una descripción. Sin embargo, otros datos también son necesarios para describir un producto o servicio:

- Tipo de producto: artículo o servicio
- Subtipo de producto: productos únicos o productos maestros
- Definición del modelo de variante del producto:

     - Dimensiones de productos y grupos de dimensiones
     - Nomenclatura de producto
     - Modelos de configuración del producto

- Asociación del producto con una o más categorías
- Definición de los atributos de producto y categoría
- Imágenes del producto
- Archivos adjuntos
- Unidades de medida y conversiones relacionadas
- Traducciones de todos los nombres y descripciones

## <a name="distribution-export-and-import-of-product-data"></a>Distribución, exportación e importación de datos de producto

La definición de producto se puede crear en Supply Chain Management. También se puede importar de la gestión del ciclo de vida del producto (PLM), de la gestión de datos del producto (PDM) o de sistemas de gestión de la información del producto (PIM). Cuando se usa más de una instancia de Supply Chain Management, una instancia se suele usar como el maestro de los datos del producto para el resto de las instancias. Este enfoque es compatible con un gran conjunto de entidades de datos que habilitan la exportación e importación de datos de definición de productos desde una instancia a otra.

Para apoyar la distribución de los datos de productos a varias instancias, Supply Chain Management le permite usar Common Data Service. Las definiciones de producto se pueden exportar de una instancia de Supply Chain Management a Common Data Service. A continuación las definiciones de producto se pueden utilizar para aprovisionar aplicaciones empresariales, como Dynamics 365 Sales, con datos de productos.

Tenga en cuenta que, en organizaciones dinámicas y ágiles, los datos de la información de producto cambia cada día. Por lo tanto, el mantenimiento de datos de producto reales y precisos es un proceso empresarial crítico en sí mismo.

## <a name="product-masters-and-product-variants"></a>Productos maestros y variantes de productos

En un mundo ágil, donde los productos deben ajustarse rápidamente a los requisitos de cliente, las definiciones de producto especifican un conjunto de productos en lugar de productos únicos. En Supply Chain Management, los productos genéricos se conocen como *productos maestros*. Los productos maestros albergan la definición y las reglas que especifican cómo se describen los productos únicos y se comportan en los procesos empresariales. Basándose en estas definiciones, pueden generarse los productos únicos. Estos productos únicos se conocen como *variantes de producto*.

Un producto maestro se asocia a un grupo de dimensiones de producto y a una tecnología de configuración para especificar las reglas de negocio. Las dimensiones del producto (color, tamaño, estilo y configuración) son un conjunto concreto de atributos que se pueden usar en la aplicación para definir y para seguir comportamientos específicos de productos relacionados. Estas dimensiones también ayudan a los usuarios a buscar e identificar los productos.

## <a name="configuration-technologies"></a>Tecnologías de configuración

Puede elegir entre tres tecnologías de configuración:

- Las dimensiones de producto predefinidas definen las variantes predefinidas. La definición de variante incluye la definición de una combinación válida específica de dimensiones, como color, estilo y tamaño. Cada combinación produce una variante del producto única.
- La configuración basada en dimensiones se suele usar en los escenarios de fabricación y le permite usar la dimensión de configuración en la definición de las listas de materiales (L. MAT). Tras seleccionar una configuración específica, el sistema utiliza el subconjunto de líneas de L. MAT válidas para esa configuración para la planificación y la producción. Este concepto también se conoce como *L. MAT global* porque una lista de materiales compartida se utiliza para todas las configuraciones de un producto.
- La configuración basada en restricciones utiliza un modelo de configuración de productos para describir todos los atributos y componentes posibles necesarios para describir a todas las variantes posibles de un producto en un único modelo. Las restricciones de combinaciones de atributos se pueden describir mediante expresiones regulares o restricciones basadas en tablas. Los modelos de configuración y los configuradores se vuelven más importantes en la gestión de la información de productos y se utilizan en todas las industrias.

Cuando planifique la implementación de Supply Chain Management, es muy importante que elija la tecnología de configuración correcta para un proceso empresarial. Un producto no se puede convertir de un modelo a otro después de la implementación.

## <a name="product-variant-model-definition-workspace"></a>Espacio de trabajo Definición de modelo de variante del producto

El espacio de trabajo **Definición de modelo de variante del producto** ofrece una visión general de los productos maestros. También muestra el estado de liberación de maestros y de variantes relacionadas con las entidades jurídicas específicas.

## <a name="released-products"></a>Productos emitidos

Los productos emitidos a una entidad jurídica específica se conocen como *productos emitidos*. Los productos se pueden liberar en grandes cantidades a una entidad jurídica o a muchas entidades jurídicas al mismo tiempo. Dado que podría ser necesario agregar las diferentes propiedades y atributos de los productos por entidad jurídica, el espacio de trabajo **Mantenimiento de producto emitido** le permite supervisar y completar los productos emitidos recientemente en cada entidad jurídica, o en las suborganizations de una entidad jurídica.

### <a name="released-product-maintenance-workspace"></a>Espacio de trabajo Mantenimiento de producto emitido

Puede configurar el espacio de trabajo **Mantenimiento de producto emitido** desde el elemento de menú **Configurar mi espacio de trabajo** . Seleccione una jerarquía de categoría y una categoría por las que filtrar el espacio de trabajo. Para ajustar los datos relevantes de productos en el espacio de trabajo, también puede definir, en días, los límites de tiempo para **Productos emitidos recientemente** y **Productos emitidos detenidos**.

El espacio de trabajo consiste en un resumen de mosaicos y dos listas. La lista **Casos abiertos** muestra casos de cambios en productos que tienen productos en la jerarquía de categoría de productos seleccionada que no están completados y cerrados. La lista **Emitidos recientemente** muestra productos que se han emitido en el límite de tiempo establecido en la configuración del espacio de trabajo. Para cada artículo de la lista, se ejecuta la validación y se muestra el estado de validación. Este estado puede indicar que los parámetros necesarios para la entidad jurídica no se han completado. En la lista, puede acceder directamente a las páginas **Detalles de producto emitido**, **Mantenimiento de atributo del producto**, **Mantenimiento de la categoría de producto**, **Configuración predeterminada de pedido** y **Traducciones de texto** para completar la configuración necesaria del producto.

### <a name="manually-creating-a-new-released-product"></a>Creación manual de un nuevo producto emitido

Puede crear manualmente un producto emitido en una sola ejecución, en función de los procesos empresariales de la organización y de las reglas sobre si esta función se debe usar. Esta función crea un nuevo producto y lo emite automáticamente a la entidad jurídica actual. Para crear un nuevo producto, haga clic en **Productos emitidos** en el espacio de trabajo **Mantenimiento de producto emitido** o en la página de lista **Producto emitido**.
