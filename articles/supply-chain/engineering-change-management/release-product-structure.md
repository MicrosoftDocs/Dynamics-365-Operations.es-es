---
title: Liberar estructuras de producto
description: Este tema explica cómo puede liberar estructuras de productos completas además de lanzar productos junto con sus versiones de ingeniería. De esta manera, puede asegurarse de que los datos de productos relevantes para la ingeniería se puedan reutilizar fácilmente en diferentes entidades legales.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4dc1b073350044ef8afb765470ed14da88a70fdd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567496"
---
# <a name="release-product-structures"></a>Liberar estructuras de producto

[!include [banner](../includes/banner.md)]

Para garantizar que los datos de productos relevantes para la ingeniería se puedan reutilizar fácilmente en diferentes entidades legales, puede liberar estructuras de productos completas además de lanzar productos junto con sus versiones de ingeniería. Por lo tanto, puede liberar estructuras de listas de materiales (BOM) de varios niveles junto con el padre en una sola acción de liberación. En este caso, también se liberan la lista de materiales y los productos de nivel inferior.

Los productos de ingeniería son creados y mantenidos por su empresa de ingeniería de tal manera que cumplen con los requisitos de calidad a medida que se diseñan. Cada empresa operativa que fabrica un producto necesita el mismo producto y la misma lista de materiales subyacente. Dependiendo de la instalación de producción, la ruta puede crearse localmente. En este caso, no lanzará una ruta junto con el producto. Para las entidades legales que venderán los productos pero no los fabricarán, es posible que no se requiera la lista de materiales.

Para que el proceso sea más eficiente, todos los datos relevantes para la ingeniería se pueden entregar a otras compañías operativas al mismo tiempo. Estos datos incluyen la estructura del producto. Durante el proceso de publicación, puede elegir qué parte de los datos del producto debe publicarse.

Para obtener más información sobre empresas de ingeniería y empresas operativas, consulte [Empresas de ingeniería y reglas de propiedad de datos](engineering-org-data-ownership-rules.md).

Tenga en cuenta que puede lanzar tanto productos estándar como productos de ingeniería junto con la estructura de producto de lanzamiento. Durante este proceso, se liberará toda la estructura del producto, incluso la lista de materiales y la ruta de la empresa en la que se lanzan los productos.

