---
title: Identificadores de producto
description: Este tema proporciona información sobre los distintos tipos de identificadores de producto y explica cómo puede agregar los identificadores de producto en sus datos de producto.
author: cvocph
manager: tfehr
ms.date: 03/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductEntityIdentifierCode, EcoResProductListPage, EcoResProductDetailsExtended, EcoResProductVariantsPerCompany
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 1e771d6cbad3faf99f88782d424273f0d8ac98b4
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574206"
---
# <a name="product-identifiers"></a>Identificadores de producto

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre los distintos tipos de identificadores de producto y explica cómo puede agregar los identificadores de producto en sus datos de producto.

Al trabajar con los productos en planta o en un almacén en Microsoft Dynamics ERP o Microsoft Dynamics CRM, debe tener una buena estrategia para identificar los productos y variantes de producto.

## <a name="unique-product-numberproduct-id"></a>Número de producto único/ID de producto

En Dynamics 365 Supply Chain Management el identificador principal de un producto es el número de producto (es decir, el identificador único del producto). Este número se puede generar automáticamente mediante una secuencia numérica, o se puede asociar manualmente a un producto. Para las variantes de producto, los números se pueden definir a través de la plantilla de nomenclatura de producto.

En muchos casos, el número de producto no se crea originalmente en Dynamics 365 Supply Chain Management. En su lugar, se ha asociado a un producto en un sistema de administración del ciclo de vida del producto (PLM) o un sistema de gestión de datos de producto (PDM). En este caso, se utilizan entidades de datos para importar los productos y las variantes de producto. Supply Chain Management usa los números de todas las operaciones.

Cuando implementa Supply Chain Management debe prestar especial atención a su estrategia para los números de producto. Un buen sistema de numeración mejora los flujos de logística y ayuda a evitar errores. Un buen identificador de producto tiene un máximo de 15 caracteres. Idealmente, tiene menos de 10 caracteres y no incluye más de cinco caracteres de clasificación. También puede usar nombres de búsqueda para habilitar búsquedas rápidas. Un nombre de búsqueda es un nombre extra que representa las clasificaciones de un producto.

Cuando use Microsoft Dataverse, el número del producto en Supply Chain Management es también el número de producto en Microsoft Dataverse. Las variantes de producto se sincronizan con Dataverse como productos únicos.

## <a name="item-number-and-product-dimensions"></a>Número de artículo y dimensiones de producto

El número de artículo es el identificador del producto que usa una entidad jurídica específica. Idealmente, el número de artículo debe ser idéntico al número de producto. Si la nomenclatura difiere según la entidad jurídica, resultará difícil seguir un producto en la cadena de suministro y se introducen procesos de reetiquetado y referenciación onerosos. Para compatibilidad con versiones anteriores (es decir, con Microsoft Dynamics AX 2009 y anterior), hemos preservado este modelo. Sin embargo, se recomienda eliminar los identificadores específicos de las entidades jurídicas siempre que pueda y que usar el número de producto único como identificador principal en su lugar.

Además, una variante del producto no se podrá identificar exclusivamente por un código de artículo. Siempre se requiere la combinación de un número de artículo y de todas las dimensiones de producto que se definen en el producto maestro. Este requisito puede convertirse en un obstáculo y retrasar los procesos de la identificación. Por este motivo, también se recomienda usar el número de producto único en lugar del número de artículo siempre que pueda.

Muchas páginas aún tienen el número de artículo y las dimensiones del producto como los identificadores principales. Sin embargo, los números de producto se pueden usar para realizar búsquedas. En **Ventas y marketing** &gt; **Configuración** &gt; **Buscar** &gt; **Parámetros de búsqueda**, puede cambiar la búsqueda, de modo que utilice los números de producto en lugar de números de artículo como estrategia de búsqueda principal. Si establece la opción **Habilitar la búsqueda de productos** en **Sí**, la búsqueda muestra no sólo los productos maestros sino las variantes de producto. Para obtener más información, consulte [Buscar los productos y variantes de producto durante la entrada de pedidos](search-products-product-variants.md).

