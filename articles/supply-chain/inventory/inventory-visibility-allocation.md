---
title: Asignación de inventario de Inventory Visibility
description: Este artículo explica cómo configurar y usar la característica de asignación de inventario, que le permite reservar un inventario dedicado para garantizar que pueda cumplir con sus canales o clientes más rentables.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: ccc3a8c4b3d0649397b1d1f9139f7feebf39b02f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852516"
---
# <a name="inventory-visibility-inventory-allocation"></a>Asignación de inventario para para visibilidad de inventario

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Antecedentes comerciales y propósito

En muchos casos, los fabricantes, minoristas y otros titulares de negocios de la cadena de suministro deben preasignar existencias para canales de ventas, ubicaciones o clientes importantes, o para eventos de ventas específicos. La asignación de inventario es una práctica típica en el proceso de planificación operativa de ventas y se realiza antes de que ocurran las actividades de ventas reales y se creen pedidos de ventas.

Por ejemplo, una empresa de bicicletas tiene existencias limitadas disponibles de una bicicleta muy popular. Esta empresa realiza ventas tanto en línea como en tienda. En cada canal de venta, la empresa tiene algunos socios corporativos importantes (mercados y grandes minoristas) que exigen que se les guarde una porción específica del inventario disponible de bicicletas. Por lo tanto, la empresa de bicicletas debe poder equilibrar la distribución de existencias en todos los canales y también gestionar las expectativas de sus socios VIP. La mejor manera de lograr ambos objetivos es utilizar la asignación de inventario, de modo que cada canal y minorista pueda recibir cantidades asignadas específicas que puedan venderse a los consumidores más adelante.

La asignación de inventario tiene dos propósitos comerciales básicos:

- **Salvaguardia de inventario (ringfencing)**: las organizaciones desean preasignar existencias restringidas o limitadas a canales, regiones, clientes VIP y empresas subsidiarias priorizados. La característica de asignación de visibilidad de inventario tiene como objetivo proteger el inventario asignado, de modo que otras asignaciones, reservas u otras demandas de ventas no afecten al inventario previamente asignado.
- **Control de sobreventa**: la función de asignación de visibilidad de inventario tiene como objetivo poner una restricción sobre las cantidades previamente asignadas, de modo que la parte receptora (por ejemplo, un canal o grupo de clientes) no las consuma en exceso cuando la transacción de venta real que se basa en una reserva no en firme entre en vigor.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definición de asignación en el Servicio de visibilidad de inventario

Aunque la característica de asignación en el servicio de Visibilidad de inventario no reserva cantidades de inventario físico, sí se refiere a la cantidad de inventario físico disponible para definir cantidad inicial del grupo virtual *disponible para asignar*. La asignación de inventario en la visibilidad de inventario es una asignación flexible. Se realiza antes de que se produzcan las transacciones de venta reales y no depende de los pedidos de venta. Por ejemplo, puede asignar existencias a sus canales de ventas más importantes o a los grandes minoristas corporativos antes de que los clientes finales visiten el canal de ventas o la tienda minorista para comprar.

