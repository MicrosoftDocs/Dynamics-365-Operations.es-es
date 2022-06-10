---
title: Planes de cambio de visibilidad de inventario disponible y neto no comprometido
description: Este tema describe cómo programar futuros cambios de inventario disponible y calcular cantidades de neto no comprometido (NNC).
author: yufeihuang
ms.date: 05/11/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 7456f87bede7bd0073223fa4762f96f919799e06
ms.sourcegitcommit: 38d97efafb66de298c3f504b83a5c9b822f5a62a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763264"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Planes de cambio de visibilidad de inventario disponible y neto no comprometido

[!include [banner](../includes/banner.md)]

Este tema describe cómo configurar la función *Programación de cambio de inventario disponible* para programar futuros cambios de inventario disponible y calcular cantidades de neto no comprometido (NNC). El NNC es la cantidad de un artículo que esté disponible y se pueda prometer a un cliente en el siguiente periodo. El uso de este cálculo puede aumentar considerablemente la capacidad de entrega de su pedido.

Para muchos fabricantes, minoristas o vendedores, no es suficiente saber lo que está disponible actualmente. Deben tener una visibilidad completa de la disponibilidad futura. Esta disponibilidad futura debe considerar el suministro futuro, la demanda futura y el NNC.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Habilitar y configurar las funciones

Antes de poder usar NNC, debe configurar una o más medidas calculadas para calcular las cantidades de NNC. También debe activar la función y configurar los ajustes de NNC en Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Configurar medidas calculadas para cantidades de NNC

*Medida calculada de NNC* es una medida calculada predefinida que normalmente se usa para encontrar la cantidad disponible actualmente. La *Cantidad de suministro* es la suma de cantidades para aquellas medidas físicas que tienen un tipo modificador de *suma*, y la *cantidad de demanda* es la suma de cantidades para aquellas medidas físicas que tienen un tipo de modificador de *resta*.

Puede agregar varias medidas calculadas para calcular varias cantidades de NNC. Sin embargo, el número total de medidas físicas distintas en todas las medidas calculadas de NNC debe ser inferior a nueve.

> [!IMPORTANT]
> Una medida calculada es una composición de medidas físicas. Su fórmula puede incluir solo medidas físicas sin duplicados, y no medidas calculadas.

Por ejemplo, puede configurar la siguiente medida calculada:

**Disponible** = (*Inventariofísico* + *Disponible* + *Nolimitado* + *Inspeccion de calidad* + *Entrante*) – (*Reserva física* + *ReservaProvis* + *Saliente*)

La suma (*Inventariofísico* + *Disponible* + *Nolimitado* + *InspecciónCalidad* + *Entrante*) representa el suministro y la suma (*ReservaFísica* + *ReservaProvis* + *Saliente*) representa la demanda. Por lo tanto, la medida calculada se puede entender de la siguiente manera:

**Disponible** = *Suministro* – *Demanda*

Puede agregar otra medida calculada para calcular la cantidad NNC **On-hand-physical**.

**On-hand-physical** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*Outbound*)

Hay ocho medidas físicas distintas en esas dos medidas calculadas por ATP: *PhysicalInvent*, *OnHand*, *Unrestricted*, *QualityInspection*, *Inbound*, *ReservPhysical*, *SoftReservePhysical* y *Outbound*.

