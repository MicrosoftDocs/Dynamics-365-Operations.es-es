---
title: Configurar la visibilidad de inventario
description: Este tema describe cómo configurar Visibilidad de inventario.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8ba478fef424a6c4688191ed4e5375bbce52de0c
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061010"
---
# <a name="configure-inventory-visibility"></a>Configurar la visibilidad de inventario

[!include [banner](../includes/banner.md)]


Este tema describe cómo configurar la visibilidad de inventario usando la aplicación Visibilidad de inventario de Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introducción

Antes de comenzar a trabajar con Visibilidad de inventario, debe completar la siguiente configuración como se describe en este tema:

- [Configuración del origen de datos](#data-source-configuration)
- [Configuración de partición](#partition-configuration)
- [Configuración de jerarquía de índice de productos](#index-configuration)
- [Configuración de reserva (opcional)](#reservation-configuration)
- [Muestra de configuración predeterminada](#default-configuration-sample)

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, instale y configure el complemento de visibilidad de inventario como se describe en [Instalar y configurar la visibilidad del inventario](inventory-visibility-setup.md).

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Habilite las funciones de visibilidad de inventario en la gestión de funciones de Power Apps

El complemento de visibilidad de inventario agrega varias funciones nuevas a su instalación de Power Apps. De forma predeterminada, estas funciones están desactivadas. Para usarlas, abra la página **Configuración** en Power Apps y luego, en la ficha **Gestión de funciones**, active las siguientes caracetrísticas.

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Buscar el punto de conexión de servicio

Si no conoce el punto de conexión de servicio de visibilidad de inventario correcto, abra la página **Configuración** en Power Apps y luego seleccione **Mostrar punto de conexión de servicio** en la esquina superior derecha. La página mostrará el punto de conexión de servicio correcto.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>La página de configuración de la aplicación Inventory Visibility

En Power Apps, la página **Configuración** de la [aplicación Visibilidad de inventario](inventory-visibility-power-platform.md) le ayuda a configurar la configuración disponible y la configuración de reserva flexible. Una vez instalado el complemento, la configuración predeterminada incluye el valor de Microsoft Dynamics 365 Supply Chain Management (el origen de datos `fno`). Puede revisar la configuración predeterminada. Además, según sus requisitos comerciales y los requisitos de registro de inventario de su sistema externo, puede modificar la configuración para estandarizar la forma en que los cambios de inventario se pueden publicar, organizar y consultar en los múltiples sistemas. Las secciones restantes de este tema explican cómo utilizar cada parte de la página **Configuración**.

Una vez completada la configuración, asegúrese de seleccionar **Actualizar configuración** en la aplicación.

## <a name="data-source-configuration"></a>Configuración del origen de datos

Cada origen de datos representa un sistema del que provienen sus datos. Los nombres de origen de datos de ejemplo incluyen `fno` (que significa aplicaciones de "Dynamics 365 Finance y operaciones") y `pos` (que significa "punto de venta"). De forma predeterminada, Supply Chain Management está configurado como origen de datos predeterminado (`fno`) en Visibilidad de inventario.

> [!NOTE]
> El origen de datos `fno` está reservado para Supply Chain Management. Si su complemento de visibilidad de inventario está integrado con un entorno de Supply Chain Management, le recomendamos que no elimine las configuraciones relacionadas con `fno` en la fuente de datos.

Para añadir un origen de datos, siga estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, seleccione **Nuevo origen de datos** para agregar un origen de datos.

> [!NOTE]
> Cuando agregue un origen de datos, asegúrese de validar el nombre del origen de datos, las medidas físicas y las asignaciones de dimensiones antes de actualizar la configuración del servicio de Visibilidad de inventario. No podrá modificar esta configuración después de seleccionar **Actualizar configuración**.

La configuración de origen de datos incluye las siguientes partes:

- Dimensiones (asignación de dimensiones)
- Medidas físicas
- Medidas calculadas

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensiones (asignación de dimensiones)

El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para registrar eventos y consultas, según las combinaciones de dimensiones. Visibilidad del inventario proporciona una lista de dimensiones base que se pueden asignar a partir de las dimensiones de su origen de datos. Treinta y tres dimensiones están disponibles para asignar.

- De forma predeterminada, si utiliza Supply Chain Management como uno de sus orígenes de datos, 13 dimensiones se asignan a las dimensiones estándar de Supply Chain Management. Doce otras dimensiones (`inventDimension1` hasta `inventDimension12`) se asignan a dimensiones personalizadas en Supply Chain Management. Las ocho dimensiones restantes son dimensiones extendidas que puede asignar a orígenes de datos externos.
- Si no utiliza Supply Chain Management como uno de sus orígenes de datos, puede asignar libremente las dimensiones. La siguiente tabla muestra la lista completa de dimensiones disponibles.

> [!NOTE]
> Si su dimensión no está en la lista de dimensiones predeterminadas y está utilizando un origen de datos externo, le recomendamos que utilice `ExtendedDimension1` hasta `ExtendedDimension8` para hacer la asignación.

| Tipo de dimensión | Dimensión base |
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
| Específica del almacén | `WMSLocationId` |
| Específica del almacén | `WMSPalletId` |
| Específica del almacén | `LicensePlateId` |
| Otros | `VersionId` |
| Inventario (personalizado) | `InventDimension1` hasta `InventDimension12` |
| Extensión | `ExtendedDimension1` hasta `ExtendedDimension8` |
| System | `Empty` |

> [!NOTE]
> Los tipos de dimensión enumerados en la lista anterior son solo para referencia. No es necesario definirlos en Visibilidad de inventario.
>
> Las dimensiones de inventario (personalizadas) pueden reservarse para Supply Chain Management. En ese caso, puede utilizar las dimensiones extendidas en su lugar.

Los sistemas externos pueden acceder a Visibilidad de inventario a través de sus API RESTful. Para la integración, Visibilidad de inventario le permite configurar el _origen de datos externo_ y la asignación de las _dimensiones externas_ a las _dimensiones base_. A continuación se muestra un ejemplo de una tabla de asignación de dimensiones.

| Dimensión externa | Dimensión base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Al configurar una asignación de dimensiones, puede enviar las dimensiones externas directamente a Visibilidad de inventario. Visibilidad de inventario convertirá automáticamente las dimensiones externas en dimensiones base.

Para agregar asignaciones de dimensiones, siga estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, en la sección **Asignaciones de dimensiones**, seleccione **Agregar** para agregar asignaciones de dimensiones.
    ![Añadir asignaciones de dimensiones](media/inventory-visibility-dimension-mapping.png "Añadir asignaciones de dimensiones")

1. En el campo **Nombre de dimensión**, especifique la dimensión de origen.
1. En el campo **A dimensión base**, seleccione la dimensión en Visibilidad de inventario que desea asignar.
1. Seleccione **Guardar**.

Por ejemplo, si su origen de datos incluye una dimensión de color de producto, puede asignarla a la dimensión base `ColorId` para agregar una dimensión personalizada de `ProductColor` en el origen de datos `exterchannel`. Luego se asigna a la dimensión base `ColorId`.

### <a name="physical-measures"></a>Medidas físicas

Cuando un origen de datos publica un cambio de inventario en Visibilidad de inventario, publica ese cambio utilizando *medidas físicas*. Las medidas físicas modifican la cantidad y reflejan el estado del inventario. Puede definir sus propias medidas físicas, según sus requisitos. Las consultas pueden basarse en las medidas físicas.

Visibilidad de inventario proporciona una lista de medidas físicas predeterminadas que están vinculadas a Supply Chain Management (el origen de datos `fno`). Estas medidas físicas predeterminadas se toman de los estados de las transacciones de inventario de la página **Lista disponible** en Supply Chain Management (**Gestión de inventario\> Consultas e informe\> Lista disponible**). La siguiente tabla proporciona un ejemplo de medidas físicas.

| Nombre de la medida física | Descripción |
|---|---|
| `NotSpecified` | No especificado |
| `Arrived` | Recepcionado |
| `AvailOrdered` | Disponible solicitado |
| `AvailPhysical` | Física disponible |
| `Deducted` | Deducido |
| `OnOrder` | Sobre pedido |
| `Ordered` | Pedido |
| `PhysicalInvent` | Inventario físico |
| `Picked` | Seleccionado |
| `PostedQty` | Cantidad registrada |
| `QuotationIssue` | Emisión de presupuesto |
| `QuotationReceipt` | Recepción de presupuesto |
| `Received` | Recibidos |
| `Registered` | Registrada |
| `ReservOrdered` | Ordenada reservada |
| `ReservPhysical` | Física reservada |

Si el origen de datos es Supply Chain Management, no es necesario que vuelva a crear las medidas físicas predeterminadas. Sin embargo, para orígenes de datos externos, puede crear nuevas medidas físicas siguiendo estos pasos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Origen de datos**, en la sección **Medidas físicas**, seleccione **Agregar**, especifique un nombre de medida de origen y guarde los cambios.

### <a name="calculated-measures"></a>Medidas calculadas

Puede utilizar Visibilidad del inventario para consultar tanto las medidas físicas del inventario como *medidas calculadas personalizadas*. Las medidas calculadas proporcionan una fórmula de cálculo personalizada que consta de una combinación de medidas físicas. Esta funcionalidad le permite definir un conjunto de medidas físicas que se agregarán o un conjunto de medidas físicas que se restarán, para crear la medida personalizada.

La configuración le permite definir un conjunto de modificadores que se suman o restan para obtener la cantidad de salida agregada total.

Para configurar una medida calculada personalizada, siga estos pasos:

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

Por ejemplo, podría tener el siguiente resultado de consulta.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

A continuación, configura una medida calculada llamada `MyCustomAvailableforReservation`, como se muestra en la siguiente tabla. Esta medida calculada será consumida por el sistema de consumo.

| Sistema de consumo | Medida calculada | Origen de datos | Medida física | Tipo de cálculo |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Cuando se utiliza esta fórmula de cálculo, el nuevo resultado de la consulta incluirá la medida personalizada.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

El resultado de `MyCustomAvailableforReservation`, basado en la configuración de cálculo en las medidas personalizadas es 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuración de partición

Actualmente, la configuración de la partición consta de dos dimensiones base (`SiteId` y `LocationId`) que indican cómo se distribuyen los datos. Las operaciones en la misma partición pueden ofrecer un mayor rendimiento a un menor costo. La siguiente tabla muestra la configuración de partición predeterminada que proporciona el complemento Visibilidad de inventario.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

La solución incluye esta configuración de partición por defecto. Por lo tanto, *no es necesario volver a calcular manualmente*.

> [!IMPORTANT]
> No personalice la configuración de partición predeterminada. Si lo elimina o lo cambia, es probable que provoque un error inesperado.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuración de jerarquía de índice de productos

La mayoría de las veces, la consulta de inventario disponible no estará solo en el nivel "total" más alto. En su lugar, es posible que también desee ver resultados agregados en función de las dimensiones del inventario.

Visibilidad de inventario proporciona flexibilidad al permitirle configurar los _índices_. Estos índices se basan en una dimensión o una combinación de dimensiones. Un índice consta de un *número de conjunto*, una *dimensión* y una *jerarquía*, como se define en la siguiente tabla.

| Nombre | Descripción |
|---|---|
| Número de conjunto | Dimensiones que pertenecen al mismo conjunto (índice) se agruparán y se les asignará el mismo número de conjunto. |
| Dimensión | Dimensiones base en las que se agrega el resultado de la consulta. |
| Jerarquía | La jerarquía se utiliza para definir las combinaciones de dimensiones admitidas que se pueden consultar. Por ejemplo, configura un conjunto de dimensiones que tiene una secuencia de jerarquía de `(ColorId, SizeId, StyleId)`. En este caso, el sistema admite consultas en cuatro combinaciones de dimensiones. La primera combinación está vacía, la segunda es `(ColorId)`, la tercera es `(ColorId, SizeId)` y la cuarta es `(ColorId, SizeId, StyleId)`. Las otras combinaciones no son compatibles. Para obtener más información, consulte los siguientes ejemplos. |

Siga estos pasos para configurar el índice de jerarquía de productos.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Índice de jerarquía de productos**, en la sección **Asignaciones de dimensiones**, seleccione **Agregar** para agregar asignaciones de dimensiones.
1. De forma predeterminada, se proporciona una lista de índices. Para modificar un índice existente, seleccione **Editar** o **Agregar** en la sección del índice correspondiente. Para crear un nuevo conjunto de índices, seleccione **Nuevo conjunto de índices**. Para cada fila en cada conjunto de índices, en el campo **Dimensión**, seleccione de la lista de dimensiones base. Los valores para los siguientes campos se generan automáticamente:

    - **Número de conjunto** - Las dimensiones que pertenecen al mismo grupo (índice) se agruparán y se les asignará el mismo número de conjunto.
    - **Jerarquía** - La jerarquía se utiliza para definir las combinaciones de dimensiones admitidas que se pueden consultar en un grupo de dimensiones (índice). Por ejemplo, si configura un grupo de dimensiones que tiene una secuencia de jerarquía de *Estilo*, *Color* y *Tamaño*, el sistema admite el resultado de tres grupos de consultas. El primer grupo es solo de estilo. El segundo grupo es una combinación de estilo y color. Y el tercer grupo es una combinación de estilo, color y tamaño. Las otras combinaciones no son compatibles.

### <a name="example"></a>Ejemplo

Esta sección proporciona un ejemplo que muestra cómo funciona la jerarquía.

La siguiente tabla proporciona una lista del inventario disponible para este ejemplo.

| Artículo | ColorId | SizeId | StyleId | Cantidad |
|---|---|---|---|---|
| Camiseta | Negro | Pequeños | Ancho | 1 |
| Camiseta | Negro | Pequeños | Regular | 2 |
| Camiseta | Negro | Grandes | Ancho | 3 |
| Camiseta | Negro | Grandes | Regular | 4 |
| Camiseta | Rojo | Pequeños | Ancho | 5 |
| Camiseta | Rojo | Pequeños | Regular | 6 |
| Camiseta | Rojo | Grandes | Regular | 7 |

En la tabla siguiente se muestra cómo está configurada la jerarquía del índice.

| Número de conjunto | Dimensión | Jerarquía |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

El índice le permite consultar el inventario disponible de las siguientes maneras:

- `()` – Agrupado por todo

    - Camiseta, 28

- `(ColorId)` – Agrupado por `ColorId`

    - Camiseta, Negra, 10
    - Camiseta, Roja, 18

- `(ColorId, SizeId)` – Agrupado por la combinación de `ColorId` y `SizeId`

    - Camiseta, Negra, Pequeña, 3
    - Camiseta, Negra, Grande, 7
    - Camiseta, Roja, Pequeña, 11
    - Camiseta, Roja, Grande, 7

- `(ColorId, SizeId, StyleId)` – Agrupado por la combinación de `ColorId`, `SizeId` y `StyleId`

    - Camiseta, Negra, Pequeña, Ancha, 1
    - Camiseta, Negra, Pequeña, Normal, 2
    - Camiseta, Negra, Grande, Ancha, 3
    - Camiseta, Negra, Grande, Normal, 4
    - Camiseta, Roja, Pequeña, Ancha, 5
    - Camiseta, Roja, Pequeña, Normal, 6
    - Camiseta, Roja, Grande, Normal, 7

> [!NOTE]
> Las dimensiones base que se definen en la configuración de la partición no deben definirse en las configuraciones de índice.
> 
> Si debe consultar solo el inventario agregado por todas las combinaciones de dimensiones, puede configurar un único índice que contenga la dimensión base `Empty`.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuración de reserva (opcional)

Se requiere la configuración de la reserva si desea utilizar la función de reserva flexible. La configuración consta de dos partes fundamentales:

- Asignación de reserva flexible
- Jerarquía de reserva flexible

### <a name="soft-reservation-mapping"></a>Asignación de reserva flexible

Cuando realiza una reserva, es posible que desee saber si el inventario disponible está actualmente disponible para la reserva. La validación está vinculada a una medida calculada que representa una fórmula de cálculo de una combinación de medidas físicas.

Al configurar la asignación de la medida física a la medida calculada, habilita el servicio de visibilidad de inventario para validar automáticamente la disponibilidad de la reserva, según la medida física.

Antes de configurar esta asignación, las medidas físicas, las medidas calculadas y sus orígenes de datos deben definirse en las fichas **Origen de datos** y **Medida calculada** de la página **Configuración** en Power Apps (como se describió anteriormente en este tema).

Para definir la asignación de reserva flexible, siga estos pasos.

1. Defina la medida física que sirve como medida de reserva flexible (por ejemplo, `SoftReservOrdered`).
1. En la ficha **Medida calculada** de la página **Configuración**, defina la medida calculada *disponible para reserva* (AFR) que contiene la fórmula de cálculo de AFR que desea asignar a la medida física. Por ejemplo, puede configurar `AvailableToReserve` (disponible para reserva) para que se asigne a la medida física `SoftReservOrdered` definida previamente. De esta forma, puede encontrar qué cantidades que tienen el estado de inventario `SoftReservOrdered` estarán disponibles para reserva. La siguiente tabla muestra la fórmula de cálculo de AFR.

    | Tipo de cálculo | Origen de datos | Medida física |
    |---|---|---|
    | Suma | `fno` | `AvailPhysical` |
    | Suma | `pos` | `Inbound` |
    | Resta | `pos` | `Outbound` |
    | Resta | `iv` | `SoftReservOrdered` |

    Le recomendamos que configure la medida calculada para que contenga la medida física en la que se basa la medida de reserva. De esta forma, la cantidad de medida calculada se verá afectada por la cantidad de medida de reserva. Por lo tanto, en este ejemplo, la medida calculada `AvailableToReserve` de la fuente de datos `iv` debe contener la medida física `SoftReservOrdered` de `iv` como componente.

1. Abra la página **Configuración**.
1. En la ficha **Asignación de reservas flexibles**, configure la asignación de la medida física a la medida calculada. Para el ejemplo anterior, puede usar la siguiente configuración para asignar `AvailableToReserve` a la medida física `SoftReservOrdered` definida previamente.

    | Origen de datos de medida física | Medida física | Origen de datos de disponible para reserva | Medida calculada de disponible para reserva |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Si no puede editar la ficha **Asignación de reserva flexible**, puede que necesite activar la función *OnHandReservation* en la ficha **Gestión de funciones**.

Ahora, cuando haga la reserva en `SoftReservOrdered`, Visibilidad de inventario encontrará automáticamente `AvailableToReserve` y su fórmula de cálculo relacionada para hacer la validación de la reserva.

Por ejemplo, tiene el siguiente inventario disponible en Visibilidad de inventario.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

En este caso, se aplica el cálculo siguiente:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Por lo tanto, si intenta hacer reservas en `iv.SoftReservOrdered` y la cantidad es menor o igual a `AvailableToReserve` (10), puede hacer la reserva.

> [!NOTE]
> Cuando llama a la API de reserva, puede controlar la validación de la reserva especificando el parámetro booleano `ifCheckAvailForReserv` en el cuerpo de la solicitud. Un valor `True` significa que se requiere la validación, mientras que un valor `False` significa que la validación no es necesaria. El valor predeterminado es `True`.

### <a name="soft-reservation-hierarchy"></a>Jerarquía de reserva flexible

La jerarquía de reservas describe la secuencia de dimensiones que deben especificarse cuando se realizan las reservas. Funciona de la misma forma que la jerarquía del índice de productos para las consultas disponibles.

La jerarquía de reservas es independiente de la jerarquía del índice de productos. Esta independencia le permite implementar la gestión de categorías donde los usuarios pueden desglosar las dimensiones en detalles para especificar los requisitos para hacer reservas más precisas. Su jerarquía de reservas blandas debe contener `SiteId` y `LocationId` como componentes, porque construyen la configuración de la partición. Cuando realiza la reserva, debe especificar una partición para el producto.

A continuación se muestra un ejemplo de una jerarquía de reserva flexible.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

En este ejemplo, puede realizar reservas en las siguientes secuencias de dimensión. Debe especificar una partición para el producto cuando realiza la reserva. Por lo tanto, la jerarquía básica que puede utilizar es `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Una secuencia de dimensión válida debe seguir estrictamente la jerarquía de reservas, dimensión por dimensión. Por ejemplo, la secuencia de jerarquía`(SiteId, LocationId, SizeId)` no es válida, porque falta `ColorId`.

## <a name="complete-and-update-the-configuration"></a>Completar y actualizar la configuración

Una vez que haya completado la configuración, debe confirmar todos los cambios en Visibilidad de inventario. Para confirmar los cambios, seleccione **Actualizar configuración** en la esquina superior derecha de la página **Configuración** en Power Apps.

La primera vez que selecciona **Actualizar configuración**, el sistema solicita sus credenciales.

- **Id. de cliente** - Id. de la aplicación de Azure que creó para Visibilidad del inventario.
- **Id. de inquilino** - Su Id. de inquilino de Azure.
- **Secreto de cliente** - Secreto de la aplicación de Azure que creó para Visibilidad del inventario.

Después de iniciar sesión, la configuración se actualiza en el servicio de visibilidad de inventario.

> [!NOTE]
> Asegúrese de validar el nombre del origen de datos, las medidas físicas y las asignaciones de dimensiones antes de actualizar la configuración del servicio de Visibilidad de inventario. No podrá modificar esta configuración después de seleccionar **Actualizar configuración**.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Muestra de configuración predeterminada

Durante su etapa de inicialización, Visibilidad de inventario establece una configuración predeterminada, que se detalla aquí. Puede modificar esta configuración según sus necesidades.

### <a name="data-source-configuration"></a>Configuración del origen de datos

#### <a name="configuration-of-the-iv-data-source"></a>Configuración del origen de datos de Visibilidad de inventario

Esta sección describe cómo se configura el origen de datos de `iv`.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Medidas físicas configuradas para el origen de datos de Visibilidad de inventario

Las siguientes medidas físicas están configuradas para el origen de datos de `iv`:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Medida calculada OrderedTotal

La medida calculada `OrderedTotal` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `Ordered` |
| Suma | `fno` | `Arrived` |
| Suma | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Medida calculada OnHand

La medida calculada `OnHand` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `PhysicalInvent` |
| Suma | `iom` | `OnHand` |
| Suma | `erp` | `Unrestricted` |
| Suma | `erp` | `QualityInspection` |
| Suma | `pos` | `PosInbound` |
| Resta | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>Medida calculada ReservedTotal

La medida calculada `ReservedTotal` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `ReservPhysical` |
| Suma | `fno` | `ReservOrdered` |
| Suma | `iv` | `SoftReservPhysical` |
| Suma | `iv` | `SoftReservOrdered` |
| Suma | `iv` | `ReservPhysical` |
| Suma | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Medida calculada SoftReserved

La medida calculada `SoftReserved` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `iv` | `SoftReservPhysical` |
| Suma | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>Medida calculada HardReserved

La medida calculada `HardReserved` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `ReservPhysical` |
| Suma | `fno` | `ReservOrdered` |
| Suma | `iv` | `ReservPhysical` |
| Suma | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Medida calculada OpenOrder

La medida calculada `OpenOrder` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `OnOrder` |
| Suma | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Medida calculada OnHandAvailable

La medida calculada `OnHandAvailable` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `PhysicalInvent` |
| Suma | `iom` | `OnHand` |
| Suma | `erp` | `Unrestricted` |
| Suma | `erp` | `QualityInspection` |
| Suma | `pos` | `PosInbound` |
| Resta | `fno` | `ReservPhysical` |
| Resta | `iv` | `SoftReservPhysical` |
| Resta | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Medida calculada AvailableToReserve

La medida calculada `AvailableToReserve` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `PhysicalInvent` |
| Suma | `iom` | `OnHand` |
| Suma | `erp` | `Unrestricted` |
| Suma | `erp` | `QualityInspection` |
| Suma | `pos` | `PosInbound` |
| Suma | `fno` | `Ordered` |
| Suma | `fno` | `Arrived` |
| Suma | `iv` | `Ordered` |
| Resta | `fno` | `ReservPhysical` |
| Resta | `fno` | `ReservOrdered` |
| Resta | `iv` | `SoftReservPhysical` |
| Resta | `iv` | `SoftReservOrdered` |
| Resta | `iv` | `ReservPhysical` |
| Resta | `iv` | `ReservOrdered` |
| Resta | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Medida calculada InventorySupply

La medida calculada `InventorySupply` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `Ordered` |
| Suma | `fno` | `Arrived` |
| Suma | `iv` | `Ordered` |
| Suma | `fno` | `PhysicalInvent` |
| Suma | `iom` | `OnHand` |
| Suma | `erp` | `Unrestricted` |
| Suma | `erp` | `QualityInspection` |
| Suma | `pos` | `PosInbound` |
| Resta | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Medida calculada InventoryDemand

La medida calculada `InventoryDemand` se configura para el origen de datos de `iv` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `OnOrder` |
| Suma | `iom` | `OnOrder` |
| Suma | `iv` | `SoftReservPhysical` |
| Suma | `iv` | `SoftReservOrdered` |
| Suma | `fno` | `ReservPhysical` |
| Suma | `fno` | `ReservOrdered` |
| Suma | `iv` | `ReservPhysical` |
| Suma | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Configuración del origen de datos de fno

Esta sección describe cómo se configura el origen de datos de `fno`.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Asignaciones de dimensiones para el origen de datos fno

Las asignaciones de dimensiones que se enumeran en la siguiente tabla están configuradas para el origen de datos `fno`.

| Dimensión externa | Dimensión base |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Medidas físicas configuradas para el origen de datos de fno

Las siguientes medidas físicas están configuradas para el origen de datos de `fno`:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Configuración del origen de datos de pos

Esta sección describe cómo se configura el origen de datos de `pos`.

##### <a name="physical-measures-for-the-pos-data-source"></a>Medidas físicas para el origen de datos de pos

Las siguientes medidas físicas están configuradas para el origen de datos de `pos`:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Medida calculada AvailQuantity

La medida calculada `AvailQuantity` se configura para el origen de datos de `pos` como se muestra en la siguiente tabla.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `AvailPhysical` |
| Suma | `pos` | `PosInbound` |
| Resta | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Configuración del origen de datos de iom

Las siguientes medidas físicas están configuradas para el origen de datos de `iom` (Intelligent Order Management):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configuración del origen de datos de erp

Las siguientes medidas físicas están configuradas para el origen de datos de `erp` (Planificación de recursos empresariales):

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Configuración de partición

La siguiente tabla muestra la configuración de partición predeterminada.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Configuración de índices

La siguiente tabla muestra la configuración de índices predeterminada.

| Número de conjunto | Dimensión | Jerarquía |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Configuración de reserva

Esta sección describe la configuración de reserva predeterminada.

#### <a name="reservation-mapping"></a>Asignación de reservas

La siguiente tabla muestra la asignación de reservas predeterminada.

| Origen de datos de medida física | Medida física | Origen de datos de disponible para reserva | Medida calculada de disponible para reserva |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Jerarquía de reservas

La siguiente tabla muestra la jerarquía de reservas predeterminada.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]