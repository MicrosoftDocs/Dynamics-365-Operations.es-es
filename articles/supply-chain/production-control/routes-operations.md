---
title: Rutas y operaciones.
description: Este tema proporciona información acerca de las rutas y las operaciones.
author: sorenva
manager: tfehr
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable, ProdRouteJob, ProdRouteTrans, ProdRouteOverview, ProdRouteJobOverview, ProdRouteJobListPagePreviewPane, RouteTable, RouteVersionFeasibility, ProdRouteJobCurrent, RouteGroup, RouteProductionOrder, EngChgCaseRouteTablePart, EcoResProductProdTypeFormulaNoActiveRouteFormPart,
ms.author: sorenand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adf890f5305f4e6a62c2d7527ff3b593ed61eff3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436664"
---
# <a name="routes-and-operations"></a>Rutas y operaciones.

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de las rutas y las operaciones. Una ruta define el proceso para producir un producto o una variante del producto. Describe cada paso (operación) en el proceso de producción y el orden en que estos pasos se deben realizar. Para cada etapa, la ruta también define los recursos de operaciones necesarios, el tiempo de configuración necesaria y el tiempo de ejecución, y cómo el coste se debe calcular.

<a name="overview"></a>Visión general
--------

Una ruta describe el orden de las operaciones que se necesitan para producir un producto o una variante del producto. Para cada operación, la ruta también define los recursos de operaciones que se necesitan, el tiempo necesario para configurar y ejecutar la operación, y cómo el coste se debe calcular. Puede usar la misma ruta para generar varios productos o puede definir una ruta única para cada producto o variante del producto. Puede incluso tener varias rutas para el mismo producto. En este caso, la ruta que se utiliza varía, en función de factores como la cantidad que se debe producir. La definición de una ruta en Supply Chain Management consta de cuatro elementos independientes, en conjunto, describen el proceso de producción:

- **Ruta**: una ruta define la estructura del proceso de producción. Es decir, define el orden de las operaciones.
- **Operación**: una operación identifica un paso con nombre en una ruta, por ejemplo **Ensamblado**. La misma operación puede producirse en varias rutas y puede tener diferentes números de operación.
- **Relación de operación**: una relación de operación define las propiedades operativas de una operación, como el tiempo de configuración y el tiempo de ejecución, las categorías de coste, los parámetros de consumo y los requisitos de recursos. La relación de operación permite a las propiedades operativas de una operación variar, en función de la ruta que la operación use en los productos que se generan.
- **Versión de la ruta**: una versión de ruta define la ruta que se usa para generar un producto o una variante del producto. Las versiones de ruta permiten volver a utilizar las rutas en todos los productos o cambiarlas con el tiempo. También habilitan diferentes rutas que se utilizarán para generar el mismo producto. En este caso, la ruta que se utiliza depende de factores como la ubicación o la cantidad que se debe producir.

## <a name="routes"></a>Rutas
Una ruta describe el orden de las operaciones que se usan para producir un producto o una variante del producto. A cada operación se le asigna un número de operación y una operación sucesora. El orden de las operaciones forma una red de rutas que se puede representar mediante un gráfico dirigido con uno o más puntos de inicio y un único punto de destino. En Supply Chain Management, las rutas se diferencian en función del tipo de estructura. Los dos tipos de rutas son rutas simples y redes de rutas. En los parámetros de control de producción, puede especificar si solo se pueden usar rutas simples o si se pueden usar redes de rutas más complejas.

### <a name="simple-routes"></a>Rutas simples

Una ruta sencilla es secuencial y solo hay un punto de inicio para la ruta.  

