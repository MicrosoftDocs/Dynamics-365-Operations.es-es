---
title: Versiones de ingeniería y categorías de productos de ingeniería
description: Este tema proporciona información sobre el concepto de versiones de ingeniería. Las versiones de ingeniería garantizan que los diferentes estados de un producto y sus datos se mantengan actualizados y claros, y que se puedan visualizar en el sistema.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 1ebcb43b6c62ce895d3b1b36d7793f90208ca23e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836647"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Versiones de ingeniería y categorías de productos de ingeniería

[!include [banner](../includes/banner.md)]

Los productos de ingeniería evolucionan durante su ciclo de vida del producto, por muchas razones. Por ejemplo, se pueden introducir cambios para mejorar la capacidad de servicio del producto, cambiar un componente porque el proveedor ya no lo ofrece, responder a nuevos conocimientos o corregir errores en el diseño inicial. También hay muchas razones por las que estos cambios deben almacenarse como parte de un producto en curso, de tal manera que los datos anteriores no se sobrescriban. Estas son algunas de estas razones:

- Desea realizar un seguimiento del producto tal como se fabricó y se entregó a sus clientes en estados anteriores del ciclo de vida.
- Necesita un plazo de entrega antes de aprobar y aplicar los cambios.
- Desea tener una marca de tiempo en cada cambio y desea poder entregar productos fabricados previamente por separado.

Las *versiones de ingeniería* garantizan que los distintos estados de un producto y sus datos se mantengan actualizados y claros, y que se puedan visualizar en el sistema. Este concepto le ayuda a mantener la coherencia, bloquear la lista de materiales (BOM) para la producción, eliminar la variabilidad e identificar fácilmente los cambios.

Generalmente, la regla *función-forma-ajuste* se aplica para determinar si un cambio requiere un nuevo producto, una nueva versión o una actualización de una versión existente. Cada uno de los tres términos en el nombre de esta regla se refiere a un aspecto específico de una pieza, lo que ayuda a los ingenieros a adaptar las piezas a las necesidades. La regla forma-ajuste-función aumenta la flexibilidad de los cambios de diseño, porque se requiere un costo mínimo de documentación y diseño para cambiar una pieza, siempre que se mantengan el ajuste, la forma y la función del producto.

- **Ajuste** se refiere a la capacidad de la pieza o función para conectarse, acoplarse o unirse a otra función o pieza en un ensamblaje. El ajuste permite que la pieza cumpla con las tolerancias de ensamblaje requeridas para que pueda ser útil.
- **Formar** se refiere a las características de una pieza o ensamblaje, como las dimensiones externas, el peso, el tamaño y la apariencia visual. La forma es el aspecto más afectado por las elecciones estéticas de un ingeniero. Incluye el gabinete, el chasis y el panel de control, que se convierten en la "cara" externa del producto.
- **Función** es un criterio que se cumple cuando la pieza cumple con eficacia y fiabilidad su propósito declarado. Por ejemplo, en un producto electrónico, la función puede depender de los componentes de estado sólido que se utilizan y del software o firmware. A menudo, también puede depender de las características del gabinete seleccionado. Dos de las razones más comunes por las que un gabinete puede fallar en el criterio de función son puertos mal ubicados o de tamaño reducido y etiquetado engañoso o faltante. 

## <a name="engineering-versions"></a>Versiones de ingeniería

Cuando utiliza productos de ingeniería, cada producto tiene al menos una versión de ingeniería. La versión de ingeniería inicial se crea automáticamente cuando crea un producto de ingeniería. Cada versión de ingeniería almacena los datos relevantes para la ingeniería que son específicos de esa versión. Algunos ejemplos de estos datos son:

- El número de versión y el número de versión anterior (si corresponde)
- Las fechas de entrada en vigor y hasta
- El estado activo de la versión del producto, que indica si la versión se puede liberar y utilizar en transacciones (para obtener más información, consulte [Disponibilidad del producto](product-readiness.md) .)
- La empresa de ingeniería que creó y es propietaria del producto (para obtener más información, consulte [Empresas de ingeniería y reglas de propiedad de datos](engineering-org-data-ownership-rules.md) .)
- Documentos de ingeniería relacionados, como un manual de ensamblaje, instrucciones para el usuario, imágenes y enlaces
- Los atributos de ingeniería (Para obtener más información, consulte [Atributos de ingeniería y búsqueda de atributos de ingeniería](engineering-attributes-and-search.md)).
- Las listas de materiales de ingeniería
- Las rutas de ingeniería

