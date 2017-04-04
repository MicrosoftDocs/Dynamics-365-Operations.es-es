---
title: Rutas y operaciones
description: "Este tema proporciona información acerca de las rutas y operaciones. Una ruta define el proceso para producir un producto o una variante del producto. Describe cada paso (operación) en el proceso de producción y el orden que estos pasos se deben realizar en. Para cada etapa, la ruta también define los recursos de operaciones necesarios, el tiempo de configuración necesaria y el tiempo de ejecución, y cómo el coste debe calcular."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Rutas y operaciones

Este tema proporciona información acerca de las rutas y operaciones. Una ruta define el proceso para producir un producto o una variante del producto. Describe cada paso (operación) en el proceso de producción y el orden que estos pasos se deben realizar en. Para cada etapa, la ruta también define los recursos de operaciones necesarios, el tiempo de configuración necesaria y el tiempo de ejecución, y cómo el coste debe calcular.

<a name="overview"></a>Visión general
--------

Una ruta describe el orden de las operaciones que se necesita para producir un producto o una variante del producto. Para cada operación, la ruta también define a recursos de operaciones son obligatorios, el tiempo necesario para configurar y ejecutar la operación, y cómo el coste debe calcular. Puede usar la misma ruta para generar varios productos, o puede definir una ruta única para cada producto o variante del producto. Puede incluso tener varias rutas para el mismo producto. En este caso, la ruta que se utiliza varía, en función de factores como la cantidad que se debe producir. La definición de una ruta en Microsoft Dynamics 365 para las operaciones consta de cuatro artículos independientes, que describan conjunto, el proceso de producción:

-   ** La ruta – ** una ruta define la estructura del proceso de producción. Es decir define el orden de las operaciones.
-   ** La operación ** – una operación identifica un paso llama en una ruta, por ejemplo ** asamblea **. La misma operación puede aparecer varias rutas en y puede tener diferentes números de operación.
-   ** La relación de operación ** – una relación de operación define las propiedades operativas de una operación, como el tiempo de preparación y el tiempo de ejecución, categorías de coste, los parámetros del consumo, y los requisitos de recursos. La relación de operación permite a las propiedades operativas de una operación para variar, en función de la ruta que la operación se usa en los productos que se produce.
-   ** La versión de ruta – ** una versión de ruta define la ruta que se usa para generar un producto o una variante del producto. Rutas de permisos de las versiones de ruta que se reusarán a través de productos o cambiado en el tiempo. También habilitan las rutas diferentes que se utilizarán para generar el mismo producto. En este caso, la ruta que se utiliza depende de factores como la ubicación o la cantidad que se deben generar.

## <a name="routes"></a>Rutas
Una ruta describe el orden de las operaciones que se usa para generar un producto o una variante del producto. Cada operación se asigna un número de operación y una operación sucesora. El pedido de operaciones forma una red de rutas que se pueda actuar por un gráfico dirigido con uno o más puntos de inicio y un único extremo. En Dynamics 365 para las operaciones, las rutas son diferenciados basadas en el tipo de estructura. Los dos tipos de rutas son rutas y redes de rutas simples. En los parámetros de control de producción, puede especificar si solo las rutas simples pueden ser utilizadas, o si las redes de rutas más complejas pueden usar.

### <a name="simple-routes"></a>Rutas simples

Una ruta es simple secuencial, y sólo hay un punto de inicio para la ruta.  

[ruta simple de![] (. /media/routes-and-operations-1-simple-route.png])(. /media/routes-and-operations-1-simple-route.png)  

Si habilita solo las rutas simples en parámetros de control de producción, Dynamics 365 para las operaciones genera automáticamente los números de operación (10, 20, 30, etc.) al definir la ruta.

### <a name="route-networks"></a>Permite de rutas

Si habilita las redes de rutas más complejas en parámetros de control de producción, puede definir las rutas que tienen los puntos de inicio y operaciones múltiples que se pueden ejecutar en paralelo.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Notas:**