Además, podrá realizar búsquedas y filtros en el código de producto, el nombre y la descripción del producto y los id. de la dimensión del producto de la variante del producto. Al seleccionar una variante, el número de artículo relacionado y todos los id. de la dimensión del producto se seleccionarán. Por lo tanto, puede encontrar más fácilmente la variante correcta y seleccionarla. Este valor es muy recomendable si usa las variantes de producto y el número de producto único como los identificadores principales para los productos. La única excepción podría ser la industria de la moda, donde los procesos de negocio requieren a menudo que seleccione el maestro antes de seleccionar una variante. Debe evaluar con cuidado esta opción antes de implementar el sistema de numeración.

> [!NOTE]
> El número de artículo para un producto no se puede cambiar una vez que existan una o más transacciones para ese producto.

## <a name="product-name-and-description"></a>Nombre y descripción del producto

El nombre y la descripción del producto son los identificadores legibles de un producto y se pueden mantener en varios idiomas. De forma predeterminada, el cliente de Supply Chain Management muestra toda la información de producto en el idioma predeterminado de la empresa, no en el idioma del usuario. Sin embargo, los nombres de producto y las descripciones traducidas se usan en toda la comunicación con los clientes y los proveedores. Las traducciones se basan en el código de idioma del cliente y las cuentas de proveedor.

Para las variantes de producto, los nombres de producto se pueden generar a través de una plantilla de nomenclatura de producto. Dado que no hay requisitos de que los nombres de producto sean únicos, puede encontrar varios productos que tengan el mismo nombre.

## <a name="product-and-item-search-names"></a>Nombres de búsqueda del producto y de artículo

Supply Chain Management proporciona un nombre de búsqueda secundario para los productos y también para artículos (productos emitidos). Este nombre de búsqueda no tiene que ser único, y puede modificarse tras la creación de un producto o una variante del producto. Se recomienda que use el nombre de búsqueda para buscar productos por categorías. Los nombres de búsqueda habilitan búsquedas rápidas, especialmente en procesos de ventas y compras.

El nombre de búsqueda también puede contener un identificador de producto de clientes o proveedores, o algún otro identificador externo del producto, si este identificador externo es el criterio de búsqueda principal para un producto.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Identificadores externos de producto (identificadores de cliente y proveedor)

Para los productos liberados, puede mantener los números de artículo, los nombres de artículo y las descripciones del artículo que utiliza el cliente o proveedor. Las referencias se muestran en los documentos externos, como pedidos de ventas, pedidos de compras, albaranes y facturas. En la versión actual de Supply Chain Management, las referencias externas no se muestran en las páginas básicas de las operaciones. La única excepción es el número de artículo del proveedor. Este número se muestra en el cuadro de diálogo **Información del producto** si se define un proveedor predeterminado para el producto liberado.

Puede mantener los identificadores externos de producto por producto liberado, variante de producto liberado, cliente, grupo de clientes, proveedor o grupo de proveedores.

En la página **Productos emitidos**, siga uno de estos pasos.

- Para clientes, en la pestaña **Venta**, en el grupo **Información relacionada**, selecione **Descripción externa del artículo**.
- Para proveedores, en la pestaña **Compra**, en el grupo **Información relacionada**, selecione **Descripción externa del artículo**.

En la página **Descripciones externas de artículos**, puede asociar el número de artículo del cliente o de proveedor a un producto liberado. Esta asociación se debe hacer para cada entidad jurídica. La información siguiente se puede capturar. Desafortunadamente, las etiquetas son ligeramente engañosas en la versión actual de Supply Chain Management. Sin embargo, estas etiquetas podrían cambiar en una versión futura.

| Campo | Información del cliente correspondiente | Información del proveedor correspondiente |
|-------|------------------------------------|----------------------------------|
| Código de artículo externo | Código de artículo del cliente | Número de artículo del proveedor. |
| Descripción | El nombre que el cliente asocia al artículo | El nombre que el proveedor asocia al artículo |
| Texto de artículo externo | Descripción de artículo del cliente. | Descripción de artículo del proveedor. |

Si muchos clientes o proveedores utilizan los mismos números de artículo (como con una asociación de compras o de un grupo de Commerce, por ejemplo), puede crear grupos de cliente o de proveedores para simplificar el mantenimiento de la información de producto externa.