Puede actualizar estos datos en una versión existente, o crear una nueva versión, utilizando una *orden de cambio de ingeniería*. (Para más información, vea [Gestionar cambios en productos de ingeniería](engineering-change-management.md)). Si crea una nueva versión de un producto, el sistema copia todos los datos relevantes para la ingeniería en esa nueva versión. A continuación, puede modificar los datos de esa nueva versión. De esta manera, puede rastrear datos específicos para cada versión consecutiva. Para comparar las diferencias entre versiones de ingeniería consecutivas, inspeccione la orden de cambio de ingeniería, que incluye tipos de cambio que indican todos los cambios.

Como se ha dicho, la versión de ingeniería inicial se crea automáticamente cuando crea un producto de ingeniería. El número de versión para esta versión sigue la regla de número de versión que se define en la categoría de ingeniería para el producto. Para realizar la transición a una versión posterior, debe agregar el producto a una orden de cambio de ingeniería como una línea y debe establecer el campo **Impacto** en *Nueva versión*. La orden de cambio de ingeniería incluirá los detalles del cambio de la versión actual a la próxima versión.

Tenga en cuenta que un producto de ingeniería solo puede estar en una orden de cambio de ingeniería a la vez. Esta restricción garantiza la precisión de los datos y ayuda a evitar cambios superpuestos o contradictorios en el producto. También tenga en cuenta que el campo **Ingeniero** en la vista **Encabezamiento** de la orden de cambio de ingeniería muestra al ingeniero responsable de la orden de cambio. Si el ingeniero pertenece a un equipo definido en el sistema, el campo **Responsable** muestra el líder de ese equipo.

## <a name="track-versions-in-transactions"></a>Seguimiento de versiones en transacciones