-   Cada operación sólo puede tener una operación sucesora, y la ruta del conjunto debe terminar en una sola operación.
-   No hay garantizar que las operaciones múltiples con la misma operación (sucesora por ejemplo, las operaciones 30 y 40 en la ilustración anterior) se ejecutarán realmente en paralelo. La disponibilidad y la capacidad de recursos pueden configurar restricciones del camino las operaciones que están programadas.
-   No puede usar 0 (cero) como el número de operación. Que el número está reservado y utilizado para especificar que la última operación de la ruta no tiene ninguna operación sucesora.

### <a name="parallel-operations"></a>Operaciones paralelas

A veces, requieren una combinación de recursos de operaciones múltiples que tienen varias funciones para la operación. Por ejemplo, una operación de ensamblado requiera un equipo, una herramienta, y un trabajador para que cada dos equipos supervisen la operación. Este ejemplo se puede crear un modelo usando las operaciones paralelas, donde una operación se designa como la operación principal y las otras son secundarias.  

[ruta![que tiene operaciones principales y secundarias] (. /media/routes-and-operations-3-parallel-operations.png])(. /media/routes-and-operations-3-parallel-operations.png)  

Normalmente, la operación principal representa el cuello de botella y dicta el tiempo de ejecución de las operaciones secundarias. Sin embargo, durante la programación que implique la capacidad limitada, los recursos a los que se programan la operación principal y las operaciones secundarias debe estar disponible y tener libre capacidad al mismo tiempo.  

La operación principal y las operaciones secundarias deben tener la misma operación número 30 (en la ilustración anterior).  

