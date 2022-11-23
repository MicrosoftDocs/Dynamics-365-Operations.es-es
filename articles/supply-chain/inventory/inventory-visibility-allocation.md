---
title: Asignación de inventario de Inventory Visibility
description: Este artículo explica cómo configurar y usar la característica de asignación de inventario, que le permite reservar un inventario dedicado para garantizar que pueda cumplir con sus canales o clientes más rentables.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762682"
---
# <a name="inventory-visibility-inventory-allocation"></a>Asignación de inventario de Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Antecedentes comerciales y propósito

Las organizaciones a menudo tienen que preasignar su stock disponible a sus canales de ventas, grupos de clientes, regiones y eventos promocionales más importantes para garantizar que el stock preasignado esté protegido contra cualquier otro uso y se pueda consumir solo a través de transacciones de venta que sean relevantes para el asignación. La asignación de inventario en Visibilidad de inventario es un componente del proceso proceso de planificación operativa de ventas y se realiza antes de que ocurran las actividades de ventas reales y se creen pedidos de ventas.

Por ejemplo, una empresa que se llama Contoso produce una bicicleta popular. Desafortunadamente, debido a que una interrupción reciente de la cadena de suministro afectó todo el stock en tránsito de esa bicicleta, Contoso solo tiene un stock disponible limitado y debe aprovecharlo al máximo. Contoso opera tanto en línea como en tienda. En cada canal de venta, la empresa tiene algunos socios corporativos importantes (mercados y grandes minoristas) que exigen que se les guarde una porción específica del inventario disponible de bicicletas. Por lo tanto, la empresa de bicicletas debe poder equilibrar la distribución de existencias en todos los canales y también gestionar las expectativas de sus socios VIP. La mejor manera de lograr ambos objetivos es utilizar la asignación de inventario, de modo que cada canal y minorista pueda recibir cantidades asignadas específicas que puedan venderse a los consumidores más adelante.

La asignación de inventario tiene dos propósitos comerciales básicos:

- **Salvaguardia de inventario (ring fencing)**: las organizaciones desean preasignar existencias restringidas o limitadas a canales, regiones, clientes VIP y empresas subsidiarias priorizados. La característica de asignación de visibilidad de inventario tiene como objetivo proteger el inventario asignado, de modo que otras asignaciones, reservas u otras demandas de ventas no afecten al inventario previamente asignado.
- **Control de sobreventa**: la función de asignación de visibilidad de inventario tiene como objetivo poner una restricción sobre las cantidades previamente asignadas, de modo que la parte receptora (por ejemplo, un canal o grupo de clientes) no las consuma en exceso cuando la transacción de venta real que se basa en una reserva no en firme entre en vigor.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definición de asignación en el Servicio de visibilidad de inventario

### <a name="allocation-virtual-pool"></a>Pool virtual de asignación

Aunque la característica de asignación en Visibilidad de inventario no reserva cantidades de inventario físico, sí se refiere a la cantidad de inventario físico disponible para definir cantidad inicial del grupo virtual *disponible para asignar*. La asignación de inventario en la visibilidad de inventario es una asignación flexible. Se realiza antes de que se produzcan las transacciones de venta reales y no depende de los pedidos de venta. Por ejemplo, puede asignar existencias a sus canales de ventas más importantes o a los grandes minoristas corporativos antes de que los clientes finales visiten el canal de ventas o la tienda minorista para comprar.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Diferencia entre asignación de inventario y reserva suave