- Para los grupos de clientes, vaya a **Ventas** &gt; **Configuración** &gt; **Artículos** &gt; **Descripción externa de artículos** para crear y mantener los grupos y números de artículos relacionados. Para asociar clientes a un grupo, vaya a **clientes** &gt; **Clientes** &gt; **Todos los clientes** y, a continuación, en la ficha desplegable **Valores predeterminados del pedido de ventas**, especifique un valor en el campo **Artículo - Grupo de clientes**.
- Para los grupos de proveedores, vaya a **Adquisición y abastecimiento** &gt; **Configuración** &gt; **Grupo de descripción externa de artículos** para crear y mantener los grupos y números de artículos relacionados. Para asociar proveedores a un grupo, vaya a **Proveedores** &gt; **Proveedores** &gt; **Todos los proveedores** y, a continuación, en la ficha desplegable **Valores predeterminados del pedido de compra**, especifique un valor en el campo **Artículo - Grupo de proveedores**.
 
## <a name="bar-codes"></a>Códigos de barras

Si desea usar un escáner de códigos de barras para identificar productos, el identificador de producto debe cumplir los requisitos del estándar de código de barras que se usa. Por lo tanto, los códigos de barras no contienen normalmente el número de producto sin formato pero un número que se genera específicamente para la tecnología del código de barras seleccionado. Puede mantener varios códigos de barras por tipo de código de barras. Puede asociar incluso el mismo código de barras a varios productos y después seleccionar la asociación activa real al digitalizar un código de barras.

Antes de definir códigos de barras, puede definir una o más configuraciones de código de barras. Las configuraciones de código de barras pueden ayudar a validar que los códigos de barras sigan las instrucciones necesarias, y que puedan por tanto imprimirse y procesarse correctamente. También puede mantener códigos de barras especiales para cantidades de producto específicas.

Recomendamos que utilice la configuración de código de barras para mantener los códigos del número de artículo comercial global (GTIN) o del número de artículo internacional (EAN).

Para mantener códigos de barras en la página **Productos liberados**, en la pestaña **Gestionar el inventario**, en el grupo **Almacén** seleccione **Códigos de barras**.

## <a name="gtin-codes"></a>Códigos GTIN