En el ejemplo anterior, el requisito de recurso para la operación principal (30) es el equipo, mientras que los requisitos de recurso para operaciones secundarias ('30 y 30 ") es la herramienta y el trabajador. Las ayudas de una carga de cincuenta- PERCENT garantizan que el trabajador puede supervisar programado dos equipos el mismo tiempo.

### <a name="approval-of-routes"></a>Aprobación de rutas

Una ruta debe estar aprobada antes de poder usarlas en el proceso de planificación ni de fabricación. La aprobación indica que el diseño de la ruta se ha completado. El mismo producto emitido o variante del producto puede tener varias rutas aprobadas. Normalmente, la aprobación de una ruta aparece cuando se aprueba la primera versión de ruta relevante. Sin embargo, en algunos escenarios empresariales, la aprobación de la ruta y la versión de ruta son actividades individuales que pueden implicar a propietarios del proceso diferente.  

Cada ruta puede ser aprobado o no aprobado por separado. Sin embargo, tenga en cuenta que, cuando una ruta no está aprobado, todas las versiones de ruta relacionadas son también no aprobado. En los parámetros de control de producción, puede especificar si las rutas no estén aprobado, y si las rutas aprobadas se pueden modificar.  

Si debe retener un registro que los registros que aprueba cada ruta, puede requerir firmas electrónicas para la aprobación de la ruta. Los usuarios que tendrán continuación confirmar su identidad con [la firma electrónica (/dynamics365/operations/organization-administration/electronic-signature-overview]).

## <a name="operations"></a>Operaciones
Una operación es un paso del proceso de producción. En Dynamics 365 para las operaciones, cada operación tiene un identificador y una descripción sencilla. En las siguientes tablas se muestran ejemplos típicos de operaciones de un departamento de equipo.

| Operación  | Descripción        |
|------------|--------------------|
| PipeCut    | Cortar de proceso       |
| TIGweld    | Unificar de TIG        |
| JigAssy    | Ensamblado de la plantilla       |
| Inspección | Inspección de calidad |

Las propiedades operativas de la operación, como el tiempo de preparación y el tiempo de ejecución, los requisitos de recursos, información de gestión de costes, y cálculo del consumo, se especifican en la relación de operación. (Para obtener más información sobre las relaciones de operación, consulte la sección siguiente.)

## <a name="operation-relations"></a>Relaciones de operación
Las propiedades siguientes operativas de una operación se mantienen en la relación de operación:

-   Categorías de coste
-   Parámetros de consumo
-   Tiempos de procesamiento
-   Cantidades de procesamiento
-   Requisitos de recursos
-   Notas e instrucciones

Puede definir las relaciones de operación varios para la misma operación. Sin embargo, cada relación de operación es específica de una operación, y se almacenan las propiedades que son específicas de una ruta, a un producto liberado, o un conjunto de productos emitidos relacionadas con un grupo de artículos. Por lo tanto, la misma operación se puede utilizar en las varias rutas que tengan propiedades diferentes operativas. Además, puede con mayor facilidad mantener sus datos maestros si usa las operaciones estándar que tengan las mismas propiedades operativas, independientemente de la ruta que se utiliza y el producto que se genera. El ámbito de la relación de operación se define mediante ** código de artículo, ** ** relación de artículo, ** ** código de ruta y ** ** relación de ruta ** de propiedades, como se muestra en la tabla siguiente.

| Código de artículo | Relación de artículos         | Código de ruta | Relación de ruta   | Ámbito de la relación de operación                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabla     | &lt;Id. de artículo&gt;       | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas de una operación cuando ha utilizado en el identificador de la ruta=de la ruta en la que **&lt;número de ruta **&gt; generar el producto emitido donde ** número de artículo ** Id&lt;. de artículo=&gt;.                                                                                                                        |
| Tabla     | &lt;Id. de artículo&gt;       | Todas        |                  | Las propiedades operativas predeterminadas de una operación cuando generaba el producto emitido donde ** número de artículo ** Id&lt;. de artículo=&gt;. Es decir estas propiedades operativas se aplican si no hay relación de operación de la ruta específica del producto liberado.                                     |
| Grupo     | &lt;Identificación del grupo de artículo&gt; | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas de una operación cuando ha utilizado en el identificador de la ruta=de la ruta en la que **&lt;número de ruta **&gt; generar los productos emitidos que se asocian a identificación &lt;del grupo de artículo del&gt;grupo de artículos, a menos que haya una relación de operación de la ruta específica del producto liberado.                         |
| Grupo     | &lt;Identificación del grupo de artículo&gt; | Todas        |                  | Las propiedades operativas predeterminadas de una operación cuando generaba los productos emitidos que se asocian a identificación &lt;del grupo de artículo del&gt;grupo de artículos, a menos que exista una relación de operación más específica.                                                                                                  |
| Todas       |                       | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas predeterminados de la operación cuando ha utilizado en la ruta en la que ** número de ruta ** identificador&lt;=la ruta=&gt;. Es decir estas propiedades operativas se aplican si no hay relación de operación para esta ruta que sea específica para el producto liberado o su grupo de artículos asociados. |
| Todas       |                       | Todas        |                  | Las propiedades operativas predeterminadas de una operación. Estas propiedades operativas se aplican si no existe una relación de operación más específica.                                                                                                                                                                |

También puede especificar que una relación de operación es específica de un sitio. De esta manera, las propiedades operativas de una operación pueden variar, en función de la ubicación (es decir, el sitio) que se lleva a cabo la operación. Para los productos configurados, también puede especificar diferentes propiedades operativas para cada configuración de productos.  

Las relaciones de operación proporcionan lotes de flexibilidad al definir sus rutas. Además, la capacidad de ayuda de definir las propiedades predeterminadas se reduce el importe de datos maestros que deba mantener. Sin embargo, esta flexibilidad quiere decir que debe tener en cuenta de contexto que modifica una relación de operación en.  

** Nota: ** Dado que las propiedades operativas se relaciones de operaciones almacenadas por operación en la ruta, todas las apariciones de la misma operación (por ejemplo, asamblea) tienen el mismo tiempo de preparación, el tiempo de ejecución, requisitos de recurso, y así sucesivamente. Por lo tanto, si dos apariciones de una operación que deben aparecer en la misma ruta pero tener distintos tiempo de ejecución, debe crear dos operaciones distintas, como Assembly1 y Assembly2.

### <a name="modifying-product-specific-routes"></a>Rutas de específicas de modificación

Al abrir ** ruta ** la página ** Detalles de producto emitido ** de la página, se muestran las versiones de ruta que se está asociado el producto liberado. En este contexto, para cada operación, Dynamics 365 para las operaciones muestra las propiedades operativas de la relación de operación que coincide con el mejor la versión de ruta. Se observará que la lista de operaciones incluye ** código de artículo y ** ** código de ruta ** propiedades de la relación de operación. Por lo tanto, puede determinar se muestra qué relación de operación.  

En ** ruta ** la página, puede modificar las propiedades operativas de la operación, como el tiempo de ejecución o las categorías de coste. Sus cambios se almacenan en la relación de operación específica de la ruta y el productos que se haga referencia en la versión de ruta actual. Si la relación de operación se muestra que no sea específica para la ruta y el productos, antes de que se almacenan los cambios, el sistema crea una copia de la relación de operación. Este específico de *is* de copiado a la ruta y el producto liberado. Por lo tanto, los cambios no afectarán a otras rutas o productos emitidos. Para comprobar qué relación de operación se está modificando en ** ruta ** la página, mire ** código de artículo y ** ** el código de ruta ** los campos.  

También puede crear manualmente una operación que sea específica a una ruta y a un producto liberado mediante ** copia y relación de edición ** la función.  

** Nota: ** Si agrega una nueva operación a una ruta en ** ruta ** la página, una relación de operación está diseñado únicamente para el producto emitido actual. Por lo tanto, si la ruta también se usa para generar otros productos emitidos, ninguna relación de operación existirá aplicable para dichos productos emitidos, y la ruta se puede usar ya no para dichos productos emitidos.

### <a name="maintaining-operation-relations-per-route"></a>Relaciones de operación mantenimiento por ruta

Al abrir ** la ruta ** Detalles de la página ** rutas ** de la página de lista, una lista de todas las relaciones de operación que se aplican a la ruta seleccionada se muestra. Por lo tanto, puede fácilmente comprobar que las propiedades operativas se usan para las que los productos. Puede modificar valores predeterminados de propiedades y valores de propiedades de específicos.  

Si agrega una nueva relación de operación en la ruta ** ** Detalles de la página, ** código de ruta ** el campo se establece automáticamente ** ** ruta, y ** relación de ruta ** el campo se establece con el número de ruta de la ruta actual.

### <a name="maintaining-operation-relations-per-operation"></a>Relaciones de operación mantenimiento por operación

** Las operaciones ** de la página, puede abrir ** las relaciones de operación ** la página. En esta página, puede modificar todas las relaciones de operaciones para una operación específica. Puede incluso modificar las relaciones de operación que contienen valores predeterminados.  

Si su empresa utiliza operaciones estándar, y si los parámetros operativos son iguales entre todos los productos y procesos, ** las relaciones de operación ** la página ofrece una forma cómoda de mantener las propiedades operativas predeterminadas de dichas operaciones.

### <a name="applying-operation-relations"></a>Relaciones de operación que se aplican

En algunos casos, Dynamics 365 para las operaciones debe buscar las propiedades operativas para una operación. Por ejemplo, cuando se crea un pedido de compra, las propiedades operativas de cada operación se deben copiar de relaciones de operaciones a la ruta de producción. En estos casos, Dynamics 365 para las operaciones busca las relaciones de operación relevantes de la combinación más específica a la combinación menos específica.  

Cuando Dynamics 365 para las búsquedas de operaciones para la relación de operación guarde mayor para un producto liberado, una relación de operación que coincida con el Id. de artículo del producto se prefiere acerca de una relación de operación que coincida con la identificación del grupo de artículo. A su vez, una relación de operación que coincide con la identificación del grupo de artículo se prefiere sobre la relación de operación predeterminado. La búsqueda se realiza en el siguiente orden:

1.  ** Código de artículo **=** tabla ** y ** relación de artículo ** Id&lt;. de artículo=&gt;
2.  ** Código de artículo **=** grupo ** y ** relación de artículo ** identificación&lt;del grupo de artículo=&gt;
3.  ** Código de artículo **=** todos **
4.  ** Código de ruta **=** ** ruta y ** relación de ruta ** identificador&lt;=la ruta=&gt;
5.  ** Código de ruta **=** todos **
6.  ** Configuración ** identificador de configuración&lt;de=&gt;
7.  **Configuration**=
8.  ** Sitio ** identificador&lt;de sitio=&gt;
9.  **Site**=

Por lo tanto, una operación se debe usar solo una vez para cada ruta. Si la operación tiene lugar varias veces en la misma ruta, todas las apariciones de esa operación tendrán el mismo relación de operación, y no se podrá haber distintas propiedades (por ejemplo, tiempo de ejecución) para cada aparición.

## <a name="route-versions"></a>Versiones de ruta
Las versiones de ruta se utilizan para incorporar variaciones en la producción de productos o para proporcionar un mayor control sobre el proceso de producción. Definen la ruta que se utilizará cuando envíen un producto liberado o a una variante específicas de producto liberado. Puede usar las restricciones siguientes para definir la ruta que se utiliza para un producto liberado:

-   Dimensiones de productos (color, tamaño, estilo, o configuración)
-   Cantidad de producción
-   Sitio de producción
-   Fecha de producción

Cuando se está generando el producto en un sitio específico, en una cantidad específica, o en un período específico, puede designar una versión de ruta específica como la versión de la ruta predeterminada. Sin embargo, tenga en cuenta que sólo una ruta activa está permitida para un producto liberado dado y un conjunto concreto de restricciones.  

En parámetros de control de producción, se puede requerir que el período de validez de una versión de ruta siempre esté especificado.

### <a name="approval-of-route-versions"></a>Aprobación de versiones de ruta

Para que una versión de ruta se puede utilizar en el proceso de planificación ni de fabricación, debe estar aprobada. Al aprobar una versión de ruta, también puede aprobar la ruta relacionada. Sin embargo, tenga en cuenta que una versión de ruta puede ser aprobada si la ruta relacionada también se aprueba.

### <a name="activating-the-default-route-version"></a>Activar la versión de la ruta predeterminada

Al activar una versión de ruta, se designa como la versión de la ruta predeterminada que la planificación maestra utilizará, o que se usará para crear pedidos de producción. Puede tener sólo una versión de ruta activa para un conjunto concreto de restricciones (por ejemplo, el período, sitio, o cantidad). Si la versión que se intentaba activar conflictos con una versión que ya está activo, recibirá un mensaje de error. Para evitar una ambigua activación, debe después desactivar la versión en conflicto o modificar las restricciones (normalmente el período) en la versión de ruta.

### <a name="electronic-signatures"></a>Firmas electrónicas

Si debe retener un registro que registra la persona que aprueba y activa cada versión de ruta, puede requerir firmas electrónicas para estas tareas. Los usuarios que aprueban y activan versiones de ruta continuación tendrán que confirmen su identidad con [la firma electrónica (/dynamics365/operations/organization-administration/electronic-signature-overview]).

### <a name="product-change-that-uses-case-management"></a>Cambio de producto que utiliza la gestión de casos

Caso del producto para su aprobación y la activación de nuevas o modificadas rutas y versiones de ruta proporciona una forma sencilla de obtener una visión general de restricciones de la versión de ruta. También puede aprobar y activar todas las rutas relacionadas con un cambio específico en una operación y documentar los resultados en el caso de cambio del producto.

## <a name="maintaining-routes"></a>Rutas mantenimiento
En función de sus necesidades empresariales, es posible que pueda reducir el esfuerzo necesario para mantener las definiciones de proceso.

### <a name="making-routes-independent-of-resources"></a>Crear a la independiente de las rutas de recursos

En muchos sistemas, el recurso de operaciones o el grupo de recursos que deben realizar una operación debe ser especificado en la ruta. Sin embargo, en Dynamics 365 para las operaciones, puede definir un conjunto de requisitos que un recurso de operaciones debe cumplir para ser aplicable para la operación. Por lo tanto, el recurso de operaciones o el grupo de recursos específicos que se usarán no tiene que ser determinado hasta que la operación se programe realmente. Esta funcionalidad es especialmente útil si tiene muchos trabajadores o equipos que puede realizar la misma operación.  

Por ejemplo, especifica que una operación requiere un recurso de operaciones de equipo ** ** escribe que tienen una sellando ** ** capacidad de 20 toneladas. El motor de programación continuación resolverá estos requisitos un recurso de operaciones a un grupo de recursos específicos cuando se programa la operación. Dado que simplemente puede especificar estos requisitos en lugar de vincular la operación a un equipo específico, tiene mucho más flexibilidad. Además, el mantenimiento resulta más fácil cuando mueven a los recursos o agregan a los nuevos recursos.  

Para obtener más información sobre los distintos tipos de requisitos de recurso y cómo ello, consulte los requisitos de recursos de operaciones y [capacidades de recursos resource-capabilities.md] ().

### <a name="sharing-routes-across-sites"></a>Compartir rutas a través de sitios

Si se genera el mismo producto en más de un sitio de producción, y si los pasos para generar el producto son iguales en todos los sitios, puede diseñar a menudo una ruta compartida que se utilice a través de todos los sitios de producción. Para crear una ruta compartida, no especifique un sitio en la misma ruta. Sin embargo, debe aún crear una versión de ruta que la ruta asociada compartida al producto en cada sitio.  

También debe asegurarse de que los requisitos de recurso para cada operación en la ruta no se solicita a recursos de operaciones o grupos de recursos específicos, pero en su lugar se expresa en términos de características de los recursos requeridos. El motor de programación continuación podrá asignar a recursos de operaciones adecuados del sitio que el de la producción está programada en. Por ejemplo, si hay pequeñas diferencias en el tiempo de ejecución, o si el tiempo de preparación para una determinada operación es específico, puede especificar esta información agregando una relación de operación adicional para dicho sitio.  

Para aprovechar las ventajas de prestaciones de rutas compartidas, debe usar el consumo del recurso en la lista de materiales correspondiente (BOM). Cuando establece el indicador para el consumo de recursos en la línea de L, el almacén y la ubicación que las materias primas se van a consumir de deducen del recurso de operaciones que está programada la operación en. Por lo tanto, el almacén y la ubicación que no tienen determinase hasta que la producción se programe realmente. De esta manera, puede crear la L y la independiente de la ruta de la ubicación física donde se genera el producto.

### <a name="standard-operation-relations"></a>Relaciones de operación estándar

Si su empresa utiliza estandarizadas operaciones en la producción, y si hay nada reducido o de variación en el tiempo de preparación, el tiempo de ejecución, cálculos de consumo, cálculo de costes, etc., es posible que se podría beneficiar de crear relaciones de operación predeterminadas para todas las operaciones. En este caso, evite crear relaciones de operación que son específicas de cualquier ruta o producto emitido.  

Si también expresa requisitos de recurso en términos de conocimientos y capacidades, y crear sus rutas sitio independiente, puede ayudar a mantener el mantenimiento en curso de los procesos empresariales en el mínimo.  

Cuando usa este planteamiento, ** las relaciones de operación ** la página se convierte en su destino principal para el tiempo de ejecución mantenimiento y otras propiedades.

### <a name="resource-specific-process-times"></a>tiempos de proceso Recurso- específicas

Si no especifica un recurso de operaciones a un grupo de recursos como parte de los requisitos de recurso para una operación, los recursos aplicables pueden trabajar en varias velocidades. Por lo tanto, el tiempo necesario para procesar una operación puede variar. Para resolver este problema, puede usar ** fórmula ** campos de la relación de operación para especificar cómo se calcula el tiempo de proceso. Están disponibles las siguientes opciones:

-   ** El estándar ** – (opción predeterminada) el cálculo usa sólo los campos de la relación de operación y multiplica el tiempo de ejecución especificado por la cantidad de pedido.
-   ** Capacidad – ** el cálculo incluye ** ** campos capacidad del recurso de operaciones. Por lo tanto, el tiempo es laborales dependiente. El valor que se especifica en el recurso de operaciones es capacidad por hora. Este valor se multiplica por la cantidad de pedido y ** factor ** el valor de la relación de operación.
-   ** El lote ** – una capacidad de lote se calcula usando la información de la relación de operación. El número de lotes y, por tanto, el tiempo de proceso se pueden calcular en función de la cantidad de pedido.
-   ** El lote de recursos – ** esta opción es básicamente el mismo lote que ** ** la opción. Sin embargo, el cálculo incluye ** capacidad de lote ** los campos de recursos de operaciones. Por lo tanto, el tiempo es laborales dependiente.


<a name="see-also"></a>Consulte también
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