Cuando utiliza la gestión de cambios de ingeniería, los datos maestros de sus productos siempre incluyen una o más versiones de ingeniería. En su configuración de productos de ingeniería, puede elegir si la versión de ingeniería también forma parte de *transacciones logísticas*. (Para obtener más información, consulte [Configurar categorías de productos de ingeniería](#product-category) más adelante en este tema). Si el impacto logístico es relevante, difiere por producto y por empresa. A veces, solo se utiliza la última versión de un producto. Por lo tanto, cuando introduce una nueva versión, la versión anterior ya no se puede utilizar. En otros casos, se requiere la versión anterior en transacciones logísticas para superar los siguientes desafíos:

- El departamento de Logística debe enviar dos piezas de un producto a un cliente. En este caso, debe decidir si desea o permitirá que se envíen dos versiones diferentes.
- Más tarde se descubre que ocurre un problema y que está relacionado con un cambio específico. En este caso, podría ser beneficioso determinar exactamente qué versión se envió en cada pedido.
- Las empresas normalmente quieren enviar versiones antiguas primero, para eliminarlas gradualmente del inventario. Especialmente para productos de bajo volumen, este enfoque a menudo se puede manejar determinando las fechas de vigencia de la nueva versión en relación con las predicciones sobre cuándo se agotarán las existencias de la versión anterior. Sin embargo, a veces es posible que no pueda realizar esta comparación o que considere que la incertidumbre de las predicciones del nivel de existencias es demasiado alta.

La decisión de hacer visibles las versiones en el inventario depende de factores como los que se mencionaron anteriormente, además de la práctica de la empresa y otras consideraciones que son específicas de cada empresa. Puede especificar el comportamiento de la *categoría de producto de ingeniería*. Luego se aplicará a todos los productos que se creen a partir de esa categoría, para todas las empresas a las que se lanza el producto.

Para los productos que se configuran para que tengan un impacto logístico, la versión de ingeniería debe especificarse en cada transacción. Aunque el sistema propondrá la *última versión activa*, puede seleccionar entre todas las versiones activas que están disponibles para la empresa. Para los productos que se configuran para que no tengan un impacto logístico, la versión de ingeniería no se especifica en las transacciones. Sin embargo, el sistema utiliza la última versión activa. Por ejemplo, cuando agrega un producto a una lista de materiales de producción, se utilizará la última versión, y cuando ejecute la planificación maestra, se asumirá la última versión.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Configurar categorías de productos de ingeniería

Una categoría de productos de ingeniería proporciona una base para crear un producto de ingeniería específico. Cada categoría establece un conjunto de valores y políticas predeterminados. Por lo tanto, cuando crea un producto de ingeniería, primero selecciona la categoría desde la que crearlo.

Tenga en cuenta que un nuevo tipo de jerarquía de categorías (*jerarquía de productos de ingeniería*) se configura automáticamente para usted. Puede crear las categorías manualmente yendo a **Gestión de cambios de ingeniería \> Preparar \> Detalles de la categoría de productos de ingeniería**.

Cada categoría de producto de ingeniería establece el comportamiento predeterminado de los productos de ingeniería que se crean en función de esa categoría. Después de haber creado un producto de ingeniería, no puede cambiar su categoría de producto de ingeniería. Sin embargo, si selecciona la categoría incorrecta, puede eliminar el producto y luego volver a crearlo.

Cuando se crea una categoría de producto de ingeniería, no puede cambiar la siguiente configuración:

- Compañía de ingeniería
- Tipo de producto
- Subtipo de producto
- Grupo de dimensiones de producto
- Tecnología de configuración
- Regla de número de versión

Otras configuraciones pueden heredar valores predeterminados que se configuran para la categoría de productos de ingeniería. Sin embargo, de acuerdo con las reglas del sistema, esos valores se pueden cambiar.

Puede trabajar con categorías de producto de ingeniería, vaya a **Gestión de cambios de ingeniería \> Preparar \> Detalles de la categoría de productos de ingeniería**. Luego siga uno de estos pasos.

- Para crear una nueva categoría, seleccione **Nuevo** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para editar una categoría existente, selecciónelo en el panel de lista, seleccione **Editar** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para eliminar una categoría existente, selecciónelo en el panel de lista y luego seleccione **Eliminar** en el Panel de acciones.

### <a name="header"></a>Encabezado

Configure los siguientes campos en el encabezado de una categoría de producto de ingeniería.

| Campo | Descripción |
|---|---|
| Nombre | Permite especificar un nombre para la categoría producto de ingeniería. |
| Compañía de ingeniería | Seleccione la empresa de ingeniería donde se pueden crear los productos de esta categoría de productos de ingeniería y dónde se mantendrán. |

### <a name="details-fasttab"></a>Ficha desplegable Detalles

Configure los siguientes campos en la ficha desplegable **Detalles** de una categoría de producto de ingeniería.

| Campo | Descripción |
|---|---|
| Tipo de producto | Seleccione si la categoría se aplica a productos o servicios. |
| Seguimiento de versiones en transacciones | Seleccione si la versión del producto debe estamparse en todas las transacciones (impacto logístico). Por ejemplo, si realiza un seguimiento de la versión en las transacciones, cada orden de venta mostrará qué versión específica del producto se vendió en esa orden de venta. Si no realiza un seguimiento de la versión en las transacciones, los pedidos de venta no mostrarán qué versión específica se vendió. En cambio, siempre muestran la última versión.<ul><li>Si esta opción se establece en *Sí*, se crea un producto maestro para el producto, y cada versión del producto será una variante que utiliza la dimensión de producto *versión*. El campo **Subtipo de producto** se establece automáticamente en *Maestro de producto* y debe seleccionar un grupo de dimensiones de producto donde la dimensión *versión* está activa. Solo se mostrarán los grupos de dimensiones de productos donde *versión* sea una dimensión activa. Puede crear nuevos grupos de dimensiones de productos seleccionando el botón **Editar** (símbolo de lápiz).</li><li>Si esta opción se establece en *No*, la la dimensión del producto *versión* no se utilizará. A continuación, puede seleccionar si desea crear un producto o un producto maestro que utilice las otras dimensiones.</li></ul><p>Esta opción se usa a menudo para productos que tienen una diferencia de costo entre versiones, o productos donde se aplican diferentes condiciones en relación con el cliente. Por tanto, es importante indicar qué versión se utilizó en cada transacción.</p> |
| Subtipo de producto | Seleccione si la categoría incluirá productos o productos maestros. Para los maestros de producto, se utilizarán las dimensiones del producto.
| Grupo de dimensiones de producto | La opción **Seguimiento de versiones en transacciones** le ayuda a seleccionar el subtipo de producto. Si especificó que desea realizar un seguimiento de la versión en las transacciones, se mostrarán los grupos de dimensiones de producto donde se use la dimensión *versión*. En caso contrario, solo se mostrarán los grupos de dimensiones de productos donde no se use la dimensión *versión*. |
| Estado de ciclo de vida de producto en el momento de su creación | Configure el estado del ciclo de vida del producto predeterminado que debe tener un producto de ingeniería cuando se crea por primera vez. Para más información, vea [Estados y transacciones del ciclo de vida del producto](product-lifecycle-state-transactions.md). |
| Regla de número de versión | Seleccione la regla de número de versión que se aplica a la categoría.<ul><li>**Manual** - Usted elige el número de versión para cada nueva versión.</li><li>**Automático** - El sistema establece el número de versión, según un formato que usted defina. Cuando configure el formato, use un signo de número (\#) para representar un dígito y cualquier otro carácter para representar un valor constante. Por ejemplo, si define el formato como *V-\#\#*, la primera versión será "V-01", la segunda versión será "V-02" y así sucesivamente.</li><li>**Lista** - El sistema toma el siguiente número de una lista predefinida de valores personalizados que usted define.</li></ul> |
| Aplicar vigencia | Seleccione si las fechas de vigencia de las versiones de ingeniería deben ser contiguas o si puede haber espacios y superposiciones. Esta configuración afecta la forma en que puede utilizar los campos **Válido desde** y **Efectivo para** para cada versión de ingeniería donde se aplica la categoría.<ul><li>Si esta opción se establece en *Sí*, debe especificarse un valor **Válido desde** para cada versión y no se permiten superposiciones ni espacios entre versiones. El rango de fechas para cada versión de ingeniería está conectado directamente a las versiones de ingeniería anterior y siguiente, si existen. En este escenario, siempre se usa la versión más reciente y las versiones anteriores ya no se usan.</li><li>Si esta opción se establece en **No**, no hay restricciones en los campos de fecha de vigencia para las versiones de ingeniería y se permiten tanto superposiciones como espacios. En este escenario, varias versiones pueden estar activas al mismo tiempo y puede trabajar con cualquier versión activa.</li></ul><p>Esta opción también afecta a las listas de materiales y las rutas que están conectadas a una versión del producto. Para obtener más información, consulte la sección [Conecte listas de materiales y rutas a versiones de ingeniería](#boms-routes) más adelante en este tema.</p> |
| Usar nomenclatura de regla de números | Establezca esta opción en *Sí* para habilitar reglas para definir un número de producto mediante el uso de secuencias numéricas, nombres y valores de atributos de ingeniería y constantes de texto como segmentos. Para crear o modificar reglas, seleccione el botón **Editar**. |
| Usar nomenclatura de regla de nombres | Establezca esta opción en *Sí* para habilitar reglas para definir un nombre mediante los nombres de atributos de ingeniería, valores de atributos de ingeniería y constantes de texto como segmentos. Para crear o modificar reglas, seleccione el botón **Editar**. |
| Usar nomenclatura de regla de descripción | Establezca esta opción en *Sí* para habilitar reglas para definir la descripción mediante los nombres de atributos de ingeniería, valores de atributos de ingeniería y constantes de texto como segmentos. Para crear o modificar reglas, seleccione el botón **Editar**. |

### <a name="attributes-fasttab"></a>Ficha desplegable Atributos

Utilice la cuadrícula de la ficha desplegable **Atributos** para configurar los atributos de ingeniería que se aplican a los productos que pertenecen a esta categoría. Para obtener más información sobre cómo crear atributos de ingeniería, consulte [Atributos de ingeniería y búsqueda de atributos de ingeniería](engineering-attributes-and-search.md).

Utilice los botones de la ficha desplegable **Atributos** para agregar, quitar y organizar atributos en la cuadrícula.

Si cambia la selección de atributos para una categoría de ingeniería y ya existen productos que se basan en esa categoría, debe decidir si aplica los cambios a esos productos. Si desea que los productos existentes reflejen los cambios, seleccione **Actualizar productos existentes** en la ficha desplegable **Atributos**.

Para cada fila que agregue a la cuadrícula, configure los siguientes campos.

| Campo | Descripción |
|---|---|
| Nombre | Seleccione el atributo para agregar. |
| Valor | Seleccione el valor predeterminado para el atributo. |
| Obligatoria | Para los atributos de tipo *Booleano*, si esta opción se establece en *Sí*, los usuarios deben establecer el atributo en *Sí*. Si esta opción se establece en *No*, los usuarios pueden establecer el atributo en *Sí* o *No*. Para otros tipos de datos, la configuración de esta opción es solo informativa. |
| Atributo de lote | Seleccione si el atributo debe propagarse a través de la funcionalidad por lotes. |

### <a name="readiness-policy-fasttab"></a>Ficha desplegable Política de preparación

Utilice el campo **Política de preparación del producto** para seleccionar la política de preparación que se aplica a los productos que pertenecen a esta categoría. Para obtener más información, consulte [Preparación del producto](product-readiness.md).

### <a name="release-policy-fasttab"></a>Ficha desplegable Política de versiones

Utilice el campo **Política de lanzamiento del producto** para seleccionar la política de lanzamiento que se aplica a los productos que pertenecen a esta categoría. Para obtener más información, consulte [Liberar estructuras de productos](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Conecte listas de materiales y rutas a versiones de ingeniería

El escenario de la opción **Hacer cumplir la efectividad** es importante para la conexión de listas de materiales y rutas a cada versión de ingeniería. Puede activar varias listas de materiales o rutas por producto solo si hay una diferencia en cualquiera de las siguientes configuraciones:

- Dimensión de producto
- Cantidad
- Sitio
- Fechas de vigencia

Las listas de materiales de ingeniería y las rutas se crean a partir de la versión de ingeniería en la que se aplican. Pueden ser reconocidos por la marca de verificación en la casilla de verificación **Ingeniería controlada**. Cuando trabaja con listas de materiales y rutas de ingeniería, normalmente no las diseñará utilizando diferentes cantidades. Por lo general, tampoco diseñará diferentes listas de materiales por sitio. Además, para las listas de materiales y las rutas de ingeniería, las fechas de vigencia siempre se toman de la versión de ingeniería. Por lo tanto, una versión de ingeniería, su lista de materiales y su ruta tendrán las mismas fechas de vigencia.

Para los productos en los que utiliza la dimensión del producto *versión* (junto con el impacto logístico en las transacciones), la versión también se agrega a las listas de materiales y rutas. Este comportamiento ayuda a diferenciar las listas de materiales y las rutas de versiones consecutivas, independientemente de la configuración de **Hacer cumplir la efectividad**.

Para los productos en los que no utiliza la dimensión del producto *versión* (sin impacto logístico en las transacciones), la versión no se agrega a las listas de materiales o rutas. Por lo tanto, no habrá diferencia entre las listas de materiales y las rutas de versiones consecutivas. En este caso, le recomendamos encarecidamente que configure la opción **Hacer cumplir la efectividad** en *Sí*. De esta forma, ayuda a evitar que las versiones de ingeniería se superpongan y también puede activar la lista de materiales y la ruta de una versión más nueva sin tener que desactivar primero la lista de materiales y la ruta de la versión anterior. Si configura la opción **Hacer cumplir la efectividad** como *Sí* en este caso, debe desactivar manualmente las listas de materiales y las rutas de versiones anteriores antes de poder activar la última versión.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]