En e-commerce, es esencial que todas las partes hablen un idioma en común y consulten los productos mediante un conjunto en común de identificadores. Por lo tanto, algunos sectores confían en [GTIN](https://www.gs1.org/id-keys/gtin), que es un sistema de numeración de artículos global que GS1 facilita.

Recomendamos que se mantenga el GTIN como código de barras. Sin embargo, también puede mantenerlo en la página **Artículo - GTIN**. Para abrir esta página, en la página **Productos liberados**, en la pestaña **Gestionar el inventario**, en el grupo **Almacén** seleccione **Códigos GTIN**. El GTIN no se mantiene como número global. En su lugar, se mantiene por entidad jurídica.

En Supply Chain Management define variantes de embalaje en operaciones de almacén definiendo las unidades de medida específicas. Por ejemplo, un artículo puede estar almacenado por piezas, por agrupaciones de seis, en bandejas de 18, o en pallets completos. Una unidad de medida específica se definirá para cada una de estas variantes de embalaje. Dado que el GTIN está relacionado normalmente con la unidad de embalaje de un producto, la página **Artículo - GTIN** permite mantener varios códigos GTIN por producto y unidad de medida. Sin embargo, no puede utilizar el mismo código GTIN más de una vez para diferentes artículos o variantes de producto de una entidad jurídica.

Para mantener **Códigos GTIN** en la página **Productos liberados** , en la pestaña **Gestionar el inventario**, en el grupo **Almacén** seleccione **GTIN**.

## <a name="external-codes"></a>Códigos externos

Los códigos externos se pueden definir para varias entidades. Por ejemplo, puede definir códigos externos para identificar productos y productos liberados. Estos códigos externos se pueden utilizar para asociar códigos estadísticos o códigos de impuestos a productos liberados y variantes de productos liberados. Los códigos externos se definen por la entidad jurídica y el tipo de código. Deben ser únicos por entidad jurídica, tipo de código, y referencia de tabla.

Desafortunadamente, no hay función estándar que le permita buscar los productos por códigos externos.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Entidades de datos que se usan para importar y exportar identificadores de producto

| Nombre de entidad | Identificadores de importación | Identificadores de exportación | Comentarios |
|-------------|--------------------|--------------------|----------|
| Productos V2 | Número de producto, nombre de búsqueda de producto, nombre de producto, descripción del producto | Número de producto, nombre de búsqueda de producto, nombre de producto, descripción del producto | En función de la configuración de la entidad y la secuencia numérica para el número de producto, el número de producto se puede crear automáticamente en el momento de la importación. |
| Variantes del producto | Número de producto, nombre de búsqueda de producto, nombre de producto, descripción del producto | Número de producto, nombre de búsqueda de producto, nombre de producto, descripción del producto | Según la plantilla de la nomenclatura de producto, el número de producto se puede crear automáticamente en el momento de la importación. Sin embargo, puede importar cualquier número de producto único y dicho número de producto no necesitará seguir la estructura de las plantillas de la nomenclatura de producto. |
| Traducciones del producto | Nombre de producto, descripción del producto | Nombre de producto, descripción del producto | Esta entidad sobrescribe cualquier lenguaje. Cuando el nombre o la descripción del idioma principal de la entidad jurídica se sobrescribe, el nombre y la descripción del producto en sí se cambian. |
| Creación de productos liberados V2 | Número de artículo, número de producto, nombre de búsqueda del artículo| Número de artículo, número de producto, nombre de búsqueda del artículo, nombre de búsqueda de producto, nombre de producto | Esta entidad puede ser un desafío cuando las secuencias numéricas se usan durante la creación de nuevos productos liberados. Tanto la secuencia numérica **Código de artículo** como la secuencia numérica **Código de producto** tienen una influencia. Sin embargo, la secuencia numérica **Código de artículo** es por la entidad jurídica, mientras que la secuencia numérica **Número de producto** es global. Por lo tanto, no se recomienda usar la secuencia del número **Código de artículo** al implementar los productos recién liberados. Obviamente, cuando use la entidad para liberar un producto existente, el número de producto debe darse en la entidad. Para obtener más información, consulte la sección "secuencias numéricas de producto y artículo" en este tema. |
| Variantes de productos emitidos | Código de artículo, dimensiones de producto, número de producto | Número de producto, nombre de búsqueda de producto, nombre de producto, descripción del producto, dimensiones de producto | Al igual que la entidad **Variantes del producto**, esta entidad puede ser utilizada para crear nuevos productos que sigan la plantilla de la nomenclatura de producto o utilicen sus propios números de producto para la variante. |
| Descripción externa de artículos para clientes | El código de artículo del cliente, nombre de artículo del cliente, descripción del cliente, la cuenta del cliente | El código de artículo del cliente, nombre de artículo del cliente, descripción del cliente, la cuenta del cliente | Un grupo de clientes (por ejemplo, asociación del comprador) se puede agregar a un grupo mediante la entidad **Grupos de clientes de la descripción externa de artículos**. |
| Descripción externas de artículos para proveedores | Código de artículo de proveedor, nombre de artículo de proveedor, descripción del proveedor, cuenta de proveedor | Código de artículo de proveedor, nombre de artículo de proveedor, descripción del proveedor, cuenta de proveedor | Un grupo de proveedores (por ejemplo, asociación de compras u organización industrial) se puede agregar a un grupo mediante la entidad **Grupos de proveedores de la descripción externa de artículos**. |
| Códigos de barras de artículos | Código de barras | Código de barras | En el momento de la importación, debe hacer referencia a una configuración de código de barras que se define en el sistema de destino. Las referencias importadas del código de barras se validan con esa configuración de código de barras y se rechazan si no coinciden los códigos de barras con los requisitos que se definen en dicha configuración. |
| Códigos externos para productos liberados | Código externo | El código externo, clases de código externo, número de artículo | Los códigos externos son por entidad jurídica. Para la importación, debe hacer referencia a una clase del código definido. Importe las clases de códigos mediante la entidad **Clases de código externo para productos liberados**. |
| Códigos externos para variantes de productos liberados | Código externo | El código externo, clases de código externo, número de artículo, dimensiones del producto | Los códigos externos son por entidad jurídica. Para la importación, debe hacer referencia a una clase del código definido. Importe las clases de códigos mediante la entidad **Clases de código externo para productos liberados**. Esta entidad se refiere a las variantes de producto por el número de artículo y las dimensiones del producto. |
| Códigos externos de identificador del número de producto derivado de las variantes de productos liberados | Código externo | El código externo, clases de código externo, número de producto | Los códigos externos son por entidad jurídica. Para la importación, debe hacer referencia a una clase del código definido. Importe las clases de códigos mediante la entidad **Clases de código externo para productos liberados**. Esta entidad se refiere a las variantes de producto por el número de producto de la variante. (De la versión siguiente) |
| GTIN | No aplicable | No aplicable | Actualmente, no hay entidad específica que se use para importar y exportar códigos GTIN. Recomendamos que utilice la entidad **Códigos de barras de artículos** en su lugar. |
| Entidad de identificador de common data service de la entidad del producto | No aplicable | Número de artículo, nombre de búsqueda del artículo, nombre de búsqueda del producto, código de artículo de proveedor, número de artículo del cliente, códigos externos, códigos GTIN, códigos de barras | Esta entidad consolida todos los identificadores en un modelo de datos, para poder utilizar una única interfaz para exportar fácilmente todos los identificadores y sus tipos relacionados. Use la entidad **Código de identificador de entidad de producto** para exportar códigos y descripciones de identificador. Use la entidad **Ámbito del identificador de entidad de producto** para exportar información adicional de ámbito a un identificador, como la parte, la entidad jurídica, la cantidad, o la unidad. |

### <a name="product-and-item-number-sequences"></a>Secuencias de producto y número de artículo

En el formulario dos secuencias númerica diferentes:

- La secuencia numérica **Código de producto** del código de producto global.
- La secuencia del número **Código de artículo** del artículo por entidad jurídica

> [!NOTE]
> Debe usar el número de artículo como identificador independiente solo al migrar entidades jurídicas diferentes desde orígenes diferentes que tenían diferentes sistemas de numeración. Debe intentar siempre utilizar un identificador de producto que sea único en todas las entidades jurídicas. Por lo tanto, debe establecer la opción **Manual** en **Sí** para la secuencia del número **Código de artículo**. De esta manera, el número de artículo seguirá al número de producto en la creación. Si Supply Chain Management no es el sistema principal para nuevos números de producto, debe establecer la opción **Manual** en **Sí** para las secuencias numéricas **Código de artículo** y **Número de producto**.

Cuando utilice la entidad **Producto liberado creación V2** para crear productos, los valores múltiples pueden afectar a cómo las secuencias numéricas se usan para crear el número de producto y el número de artículo:

- Configuración de la secuencia de números **Código de producto**
- Configuración de la secuencia de números **Código de artículo**
- La asignación del número de artículo 
- La asignación del número de producto

La tabla siguiente proporciona una visión general de los resultados de la importación y de la creación manual cuando hay combinaciones específicas de los valores de la secuencia numérica y la asignación de campos.

| Secuencia numérica de código de producto | Secuencia numérica del número de artículo | Asignación del número del artículo | Asignación del número de producto | Resultado de una importación de entidad | Resultado de la creación manual | Conclusión |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Manual = No | Manual = No | Sin asignación | Sin asignación | Los números de producto usan la secuencia numérica **Código de producto**. Los números de artículo usan la secuencia numérica **Código de artículo**. | Los números de producto usan la secuencia numérica **Código de producto**. Los números de artículo usan la secuencia numérica **Código de artículo**. | Con esta configuración, los números de producto seguirán la secuencia de números de producto y los números de artículo seguirán la secuencia de números de artículo. Sin embargo, esta configuración no funcionará si hay más de un elemento (fila) para importar. |
| Manual = No | Manual = Sí | Generar automáticamente | Sin asignación | Los números de producto y códigos de artículo usan la secuencia numérica **Código de artículo**. | Los números de producto y códigos de artículo usan la secuencia numérica **Código de producto**. | Los números de producto y códigos de artículo seguirán la secuencia numérica del producto. Este es el enfoque recomendado para importar productos a granel con la entidad de datos V2 de creación de productos liberados.<br><br>Solo puede utilizar este enfoque cuando importe elementos de forma masiva (varias filas) y cuando no esté creando elementos a través de la interfaz de usuario. Si necesita tanto realizar una importación masiva como crear productos a través de la interfaz de usuario, utilice el procedimiento de la siguiente fila de esta tabla. Para pasar de usar un enfoque de importación masiva a usar la interfaz de usuario para importar y crear productos manualmente, debe ajustar manualmente el **Siguiente numero** en la secuencia del número de artículo para que coincida con el **Siguiente numero** en la secuencia de números de número de producto. Luego, podría cambiar al enfoque de la siguiente fila de esta tabla. |
| Manual = No | Manual = Sí | Sin asignación | Sin asignación | Los números de producto y códigos de artículo usan la secuencia numérica **Código de producto**. | Los números de producto y códigos de artículo usan la secuencia numérica **Código de producto**. | Los números de producto y códigos de artículo usarán la secuencia numérica del producto. Sin embargo, esta configuración no funcionará si hay más de un elemento (fila) para importar.<br><br>Debe utilizar este enfoque si necesita importar productos utilizando las entidades (solo se puede importar una fila a la vez) y crear productos a través de la interfaz de usuario. |
| Manual = Sí | No aplicable | No aplicable | Generar automáticamente | Recibe el siguiente mensaje de error: “La secuencia numérica no se puede detectar”. | Según la secuencia de números **Código de artículo** | Este valor no se admite para la importación. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identificador de entidad de producto (exportar todos los identificadores de producto)

El modelo de identificador de entidad de producto se ha creado para permitir el aprovisionamiento de la versión 1.0 de Dataverse con todos los identificadores que se usan para hacer referencia a un producto. Para simplificar esta tarea, todos los identificadores se agregan en una tabla de identificador global, de forma que se puedan exportar como modelo. Tenga en cuenta que esta versión de Dataverse no usa el modelo de los identificadores de producto. Por lo tanto, la entidad **Entidad de identificador de common data service de la entidad del producto** y este proceso tienen un uso práctico limitado y estarán probablemente sujetos a cambios en el futuro.

La tabla de identificador del producto es una tabla global que se rellena a partir de todas las tablas de referencia de la entidad jurídica principal con un trabajo por lotes periódico. Debe seleccionar una entidad jurídica y una jerarquía de la categoría de producto como definición de ámbito global de producto maestro. La generación de la tabla global del identificador del producto se limita a los productos que se liberan en la entidad jurídica seleccionada y productos que son miembros de la jerarquía del producto seleccionado para el rol **Servicio de datos común** en la jerarquía de la categoría de producto.

Este proceso presupone que los datos del producto maestro se mantienen principalmente en una entidad jurídica central. (Sin embargo, esta entidad jurídica puede ser una entidad jurídica virtual que se usa solo para mantener datos maestros globales).

Siga estos pasos para configurar el entorno.

1. Seleccionar la jerarquía de categoría de Dataverse. En la página **Asociaciones de rol de jerarquía de categoría** , si no está asociada ninguna jerarquía al rol **Servicio de datos común**, debe crear una nueva asociación. Seleccione el rol **Common Data Service** y después asocie la jerarquía de categoría que representa la cartera de producto que se debe sincronizar con Dataverse.
2. Seleccione la entidad jurídica para los datos maestros de producto. En la página **Parámetros de la Gestión de información de productos**, en la pestaña **Atributos del producto**, seleccione la empresa principal donde los identificadores de producto y de artículo se mantienen principalmente.
3. Defina los tipos de códigos y los códigos del identificador que se vayan a exportar. Vaya a **Gestión de información de productos** &gt; **Configuración** &gt; **Códigos de identificador del producto**. Para generar los tipos de códigos de identificador, seleccione **Generar códigos**. Una entrada del tipo código se genera para cada tipo para el identificador que se encuentra en la entidad jurídica seleccionada.

    Para los códigos de barras, se genera un tipo de código para cada configuración de código de barras. Para los códigos externos, se genera un tipo de código para cada clase del código externo.

    Ahora puede mantener la lista de tipos de código. Se puede cambiar el código, el nombre y la descripción. También puede eliminar tipos de códigos. No se va a utilizar los tipos de códigos que elimina para rellenar las tablas globales del identificador de entidad de producto.

4. Cuando haya terminado de definir los tipos de código de Id de productos, puede crear los identificadores de la tabla global comenzando el trabajo **Crear identificadores de entidad de producto** en la página **Códigos de identificador de entidad de producto** . Debe ejecutar este trabajo en un lote. Este trabajo se debe configurar como un trabajo por lotes periódico para rellenar la tabla según las nuevas entradas.

Ahora puede usar entidades de datos **Entidad de identificador de common data service de la entidad del producto**, **Código de identificador de entidad de producto** y **Ámbito del identificador de entidad de producto** para exportar los identificadores para cualquier sistema de destino.

## <a name="related-topic"></a>Tema relacionado

[Buscar los productos y variantes de producto durante la entrada de pedidos](search-products-product-variants.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
