---
title: Aplicación Visibilidad de inventario
description: Este tema describe cómo usar la aplicación Visibilidad de inventario.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345011"
---
# <a name="inventory-visibility-app"></a>Aplicación Visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tema describe cómo usar la aplicación Visibilidad de inventario.

Visibilidad de inventario proporciona una aplicación basada en modelo para la visualización. La aplicación contiene tres páginas: **Configuración**, **Visibilidad operativa** y **Resumen de inventario**. Tiene las siguientes características:

- Proporciona una interfaz de usuario (IU) para la configuración disponible y la configuración de reserva flexible.
- Admite consultas de inventario disponible en tiempo real en varias combinaciones de dimensiones.
- Proporciona una interfaz de usuario para publicar solicitudes de reserva.
- Proporciona una vista personalizada del inventario disponible para productos junto con todas las dimensiones.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, instale y configure el complemento de visibilidad de inventario como se describe en [Configurar visibilidad del inventario](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Configuración

La página **Configuración** le ayuda a configurar la configuración disponible y la configuración de reserva flexible. Una vez instalado el complemento, la configuración predeterminada incluye el valor de Microsoft Dynamics 365 Supply Chain Management (el origen de datos `fno`). Puede revisar la configuración predeterminada. Además, según sus requisitos comerciales y los requisitos de registro de inventario de su sistema externo, puede modificar la configuración en [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) para estandarizar la forma en que los cambios de inventario se pueden publicar, organizar y consultar en los múltiples sistemas.

### <a name="define-data-sources"></a>Definir orígenes de datos

Puede definir cada *origen de datos* que desea integrar con Visibilidad de inventario. Visibilidad de inventario admite la integración con varios orígenes de datos, como su sistema de punto de venta (PDV), Supply Chain Management y otros sistemas externos. De forma predeterminada, Supply Chain Management está configurado como origen de datos predeterminado (`fno`) en Visibilidad de inventario.

Para añadir un origen de datos, siga estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, seleccione **Nuevo origen de datos** para agregar un origen de datos.

> [!NOTE]
> Cuando agregue un origen de datos, asegúrese de validar el nombre del origen de datos, las medidas físicas y las asignaciones de dimensiones antes de actualizar la configuración del servicio de Visibilidad de inventario. No podrá modificar esta configuración después de seleccionar **Actualizar configuración**.

### <a name="set-up-dimension-mappings"></a>Configurar asignaciones de dimensiones

Visibilidad del inventario proporciona una lista de dimensiones base que se pueden asignar a partir de las dimensiones de su origen de datos. Treinta y tres dimensiones están disponibles para asignar.

- De forma predeterminada, si utiliza Supply Chain Management como uno de sus orígenes de datos, 13 dimensiones se asignan a las dimensiones estándar de Supply Chain Management. Doce otras dimensiones (`inventDimension1` hasta `inventDimension12`) se asignan a dimensiones personalizadas en Supply Chain Management. Las ocho dimensiones restantes son dimensiones extendidas que puede asignar a orígenes de datos externos.
- Si no utiliza Supply Chain Management como uno de sus orígenes de datos, puede asignar libremente las dimensiones. La siguiente tabla muestra la lista completa de dimensiones disponibles.

> [!NOTE]
> Si su dimensión no está en la lista de dimensiones predeterminadas y está utilizando un origen de datos externo, le recomendamos que utilice `ExtendedDimension1` hasta `ExtendedDimension8` para hacer la asignación.

| Tipo de dimensión | Nombre de dimensión |
|---|---|
| Producto | `ColorId` |
| Producto | `SizeId` |
| Producto | `StyleId` |
| Producto | `ConfigId` |
| Seguimiento | `BatchId` |
| Seguimiento | `SerialId` |
| Ubicación | `LocationId` |
| Ubicación | `SiteId` |
| Estado de inventario | `StatusId` |
| Específico del almacén | `WMSLocationId` |
| Específico del almacén | `WMSPalletId` |
| Específico del almacén | `LicensePlateId` |
| Otra | `VersionId` |
| Inventario (personalizado) | `InventDimension1` hasta `InventDimension12` |
| Otra | `ExtendedDimension1` hasta `ExtendedDimension8` |

Para agregar asignaciones de dimensiones, siga estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, en la sección **Asignaciones de dimensiones**, seleccione **Agregar** para agregar asignaciones de dimensiones.
1. En el campo **Nombre de dimensión**, especifique la dimensión de origen.
1. En el campo **A dimensión base**, seleccione la dimensión en Visibilidad de inventario que desea asignar.
1. Seleccione **Guardar**.

![Añadir asignaciones de dimensiones](media/inventory-visibility-dimension-mapping.png "Añadir asignaciones de dimensiones")

Por ejemplo, si su origen de datos incluye una dimensión de color de producto, puede asignarla a la dimensión base `ColorId` para agregar una dimensión personalizada de `ProductColor` en el origen de datos `exterchannel`. Luego se asigna a la dimensión base `ColorId`.

## <a name="create-a-physical-measure"></a>Creación de medida física

Cuando un origen de datos publica un cambio de inventario en Visibilidad de inventario, publica ese cambio utilizando *medidas físicas*. Las medidas físicas son modificadores que reflejan los estados resumidos de las transacciones de inventario. Las consultas pueden basarse en las medidas físicas.

Visibilidad del inventario tiene una lista de medidas físicas predeterminadas. Estas medidas físicas predeterminadas se toman de los estados de las transacciones de inventario de la página **Lista disponible** en Supply Chain Management (**Gestión de inventario\> Consultas e informe\> Lista disponible**).

| Modificador | Nombre |
|---|---|
| `PhysicalInvent` | Inventario físico |
| `ReservPhysical` | Físico reservado |
| `AvailPhysical` | Físico disponible |
| `ReservOrdered` | Pedido reservado |
| `PostedQty` | Cantidad registrada |
| `Deducted` | Deducido |
| `Picked` | Seleccionado |
| `Received` | Recibidos |
| `Registered` | Registrada |
| `Arrived` | Recepcionado |
| `Ordered` | Pedido |
| `OnOrder` | Sobre pedido |
| `QuotationReceipt` | Recepción de presupuesto |
| `QuotationIssue` | Emisión de presupuesto |

Si el origen de datos es Supply Chain Management, no es necesario que vuelva a crear las medidas físicas predeterminadas. Sin embargo, para orígenes de datos externos, puede crear nuevas medidas físicas siguiendo estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, en la sección **Medidas físicas**, seleccione **Agregar**, especifique un nombre de medida de origen y guarde los cambios.

## <a name="define-the-product-hierarchy-index"></a>Definir el índice de jerarquía de productos

Al configurar grupos de dimensiones agregados, puede utilizar Visibilidad del inventario para consultar el estado del inventario disponible. En Visibilidad de inventario, cada grupo de dimensiones se conoce como *índice*. Cada índice corresponde a un número determinado. Puede decidir qué dimensiones se utilizarán para configurar la indexación, según la forma en que consultará sobre la visibilidad del inventario.

Siga estos pasos para configurar el índice de jerarquía de productos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Índice de jerarquía de productos**, en la sección **Asignaciones de dimensiones**, seleccione **Agregar** para agregar asignaciones de dimensiones.
1. De forma predeterminada, se proporciona una lista de índices. Para modificar un índice existente, seleccione **Editar** o **Agregar** en la sección del índice correspondiente. Para crear un nuevo conjunto de índices, seleccione **Nuevo conjunto de índices**. Para cada fila en cada conjunto de índices, en el campo **Dimensión**, seleccione de la lista de dimensiones base. Los valores para los siguientes campos se generan automáticamente:

    - **Número de conjunto** - Las dimensiones que pertenecen al mismo grupo (índice) se agruparán y se les asignará el mismo número de conjunto.
    - **Jerarquía** - La jerarquía se utiliza para definir las combinaciones de dimensiones admitidas que se pueden consultar en un grupo de dimensiones (índice). Por ejemplo, si configura un grupo de dimensiones que tiene una secuencia de jerarquía de *Estilo*, *Color* y *Tamaño*, el sistema admite el resultado de tres grupos de consultas. El primer grupo es solo de estilo. El segundo grupo es una combinación de estilo y color. Y el tercer grupo es una combinación de estilo, color y tamaño. Las otras combinaciones no son compatibles.

Para obtener más información, consulte [Configuración de jerarquía de índice de productos](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Ejemplo

Esta sección proporciona un ejemplo que muestra cómo funciona la jerarquía. La siguiente tabla proporciona una lista del inventario disponible para este ejemplo.

| Artículo | Estilo | Color | Talla | Cantidad |
|---|---|---|---|---|
| I0001 | Ancho | Negro | Pequeños | 1 |
| I0001 | Ancho | Negro | Grandes | 2 |
| I0001 | Ancho | Rojo | Pequeños | 3 |
| I0001 | Regular | Negro | Pequeños | 4 |
| I0001 | Regular | Negro | Grandes | 5 |
| I0001 | Regular | Rojo | Pequeños | 6 |
| I0001 | Regular | Rojo | Grandes | 7 |

En la tabla siguiente se muestra cómo está configurada la jerarquía del índice.

| Clave | Número de conjunto | Jerarquía |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Según la configuración anterior, la combinación de dimensiones para la consulta de visibilidad de inventario es *Estilo*, *Color* y *Tamaño*. La configuración de la jerarquía permite que los sistemas externos consulten el inventario disponible de las siguientes maneras:

- `()` – Agrupado por todo. Este es el resultado:

    - I0001, 28

- `(StyleId)` – Agrupado por estilo. Este es el resultado:

    - I0001, Ancho, 6
    - I0001, Normal, 22

- `(StyleId, ColorId)` – Agrupado por la combinación de estilo y color. Este es el resultado:

    - I0001, Ancho, Negro, 3
    - I0001, Ancho, Rojo, 3
    - I0001, Normal, Negro, 9
    - I0001, Normal, Rojo, 13

- `(StyleId, ColorId, SizeId)` – Agrupado por la combinación de estilo, color y tamaño. Este es el resultado:

    - I0001, Ancho, Negro, Pequeño, 1
    - I0001, Ancho, Negro, Grande, 2
    - I0001, Ancho, Rojo, Pequeño, 3
    - I0001, Normal, Negro, Pequeño 4
    - I0001, Normal, Negro, Grande 5
    - I0001, Normal, Rojo, Pequeño, 6
    - I0001, Normal, Rojo, Grande, 7

## <a name="set-up-a-custom-calculated-measure"></a>Configurar una medida calculada personalizada

Puede utilizar Visibilidad del inventario para consultar tanto las medidas físicas del inventario como *medidas calculadas personalizadas*.

La configuración le permite definir un conjunto de modificadores que se suman o restan para obtener la cantidad de salida agregada total.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Medida calculada**, seleccione **Nueva medida calculada** para agregar una medida calculada. Luego, configure los campos como se describe en la tabla siguiente.

    | Campo | Valor |
    |---|---|
    | Nuevo nombre de medida calculada | Escriba el nombre de la medida calculada. |
    | Origen de datos | El sistema de consultas es un origen de datos. |
    | Origen de datos del modificador | Introduzca el origen de datos del modificador. |
    | Modificador | Introduzca el nombre del modificador. |
    | Tipo de modificador | Seleccione el tipo de modificador (*Suma* o *Resta*). |

La tabla siguiente muestra un ejemplo de la medida calculada personalizad `MyCustomAvailableforReservation`. Para obtener más información sobre este ejemplo, consulte [Configuración de origen de datos](inventory-visibility-configuration.md#data-source-configuration).

| Origen de datos de medida calculada | Medida calculada | Origen de datos del modificador | Modificador | Tipo de modificador |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Configurar una asignación de reserva flexible

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Antes de poder editar la ficha **Asignación de reserva flexible**, debe activar la función *OnHandReservation* en la ficha **Gestión de funciones**.

Al configurar la asignación de la medida física a la medida calculada, habilita el servicio de visibilidad de inventario para validar automáticamente la disponibilidad de la reserva, según la medida física.

Antes de configurar esta asignación, las medidas físicas, las medidas calculadas y sus orígenes de datos deben definirse en las fichas **Origen de datos** y **Medida calculada** de la página **Configuración** en Power Apps (como se describió anteriormente en este tema).

Para definir la asignación de reserva flexible, siga estos pasos.

1. Defina la medida física que sirve como medida de reserva flexible (por ejemplo, `softreservordered`).
1. En la ficha **Medida calculada** de la página **Configuración**, defina la medida calculada *disponible para reserva* (AFR) que contiene la fórmula de cálculo de AFR que desea asignar a la medida física. Por ejemplo, puede configurar `availforreserv` (disponible para reserva) para que se asigne a la medida física `softreservordered` definida previamente. De esta forma, puede encontrar qué cantidades que tienen el estado de inventario `softreservordered` estarán disponibles para reserva. La siguiente tabla muestra la fórmula de cálculo de AFR.

    | Modificador | Origen de datos | Medida |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Abra la página **Configuración**.
1. En la ficha **Asignación de reservas flexibles**, configure la asignación de la medida física a la medida calculada. Para el ejemplo anterior, puede usar la siguiente configuración para asignar `availforreserv` a la medida física `softreservordered` definida previamente.

    | Origen de datos de medida física | Medida física | Origen de datos de disponible para reserva | Medida calculada de disponible para reserva |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Configurar una jerarquía de reserva flexible

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Antes de poder editar la ficha **Jerarquía de reserva flexible**, debe activar la función *OnHandReservation* en la ficha **Gestión de funciones**.

La jerarquía de reservas describe la secuencia de dimensiones que deben especificarse cuando se realizan las reservas. Funciona de la misma forma que la jerarquía del índice de productos para las consultas disponibles.

La jerarquía de reservas puede diferir de la jerarquía del índice disponible. Esta independencia le permite implementar la gestión de categorías donde los usuarios pueden desglosar las dimensiones en detalles para especificar los requisitos para hacer reservas más precisas.

#### <a name="example"></a>Ejemplo

La siguiente jerarquía de reservas está configurada en su sistema.

| Dimensión | Jerarquía |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Dada esta jerarquía de reservas, puede realizar reservas en los siguientes órdenes de dimensión:

- `()` – No se indica ninguna dimensión.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

El orden de las dimensiones debe seguir estrictamente la secuencia de la jerarquía de reservas, dimensión por dimensión. Por ejemplo, las reservas que tienen `(ColorId, StyleId)` no se permitirán en este ejemplo, porque esta secuencia no está definida en la jerarquía de reservas.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Gestión de funciones de control

El complemento de visibilidad de inventario proporciona funciones como *OnHandReservation* y *OnHandMostSpecificBackgroundService*. De forma predeterminada, estas funciones están desactivadas. Para usarlas, abra la página **Configuración** en Power Apps y luego, en la ficha **Gestión de funciones**, actívelas.

### <a name="complete-and-update-the-configuration"></a>Completar y actualizar la configuración

Una vez que haya completado la configuración, debe confirmar todos los cambios en Visibilidad de inventario. Para confirmar los cambios, seleccione **Actualizar configuración** en la esquina superior derecha de la página **Configuración** en Power Apps.

La primera vez que selecciona **Actualizar configuración**, el sistema solicita sus credenciales.

- **Id. de cliente** - Id. de la aplicación de Azure que creó para Visibilidad del inventario.
- **Id. de inquilino** - Su Id. de inquilino de Azure.
- **Secreto de cliente** - Secreto de la aplicación de Azure que creó para Visibilidad del inventario.

Después de iniciar sesión, la configuración se actualiza en el servicio de visibilidad de inventario.

> [!NOTE]
> Asegúrese de validar el nombre del origen de datos, las medidas físicas y las asignaciones de dimensiones antes de actualizar la configuración del servicio de Visibilidad de inventario. No podrá modificar esta configuración después de seleccionar **Actualizar configuración**.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Buscar el punto de conexión de servicio

Si no conoce el punto de conexión de servicio de visibilidad de inventario correcto, abra la página **Configuración** en Power Apps y luego seleccione **Mostrar punto de conexión de servicio** en la esquina superior derecha. La página mostrará el punto de conexión de servicio correcto.

## <a name="operational-visibility"></a>Visibilidad operativa

La página **Visibilidad operativa** proporciona los resultados de una consulta de inventario disponible en tiempo real, basada en varias combinaciones de dimensiones. Cuando la función *OnHandReservation* está activada, también puede registrar solicitudes de reserva desde la página **Visibilidad operativa**.

### <a name="on-hand-query"></a>Consulta de inventario disponible

La ficha **Consulta de inventario disponible** muestra los resultados de una consulta de inventario disponible en tiempo real.

Cuando selecciona la ficha **Consulta de inventario disponible**, el sistema solicita sus credenciales para poder obtener el token de portador que se requiere para consultar el servicio de visibilidad de inventario. Puede pegar el token de portador en el campo **BearerToken** campo y cerrar el cuadro de diálogo. A continuación, puede registrar una solicitud de consulta de inventario disponible.

Si el token de portador no es válido, o si ha caducado, debe pegar uno nuevo en el campo **BearerToken**. Introduzca los valores correctos de **Id. de cliente**, **Id. de inquilino**, **Secreto de cliente** y luego seleccione **Actualizar**. El sistema obtendrá automáticamente un token de portador nuevo y válido.

Para registrar una consulta de inventario disponible, introduzca la consulta en el cuerpo de la solicitud. Utilice el patrón que se describe en [Consultar mediante el método de registro](inventory-visibility-api.md#query-with-post-method).

![Configuración de consulta de inventario disponible](media/inventory-visibility-query-settings.png "Configuración de consulta de inventario disponible")

### <a name="reservation-posting"></a>Registro de reservas

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Utilice la ficha **Registro de reserva** para registrar una solicitud de reserva. Antes de poder registrar una solicitud de reserva, debe activar la función *OnHandReservation*. Para obtener más información sobre esta función, consulte [Reservas de visibilidad de inventario ](inventory-visibility-reservations.md).

Para registrar una solicitud de reserva, debe introducir un valor en el cuerpo de la solicitud. Utilice el patrón que se describe en [Crear un evento de reserva](inventory-visibility-api.md#create-one-reservation-event). A continuación, seleccione **Registrar**. Para ver los detalles de la respuesta a la solicitud, seleccione **Mostrar detalles**. También puede obtener el valor de **reservationId** de los detalles de la respuesta.

## <a name="inventory-summary"></a>Resumen de inventario

**Resumen de inventario** es una vista personalizada para la *Entidad de suma de inventario disponible*. Proporciona un resumen de inventario de productos junto con todas las dimensiones. Usando el **Filtro avanzado** que proporciona Dataverse, puede crear una vista personal que muestre las filas que son importantes para usted. Las opciones de filtro avanzadas le permiten crear una amplia gama de vistas, desde simples hasta complejas. También le permiten agregar condiciones agrupadas y anidadas a los filtros.

Para obtener más información sobre cómo utilizar el **Filtro avanzado**, consulte [Editar o crear vistas personales utilizando filtros de cuadrícula avanzados](/powerapps/user/grid-filters-advanced)

La parte superior de la vista personalizada proporciona tres campos :**Dimensión predeterminada**, **Dimensión personalizada** y **Medida**. Puede utilizar estos campos para controlar qué columnas están visibles.

Puede seleccionar el encabezado de la columna para filtrar u ordenar el resultado actual.

La parte inferior de la vista personalizada muestra información como "50 registros (29 seleccionados)" o "50 registros". Esta información se refiere a los registros cargados actualmente del resultado de **Filtro avanzado**. El texto "29 seleccionados" se refiere al número de registros que se han seleccionado mediante el filtro de encabezado de columna para los registros cargados.

En la parte inferior de la vista hay un botón **Cargar más** que puede utilizar para cargar más registros desde Dataverse. El número predeterminado de registros que se cargan es 50. Cuando selecciona **Cargar más**, los siguientes 1000 registros disponibles se cargan en la vista. El número en el botón **Cargar más** indica los registros cargados actualmente y el número total de registros para el resultado de **Filtro avanzado**.

![Resumen de inventario](media/inventory-visibility-onhand-list.png "Resumen de inventario")