Para obtener información acerca de las medidas calculadas, vea [Medidas calculadas](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Active la función Programación de cambio de inventario disponible y configure los ajustes de NNC

Siga estos pasos para encender la función *Programación de cambio de inventario disponible* en Power Apps y configurar los ajustes de NNC.

1. Inicie sesión en Power Apps y abra Visibilidad de inventario.
1. Abra la página **Configuración**.
1. En la pestaña **Gestión de funciones**, active la función *Programación de cambio de inventario disponible*.
1. Seleccionar la pestaña **Ajustes de NNC**.
1. Cuando consulta la Visibilidad del inventario, proporcionará un resultado que incluye cada medida calculada de NNC que agregue aquí. Seleccione **Agregar** para agregar una nueva medida calculada para NNC.
1. Establezca los campos siguientes:

    - **Origen de datos**: seleccione el origen de datos asociado a la medida calculada.
    - **Medida calculada**: seleccione la medida calculada que está asociada con el origen de datos seleccionado y que desea usar para encontrar la cantidad disponible actualmente.
    - **Período de programación**: introduzca la cantidad de días que los usuarios pueden ver y enviar cambios de inventario disponible programados cuando se usa la medida calculada seleccionada. Los usuarios que consultan información de stock obtendrán la cantidad disponible, los cambios de inventario disponible programados y el NNC para cada día en este período, comenzando con la fecha actual. Seleccione un número entero entre 1 y 7.

    > [!IMPORTANT]
    > El período de programación incluye la fecha actual. Por lo tanto, los usuarios pueden programar cambios de inventario disponible para que ocurran en cualquier momento desde la fecha actual (el día en que se envía el cambio) hasta (período de programación - 1) días en el futuro.

1. Seleccione **Guardar**.
1. Repita los pasos del 5 al 7 hasta que haya agregado todas las medidas calculadas que necesite para el NNC.
1. Cuando haya terminado de configurar todos los ajustes necesarios, seleccione **Actualizar configuración**.

Para obtener más información, consulte [Completar y actualizar la configuración](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Cómo funcionan la Programación de cambio de inventario disponible y los cálculos del NNC

Una *Programación de cambio de inventario disponible* establece fechas esperadas y cantidades de cambios de inventario disponible programados. Puede enviar una Programación de cambio de inventario disponible a Visibilidad de inventario, siempre que las fechas estén dentro del período definido por el ajuste **Período de programación** (ver la sección [Habilitar y configurar las funciones](#setup)). Los usuarios que consultan información de stock obtendrán la cantidad disponible, los cambios de inventario disponible programados y el NNC para cada día en este período.

Los cambios programados inicialmente no están comprometidos y, por lo tanto, no afectan las cantidades disponibles reales en el sistema. Para confirmar los cambios, debe enviar un *evento de cambio de inventario disponible*, que actualiza la cantidad disponible real. A continuación, debe revertir el cambio programado enviando un programa de cambio de inventario disponible para una cantidad negativa coincidente.

Por ejemplo, realiza un pedido de 10 bicicletas y espera que llegue mañana. Por lo tanto, usted envía un programa de cambio de inventario disponible que tiene una cantidad de entrada de 10 y está fechado para mañana. Cuando llega el pedido al día siguiente, agrega las bicicletas a su inventario físico disponible. A continuación, debe confirmar el cambio en su sistema para actualizar la cantidad de inventario disponible real. Para confirmar el cambio, envíe un evento de cambio de inventario disponible que tenga una cantidad entrante de 10. A continuación, debe revertir el cambio programado enviando un programa de cambio de inventario disponible que tenga una cantidad entrante de -10.

Cuando consulta la Visibilidad del inventario para las cantidades disponibles y NNC, se devuelve la siguiente información para cada día en el período de programación:

- **Fecha**: la fecha a la que se aplica el resultado. El huso horario es el Tiempo Universal Coordinado (UTC).
- **Cantidad disponible** – La cantidad de inventario disponible real para la fecha especificada. Este cálculo se realiza de acuerdo con la medida calculada de NNC que está configurada para Visibilidad de inventario.
- **Suministro programado** – La suma de todas las cantidades entrantes programadas que no han estado físicamente disponibles para consumo o envío inmediatos a partir de la fecha especificada.
- **Demanda programada** – La suma de todas las cantidades de salida programadas que no se han consumido o enviado en la fecha especificada.
- **Cantidad de NNC** – La cantidad de inventario disponible mínima proyectada desde la fecha especificada hasta el final del período de programación. Esta cantidad incluye todos los ajustes de cantidad programados. Es la cantidad máxima que se puede prometer en la fecha actual para entrega o consumo en ese día.

Por ejemplo, si la fecha actual es el 1 de febrero de 2022 y el período de programación es 7, los usuarios pueden enviar cambios de inventario disponible programado que se espera que ocurran entre el 1 y el 7 de febrero de 2022. En este caso, la cantidad de NNC para el 3 de febrero, por ejemplo, se calcula en función de la cantidad disponible para ese día y las cantidades programadas del 3 al 7 de febrero.

## <a name="example"></a>Ejemplo

El siguiente ejemplo muestra cómo una serie de cambios en la cantidad programada afecta las cantidades disponibles y de NNC de las que informa visibilidad de inventario. También muestra cómo confirmar un cambio programado, cómo un cambio de programación confirmado afecta los resultados y qué puede ocurrir si no confirma un cambio programado.

Los resultados en este ejemplo muestran un valor *inventario disponible proyectado*. Este valor incorpora todas las actualizaciones programadas con fines ilustrativos, pero en realidad no se informa cuando consulta la visibilidad del inventario.

1. Los siguientes ajustes están configurados para su sistema en la página **Ajustes de NNC** de Power Apps:

    - **Medida calculada de NNC** – Tiene una medida calculada que se llama *Disponible*. Se calcula como *Disponible = suministro – Demanda*. Usted selecciona esa medida aquí.
    - **Período de programación** - usted selecciona *7*.

1. También se aplican las siguientes condiciones:

    - La fecha actual es 1 de febrero de 2022.
    - La cantidad de inventario disponible actual es 20.

1. Para la fecha actual (1 de febrero de 2022), usted envía una cantidad de demanda programada de 3 a Visibilidad de inventario. Así pues, la cantidad disponible proyectada es 17. La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | | | 17 | 17 |
    | 04/02/2022 | 20 | | | 17 | 17 |
    | 05/02/2022 | 20 | | | 17 | 17 |
    | 06/02/2022 | 20 | | | 17 | 17 |
    | 07/02/2022 | 20 | | | 17 | 17 |

1. En la fecha actual (1 de febrero de 2022), envía una cantidad de suministro programado de 10 para el 3 de febrero de 2022. La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | 10 | | 27 | 27 |
    | 04/02/2022 | 20 | | | 27 | 27 |
    | 05/02/2022 | 20 | | | 27 | 27 |
    | 06/02/2022 | 20 | | | 27 | 27 |
    | 07/02/2022 | 20 | | | 27 | 27 |

1. En la fecha actual (1 de febrero de 2022), envía los siguientes cambios de cantidad programados:

    - Cantidad de demanda de 15 para el 4 de febrero de 2022
    - Cantidad de suministro de 1 para el 5 de febrero de 2022
    - Cantidad de suministro de 3 para el 6 de febrero de 2022

    La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 12 |
    | 02/02/2022 | 20 | | | 17 | 12 |
    | 03/02/2022 | 20 | 10 | | 27 | 12 |
    | 04/02/2022 | 20 | | 15 | 12 | 12 |
    | 05/02/2022 | 20 | 1 | | 13 | 13 |
    | 06/02/2022 | 20 | 3 | | 16 | 16 |
    | 07/02/2022 | 20 | | | 16 | 16 |

1. En la fecha actual (1 de febrero de 2022), envía la cantidad de demanda programada de 3. Por lo tanto, debe confirmar este cambio para que se refleje en su cantidad de inventario disponible real. Para confirmar el cambio, envíe un evento de cambio de inventario disponible que tenga una cantidad saliente de 3. A continuación, debe revertir el cambio programado enviando un programa de cambio de inventario disponible que tenga una cantidad saliente de -3. La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 17 | | 0 | 17 | 12 |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |

1. Al día siguiente (2 de febrero de 2022), el período de programación se adelanta un día. La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |
    | 08/02/2022 | 17 | | | 16 | 16 |

1. Sin embargo, dos días después (4 de febrero de 2022), la cantidad de suministro de 10 que estaba programada para el 3 de febrero aún no ha llegado. La tabla siguiente muestra el resultado.

    | Fecha | Disponible | Suministro programado | Demanda programada | Inventario disponible proyectado | NNC |
    | --- | --- | --- | --- | --- | --- |
    | 04/02/2022 | 17 | | 15 | 2 | 2 |
    | 05/02/2022 | 17 | 1 | | 3 | 3 |
    | 06/02/2022 | 17 | 3 | | 6 | 6 |
    | 07/02/2022 | 17 | | | 6 | 6 |
    | 08/02/2022 | 17 | | | 6 | 6 |
    | 09/02/2022 | 17 | | | 6 | 6 |
    | 10/02/2022 | 17 | | | 6 | 6 |

    Como puede ver, los cambios de inventario disponible programados (pero no comprometidos) no afectan a la cantidad de inventario disponible real.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Envíe programaciones de cambios, eventos de cambios y consultas NNC a través de la API

Puede usar las siguientes direcciones URL de la interfaz de programación de aplicaciones (API) para enviar programaciones de cambios de inventario disponible, eventos de cambios y consultas.

| Ruta | Método | Description |
| --- | --- | --- |
| `/api/environment/{environmentId}/onhand/changeschedule` | `POST` | Crear un cambio de inventario disponible programado. |
| `/api/environment/{environmentId}/onhand/changeschedule/bulk` | `POST` | Crear múltiples cambios de inventario disponible programados. |
| `/api/environment/{environmentId}/onhand` | `POST` | Crear un evento de cambio de inventario disponible. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Crear muchos eventos de cambio de inventario disponible. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Consulta mediante el método `POST`. |
| `/api/environment/{environmentId}/onhand` | `GET` | Consulta mediante el método `GET`. |

Para obtener más información, consulte [API públicas de Visibilidad de inventario](inventory-visibility-api.md).

### <a name="create-one-on-hand-change-schedule"></a>Crear una programación de cambio de disponible

Las programaciones de cambio de disponible se crean enviando una solicitud `POST` a la URL del servicio de visibilidad de inventario correspondiente (consulte la sección [Enviar programaciones de cambios, eventos de cambios y consultas NNC a través de la API](#api-urls)). También puede enviar solicitudes masivas.

Una programación de cambio de disponible puede crearse solo si la fecha programada está entre la fecha actual y el final del período de programación actual. El formato datetime debe ser *año/mes/dia* (por ejemplo, **22/02/01**). El formato de hora debe ser exacto solo para el día.

Esta API crea una única programación de cambio de inventario.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # optional
        dimensions: {
            [key:string]: string,
        },
        quantitiesByDate: {
            [datetime:datetime]: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
    }
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra sin `dimensionDataSource`.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    },
    "quantitiesByDate":
    {
        "2022-02-01": // today
        {
            "pos":{
                "inbound": 10
            }
        }
    }
}
```

### <a name="create-multiple-on-hand-change-schedules"></a>Crear múltiples programaciones de cambio de inventario disponible

Esta API puede crear varios registros al mismo tiempo. Las únicas diferencias entre esta API y la API de evento único son los valores de `Path` y `Body`. Para esta API, `Body` proporciona una matriz de registros. El número máximo de registros es de 512. Por lo tanto, la API masiva de programación de cambios de disponible puede admitir hasta 512 cambios programados a la vez.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantitiesByDate: {
                [datetime:datetime]: {
                    [dataSourceName:string]: {
                        [key:string]: number,
                    },
                },
            },
        },
        ...
    ]
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra.

```json
[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-01": // today
            {
                "pos":{
                    "inbound": 10
                }
            }
        }
    },
    {
        "id": "id-car-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-05":
            {
                "pos":{
                    "outbound": 10
                }
            }
        }
    }
]
```

### <a name="create-on-hand-change-events"></a>Crear eventos de cambio de inventario disponible

Los eventos de cambios de inventario disponible se realizan enviando una solicitud `POST` a la URL del servicio de visibilidad de inventario correspondiente (consulte la sección [Envíe programaciones de cambios, eventos de cambios y consultas NNC a través de la API](#api-urls)). También puede enviar solicitudes masivas.

> [!NOTE]
> Los eventos de cambio de inventario disponible no son exclusivos de la funcionalidad NNC, sino que forman parte de la API de visibilidad de inventario estándar. Este ejemplo se ha incluido porque los eventos son relevantes cuando se trabaja con NNC. Los eventos de cambios de inventario disponible se parecen a las reservas de cambio de inventario disponible, pero los mensajes de eventos deben enviarse a una URL de API diferente y los eventos usan `quantities` en lugar de `quantityByDate` en el cuerpo del mensaje. Para obtener más información sobre los eventos de cambio de inventario disponible y otras características de la API de visibilidad de inventario, consulte[API públicas de visibilidad de inventario](inventory-visibility-api.md#create-one-onhand-change-event).

El siguiente ejemplo muestra un cuerpo de solicitud que contiene un solo evento de cambio de inventario disponible.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Consultar los cambios de inventario disponible programados y los resultados de NNC

Puede consultar los cambios de inventario disponible programados y los resultados de NNC enviando una solicitud `POST` o `GET` a la URL de la API adecuada (consulte la sección [Envíe programaciones de cambios, eventos de cambios y consultas NNC a través de la API](#api-urls)).

En su solicitud, establezca `QueryATP` como *verdadero* si desea consultar los cambios de inventario disponible programados y los resultados de NNC.

- Si está enviando la solicitud mediante el método `GET`, establezca este parámetro en la URL.
- Si está enviando la solicitud mediante el método `POST`, establezca este parámetro en el cuerpo de la solicitud.

> [!NOTE]
> Independientemente de si el parámetro `returnNegative` se establece en *cierto* o *falso* en el cuerpo de la solicitud, el resultado incluirá valores negativos cuando consulte los cambios de inventario disponible programados y los resultados de NNC. Estos valores negativos se incluirán porque, si solo se programan pedidos de demanda o si las cantidades de suministro son menores que las cantidades de demanda, las cantidades de cambio de inventario disponible programadas serán negativas. Si no se incluyeran valores negativos, los resultados serían confusos. Para obtener más información sobre esta opción y cómo funciona para otros tipos de consultas, consulte [API públicas de visibilidad de inventario](inventory-visibility-api.md#query-with-post-method).

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

El siguiente ejemplo muestra cómo crear un cuerpo de solicitud que se puede enviar a Inventory Visibility mediante el método `POST`.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "siteId": ["1"],
        "LocationId": ["11"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="get-method-example"></a>Ejemplo de método GET

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

El siguiente ejemplo muestra cómo crear una URL de solicitud como solicitud `GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&LocationId=11&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

El resultado de esta solicitud `GET` es exactamente igual que el resultado de la solicitud `POST` en el ejemplo anterior.

### <a name="query-result-example"></a>Ejemplo de resultado de consulta

Los dos ejemplos de consulta anteriores pueden producir la siguiente respuesta. Para este ejemplo, el sistema está configurado con los siguientes ajustes:

- **Medida calculada NNC:** *inv disponible = pos.entrada – pos.salida*
- **Período de programación:** *7*

A continuación se muestra un ejemplo del cuerpo de respuesta.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
