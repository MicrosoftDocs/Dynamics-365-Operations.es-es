---
title: Configuración de Visibilidad de inventario
description: Este tema describe cómo configurar Visibilidad de inventario.
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
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345042"
---
# <a name="inventory-visibility-configuration"></a>Configuración de Visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tema describe cómo configurar Visibilidad de inventario.

## <a name="introduction"></a><a name="introduction"></a>Introducción

Antes de comenzar a trabajar con Visibilidad de inventario, debe completar la siguiente configuración como se describe en este tema:

- [Configuración del origen de datos](#data-source-configuration)
- [Configuración de partición](#partition-configuration)
- [Configuración de jerarquía de índice de productos](#index-configuration)
- [Configuración de reserva (opcional)](#reservation-configuration)
- [Muestra de configuración predeterminada](#default-configuration-sample)

> [!NOTE]
> Puede ver y editar las configuraciones de Visibilidad de inventario en [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). Una vez completada la configuración, seleccione **Actualizar configuración** en la aplicación.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configuración del origen de datos

El origen de datos representa el sistema del que provienen sus datos. Ejemplos incluyen `fno` (que significa aplicaciones de "Dynamics 365 Finance and Operations") y `pos` (que significa "punto de venta").

La configuración de origen de datos incluye las siguientes partes:

- Dimensión (asignación de dimensiones)
- Medida física
- Medida calculada

> [!NOTE]
> El origen de datos `fno` está reservado para Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensión (asignación de dimensiones)

El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para registrar eventos y consultas, según las combinaciones de dimensiones.

Visibilidad de inventario admite las siguientes dimensiones básicas generales.

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

### <a name="physical-measures"></a>Medidas físicas

Las medidas físicas modifican la cantidad y reflejan el estado del inventario. Puede definir sus propias medidas físicas, según sus requisitos.

Visibilidad de inventario proporciona una lista de medidas físicas predeterminadas que están vinculadas a Supply Chain Management (el origen de datos `fno`). La siguiente tabla proporciona un ejemplo de medidas físicas.

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

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Medidas calculadas

Las medidas calculadas proporcionan una fórmula de cálculo personalizada que consta de una combinación de medidas físicas. Esta funcionalidad le permite definir un conjunto de medidas físicas que se agregarán o un conjunto de medidas físicas que se restarán, para crear la medida personalizada.

Por ejemplo, tiene el siguiente resultado de consulta.

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

El resultado de `MyCustomAvailableforReservation`, basado en la configuración de cálculo en las medidas personalizadas es 100 + 50 + 80 + 90 + 30 – 10 – 20 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuración de partición

La configuración de la partición consta de una combinación de dimensiones base. Define el patrón de distribución de datos. Las operaciones de datos en la misma partición admiten un alto rendimiento y no cuestan demasiado. Por tanto, unos buenos patrones de partición pueden aportar importantes beneficios.

Visibilidad de inventario proporciona la siguiente configuración de partición predeterminada.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> La configuración de partición predeterminada es solo para referencia. No es necesario definirla en Visibilidad de inventario. Actualmente, la configuración de la partición no es compatible.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuración de jerarquía de índice de productos

La mayoría de las veces, la consulta de inventario disponible no estará solo en el nivel "total" más alto. En su lugar, es posible que también desee ver resultados agregados en función de las dimensiones del inventario.

Visibilidad de inventario proporciona flexibilidad al permitirle configurar los _índices_. Estos índices se basan en una dimensión o una combinación de dimensiones. Un índice consta de un *número de conjunto*, una *dimensión* y una *jerarquía*, como se define en la siguiente tabla.

| Nombre | Descripción |
|---|---|
| Número de conjunto | Dimensiones que pertenecen al mismo conjunto (índice) se agruparán y se les asignará el mismo número de conjunto. |
| Dimensión | Dimensiones base en las que se agrega el resultado de la consulta. |
| Jerarquía | La jerarquía se utiliza para definir las combinaciones de dimensiones admitidas que se pueden consultar. Por ejemplo, configura un conjunto de dimensiones que tiene una secuencia de jerarquía de `(ColorId, SizeId, StyleId)`. En este caso, el sistema admite consultas en cuatro combinaciones de dimensiones. La primera combinación está vacía, la segunda es `(ColorId)`, la tercera es `(ColorId, SizeId)` y la cuarta es `(ColorId, SizeId, StyleId)`. Las otras combinaciones no son compatibles. Para obtener más información, consulte los siguientes ejemplos. |

### <a name="example"></a>Ejemplo

Esta sección proporciona un ejemplo que muestra cómo funciona la jerarquía.

Tiene los siguientes artículos en su inventario.

| Artículo | ColorId | SizeId | StyleId | Cantidad |
|---|---|---|---|---|
| Camiseta | Negro | Pequeños | Ancho | 1 |
| Camiseta | Negro | Pequeños | Regular | 2 |
| Camiseta | Negro | Grandes | Ancho | 3 |
| Camiseta | Negro | Grandes | Regular | 4 |
| Camiseta | Rojo | Pequeños | Ancho | 5 |
| Camiseta | Rojo | Pequeños | Regular | 6 |
| Camiseta | Rojo | Grandes | Regular | 7 |

Este es el índice.

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

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuración de reserva (opcional)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Se requiere la configuración de la reserva si desea utilizar la función de reserva flexible. La configuración consta de dos partes fundamentales:

- Asignación de reserva flexible
- Jerarquía de reserva flexible

### <a name="soft-reservation-mapping"></a>Asignación de reserva flexible

Cuando realiza una reserva, es posible que desee saber si el inventario disponible está actualmente disponible para la reserva. La validación está vinculada a una medida calculada que representa una fórmula de cálculo de una combinación de medidas físicas.

Por ejemplo, una medida de reserva se basa en la medida física `SoftReservOrdered` del origen de datos de `iv` (Visibilidad de inventario). En este caso, puede configurar la medida calculada `AvailableToReserve` del origen de datos de `iv` como se muestra aquí.

| Tipo de cálculo | Origen de datos | Medida física |
|---|---|---|
| Suma | `fno` | `AvailPhysical` |
| Suma | `pos` | `Inbound` |
| Resta | `pos` | `Outbound` |
| Resta | `iv` | `SoftReservOrdered` |

A continuación, configure una asignación de reserva flexible para proporcionar una asignación de la medida de reserva `SoftReservOrdered` a la medida calculada `AvailableToReserve`.

| Origen de datos de medida física | Medida física | Origen de datos de disponible para reserva | Medida calculada de disponible para reserva |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

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

### <a name="soft-reservation-hierarchy"></a>Jerarquía de reserva flexible

La jerarquía de reservas describe la secuencia de dimensiones que deben especificarse cuando se realizan las reservas. Funciona de la misma forma que la jerarquía del índice de productos para las consultas disponibles.

La jerarquía de reservas es independiente de la jerarquía del índice de productos. Esta independencia le permite implementar la gestión de categorías donde los usuarios pueden desglosar las dimensiones en detalles para especificar los requisitos para hacer reservas más precisas.

A continuación se muestra un ejemplo de una jerarquía de reserva flexible.

| Dimensión base | Jerarquía |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

En este ejemplo, puede realizar reservas en las siguientes secuencias de dimensión:

- `()` – No se especifica ninguna dimensión.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Una secuencia de dimensión válida debe seguir estrictamente la jerarquía de reservas, dimensión por dimensión. Por ejemplo, la secuencia de jerarquía`(SiteId, LocationId, SizeId)` no es válida, porque falta `ColorId`.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Muestra de configuración predeterminada

Durante su etapa de inicialización, Visibilidad de inventario establece una configuración predeterminada. Puede modificar la configuración según sus necesidades.

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

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

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