[![Ruta sencilla](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Si solo habilita rutas simples en los parámetros de control de producción, Supply Chain Management genera automáticamente los números de operación (10, 20, 30, etc.) cuando define la ruta.

### <a name="route-networks"></a>Redes de rutas

Si habilita redes de rutas más complejas en los parámetros de control de producción, puede definir las rutas que tengan múltiples puntos de inicio y operaciones que se pueden ejecutar en paralelo.  

[![Red de las rutas](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> - Cada operación solo puede tener una operación sucesora y la totalidad de la ruta debe terminar en una sola operación.
> - Esto no garantiza que múltiples operaciones con la misma operación sucesora (por ejemplo, las operaciones 30 y 40 en la ilustración anterior) se vayan a ejecutar realmente en paralelo. La disponibilidad y la capacidad de los recursos puede limitar la forma en que se programan las operaciones.
> - No puede usar 0 (cero) como el número de operación. Ese número se reserva y utiliza para especificar que la última operación de la ruta no tiene ninguna operación sucesora.

### <a name="parallel-operations"></a>Operaciones paralelas

A veces, requieren una combinación de múltiples recursos de operaciones con diversas características para realizar una operación. Por ejemplo, una operación de ensamblado puede requerir una máquina, una herramienta y un trabajador para dos máquinas poder supervisar la operación. Se puede dar forma a este ejemplo con operaciones paralelas, donde una operación se designa como la operación principal y las otras son secundarias.  

[![Ruta que tiene operaciones primarias y secundarias](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Normalmente, la operación principal representa el recurso de cuello de botella e indica el tiempo de ejecución de las operaciones secundarias. Sin embargo, durante la programación con capacidad limitada, los recursos que se programan para la operación principal y las operaciones secundarias deben estar disponibles y tener capacidad libre al mismo tiempo.  

La operación principal y las operaciones secundarias deben tener el mismo número de operación (30 en la ilustración anterior).  

En el ejemplo anterior, el requisito de recurso para la operación principal (30) es el equipo, mientras que los requisitos de recurso para las operaciones secundarias ('30 y 30 ") es la herramienta y el trabajador. Una carga del cincuenta por ciento garantiza que el trabajador programado pueda supervisar dos equipos el mismo tiempo.

### <a name="approval-of-routes"></a>Aprobación de rutas

Se debe aprobar una ruta antes de que se pueda utilizar en el proceso de planificación o fabricación. La aprobación indica que el diseño de la ruta se ha completado. El mismo producto emitido o variante de producto emitido puede tener varias rutas aprobadas. Normalmente, la aprobación de una ruta se produce cuando se aprueba la primera versión de ruta pertinente. Sin embargo, en algunos escenarios empresariales, la aprobación de la ruta y la versión de ruta son actividades individuales que pueden involucrar a diversos propietarios de procesos.  

Cada ruta se puede aprobar o desaprobar por separado. Sin embargo, tenga en cuenta que, cuando una ruta se desaprueba, también se desaprobarán todas las versiones de ruta relacionadas. En los parámetros de control de producción, puede especificar si las rutas pueden desaprobarse y si las rutas aprobadas se pueden modificar.  

Si debe retener un registro que registre quién aprueba cada ruta, puede requerir firmas electrónicas para la aprobación de la ruta. Los usuarios tendrán que confirmar su identidad con una [firma electrónica](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

## <a name="operations"></a>Operations
Las operaciones son un paso del proceso de producción. Cada operación tiene un identificador y una descripción sencilla. Las siguientes tablas muestran ejemplos típicos de operaciones de una tienda de máquinas.

| Operación  | Descripción        |
|------------|--------------------|
| PipeCut    | Corte de tuberías       |
| TIGweld    | Soldaduras TIG        |
| JigAssy    | Plantilla de montaje       |
| Inspección | Inspección de calidad |

Las propiedades operativas de la operación, como el tiempo de configuración y el tiempo de ejecución, los requisitos de los recursos, la información de la gestión de costes y el cálculo de los consumos se especifican en la relación de la operación. (Para obtener más información sobre las relaciones operativas, consulte la sección siguiente).

## <a name="operation-relations"></a>Relaciones de operación
Las propiedades operativas siguientes de una operación se mantienen en la relación de operación:

- Categorías de coste
- Parámetros de consumo
- Tiempos de procesamiento
- Cantidades de procesamiento
- Requisitos de recursos
- Notas e instrucciones

Puede definir varias relaciones de operación para la misma operación. Sin embargo, cada relación de operación es específica de una operación y se almacenan las propiedades que son específicas de una ruta, un producto liberado o un conjunto de productos nuevos relacionados con un grupo de artículos. Por lo tanto, la misma operación se puede utilizar en varias rutas que tengan propiedades operativas diferentes. Además, puede mantener con mayor facilidad sus datos maestros si usa las operaciones estándar que tengan las mismas propiedades operativas, independientemente de la ruta que se utiliza y el producto que se genera. El ámbito de la relación de operación se define mediante las propiedades **Código de artículo**, **Relación de artículo**, **Código de la ruta** y **Relación de la ruta**, como se muestra en la tabla siguiente.

| Código de artículo | Relación de artículos         | Código de ruta | Relación de ruta   | Ámbito de la relación de operación                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabla     | &lt;Id. de artículo&gt;       | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas de una operación cuando se usa en la ruta donde **Número de ruto**=&lt;Id. de ruta&gt; generan el producto donde **Número de artículo**=&lt;Id. de artículo&gt;.                                                                                                                        |
| Tabla     | &lt;Id. de artículo&gt;       | Todas        |                  | Las propiedades operativas predeterminadas de una operación cuando se usa para generar el producto liberado donde **Número de articulo**=&lt;Id. de artículo&gt;. Es decir, estas propiedades operativas se aplican cuando no hay una relación de operación específica de una ruta para el producto liberado.                                     |
| Grupo     | &lt;Id. del grupo de artículos&gt; | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas de una operación cuando se usa en la ruta donde el **Número de la ruta**=&lt;Id. e la ruta&gt; para generar productos liberados que se asocian con el &lt;Id. del grupo de artículos&gt; del grupo del artículo del grupo, a menos que haya una relación de operación específica de la ruta para el producto liberado.                         |
| Grupo     | &lt;Id. del grupo de artículos&gt; | Todas        |                  | Las propiedades operativas predeterminadas de una operación cuando se usa para generar productos liberados que están asociados con el &lt;Id. del grupo de artículos&gt; del grupo del artículo, a menos que exista una relación de operación más específica.                                                                                                  |
| Todas       |                       | Ruta      | &lt;Id. de ruta&gt; | Las propiedades operativas predeterminados de la operación cuando se usa en la ruta donde el **Número de la ruta**=&lt;Id. de la ruta&gt;. Es decir, estas propiedades operativas se aplican cuando no hay una relación de operación para esta ruta que específica de un producto liberado o su grupo de artículos asociado. |
| Todas       |                       | Todas        |                  | Las propiedades operativas predeterminadas de una operación. Estas propiedades operativas se aplican si no existe una relación de operación más específica.                                                                                                                                                                |

También puede especificar que una relación de operación es específica de un sitio. De esta manera, las propiedades operativas de una operación pueden variar, en función de la ubicación (es decir, el sitio) donde se lleva a cabo la operación. Para los productos configurados, también puede especificar diferentes propiedades operativas para cada configuración de productos.  

Las relaciones de operación proporcionan gran flexibilidad al definir sus rutas. Además, la capacidad de definir las propiedades predeterminadas ayuda a reducir la cantidad de datos maestros que debe mantener. Sin embargo, esta flexibilidad también indica debe tener en cuenta el contexto en el que modifica una relación de operación.  

> [!NOTE]
> Dado que las propiedades operativas se almacenan en relaciones de operaciones por operación y por ruta, todas las repeticiones de la misma operación (por ejemplo, ensamblado) tienen el mismo tiempo de preparación, tiempo de ejecución y requisitos de recurso. Por lo tanto, si debe haber dos repeticiones de una operación en la misma ruta pero deben tener distintos tiempos de ejecución, tendrá que crear dos operaciones distintas, como Ensamblado1 y Ensamblado2.

### <a name="modifying-product-specific-routes"></a>Modificar rutas de específicas de un producto

Cuando abre la página **Ruta** en la página **Detalles del producto liberado**, se muestran las versiones de ruta que se están asociadas con el producto liberado. En este contexto, para cada operación, Supply Chain Management muestra las propiedades operativas de la relación de operación que coincide mejor la versión de ruta. Se observará que la lista de operaciones incluye el **Código de artículo** y el **Código de la ruta** de la relación de operación. Por lo tanto, puede determinar qué relación de operación se muestra.  

En la página **Ruta**, puede modificar las propiedades operativas de la operación, como el tiempo de ejecución o las categorías de coste. Sus cambios se almacenan en la relación de operación específica de la ruta y el producto liberado al que se hace referencia en la versión de ruta actual. Si la relación de operación que se muestra no es específica de la ruta y el producto liberado, antes de que se almacenan los cambios, el sistema crea una copia de la relación de operación. Esta copia *es* específica de la ruta y el producto liberado. Por lo tanto, los cambios no afectarán a otras rutas o productos liberados. Para comprobar qué relación de operación se está modificando en la página **Ruta**, consulte los campos **Código de artículo** y **Código de ruta**.  

También puede crear manualmente una operación que sea específica para una ruta y un producto liberado mediante la función **Copiar y editar relación**.  

> [!NOTE]
> Si agrega una nueva operación a una ruta en la página **Ruta**, una relación de operación de relación se crea únicamente para el producto liberado actual. Por lo tanto, si la ruta también se usa para generar otros productos emitidos, no existirá ninguna relación de operación aplicable para dichos productos liberados, y la ruta ya no se podrá usar para esos productos liberados.

### <a name="maintaining-operation-relations-per-route"></a>Mantener relaciones de operación por ruta

Cuando abra la página **Detalles de la ruta** en la página de la lista de **Rutas**, se muestra una lista de todas las relaciones de operación que se aplican a la ruta seleccionada. Por lo tanto, puede comprobar fácilmente qué propiedades operativas se usan para qué productos. Puede modificar los valores predeterminados de propiedades y los valores de propiedades de específicos para un producto.  

Si agrega una nueva relación de operación en la página **Detalles de la ruta**, el campo **Código de la ruta** se establece automáticamente en **Ruta** y el campo **Relación de la ruta** se establece en el número de la ruta de la ruta actual.

### <a name="maintaining-operation-relations-per-operation"></a>Mantener relaciones de operación por operación

En la página **Operaciones**, puede abrir la página **Relaciones de operación**. En esta página, puede modificar todas las relaciones de operaciones para una operación específica. Puede incluso modificar las relaciones de operación que contienen valores predeterminados.  

Si su empresa utiliza operaciones estándar y si los parámetros operativos son iguales en todos los productos y procesos, la página **Relaciones de operación** ofrece una forma cómoda de mantener las propiedades operativas predeterminadas de dichas operaciones.

### <a name="applying-operation-relations"></a>Aplicar relaciones de operaciones

En algunos casos, Supply Chain Management debe buscar las propiedades operativas para una operación. Por ejemplo, cuando se crea un pedido de compra, las propiedades operativas de cada operación se deben copiar desde relaciones de operaciones hasta la ruta de producción. En estos casos, Supply Chain Management busca las relaciones de operación relevantes desde la combinación más específica hasta la combinación menos específica.  

Cuando Supply Chain Management busca la relación de operación más relevante para un producto liberado, se prefiere una relación de operación que coincida con el Id. de artículo del producto antes que una relación de operación que coincida con el identificador del grupo de artículo. A su vez, una relación de operación que coincide con el identificador del grupo de artículo se prefiere a una relación de operación predeterminada. La búsqueda se realiza en el siguiente orden:

1.  **Código de artículo**=**Tabla** y **Relación de artículo**=&lt;Id. de artículo&gt;
2.  **Código de artículo**=**Grupo** y **Relación de artículo**=&lt;Id. del grupo de artículo&gt;
3.  **Código de artículo**=**Todos**
4.  **Código de ruta**=**Ruta** y **Relación de ruta**=&lt;Id. de ruta&gt;
5.  **Código de ruta**=**Todos**
6.  **Configuración**=&lt;Id. de configuración&gt;
7.  **Configuración**=
8.  **Sitio**=&lt;Id. de sitio&gt;
9.  **Sitio**=

Por lo tanto, una operación se debe usar solo una vez para cada ruta. Si la operación tiene lugar varias veces en la misma ruta, todas las repeticiones de esa operación tendrán la misma relación de operación y no podrá haber distintas propiedades (por ejemplo, tiempo de ejecución) para cada repetición.

## <a name="route-versions"></a>Versiones de ruta

Las versiones de ruta se utilizan para contemplar variaciones en la producción de productos, así como para proporcionar un mayor control del proceso de producción. Definen la ruta que se debe utilizar cuando se genera un producto liberado específico o a una variante de un producto liberado. Puede usar las restricciones siguientes para definir la ruta que se utiliza para un producto liberado:

- Las dimensiones de producto (tamaño, color, estilo o configuración)
- Cantidad de producción
- Sitio de producción
- Fecha de producción

Cuando se está generando el producto en un sitio específico, en una cantidad específica o en un período específico, puede designar una versión de ruta específica como la versión de la ruta predeterminada. Sin embargo, tenga en cuenta que solo se permite una ruta activa para un producto liberado determinado y un conjunto concreto de restricciones.  

En los parámetros de control de producción, puede ser necesario que el período de validez de una versión de ruta esté siempre especificado.

### <a name="approval-of-route-versions"></a>Aprobación de las versiones de ruta

Antes de que se pueda usar una versión de ruta en el proceso de planificación o fabricación, se debe aprobar. Al aprobar una versión de ruta, también puede aprobar la ruta relacionada. Sin embargo, tenga en cuenta que una versión de ruta se puede aprobar solo si la ruta relacionada también está aprobada.

### <a name="activating-the-default-route-version"></a>Activar la versión de la ruta predeterminada

Al activar una versión de ruta, la designa como la versión de ruta predeterminada que la planificación maestra utilizará o que se usará para crear pedidos de producción. Puede tener solo una versión de ruta activa para un conjunto concreto de restricciones (por ejemplo, el período, el sitio o la cantidad). Si la versión que está intentando activar entra en conflicto con una versión que ya está activa, recibirá un mensaje de error. Para evitar una activación ambigua, es preciso desactivar la versión en conflicto o modificar las restricciones de la versión (normalmente el período) en la versión de la ruta.

### <a name="electronic-signatures"></a>Firmas electrónicas

Si debe retener un registro que registre quién aprueba y activa cada versión de la ruta, puede requerir firmas electrónicas para estas tareas. Los usuarios que aprueban y activan las versiones de ruta tendrán que confirmar su identidad con una [firma electrónica](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

### <a name="product-change-that-uses-case-management"></a>Cambio de producto que usa administración de casos

El caso de cambio de producto para la aprobación y activación de rutas nuevas o cambiadas y versiones de ruta le proporcionan una manera sencilla de considerar una descripción de las restricciones de la versión de ruta. También puede aprobar y activar todas las rutas relacionadas con respecto a un cambio específico en una operación y documentar los resultados en el caso de cambio del producto.

## <a name="maintaining-routes"></a>Mantener rutas

En función de sus necesidades empresariales, es posible que pueda reducir el esfuerzo necesario para mantener las definiciones del proceso.

### <a name="making-routes-independent-of-resources"></a>Crear rutas independientes de los recursos

En muchos sistemas, el recurso de operaciones o el grupo de recursos que deben realizar una operación debe ser especificado en la ruta. Sin embargo, en Supply Chain Management, puede definir un conjunto de requisitos que un recurso de operaciones debe cumplir para aplicarse a la operación. Por lo tanto, el recurso de operaciones o el grupo de recursos específicos que se usarán no tienen que determinarse hasta que la operación se programe realmente. Esta funcionalidad es especialmente útil si tiene muchos trabajadores o máquinas que pueden realizar la misma operación.  

Por ejemplo, especifica que una operación requiere un recurso de operaciones de tipo **Máquina** con una capacidad de **Sellado** de 20 toneladas. El motor de programación resolverá estos requisitos según un recurso de operaciones o un grupo de recursos específicos cuando se programa la operación. Dado que simplemente puede especificar estos requisitos en lugar de vincular la operación a una máquina específica, tiene mucha más flexibilidad. Además, el mantenimiento resulta más fácil cuando mueven los recursos o se agregan nuevos.  

Para obtener más información sobre los distintos tipos de requisitos de recurso y cómo usarlos, consulte Requisitos de recursos de operaciones y [Capacidades de recursos](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Compartir rutas a través de sitios

Si genera el mismo producto en más de un sitio de producción y si los pasos para generar el producto son iguales en todos los sitios, puede diseñar a menudo una ruta compartida que se utilice a través de todos los sitios de producción. Para crear una ruta compartida, no especifique un sitio en la misma ruta. Sin embargo, debe aún así crear una versión de ruta que asocie la ruta compartida con producto en cada sitio.  

También debe asegurarse de que los requisitos de recurso para cada operación en la ruta no solicitan recursos de operaciones o grupos de recursos específicos, pero en su lugar se expresan en términos de características de los recursos requeridos. El motor de programación podrá posteriormente asignar los recursos de operaciones adecuados desde el sitio en el que la producción está programada. Por ejemplo, si hay pequeñas diferencias en el tiempo de ejecución o si el tiempo de configuración para una determinada operación es específico para un sitio, puede especificar esta información agregando una relación de operación adicional para dicho sitio.  

Para aprovechar las ventajas de las prestaciones de rutas compartidas, debe usar el consumo de recursos en la lista de materiales (BOM)correspondiente. Cuando establece el indicador para el consumo de recursos en la línea de BOM, el almacén y la ubicación desde donde se deben consumir las materias primas se deducen del recurso de operaciones en el que está programada la operación. Por lo tanto, el almacén y la ubicación no tienen que determinase hasta que la producción se programe realmente. De esta manera, puede crear la BOM y la ruta de forma independiente de la ubicación física donde se genera el producto.

### <a name="standard-operation-relations"></a>Relaciones de operaciones estándar

Si su empresa utiliza operaciones estandarizadas en la producción, y si hay muy poca variación o ninguna en el tiempo de configuración, el tiempo de ejecución, los cálculos de consumo, el cálculo de costes, etc., es posible que se pueda beneficiar de crear relaciones de operación predeterminadas para todas las operaciones. En este caso, evite crear relaciones de operación que sean específicas de cualquier ruta o producto liberado.  

Si también expresa los requisitos de recurso en términos de conocimientos y capacidades y crea sus rutas independientemente del sitio, puede ayudar a mantener el mantenimiento continuado de los procesos empresariales al mínimo.  

Cuando usa este enfoque, la página **Relaciones de operación** se convierte en su destino principal para mantener los tiempos de ejecución y otras propiedades.

### <a name="resource-specific-process-times"></a>Tiempos de proceso específicos de los recursos

Si no especifica un recurso de operaciones o un grupo de recursos como parte de los requisitos de recurso para una operación, los recursos aplicables pueden operar a varias velocidades. Por lo tanto, el tiempo necesario para procesar una operación puede variar. Para resolver este problema, puede usar el campo **Fórmula** de la relación de operación para especificar cómo se calcula el tiempo del proceso. Están disponibles las siguientes opciones:

- **Estándar**: (opción predeterminada) el cálculo usa solo los campos de la relación de operación y multiplica el tiempo de ejecución especificado por la cantidad del pedido.
- **Capacidad:** el cálculo incluye el campo **Capacidad** del recurso de operaciones. Por lo tanto, el tiempo depende de los recursos. El valor que se especifica en el recurso de operaciones es la capacidad por hora. El **Tiempo de proceso** se calcula como **Cantidad de pedido** dividida por **Capacidad**.
- **Lote:** una capacidad de lote se calcula usando la información de la relación de operación. El número de lotes y, por tanto, el tiempo del proceso se pueden calcular en función de la cantidad del pedido.
- **Lote de recursos:** esta opción es básicamente la misma que la opción **Lote**. Sin embargo, el cálculo incluye el campo **Capacidad de lote** del recurso de operaciones. Por lo tanto, el tiempo depende de los recursos.

### <a name="set-up-route-groups"></a>Configurar grupos de rutas

Puede definir los grupos de rutas y la configuración de su ruta o tipos de trabajo en **Control de producción > Configuración > Rutas > Grupos de rutas**. Para cada ruta/tipo de trabajo en el grupo de rutas, podrá seleccionar o borrar las siguientes opciones:

- **Activación**: seleccione esta opción para habilitar cálculos y la programación del tipo de trabajo seleccionado y para recibir comentarios de trabajos cuando se ejecuta la programación de trabajos. Necesita seleccionar esta opción para habilitar el tipo de trabajo y a continuación, seleccionar el resto de las opciones para ese tipo de trabajo. Si la activación no está seleccionada, este tibo de trabajo no se habilitará, independientemente de la selección de las otras opciones. 
- **Gestión de trabajo**: seleccione esta opción para incluir el tipo de trabajo en la gestión de trabajo cuando ejecuta la programación de trabajos. 
- **Tiempo de trabajo**: seleccione esta opción para programar el tipo de trabajo de acuerdo con el calendario de horas de trabajo que se define para el recurso de operaciones, de lo contrario se usará el calendario gregoriano. El horario de trabajo se puede programar según el calendario gregoriano o según el calendario de trabajo definido. Si activa esta opción, la programación se basará en el calendario de horario de trabajo definido. Además, el trabajo del tipo de trabajo se programa desde la medianoche de la fecha que se define como la fecha de inicio del trabajo.
- **Capacidad**: seleccione esta opción para reservar capacidad para el tipo de trabajo cuando ejecuta la programación de trabajos. Si activa esta opción, se reserva capacidad cuando se ejecuta la programación del tipo de trabajo seleccionado. Esto le proporciona una visión general de los tipos de trabajo en cada grupo de rutas que usan los recursos de operaciones. Por ejemplo, en una situación en la que recursos de sequía son recursos de cuello de botella, estos recursos se deben especificar como cuellos de botella. Las operaciones de sequía que se asignan a los tipos de trabajo del tiempo en cola reservarán recursos de sequía. 

Para cada uno de los tipos de trabajo, primero debe activarlo o desactivarlo. Cuando se desactiva, no se tendrá en cuenta ninguna otra de configuración (gestión de trabajos, horario de trabajo y capacidad), ya que el tipo de trabajo no estará activo. 

Entre los tipos de trabajo puede encontrar Superposición. La superposición permite que diferentes trabajos sean efectuados al mismo tiempo. Cuando los trabajos están superpuestos, los recursos pueden ser utilizados pero no se pueden reservar para trabajos específicos.
Por lo tanto, cuando la activación se selecciona para la superposición, el resto de los valores (gestión de trabajos, horario de trabajo, y capacidad) no crea ningún impacto en el grupo de rutas. 

> [!NOTE]
> Al actualizar las versiones puede encontrar el siguiente error: **“Error de CRL producido como al llamar al motor de programación”**. Si recibe este error, vaya a la página **Grupos de rutas** y para todas las rutas donde ha activado **Superposición**, desactive las opciones **Gestión de trabajos**, **Horario de trabajo** y **Capacidad**. 

## <a name="additional-resources"></a>Recursos adicionales

- [Listas de materiales y fórmulas](bill-of-material-bom.md)

- [Categorías de costes utilizadas en las rutas de producción](../cost-management/cost-categories-used-production-routings.md)

- [Capacidades de recursos](resource-capabilities.md)

- [Visión general de la firma electrónica](../../fin-and-ops/organization-administration/electronic-signature-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]