Las [reservas no en firme](inventory-visibility-reservations.md) normalmente están vinculadas a transacciones de ventas reales (líneas de órdenes de venta). Tanto la asignación como la reserva de software se pueden usar de forma independiente, pero si desea usarlas juntas, la reserva de software debe realizarse después de la asignación. Recomendamos que realice primero la asignación de inventario y luego la reserva no en firme sobre las cantidades asignadas para lograr un consumo casi en tiempo real con respecto a la asignación. Para más información, vea [Consumir como reserva no en firme](#consume-to-soft-reserved).

La característica de asignación de inventario permite a los planificadores de ventas o gerentes de cuentas clave administrar y preasignar existencias importantes en grupos de asignación (como canales, regiones y grupos de clientes). También es compatible con el seguimiento, el ajuste y el análisis en tiempo real del consumo frente a las cantidades asignadas para garantizar que el reabastecimiento o la reasignación se puedan realizar a tiempo. Esta capacidad de tener visibilidad en tiempo real de la asignación, el consumo y el saldo de la asignación es especialmente importante en eventos de promoción o venta rápida.

## <a name="terminology"></a>Terminología

Los siguientes términos y conceptos son útiles en los planteamientos sobre la asignación de inventario:

- **Grupo de asignación**: el grupo al que pertenece la asignación, como un canal de ventas, un grupo de clientes o un tipo de pedido.
- **Valor del grupo de asignación**: el valor de cada grupo de asignación. Por ejemplo, *web* o *tienda* podría ser el valor del grupo de asignación del canal de ventas, mientras que *VIP* o *normal* podría ser el valor del grupo de asignación de clientes.
- **Jerarquía de asignación**: un medio para combinar grupos de asignación de manera jerárquica. Por ejemplo, puede definir *canal* como nivel de jerarquía 1, *región* como nivel 2 y *grupo de clientes* como nivel 3. Durante la asignación de inventario, debe seguir la secuencia de la jerarquía de asignación al especificar el valor del grupo de asignación. Por ejemplo, puede asignar 200 bicicletas rojas al canal *Web*, la región *Londres* región y el grupo de clientes *VIP*.
- **Disponible para asignar**: el *conjunto común virtual* que indica la cantidad que está disponible para futuras asignaciones. Es una medida calculada que puede definir libremente usando su propia fórmula. Si también utiliza la función de reserva no en firme, le recomendamos que utilice la misma fórmula para calcular el disponible para asignar y el disponible para reservar.
- **Asignado**: una medida física que muestra la cuota asignada que pueden consumir los grupos de asignación. Se deduce al mismo tiempo que se suma la cantidad consumida.
- **Consumido**: una medida física que indica las cantidades que se han consumido frente a la cantidad asignada original. A medida que se agregan números a esta medida física, la medida física asignada se reduce automáticamente.

En la ilustración siguiente se muestra el flujo de trabajo de asignación de inventario.

![Flujo de trabajo empresarial de asignación de visibilidad de inventario.](media/inventory-visibility-allocation-flow.png "Flujo de trabajo empresarial de asignación de visibilidad de inventario.")

La siguiente ilustración muestra la jerarquía de asignación y los grupos de asignación. El *grupo común virtual* que se muestra aquí es la cantidad disponible para asignar.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Jerarquía de asignación de Visibilidad de inventario" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

El proceso de configuración de la característica de asignación consta de tres pasos:

- Habilite la función en la aplicación Inventory Visibility yendo a **Configuración \> Configuración y gestión de funciones \> Asignación**.
- Configurar el [origen de datos](inventory-visibility-configuration.md#data-source-configuration) y sus [medidas](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configure el nombre y la jerarquía del grupo de asignación.

### <a name="predefined-data-source"></a>Origen de datos predefinido

Cuando habilita la característica de asignación y llama a la API de actualización de configuración, la visibilidad de inventario crea un origen de datos predefinido y varias medidas iniciales.

El origen de datos se llama `@iv`. Incluye un conjunto de medidas físicas predeterminadas. Puede verlos desde la aplicación Inventory Visibility yendo a **Configuración \> Fuente de datos**. Debería ver **Fuente de datos - @IV**. Ampliar la fuente de datos `@iv` para ver la lista de medidas físicas iniciales:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Seleccione la pestaña **Medidas calculadas** para ver la medida calculada inicial, que se llama `@iv.@available_to_allocate`:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Agregar otras medidas físicas a la medida calculada disponible para asignar

Para utilizar la asignación, debe configurar correctamente la fórmula para la medida calculada disponible para asignar (`@iv.@available_to_allocate`). Por ejemplo, tiene el origen de datos `fno` y la medida `onordered`, el origen de datos `pos` y la medida `inbound`, y desea hacer una asignación sobre las existencias disponibles para la suma de `fno.onordered` y `pos.inbound`. En este caso, `@iv.@available_to_allocate` debería contener `pos.inbound` y `fno.onordered` en la fórmula. Este es un ejemplo:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> Fuente de datos `@iv` es una fuente de datos predefinida y las medidas físicas definidas en `@iv` con prefijo `@` son medidas predefinidas. Estas medidas son una configuración predefinida para la función de asignación, así que no las cambie ni las elimine o es probable que encuentre errores inesperados al usar la función de asignación.
>
> Puede agregar nuevas medidas físicas a la medida calculada predefinida `@iv.@available_to_allocate`, pero no debe cambiar su nombre.

### <a name="manage-allocation-groups"></a>Gestionar grupos de asignaciones

Se puede establecer un máximo de ocho nombres de grupos de asignación. Los grupos tienen una jerarquía. Siga estos pasos para ver y actualizar los grupos de asignación.

1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración** y luego, en la pestaña **Asignación**, seleccione **Editar configuración**. De forma predeterminada, hay una jerarquía de asignación que tiene cuatro capas: `Channel` (capa superior), `customerGroup` (segunda capa), `Region` (tercera capa) y `OrderType` (cuarta capa).
1. Puede eliminar un grupo de asignación existente seleccionando la **X** junto a él. También puede agregar nuevos grupos de asignación a la jerarquía ingresando el nombre de cada nuevo grupo directamente en el campo.

    > [!IMPORTANT]
    > Tenga cuidado cuando elimine o cambie la asignación de la jerarquía de asignación. Para orientación, consulte [Consejos para usar la asignación](#allocation-tips).

1. Cuando haya terminado de configurar el grupo de asignación y la jerarquía, guarde los cambios y luego seleccione **Actualizar configuración** en la parte superior derecha. Los valores de los grupos de asignación configurados se actualizarán cuando cree una asignación mediante la interfaz de usuario o API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). Los detalles sobre ambos enfoques se proporcionan más adelante en este artículo.

Si usa cuatro nombres de grupo y los configura para \[`channel`, `customerGroup`, `region`, `orderType`\], estos nombres serán válidos para las solicitudes relacionadas con la asignación cuando llame a la API de actualización de configuración.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Sugerancias para el uso de la asignación

- Para cada producto, la función de asignación debe usarse en el mismo *nivel de dimensión*, de acuerdo con la jerarquía de índice de productos que estableció en la [configuración de la jerarquía del índice de productos](inventory-visibility-configuration.md#index-configuration). Por ejemplo, suponga que su jerarquía de índices es \[`Site`, `Location`, `Color`, `Size`\]. Si asigna alguna cantidad para un producto en el nivel de dimensión \[`Site`, `Location`, `Color`\], la próxima vez que desee asignar este producto, también debe asignar al mismo nivel, \[`Site`, `Location`, `Color`\]. Si usa el nivel \[`Site`, `Location`, `Color`, `Size`\] o \[`Site`, `Location`\], los datos serán inconsistentes.
- **Modificación de grupos de asignación y la jerarquía:** Si los datos de asignación ya existen en el sistema, la eliminación de los grupos de asignación existentes o un cambio en la jerarquía del grupo de asignación dañará la asignación existente entre los grupos de asignación. Por lo tanto, asegúrese de limpiar manualmente todos los datos antiguos antes de actualizar su nueva configuración. Sin embargo, debido a que la adición de nuevos grupos de asignación a la jerarquía más baja no afecta las asignaciones existentes, no necesitará limpiar los datos.
- La asignación tendrá éxito solo si el producto tiene una cantidad `available_to_allocate` positiva.
- Para asignar productos de un grupo de *nivel de asignación* alto a un subgrupo, use la API `Reallocate`. Por ejemplo, tiene una jerarquía de grupos de asignación \[`channel`, `customerGroup`, `region`, `orderType`\], y desea asignar algún producto del grupo de asignación \[En línea, VIP\] al grupo de subasignación \[En línea, VIP, UE\], utilice la API `Reallocate` para mover la cantidad. Si usa la API `Allocate`, asignará la cantidad del conjunto común virtual.
- Para ver la disponibilidad general del producto (el grupo común), use la API de [consulta de disponibilidad](inventory-visibility-api.md#query-on-hand) para solicitar la cantidad de inventario que está *disponible para asignar*. A continuación, puede tomar decisiones de asignación en función de esta información.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Usar la API de asignación

Actualmente, están abiertas cinco API de asignación:

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** – Esta API se utiliza para crear la asignación inicial.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Esta API se utiliza para revertir o quitar las cantidades asignadas.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Esta API se utiliza para mover la cantidad asignada de una asignación existente a otros grupos de asignación.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Esta API se utiliza para deducir (usar) la cantidad asignada.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Esta API se utiliza para comparar los registros de asignación existentes con los grupos de asignación y la jerarquía.

### <a name="allocate"></a>Asignar

Llame a la API `Allocate` para asignar un producto que tiene dimensiones específicas. Aquí está el esquema para el cuerpo de la solicitud.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Desasignar

Utilice la API `Unallocate` para revertir la operación `Allocate`. No se permite una cantidad negativa en una operación `Allocate`. El cuerpo de `Unallocate` es idéntico al cuerpo de `Allocate`.

### <a name="reallocate"></a>Reasignar

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Consumir

Utilice la API `Consume` para publicar la cantidad de consumo frente a la asignación. Por ejemplo, puede usar esta API para mover la cantidad asignada a algunas medidas reales. Aquí está el esquema para el cuerpo de la solicitud.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumir como reserva no en firme

La API `Consume` también puede consumir la cantidad asignada como una reserva flexible. En este caso, la operación `Consume` reducirá la cantidad asignada y luego hará una reserva no en firme para esa cantidad. Para utilizar este enfoque, también debe utilizar la característica [Reserva no en firme](inventory-visibility-reservations.md) de la visibilidad de inventario.

Por ejemplo, ha establecido una medida física de reserva como `iv.softreserved`. La siguiente fórmula se utiliza para la medida calculada disponible para reservar:

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Consulta

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Usar la interfaz de usuario de asignación

Puede administrar manualmente las asignaciones a través de la interfaz de usuario abriendo la aplicación Inventory Visibility y yendo a **Visibilidad operativa \> Asignación**. Desde allí, puede realizar cualquiera de las acciones que se describen en las siguientes subsecciones.

### <a name="create-an-allocation"></a>Crear una asignación

Siga estos pasos para crear una asignación a partir de la página **Asignación** de la aplicación Visibilidad de inventario.

1. Seleccione **Asignar**.
1. Establezca los valores de los campos base, las dimensiones y los grupos de asignación objetivo. (Cuando selecciona la fuente de datos recopilados en la sección **Dimensiones**, primero use la lista desplegable para especificar las dimensiones (por ejemplo, `siteId`). Luego ingrese los valores de las dimensiones en los campos que aparecen).
1. Seleccione **enviar**.

### <a name="consume-an-allocation"></a>Consumir una asignación

Seleccione **Consumir** para consumir una asignación. Para asegurarse de consumir dentro del grupo de asignación y la jerarquía correctos, ingrese los mismos conjuntos de organización y detalles de dimensión que ingresó cuando creó la asignación.

### <a name="reallocate-an-allocation"></a>Reasignar una asignación

Seleccione **Redistribuir** para mover la cantidad asignada existente de un conjunto de grupos de asignación a otro.

### <a name="query-existing-allocations"></a>Consultar asignaciones existentes

Seleccione **Consulta** y, a continuación, introduzca los valores de producto, organización, dimensión y grupo de asignación para obtener los resultados de la consulta de las asignaciones existentes.