Para ver un ejemplo de cómo lanzar un producto, consulte [Liberar un producto de ingeniería a una empresa local](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Datos publicados para un producto cuando se utiliza la estructura del producto de lanzamiento

Los siguientes datos se incluyen en el lanzamiento de productos de ingeniería:

- **Datos del producto** - Se crea un nuevo producto lanzado.
- **Datos de la versión de ingeniería** - Se crea o actualiza la versión de ingeniería y sus datos. Tenga en cuenta que si vuelve a publicar la misma versión de ingeniería para una empresa operativa, los datos de ingeniería se sobrescribirán.
- **Atributos de ingeniería** - Se crean o actualizan los atributos de ingeniería y sus valores.
- **Lista de materiales de ingeniería** - La lista de materiales de ingeniería y sus líneas se pueden crear o actualizar. Para obtener más información acerca de la propiedad de datos, vea [Propietarios de productos](product-owner.md).
- **Rutas de ingeniería** - Se crean o actualizan las rutas y sus operaciones. Para obtener más información acerca de la propiedad de datos, vea [Propietarios de productos](product-owner.md).
- **Documentos de ingeniería** - Se crean o actualizan los documentos de ingeniería que están conectados a la versión de ingeniería.

Cuando activa la gestión de cambios de ingeniería en su sistema, la estructura del producto de lanzamiento está disponible. Además, los productos estándar incluirán sus listas de materiales y rutas cuando se publiquen.

## <a name="product-acceptance"></a>Aceptación del producto

**Aceptación del producto** es un parámetro clave que influye en el proceso de liberación. Puede configurar este parámetro para cada empresa yendo a **Gestión de cambios de ingeniería \> Preparar \> Parámetros de gestión de cambios de ingeniería**. Para más información, vea [Parámetros de gestión de cambios de ingeniería](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Aceptación automática de productos

Cada lanzamiento de productos de ingeniería comienza cuando alguien de la empresa de ingeniería selecciona un producto para su lanzamiento. Cuando el parámetro **Aceptación del producto** está establecido en *Automático*, el usuario de la empresa de ingeniería decide qué datos del producto deben entregarse automáticamente a las empresas operativas. El producto se entregará automáticamente a las empresas que se seleccionen en el asistente de lanzamiento.

### <a name="manual-product-acceptance"></a>Aceptación manual del producto

Cada lanzamiento de productos de ingeniería comienza cuando alguien de la empresa de ingeniería selecciona un producto para su lanzamiento. Cuando el parámetro **Aceptación del producto** está establecido en *Manual*, el usuario de la empresa de ingeniería decide qué datos del producto deben entregarse automáticamente a las empresas operativas. Luego, un usuario de cada compañía operativa revisa los datos del producto y decide si acepta el lanzamiento. El usuario de la empresa operativa puede configurar las siguientes opciones cuando se reciben los datos:

- Si los productos (actualizaciones) no son relevantes para la empresa operativa, el usuario puede optar por no aceptar el lanzamiento.
- El usuario puede cambiar la plantilla de artículo para nuevos productos.
- El usuario puede elegir si el producto debe lanzarse junto con sus listas de materiales y / o rutas, y si deben lanzarse como aprobados y activos.
- El usuario puede cambiar las fechas de vigencia de los productos.

Para ver un ejemplo de cómo aceptar un producto, consulte [Revisar y aceptar el producto antes de lanzarlo en la empresa local.](engineering-scenarios.md#accept).

> [!NOTE]
> Para productos estándar, puede liberar de cualquier entidad legal a cualquier otra entidad legal. Para los productos de ingeniería, la única entidad legal de la que puede liberarse es la empresa de ingeniería.

## <a name="release-policies"></a>Políticas de lanzamiento

No todas las empresas operativas necesitan los mismos datos de productos. En general, las empresas operativas que fabrican productos de ingeniería requieren una lista de materiales, mientras que las empresas operativas que solo venden productos de ingeniería no requieren una lista de materiales. Puede utilizar políticas de lanzamiento para establecer los parámetros que se utilizan para el lanzamiento de productos.

Para obtener más información sobre categorías de productos de ingeniería, consulte [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

Durante el proceso de lanzamiento, puede influir en la configuración.

## <a name="create-and-manage-product-release-policies"></a>Crear y administrar políticas de lanzamiento de productos

Para trabajar con directivas de liberación de productos, vaya a **Gestión de cambios de ingeniería \> Preparar \> Directivas de liberación de productos**. Luego siga uno de estos pasos.

- Para crear una nueva directiva, seleccione **Nuevo** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para editar una directiva existente, selecciónelo en el panel de lista, seleccione **Editar** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para eliminar una política existente, selecciónela en el panel de lista, seleccione **Editar** en el Panel de acciones, y luego, en la ficha desplegable **General**, asegúrese de que la opción **Activo** está configurada en *No*. A continuación, seleccione **Eliminar** en el panel de acciones.

### <a name="header"></a>Encabezado

Configure los siguientes campos en el encabezado de una directiva de liberación de producto.

| Campo | Descripción |
|---|---|
| Nombre | Introduzca un nombre para la directiva. |
| Descripción | Especificar una descripción de la directiva. |

### <a name="general-fasttab"></a>Ficha desplegable General

Configure los siguientes campos en la ficha desplegable **General** de una directiva de liberación de producto.

| Campo | Descripción |
|---|---|
| Tipo de producto | Seleccione si la política se aplica a los productos de tipo *Artículo* o *Servicio*. No puede cambiar esta configuración después de guardar el registro. |
| Tipo de producción | Este campo aparece solo cuando ha habilitado [gestión del cambio de fórmula](manage-formula-changes.md) en su sistema. Seleccione el tipo de producción al que se aplica esta política de lanzamiento:<ul><li>**Coproducto**: utilice esta directiva de lanzamiento para administrar coproductos. Los coproductos se producen durante el proceso de fabricación y no se versionan ni son productos de ingeniería. Las directivas de lanzamiento de coproductos pueden ayudar a garantizar que configuraciones importantes, como **Grupo de dimensiones de almacenamiento** y **Grupo de dimensiones de seguimiento**, se configuran mediante una plantilla de producto publicado antes de que se publiquen en una empresa.</li><li>**Producto derivado**: utilice esta directiva de lanzamiento para administrar productos derivados. Los productos derivados se producen durante el proceso de fabricación y no se versionan ni son productos de ingeniería. Las directivas de lanzamiento de productos derivados pueden ayudar a garantizar que configuraciones importantes, como **Grupo de dimensiones de almacenamiento** y **Grupo de dimensiones de seguimiento**, se configuran mediante una plantilla de producto publicado antes de que se publiquen en una empresa.</li><li>**Ninguno**: utilice esta directiva para administrar productos estándar que no tienen versiones o productos de ingeniería, o coproductos o productos derivados.</li><li>**Elemento de planificación**: utilice esta directiva de liberación para gestionar los elementos de planificación que se producen mediante el proceso de fabricación. Los elementos de planificación utilizan fórmulas. Se parecen a los productos de fórmula, pero se utilizan para producir solo coproductos y productos derivados, no productos terminados.</li><li>**BOM**: utilice esta directiva de lanzamiento para administrar productos de ingeniería, que no usan fórmulas y, por lo general (pero no necesariamente) incluyen listas de materiales.</li><li>**Fórmula**: utilice esta directiva de liberación para gestionar los elementos terminados que se producen mediante el proceso de fabricación. Estos elementos tendrán una fórmula pero no una lista de materiales.</li></ul> |
| Aplicar plantillas | Seleccione una de las siguientes opciones para especificar si se deben aplicar las plantillas de lanzamiento de productos y cómo se deben aplicar cuando se utiliza la política:<ul><li>**Siempre** - Siempre se debe utilizar una plantilla de producto liberado para los lanzamientos. Si selecciona esta opción, utilice la ficha desplegable **Todos los productos** para especificar la plantilla que se utiliza para cada empresa a la que se envía. Si no especifica una plantilla para cada empresa que aparece en la ficha desplegable **Todos los productos**, recibirá un error cuando intente guardar la política.</li><li>**Opcional** - Si se especifica un producto publicado por plantilla para una empresa que figura en la ficha desplegable **Todos los productos**, esa plantilla se usará cuando la publique para esa empresa. De lo contrario, no se utilizará ninguna plantilla. Si selecciona esta opción, puede guardar la política sin asignar plantillas a todas las empresas. (No se mostrará ninguna advertencia).</li><li>**Nunca** - No se utilizará ningún producto publicado por plantilla para ninguna empresa a la que le entregue, incluso si se especifica una plantilla para las empresas que figuran en la ficha desplegable **Todos los productos**. Las columnas de la plantilla no estarán disponibles.</li></ul> |
| Activa | Utilice esta opción para ayudar a mantener sus políticas de lanzamiento. Ponlo en *Sí* para todas las políticas de lanzamiento que utilice. Ponlo en *No* para marcar una política de lanzamiento como inactiva cuando no se utiliza. Tenga en cuenta que no puede desactivar una política de lanzamiento asignada a una categoría de producto de ingeniería y solo puede eliminar las políticas de lanzamiento inactivas. |

### <a name="all-products-fasttab"></a>Ficha desplegable Todos los productos

Sobre la ficha desplegable **Todos los productos**, agregue una fila para cada empresa operativa para la que desee utilizar esta política para publicar. Utilice los botones de la ficha desplegable **Todos los productos** para agregar y eliminar filas según sea necesario. Para cada fila que agregue, configure los siguientes campos.

> [!NOTE]
> Los ajustes de la ficha desplegable **Todos los productos** se aplican tanto a productos de ingeniería como a productos estándar.

| Campo | Descripción |
|---|---|
| Id. de cuenta de empresa | Seleccione la empresa a la que se aplica la fila. Los parámetros de la fila se aplicarán cuando los productos se lancen a esta empresa. |
| Plantilla producto liberada | Agregue una plantilla para el producto. |
| Copiar aprobación de L. MAT | Seleccione esta casilla de verificación para copiar el estado de aprobación de la lista de materiales a la empresa receptora. |
| Copiar activación de L. MAT | Seleccione esta casilla de verificación para copiar el estado de activación de la lista de materiales a la empresa receptora. |
| Copiar aprobación de ruta | Seleccione esta casilla de verificación para copiar el estado de aprobación de la ruta a la empresa receptora.|
| Copiar activación de ruta | Seleccione esta casilla de verificación para copiar el estado de activación de la ruta a la empresa receptora. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Ficha desplegable de parámetros de opción para productos de ingeniería

Cada vez que agrega una fila en la ficha desplegable **Todos los productos**, una fila que tiene un valor **ID de cuentas de la empresa** coincidente también se crea en la ficha desplegable **Parámetros de opción para productos de ingeniería**. Después, si quita una fila de la ficha desplegable **Todos los productos**, la fila que tiene un valor **ID de cuentas de la empresa** coincidente también se quita de la ficha desplegable **Parámetros de opción para productos de ingeniería**.

Para cada fila que se muestra en la ficha despleagble **Parámetros de opción para productos de ingeniería**, establezca los siguientes campos.

> [!NOTE]
> Los ajustes de la ficha desplegalbe **Parámetros de opción para productos de ingeniería** se aplican solo a productos de ingeniería.

| Campo | Descripción |
|---|---|
| Plantilla de L. MAT | Cuando se lanza un producto que tiene una lista de materiales, se agregarán las líneas de la plantilla de lista de materiales especificada. Este campo es útil para agregar componentes locales, como paquetes o instrucciones en el idioma local. |
| Ruta de plantilla | Cuando se lanza un producto que tiene una ruta, se agregarán las líneas de la plantilla de ruta especificada. |
| Copiar vigencia | Seleccione si las fechas de vigencia deben copiarse de la empresa de ingeniería a la empresa operativa cuando lance productos. |
| Agregar automáticamente a propuesta de liberación | Seleccione esta casilla de verificación para los productos que deben lanzarse automáticamente en la orden de cambio de ingeniería. De esta forma, los productos que pertenecen a las categorías de productos de ingeniería que utilizan esta política de lanzamiento pueden entregarse automáticamente a las empresas operativas donde se configura esta opción. (Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md)).

### <a name="review-each-product-when-you-release-it"></a>Revise cada producto cuando lo lance

Cuando se lanzan productos de ingeniería que tienen listas de materiales o rutas, los parámetros se establecerán en los valores predeterminados, como se indica en la política de lanzamiento. Como usuario, puede influir en este comportamiento en el lado de la liberación cuando utiliza la estructura del producto de liberación.

Para lanzar productos de ingeniería, en la página **Productos lanzados**, seleccione los productos que desea lanzar y luego seleccione **Estructura del producto de liberación** para abrir el asistente de lanzamiento. La página **Seleccionar productos de ingeniería para lanzar** muestra los productos. Seleccione un solo producto y luego seleccione **Detalles de lanzamiento** para revisar los detalles de la versión del producto.

Sobre la página **Detalles de lanzamiento**, puede cambiar el valor de **Recibir lista de materiales**, **Copiar aprobación de lista de materiales**, **Copiar activación de lista de materiales**, **Recibir lista de materiales**, **Copiar aprobación de ruta** y **Copiar activación de ruta**. En el escenario push-pull, puede cambiar el valor de los mismos campos en el lado receptor, siempre que se liberen la lista de materiales y la ruta.

## <a name="product-owners-and-product-releases"></a>Propietarios de productos y lanzamientos de productos

Dado que los propietarios de productos saben qué entidades legales necesitan sus productos, solo los miembros del grupo de propietarios de productos de ese producto pueden lanzar un producto. Otros usuarios no pueden lanzar productos que no sean de su propiedad.

Este comportamiento se aplica solo cuando un producto se selecciona directamente para su lanzamiento. Productos que forman parte de la estructura de otro producto a través de una lista de materiales *pueden* ser liberados por usuarios no propietarios cuando lanzan el producto principal, siempre que sean propietarios del producto principal.

Por ejemplo, el producto X se asigna al grupo de propietarios de productos *Armarios de diseño*. El producto X también forma parte de la lista de materiales del producto Y, que se asigna al grupo de propietarios de productos *Ponentes de diseño*. Si un usuario del grupo propietario del producto *Ponentes de diseño* lanza el producto y su lista de materiales, el producto X se lanzará junto con el producto Y.

Para obtener más información, consulte [Propietarios de productos](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