La diferencia entre asignación de inventario y [reserva no en firme de inventario](inventory-visibility-reservations.md) es que la reserva no en firme generalmente está vinculada a transacciones de ventas reales (líneas de pedidos de venta). Por lo tanto, si desea utilizar las características de asignación y reserva anticipada juntas, le recomendamos que realice primero la asignación de inventario y luego la reserva no en firme sobre las cantidades asignadas. Para más información, vea [Consumir como reserva no en firme](#consume-to-soft-reserved).

La característica de asignación de inventario permite a los planificadores de ventas o gerentes de cuentas clave administrar y preasignar existencias importantes en grupos de asignación (como canales, regiones y grupos de clientes). También es compatible con el seguimiento, el ajuste y el análisis en tiempo real del consumo frente a las cantidades asignadas, de modo que el reabastecimiento o la reasignación se puedan realizar a tiempo. Esta capacidad de tener visibilidad en tiempo real de la asignación, el consumo y el saldo de la asignación es especialmente importante en eventos de promoción o venta rápida.

## <a name="terminology"></a>Terminología

Los siguientes términos y conceptos son útiles en los planteamientos sobre la asignación de inventario:

- **Grupo de asignación**: el grupo al que pertenece la asignación, como un canal de ventas, un grupo de clientes o un tipo de pedido.
- **Valor del grupo de asignación**: el valor de cada grupo de asignación. Por ejemplo, *web* o *tienda* podría ser el valor del grupo de asignación del canal de ventas, mientras que *VIP* o *normal* podría ser el valor del grupo de asignación de clientes.
- **Jerarquía de asignación**: un medio para combinar grupos de asignación de manera jerárquica. Por ejemplo, puede definir *canal* como nivel de jerarquía 1, *región* como nivel 2 y *grupo de clientes* como nivel 3. Durante la asignación de inventario, debe seguir la secuencia de la jerarquía de asignación al especificar el valor del grupo de asignación. Por ejemplo, puede asignar 200 bicicletas rojas al canal *Web*, la región *Londres* región y el grupo de clientes *VIP*.
- **Disponible para asignar**: el *conjunto común virtual* que indica la cantidad que está disponible para futuras asignaciones. Es una medida calculada que puede definir libremente usando su propia fórmula. Si también utiliza la función de reserva no en firme, le recomendamos que utilice la misma fórmula para calcular el disponible para asignar y el disponible para reservar.
- **Asignado**: una medida física que muestra la cuota asignada que pueden consumir los grupos de asignación.
- **Consumido**: una medida física que indica las cantidades que se han consumido frente a la cantidad asignada original. A medida que se agregan números a esta medida física, la medida física asignada se reduce automáticamente.

En la ilustración siguiente se muestra el flujo de trabajo de asignación de inventario.

![Flujo de trabajo empresarial de asignación de visibilidad de inventario.](media/inventory-visibility-allocation-flow.png "Flujo de trabajo empresarial de asignación de visibilidad de inventario.")

## <a name="set-up-inventory-allocation"></a>Establecer la asignación de inventario

La característica de asignación de inventario consta de los siguientes componentes:

- El origen de datos predefinida relacionada con la asignación, las medidas físicas y las medidas calculadas.
- Grupos de asignación personalizables que tienen un máximo de ocho niveles.
- Un conjunto de interfaces de programación de aplicaciones (API) de asignación:

    - asignar
    - reasignar
    - desasignar
    - consumir
    - consulta

El proceso de configuración de la característica de asignación consta de dos pasos:

- Configurar el [origen de datos](inventory-visibility-configuration.md#data-source-configuration) y sus [medidas](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configure el nombre y la jerarquía del grupo de asignación.

### <a name="predefined-data-source"></a>Origen de datos predefinido

Cuando habilita la característica de asignación y llama a la API de actualización de configuración, la visibilidad de inventario crea un origen de datos predefinido y varias medidas iniciales.

El origen de datos se llama `@iv`.

Aquí están las medidas físicas iniciales:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Aquí están las medidas calculadas:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Agregar otras medidas físicas a la medida calculada disponible para asignar

Para utilizar la asignación, debe configurar la medida calculada disponible para asignar (`@iv.@available_to_allocate`). Por ejemplo, tiene el origen de datos `fno` y la medida `onordered`, el origen de datos `pos` y la medida `inbound`, y desea hacer una asignación del disponible para la suma de `fno.onordered` y `pos.inbound`. En este caso, `@iv.@available_to_allocate` debería contener `pos.inbound` y `fno.onordered` en la fórmula. Este es un ejemplo:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Cambiar el nombre del grupo de asignación

Se puede establecer un máximo de ocho nombres de grupos de asignación. Los grupos tienen una jerarquía.

Se establecen los nombres de los grupos en la página **Configuración de Power App de visibilidad de inventario**. Para abrir esta página, en su entorno de Microsoft Dataverse, abra la aplicación de visibilidad de inventario y seleccione **Configuración \> Asignación**.

Por ejemplo, si usa cuatro nombres de grupo y los configura para \[`channel`, `customerGroup`, `region`, `orderType`\], estos nombres serán válidos para las solicitudes relacionadas con la asignación cuando llame a la API de actualización de configuración.

### <a name="allocation-using-tips"></a>Asignación conforme a recomendaciones

- Para cada producto, la función de asignación debe usarse en el mismo *nivel de dimensión*, de acuerdo con la jerarquía de índice de productos que estableció en la [configuración de la jerarquía del índice de productos](inventory-visibility-configuration.md#index-configuration). Por ejemplo, suponga que su jerarquía de índices es \[`Site`, `Location`, `Color`, `Size`\]. Si asigna alguna cantidad para un producto en el nivel de dimensión \[`Site`, `Location`, `Color`\], la próxima vez que desee asignar este producto, también debe asignar al mismo nivel, \[`Site`, `Location`, `Color`\]. Si usa el nivel \[`Site`, `Location`, `Color`, `Size`\] o \[`Site`, `Location`\], los datos serán inconsistentes.
- El cambio de nombre del grupo de asignación no afectará los datos guardados en el servicio.
- La asignación debe ocurrir después de que el producto tenga la cantidad disponible positiva.
- Para asignar productos de un grupo de *nivel de asignación* alto a un subgrupo, use la API `Reallocate`. Por ejemplo, tiene una jerarquía de grupos de asignación \[`channel`, `customerGroup`, `region`, `orderType`\], y desea asignar algún producto del grupo de asignación \[En línea, VIP\] al grupo de subasignación \[En línea, VIP, UE\], utilice la API `Reallocate` para mover la cantidad. Si usa la API `Allocate`, asignará la cantidad del conjunto común virtual.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Uso de la API de asignación

Actualmente, están abiertas cinco API de asignación:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Asignar

Llame a la API `Allocate` para asignar un producto que tiene dimensiones específicas. Aquí está el esquema para el cuerpo de la solicitud.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Por ejemplo, desea asignar una cantidad de 10 para el producto *Bicicleta*, sitio *1*, ubicación *11*, color *rojo*, canal *En línea*, grupo de clientes *VIP* y región *EE. UU.*. Para realizar esta asignación, puede realizar una llamada que tenga el siguiente contenido de cuerpo.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

La cantidad siempre debe ser mayor que 0 (cero).

#### <a name="unallocate"></a>Desasignar

Utilice la API `Unallocate` para revertir la operación `Allocate`. No se permite una cantidad negativa en una operación `Allocate`. El cuerpo de `Unallocate` es idéntico al cuerpo de `Allocate`.

#### <a name="reallocate"></a>Reasignar

Utilice la API `Reallocate` para mover alguna cantidad asignada a otra combinación de grupo. Aquí está el esquema para el cuerpo de la solicitud.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Por ejemplo, puede mover dos bicicletas que tengan las dimensiones \[sitio=1, ubicación=11, color=rojo\] del grupo de asignación \[En línea, VIP, EE. UU.\] al grupo de asignación \[En línea, VIP, UE\] llamando a la API `Reallocate` y proporcionando el siguiente cuerpo de texto.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Consumir

Utilice la API `Consume` para publicar la cantidad de consumo frente a la asignación. Por ejemplo, puede usar esta API para mover la cantidad asignada a algunas medidas reales. Aquí está el esquema para el cuerpo de la solicitud.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Por ejemplo, hay ocho bicicletas asignadas que tienen las dimensiones \[sitio=1, ubicación=11, color=rojo\] para el grupo de asignación \[En línea, VIP, EE. UU.\]. Se utiliza la siguiente fórmula de disponible para asignar:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

Las ocho bicicletas se asignan desde la medida `pos.inbound`.

Ahora, se venden tres bicicletas y se toman del grupo de asignación. Para realizar este movimiento, puede realizar una llamada que tenga el siguiente cuerpo de la solicitud.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Después de esta llamada, la cantidad asignada para el producto se reducirá en 3. Además, la visibilidad de inventario generará un evento de cambio de disponibilidad, donde `pos.inbound` = *-3*. Alternativamente, puede mantener el valor `pos.inbound` como es y solo consumir la cantidad asignada. Sin embargo, en este caso, debe crear otra medida física para mantener las cantidades consumidas o utilizar la medida predefinida `@iv.@consumed`.

En esta solicitud, tenga en cuenta que la medida física que utiliza en el cuerpo de la solicitud de consumo debe utilizar el tipo de modificador opuesto (suma o resta), en comparación con el tipo de modificador utilizado en la medida calculada. Así que, en este cuerpo de consumo, `iv.inbound` tiene el valor `Subtraction`, no `Addition`.

El origen de datos `fno` no se puede usar en el cuerpo de consumo, ya que siempre afirmamos que la visibilidad de inventario no puede cambiar ningún dato para el origen de datos `fno`. El flujo de datos es unidireccional, lo que significa que todas las cantidades para el origen de datos `fno` deben provenir de su entorno de Supply Chain Management.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumir como reserva no en firme

La API `Consume` también puede consumir la cantidad asignada como una reserva flexible. En este caso, la operación `Consume` reducirá la cantidad asignada y luego hará una reserva no en firme para esa cantidad. Para utilizar este enfoque, también debe utilizar la característica [Reserva no en firme](inventory-visibility-reservations.md) de la visibilidad de inventario.

Por ejemplo, ha establecido un modificador de reserva no en firme (medida) como `iv.softreserved`. La siguiente fórmula se utiliza para la medida calculada disponible para reservar:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

Para utilizar esta configuración con la característica de asignación, agregue `@iv.@allocated` a `iv.available_to_reserve` para producir la siguiente fórmula:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved` – `@iv.@allocated`

Luego, actualice `@iv.@available_to_allocate` al mismo valor.

Cuando desee consumir una cantidad de 3 y directamente reservar esta cantidad, puede realizar una llamada que tenga el siguiente cuerpo de solicitud.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

En esta solicitud, observe que `iv.softreserved` tiene el valor `Addition` y no `Subtraction`.

#### <a name="query"></a>Consulta

Utilice la API `Query` para recuperar información relacionada con la asignación de algunos productos. Puede usar filtros de dimensión y filtros de grupo de asignación para restringir los resultados. Las dimensiones deben coincidir exactamente con la que desea recuperar, por ejemplo, \[sitio=1, ubicación=11\] tendrá resultados no relacionados en comparación con \[sitio=1, ubicación=11, color=rojo\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Por ejemplo, use \[sitio=1, ubicación=11, color=rojo\] y el campo de grupos vacíos para obtener todos los registros de asignación:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Use \[sitio=1, ubicación=11, color=rojo\] y los grupos \[canal=En línea, grupo de clientes=VIP, región=EE. UU.\] para obtener registros de asignación para este grupo:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
