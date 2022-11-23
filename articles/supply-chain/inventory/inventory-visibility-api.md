---
title: API públicas de visibilidad de inventario
description: Este artículo describe las API públicas que proporciona Visibilidad de inventario.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8b0b8ca261237fbb2190f2a94cc11b816ae05af5
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762844"
---
# <a name="inventory-visibility-public-apis"></a>API públicas de visibilidad de inventario

[!include [banner](../includes/banner.md)]

Este artículo describe las API públicas que proporciona Visibilidad de inventario.

La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos para integración. Admite cuatro tipos principales de interacción:

- Publicar cambios de inventario disponible en el complemento desde un sistema externo
- Establecer o anular las cantidades de inventario disponibles en el complemento desde un sistema externo
- Registrar eventos de reserva en el complemento desde un sistema externo
- Consultar cantidades actuales disponibles desde un sistema externo

En la tabla siguiente se muestran las API actualmente disponibles:

| Ruta de acceso | Método | Descripción |
|---|---|---|
| /api/environment/{environmentId}/onhand | Registrar | [Crear un evento de cambio de inventario disponible](#create-one-onhand-change-event)|
| /api/environment/{environmentId}/onhand/bulk | Registrar | [Crear varios eventos de cambio](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Registrar | [Establecer/reemplazar cantidades disponibles](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Registrar | [Crear un evento de reserva no en firme](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Registrar | [Crear varios eventos de reserva no en firme](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Registrar | [Revertir un evento de reserva no en firme](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Registrar | [Revertir varios eventos de reserva no en firme](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Registrar | [Crear un cambio de inventario disponible programado](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Registrar | [Crear múltiples cambios de inventario disponible con fechas](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Registrar | [Consulta mediante el método POST](#query-with-post-method) (recomendado) |
| /api/environment/{environmentId}/onhand | Obtener | [Consulta mediante el método GET](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Registrar | [Consulta exacta mediante el método POST](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation<wbr>/allocate | Registrar | [Crear un evento de asignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/unallocate | Registrar | [Crear un evento de desasignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/reallocate | Registrar | [Crear un evento de reasignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/consume | Registrar | [Crear un evento de consumo](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/query | Registrar | [Resultado de asignación de consulta](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> La parte {environmentId} de la ruta es el id. de entorno en Microsoft Dynamics Lifecycle Services
> 
> La API masiva puede devolver un máximo de 512 registros para cada solicitud.

Microsoft ha proporcionado una colección de solicitudes *Postman* lista para usar. Puede importar esta colección a su software de *Postman* mediante el siguiente enlace compartido: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a><a name = "endpoint-lcs"></a>Buscar el punto de conexión de acuerdo con su entorno de Lifecycle Services

El microservicio de Visibilidad de inventario se implementa en Microsoft Azure Service Fabric, en múltiples geografías y múltiples regiones. Actualmente, no existe un punto de conexión central que pueda redirigir automáticamente su solicitud a la geografía y región correspondientes. Por lo tanto, debe componer la información en una URL utilizando el siguiente patrón:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

El nombre corto de la región se puede encontrar en el entorno de  Lifecycle Services. En la tabla siguiente se muestran las regiones actualmente disponibles.

| Región de Azure        | Nombre corto de la región |
| ------------------- | ----------------- |
| Este de Australia      | eau               |
| Sudeste de Australia | seau              |
| Canadá central      | cca               |
| Este de Canadá         | eca               |
| Norte de Europa        | neu               |
| Europa Occidental         | weu               |
| Este de EE. UU.             | eus               |
| Oeste de EE. UU.             | wus               |
| Sur del Reino Unido            | suk               |
| Oeste del Reino Unido             | wuk               |
| Este de Japón          | ejp               |
| Oeste de Japón          | wjp               |
| Centro de la India       | cin               |
| India del Sur         | sin               |
| Norte de Suiza   | nch               |
| Oeste de Suiza    | wch               |
| Sur de Francia        | sfr               |
| Este de Asia           | eas               |
| Sudeste de Asia     | seas              |
| Norte de Emiratos Árabes           | nae               |
| Este de Noruega         | eno               |
| Oeste de Noruega         | wno               |
| Oeste de Sudáfrica   | wza               |
| Norte de Sudáfrica  | nza               |

El número de isla es donde se implementa su entorno de Lifecycle Services en Service Fabric. Actualmente no hay forma de obtener esta información del lado del usuario.

Microsoft ha creado una interfaz de usuario (IU) en Power Apps para que pueda obtener el punto de conexión completo del microservicio. Para obtener más información, consulte [Buscar el punto de conexión de servicio](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autentificación

El token de seguridad de la plataforma se utiliza para llamar a la API pública de Visibilidad de inventario. Por lo tanto, debe generar un *token de Azure Active Directory (Azure AD)* usando su aploicación de Azure AD. A continuación, debe utilizar el token de Azure AD para obtener el *token de acceso* del servicio de seguridad.

Microsoft proporciona una colección de token *Postman* lista para usar. Puede importar esta colección a su software de *Postman* mediante el siguiente enlace compartido: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Para obtener un token de servicio de seguridad, siga estos pasos:

1. Inicie sesión en Azure Portal y utilícelo para buscar los valores de `clientId` y `clientSecret` para su aplicación de Dynamics 365 Supply Chain Management.
1. Recupere un token de Azure AD (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
    - **Método:** `GET`
    - **Contenido del cuerpo (datos del formulario):**

        | Clave           | Valor                                            |
        | ------------- | -------------------------------------------------|
        | client_id     | ${aadAppId}                                      |
        | client_secret | ${aadAppSecret}                                  |
        | grant_type    | client_credentials                               |
        | scope         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.default    |

    Debería recibir un token de Azure AD (`aadToken`) en respuesta. El resultado se parecerá al ejemplo siguiente.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formule una solicitud de notación de objetos JavaScript (JSON) que se parezca al siguiente ejemplo.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "{$LCS_environment_id}",
        "context_type": "finops-env"
    }
    ```

    Tenga en cuenta los aspectos siguientes:

    - El valor de `client_assertion` debe ser el token de Azure AD (`aadToken`) que recibió en el paso anterior.
    - El valor `context` debe ser el ID de entorno de Lifecycle Services en el que desea implementar el complemento.
    - Configure todos los demás valores como se muestra en el ejemplo.

1. Recupere un token de acceso (`access_token`) enviando una solicitud HTTP con las siguientes propiedades:

    - **URL:** `https://securityservice.operations365.dynamics.com/token`
    - **Método:** `POST`
    - **Encabezado HTTP:** Incluya la versión de API. (La clave es `Api-Version` y el valor es `1.0`.)
    - **Contenido del cuerpo:** Incluya la solicitud JSON que creó en el paso anterior.

    Debería recibir un token de acceso (`access_token`) en respuesta. Debe usar este token como token de portador para llamar a la API de Visibilidad de inventario. Este es un ejemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

> [!IMPORTANT]
> Cuando usa la solicitud de recopilación *Postman* para llamar a las API públicas de visibilidad de inventario, debe agregar un token de portador para cada solicitud. Para encontrar su token de portador, seleccione la pestaña **Autorización** debajo de la URL de solicitud, seleccione el tipo **Token de portador** y copie el token de acceso que se obtuvo en el último paso. En secciones posteriores de este artículo se usará el `$access_token` para representar el token que se obtuvo en el último paso.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Crear eventos de cambio de inventario disponible

Hay dos API para crear eventos de cambio de inventario disponible:

- Crear un registro: `/api/environment/{environmentId}/onhand`
- Crea varios registros: `/api/environment/{environmentId}/onhand/bulk`

La siguiente tabla resume el significado de cada campo en el cuerpo JSON.

| Id. del campo | Description |
|---|---|
| `id` | Un ID único para el evento de cambio específico. Si se produce un reenvío por un error de servicio, este ID se utiliza para garantizar que el mismo evento no se contará dos veces en el sistema. |
| `organizationId` | El identificador de la organización vinculada al evento. Este valor se asigna a una organización o Id. de área de datos en Supply Chain Management. |
| `productId` | El identificador del producto. |
| `quantities` | La cantidad por la que se debe cambiar la cantidad de inventario disponible. Por ejemplo, si se agregan 10 libros nuevos a un estante, este valor será `quantities:{ shelf:{ received: 10 }}`. Si se sacan tres libros del estante o se venden, este valor será `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | El origen de datos de las dimensiones utilizadas en la consulta y el evento de cambio de registro. Si especifica el origen de datos, puede utilizar las dimensiones personalizadas del origen de datos especificada. Visibilidad de inventario puede asignar la configuración de dimensiones para asignar las dimensiones personalizadas a las dimensiones predeterminadas generales. Si no se especifica ningún valor de `dimensionDataSource`, solo puede utilizar las [dimensiones base](inventory-visibility-configuration.md#data-source-configuration-dimension) generales en sus consultas. |
| `dimensions` | Una par de clave-valor dinámico. Los valores se asignan a algunas de las dimensiones en Supply Chain Management. Sin embargo, también puede agregar dimensiones personalizadas (por ejemplo, *Origen*) para indicar si el evento proviene de Supply Chain Management o de un sistema externo. |

> [!NOTE]
> Los parámetros `siteId` y `locationId` construyen la [configuración de la partición](inventory-visibility-configuration.md#partition-configuration). Por lo tanto, debe especificarlas en dimensiones cuando cree eventos de cambio disponibles, establezca o anule cantidades disponibles o cree eventos de reserva.

Las siguientes subsecciones proporcionan ejemplos que muestran cómo usar estas API.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Crear un evento de cambio de inventario disponible

Esta API crea un único evento de cambio de inventario disponible.

```txt
Path:
    /api/environment/{environmentId}/onhand
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
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra. En este ejemplo, la empresa tiene un sistema de punto de venta (POS) que procesa las transacciones en la tienda y, por lo tanto, los cambios de inventario. El cliente ha devuelto una camiseta roja a tu tienda. Para reflejar el cambio, publica un único evento de cambio para el producto *Camiseta de manga corta*. Este evento aumentará la cantidad del producto *Camiseta de manga corta* en 1.

```json
{
    "id": "Test201",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra sin `dimensionDataSource`. En este caso, `dimensions` serán las [dimensiones base](inventory-visibility-configuration.md#data-source-configuration-dimension). Si `dimensionDataSource` está establecido, `dimensions` puede ser las dimensiones del origen de datos o las dimensiones base.

```json
{
    "id": "Test202",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Crear varios eventos de cambio

Esta API puede crear eventos de cambio, al igual que la [API de evento único](#create-one-onhand-change-event). La única diferencia es que esta API puede crear varios registros al mismo tiempo. Por lo tanto, los valores de `Path` y `Body` difieren. Para esta API, `Body` proporciona una matriz de registros. El número máximo de registros es de 512. Por lo tanto, la API masiva de cambios de disponible puede admitir hasta 512 eventos de cambios a la vez. 

Por ejemplo, una máquina POS de una tienda minorista procesó las siguientes dos transacciones:

- Un pedido de devolución de una camiseta roja
- Una transacción de venta de tres camisetas negras

En este caso, puede incluir ambas actualizaciones de inventario en una llamada a la API.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
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
        "id": "Test203",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "Site1",
            "LocationId": "11",
            "posMachineId&quot;: &quot;0001"
            "colorId&quot;: &quot;red"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensions": {
            "siteId": "1",
            "locationId": "11",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Establecer/reemplazar cantidades disponibles

La API *Establecer valor disponible* reemplaza los datos actuales del producto especificado. Esta funcionalidad se utiliza normalmente para realizar actualizaciones de recuento de inventario. Por ejemplo, durante el recuento de inventario diario, una tienda puede descubrir que el inventario disponible real para una camiseta roja es 100. Por lo tanto, la cantidad de entrada a POS debe actualizarse a 100, independientemente de cuál era la cantidad anterior. Puede usar esta API para anular el valor existente.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra. El comportamiento de esta API difiere del comportamiento de las API que se describen en la sección [Crear eventos de cambio de inventario disponible](#create-onhand-change-event) anterior en este artículo. En esta muestra, la cantidad del producto *Camiseta de manga corta* se establecerá en 1.

```json
[
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "posMachineId": "0001"
            "colorId": "red"
        },
        "quantities": {
            "pos": {
                "inbound": 100
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Crear eventos de reserva

Para usar la API de *Reserva*, debe activar la función de reserva y completar la configuración de la reserva. Para obtener más información (incluido un flujo de datos y un escenario de muestra), consulte [Configuración de reservas (opcional)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Crear un evento de reserva

Se puede hacer una reserva con diferentes configuraciones de origen de datos. Para configurar este tipo de reserva, primero especifique el origen de datos en el parámetro `dimensionDataSource`. Entonces, en el parámetro `dimensions`, especifique las dimensiones de acuerdo con la configuración de dimensión en el origen de datos de destino.

Cuando llama a la API de reserva, puede controlar la validación de la reserva especificando el parámetro booleano `ifCheckAvailForReserv` en el cuerpo de la solicitud. Un valor `True` significa que se requiere la validación, mientras que un valor `False` significa que la validación no es necesaria. El valor predeterminado es `True`.

Si desea revertir una reserva o anular la reserva de cantidades de inventario especificadas, establezca la cantidad en un valor negativo y establezca el parámetro `ifCheckAvailForReserv` en `False` para omitir la validación. También hay una API de anulación de reserva dedicada para hacer lo mismo. La diferencia está solo en la forma en que se llama a las dos API. Es más fácil revertir un evento de reserva específico usando `reservationId` con la API *unreserve*. Para obtener más información, consulte la sección [evento Cancelar una reserva](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
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
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

El siguiente ejemplo muestra una respuesta correcta.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Crear varios eventos de reserva

Esta API es una versión masiva de la [API de evento único](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
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
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Revertir eventos de reserva

La API *Unreserve* sirve como operación inversa para eventos [*Reserva*](#create-reservation-events). Proporciona una forma de revertir un evento de reserva especificado por `reservationId` o para disminuir la cantidad de reserva.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Revertir un evento de reserva

Cuando se crea una reserva, se incluirá un `reservationId` en el cuerpo de la respuesta. Debe proporcionar el mismo `reservationId` para cancelar la reserva, e incluir los mismos `organizationId` y `dimensions` utilizados para la llamada a la API de reserva. Finalmente, especifique un valor de `OffsetQty` que represente el número de artículos a liberar de la reserva anterior. Una reserva puede revertirse total o parcialmente dependiendo de la especificación de `OffsetQty`. Por ejemplo, si se reservaron *100* unidades de artículos, puede especificar `OffsetQty: 10` para anular la reserva *10* de la cantidad inicial reservada.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
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
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

El siguiente código muestra un ejemplo de contenido del cuerpo.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

El siguiente código muestra un ejemplo de cuerpo de respuesta correcto.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> En el cuerpo de la respuesta, cuando `OffsetQty` es menor o igual que la cantidad de reserva, `processingStatus` será "*success*" y `totalInvalidOffsetQtyByReservId` será *0*.
>
> Si `OffsetQty` es mayor que la cantidad reservada, `processingStatus` será "*partialSuccess*" y `totalInvalidOffsetQtyByReservId` será la diferencia entre `OffsetQty` y la cantidad reservada.
>
>Por ejemplo, si la reserva tiene una cantidad de *10* y `OffsetQty` tiene un valor de *12*, `totalInvalidOffsetQtyByReservId` sería *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Revertir varios eventos de reserva

Esta API es una versión masiva de la [API de evento único](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
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
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Consulta de inventario disponible

Use la API de *Consulta de inventario disponible* se utiliza para obtener datos del inventario disponible actual para sus productos. Puede usar esta API siempre que deba conocer el stock, como cuando desee revisar los niveles de stock del producto en su sitio web de comercio electrónico, o cuando desee verificar la disponibilidad del producto en todas las regiones o en tiendas y almacenes cercanos. La API actualmente admite la consulta de hasta 5000 elementos individuales por el valor `productID`. También se pueden especificar varios valores `siteID` y `locationID` en cada consulta. El límite máximo está definido por la siguiente ecuación:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Consulta mediante el método POST

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

En la parte del cuerpo de esta solicitud, `dimensionDataSource` sigue siendo un parámetro opcional. Si no está configurado, `filters` se tratará como *dimensiones base*. Hay cuatro campos obligatorios para `filters`: `organizationId`, `productId`, `siteId` y `locationId`.

- `organizationId` debería contener solo un valor, pero sigue siendo una matriz.
- `productId` puede contener uno o más valores. Si es una matriz vacía, se devolverán todos los productos.
- `siteId` y `locationId` se utilizan para creación de particiones en visibilidad de inventario. Puede especificar más de un valor `siteId` y `locationId` en una solicitud *Consulta disponible*. En la versión actual, debe especificar ambos valores de `siteId` y `locationId`.

Le recomendamos que utilice el parámetro `groupByValues` para seguir su configuración para la indexación. Para obtener más información, consulte [Configuración de jerarquía de índice de productos](./inventory-visibility-configuration.md#index-configuration).

El parámetro `returnNegative` controla si los resultados contienen entradas negativas.

> [!NOTE]
> Si ha habilitado las características del programa de cambios de inventario disponible y neto no comprometido (NNC), su consulta también puede incluir el parámetro booleano `QueryATP`, que controla si los resultados de la consulta incluyen información de NNC. Para obtener más información y ver ejemplos, consulte [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](inventory-visibility-available-to-promise.md).

El siguiente ejemplo muestra el contenido del cuerpo de muestra. Muestra que puede consultar el inventario disponible desde varias ubicaciones (almacenes).

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "locationId": ["11","12","13"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

El siguiente ejemplo muestra cómo consultar todos los productos en un sitio y una ubicación específicos.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "locationId": ["11"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Consulta mediante el método GET

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

Este es un ejemplo de URL de GET. Esta solicitud GET es exactamente la misma que la muestra de POST que se proporcionó anteriormente.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="on-hand-exact-query"></a><a name="exact-query-with-post-method"></a>Consulta exacta de inventario disponible

Las consultas exactas disponibles se parecen a las consultas disponibles regulares, pero le permiten especificar una jerarquía de mapeo entre un sitio y una ubicación. Por ejemplo, tiene los dos sitios siguientes:

- Sitio 1, que está asignado a la ubicación A
- Sitio 2, que está asignado a la ubicación B

Para una consulta disponible regular, si especifica `"siteId": ["1","2"]` y `"locationId": ["A","B"]`, Visibilidad de inventario consultará automáticamente el resultado de los siguientes sitios y ubicaciones:

- Sitio 1, ubicación A
- Sitio 1, ubicación B
- Sitio 2, ubicación A
- Sitio 2, ubicación B

Como puede ver, la consulta disponible normal no reconoce que la ubicación A existe solo en el sitio 1 y la ubicación B solo existe en el sitio 2. Por lo tanto, hace consultas redundantes. Para adaptarse a esta asignación jerárquica, puede usar una consulta exacta disponible y especificar las asignaciones de ubicación en el cuerpo de la consulta. En este caso, consultará y recibirá resultados solo para el sitio 1, ubicación A y el sitio 2, ubicación B.

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Consulta exacta mediante el método POST

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
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
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

En la parte del cuerpo de esta solicitud, `dimensionDataSource` es un parámetro opcional. Si no está configurado, `dimensions` en `filters` se tratará como *dimensiones base*. Hay cuatro campos obligatorios para `filters`: `organizationId`, `productId`, `dimensions` y `values`.

- `organizationId` debería contener solo un valor, pero sigue siendo una matriz.
- `productId` puede contener uno o más valores. Si es una matriz vacía, se devolverán todos los productos.
- En la matriz `dimensions`, `siteId` y `locationId` son obligatorios, pero pueden aparecer con otros elementos en cualquier orden.
- `values` podría contener una o más tuplas distintas de valores correspondientes a `dimensions`.

`dimensions` en `filters` se agregará automáticamente `groupByValues`.

El parámetro `returnNegative` controla si los resultados contienen entradas negativas.

El siguiente ejemplo muestra el contenido del cuerpo de muestra.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

El siguiente ejemplo muestra cómo consultar todos los productos en varios sitios y ubicaciones.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Neto no comprometido

Puede configurar la visibilidad del inventario para que le permita programar futuros cambios de inventario disponible y calcular las cantidades de NNC. El NNC es la cantidad de un artículo que esté disponible y se pueda prometer a un cliente en el siguiente periodo. El uso del cálculo del NNC puede aumentar considerablemente la capacidad de entrega de su pedido. Para obtener información sobre cómo habilitar esta función y cómo interactuar con la visibilidad de inventario a través de su API después de habilitar la característica, consulte [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Asignación

Las API relacionadas con la asignación se encuentran en [Asignación de visibilidad de inventario](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
