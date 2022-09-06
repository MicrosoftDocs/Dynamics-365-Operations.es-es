---
title: API públicas de visibilidad de inventario
description: Este artículo describe las API públicas que proporciona Visibilidad de inventario.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 23f4c52b6d1d8c1af927a2c21455d6e24b24408a
ms.sourcegitcommit: 7bcaf00a3ae7e7794d55356085e46f65a6109176
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "9357651"
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
| /api/environment/{environmentId}/onhand | Registrar | [Crear un evento de cambio de inventario disponible](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Registrar | [Crear varios eventos de cambio](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Registrar | [Establecer/reemplazar cantidades disponibles](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Registrar | [Crear un evento de reserva](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Registrar | [Crear varios eventos de reserva](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Registrar | [Crear un cambio de inventario disponible programado](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Registrar | [Crear múltiples cambios de inventario disponible programados](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Registrar | [Consulta mediante el método POST](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Obtener | [Consulta mediante el método GET](#query-with-get-method) |
| /api/environment/{environmentId}/allocation/allocate | Registrar | [Crear un evento de asignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/unallocate | Registrar | [Crear un evento de desasignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/reallocate | Registrar | [Crear un evento de reasignación](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/consume | Registrar | [Crear un evento de consumo](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/query | Registrar | [Resultado de asignación de consulta](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> La parte {environmentId} de la ruta es el id. de entorno en Microsoft Dynamics Lifecycle Services (LCS).
> 
> La API masiva puede devolver un máximo de 512 registros para cada solicitud.

Microsoft ha proporcionado una colección de solicitudes *Postman* lista para usar. Puede importar esta colección a su software de *Postman* mediante el siguiente enlace compartido: <https://www.getpostman.com/collections/ad8a1322f953f88d9a55>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Buscar el punto de conexión de acuerdo con su entorno de Lifecycle Services

El microservicio de Visibilidad de inventario se implementa en Microsoft Azure Service Fabric, en múltiples geografías y múltiples regiones. Actualmente, no existe un punto de conexión central que pueda redirigir automáticamente su solicitud a la geografía y región correspondientes. Por lo tanto, debe componer la información en una URL utilizando el siguiente patrón:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

El nombre corto de la región se puede encontrar en el entorno de Microsoft Dynamics Lifecycle Services (LCS). En la tabla siguiente se muestran las regiones actualmente disponibles.

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
| Sur de Brasil        | sbr               |
| Centro y sur de EE. UU.    | scus              |

El número de isla es donde se implementa su entorno de LCS en Service Fabric. Actualmente no hay forma de obtener esta información del lado del usuario.

Microsoft ha creado una interfaz de usuario (IU) en Power Apps para que pueda obtener el punto de conexión completo del microservicio. Para obtener más información, consulte [Buscar el punto de conexión de servicio](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autentificación

El token de seguridad de la plataforma se utiliza para llamar a la API pública de Visibilidad de inventario. Por lo tanto, debe generar un _Token de Azure Active Directory (Azure AD)_ usando su aplicación de Azure AD. A continuación, debe utilizar el token de Azure AD para obtener el _token de acceso_ del servicio de seguridad.

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
   - El valor `context` debe ser el ID de entorno de LCS en el que desea implementar el complemento.
   - Configure todos los demás valores como se muestra en el ejemplo.

1. Recupere un token de acceso (`access_token`) enviando una solicitud HTTP con las siguientes propiedades:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Método:** `POST`
   - **Encabezado HTTP:** Incluya la versión de API. (La clave es `Api-Version` y el valor es `1.0`.)
   - **Contenido del cuerpo:** Incluya la solicitud JSON que creó en el paso anterior.

   Debería recibir un token de acceso (`access_token`) en respuesta. Debe usar este token como token de portador para llamar a la API de Visibilidad de inventario. He aquí un ejemplo.

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

| Id. del campo | Descripción |
|---|---|
| `id` | Un ID único para el evento de cambio específico. Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, el mismo evento no se contará dos veces en el sistema si se vuelve a enviar. |
| `organizationId` | El identificador de la organización vinculada al evento. Este valor se asigna a una organización o Id. de área de datos en Supply Chain Management. |
| `productId` | El identificador del producto. |
| `quantities` | La cantidad por la que se debe cambiar la cantidad de inventario disponible. Por ejemplo, si se agregan 10 libros nuevos a un estante, este valor será `quantities:{ shelf:{ received: 10 }}`. Si se sacan tres libros del estante o se venden, este valor será `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | El origen de datos de las dimensiones utilizadas en la consulta y el evento de cambio de registro. Si especifica el origen de datos, puede utilizar las dimensiones personalizadas del origen de datos especificada. Visibilidad de inventario puede asignar la configuración de dimensiones para asignar las dimensiones personalizadas a las dimensiones predeterminadas generales. Si no se especifica ningún valor de `dimensionDataSource`, solo puede utilizar las [dimensiones base](inventory-visibility-configuration.md#data-source-configuration-dimension) generales en sus consultas. |
| `dimensions` | Una par de clave-valor dinámico. Los valores se asignan a algunas de las dimensiones en Supply Chain Management. Sin embargo, también puede agregar dimensiones personalizadas (por ejemplo, _Origen_) para indicar si el evento proviene de Supply Chain Management o de un sistema externo. |

> [!NOTE]
> Los parámetros `SiteId` y `LocationId` construyen la [configuración de la partición](inventory-visibility-configuration.md#partition-configuration). Por lo tanto, debe especificarlas en dimensiones cuando cree eventos de cambio disponibles, establezca o anule cantidades disponibles o cree eventos de reserva.

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

El siguiente ejemplo muestra el contenido del cuerpo de muestra. En esta muestra, registra un evento de cambio para el producto *Camiseta de manga corta*. Este evento es del sistema de punto de venta (PDV) y el cliente ha devuelto una camiseta roja a su tienda. Este evento aumentará la cantidad del producto *Camiseta de manga corta* en 1.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Crear varios eventos de cambio

Esta API puede crear varios registros al mismo tiempo. Las únicas diferencias entre esta API y la [API de evento único](#create-one-onhand-change-event) son los valores de `Path` y `Body`. Para esta API, `Body` proporciona una matriz de registros. El número máximo de registros es 512, lo que significa que la API masiva de cambios disponibles puede admitir hasta 512 eventos de cambio a la vez.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Establecer/reemplazar cantidades disponibles

La API _Establecer valor disponible_ reemplaza los datos actuales del producto especificado.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Crear eventos de reserva

Para usar la API de *Reserva*, debe abrir la función de reserva y completar la configuración de la reserva. Para más información, consulte: [Configuración de reserva (opcional)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Crear un evento de reserva

Se puede hacer una reserva con diferentes configuraciones de origen de datos. Para configurar este tipo de reserva, primero especifique el origen de datos en el parámetro `dimensionDataSource`. Entonces, en el parámetro `dimensions`, especifique las dimensiones de acuerdo con la configuración de dimensión en el origen de datos de destino.

Cuando llama a la API de reserva, puede controlar la validación de la reserva especificando el parámetro booleano `ifCheckAvailForReserv` en el cuerpo de la solicitud. Un valor `True` significa que se requiere la validación, mientras que un valor `False` significa que la validación no es necesaria. El valor predeterminado es `True`.

Si desea cancelar una reserva o anular la reserva de cantidades de inventario especificadas, establezca la cantidad en un valor negativo y establezca el parámetro `ifCheckAvailForReserv` en `False` para omitir la validación.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Crear varios eventos de reserva

Esta API es una versión masiva de la [API de evento único](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Consulta de inventario disponible

Use la API de _Consulta de inventario disponible_ se utiliza para obtener datos del inventario disponible actual para sus productos. La API actualmente admite la consulta de hasta 100 elementos individuales por el valor `ProductID`. También se pueden especificar varios valores `SiteID` y `LocationID` en cada consulta. El límite máximo se define como `NumOf(SiteID) * NumOf(LocationID) <= 100`.

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

El parámetro `groupByValues` debe seguir su configuración para la indexación. Para obtener más información, consulte [Configuración de jerarquía de índice de productos](./inventory-visibility-configuration.md#index-configuration).

El parámetro `returnNegative` controla si los resultados contienen entradas negativas.

> [!NOTE]
> Si ha habilitado las características del programa de cambios de inventario disponible y neto no comprometido (NNC), su consulta también puede incluir el parámetro booleano `QueryATP`, que controla si los resultados de la consulta incluyen información de NNC. Para obtener más información y ver ejemplos, consulte [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](inventory-visibility-available-to-promise.md).

El siguiente ejemplo muestra el contenido del cuerpo de muestra.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
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
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
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

Aquí hay una URL de GET de muestra. Esta solicitud GET es exactamente la misma que la muestra de POST que se proporcionó anteriormente.

```txt
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

## <a name="available-to-promise"></a>Neto no comprometido

Puede configurar la visibilidad del inventario para que le permita programar futuros cambios de inventario disponible y calcular las cantidades de NNC. El NNC es la cantidad de un artículo que esté disponible y se pueda prometer a un cliente en el siguiente periodo. El uso del cálculo del NNC puede aumentar considerablemente la capacidad de entrega de su pedido. Para obtener información sobre cómo habilitar esta función y cómo interactuar con la visibilidad de inventario a través de su API después de habilitar la característica, consulte [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Asignación

Las API relacionadas con la asignación se encuentran en [Asignación de visibilidad de inventario](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
