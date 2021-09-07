---
title: API públicas de visibilidad de inventario
description: Este tema describe las API públicas que proporciona Visibilidad de inventario.
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
ms.openlocfilehash: 0aca5838ff6d7c9c4d881698be1e2da2e0e1c02e
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343641"
---
# <a name="inventory-visibility-public-apis"></a>API públicas de visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tema describe las API públicas que proporciona Visibilidad de inventario.

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
| /api/environment/{environmentId}/onhand/indexquery | Obtener | [Consulta mediante el método POST](#query-with-post-method) |
| /api/environment/{environmentId}/onhand/indexquery | Registrar | [Consulta mediante el método GET](#query-with-get-method) |

Microsoft ha proporcionado una colección de solicitudes *Postman* lista para usar. Puede importar esta colección a su software de *Postman* mediante el siguiente enlace compartido: <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Buscar el punto de conexión de acuerdo con su entorno de Lifecycle Services

El microservicio de Visibilidad de inventario se implementa en Microsoft Azure Service Fabric, en múltiples geografías y múltiples regiones. Actualmente, no existe un punto de conexión central que pueda redirigir automáticamente su solicitud a la geografía y región correspondientes. Por lo tanto, debe componer la información en una URL utilizando el siguiente patrón:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

El nombre corto de la región se puede encontrar en el entorno de Microsoft Dynamics Lifecycle Services (LCS). En la tabla siguiente se muestran las regiones actualmente disponibles.

| Región de Azure | Nombre corto de la región |
|---|---|
| Este de Australia | eau |
| Sudeste de Australia | seau |
| Canadá central | cca |
| Este de Canadá | eca |
| Norte de Europa | neu |
| Europa Occidental | weu |
| Este de EE. UU. | eus |
| Oeste de EE. UU. | wus |
| Sur del Reino Unido | suk |
| Oeste del Reino Unido | wuk |

El número de isla es donde se implementa su entorno de LCS en Service Fabric. Actualmente no hay forma de obtener esta información del lado del usuario.

Microsoft ha creado una interfaz de usuario (IU) en Power Apps para que pueda obtener el punto de conexión completo del microservicio. Para obtener más información, consulte [Buscar el punto de conexión de servicio](inventory-visibility-power-platform.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autentificación

El token de seguridad de la plataforma se utiliza para llamar a la API pública de Visibilidad de inventario. Por lo tanto, debe generar un _token de Azure Active Directory (Azure AD)_ usando su aploicación de Azure AD. A continuación, debe utilizar el token de Azure AD para obtener el _token de acceso_ del servicio de seguridad.

Para obtener un token de servicio de seguridad, siga estos pasos:

1. Inicie sesión en Azure Portal y utilícelo para buscar los valores de `clientId` y `clientSecret` para su aplicación de Dynamics 365 Supply Chain Management.
1. Recupere un token de Azure AD (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Método:** `GET`
    - **Contenido del cuerpo (datos del formulario):**

        | Clave | Valor |
        |---|---|
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resource | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

    Debería recibir un token de Azure AD (`aadToken`) en respuesta. El resultado se parecerá al ejemplo siguiente.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
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
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Tenga en cuenta los aspectos siguientes:

    - El valor de `client_assertion` debe ser el token de Azure AD (`aadToken`) que recibió en el paso anterior.
    - El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.
    - Configure todos los demás valores como se muestra en el ejemplo.

1. Envíe una solicitud HTTP con las siguientes propiedades:

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

En secciones posteriores, usará el `$access_token` para representar el token que se obtuvo en el último paso.

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
| `dimensionDataSource` | El origen de datos de las dimensiones utilizadas en la consulta y el evento de cambio de registro. Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada. Visibilidad de inventario puede asignar la configuración de dimensiones para asignar las dimensiones personalizadas a las dimensiones predeterminadas generales. Si no se especifica ningún valor de `dimensionDataSource`, solo puede utilizar las [dimensiones base](inventory-visibility-configuration.md#data-source-configuration-dimension) generales en sus consultas. |
| `dimensions` | Una par de clave-valor dinámico. Los valores se asignan a algunas de las dimensiones en Supply Chain Management. Sin embargo, también puede agregar dimensiones personalizadas (por ejemplo, _Origen_) para indicar si el evento proviene de Supply Chain Management o de un sistema externo. |

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
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra sin `dimensionDataSource`.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Crear varios eventos de cambio

Esta API puede crear varios registros al mismo tiempo. Las únicas diferencias entre esta API y la [API de evento único](#create-one-onhand-change-event) son los valores de `Path` y `Body`. Para esta API, `Body` proporciona una matriz de registros.

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
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "@PRODUCT1",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosMachineId&quot;: &quot;0001"
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

El siguiente ejemplo muestra el contenido del cuerpo de muestra. El comportamiento de esta API difiere del comportamiento de las API que se describen en la sección [Crear eventos de cambio de inventario disponible](#create-onhand-change-event) anterior en este tema. En esta muestra, la cantidad del producto *Camiseta de manga corta* se establecerá en 1.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
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

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Para usar la API de *Reserva*, debe abrir la función de reserva y completar la configuración de la reserva. Para más información, consulte: [Configuración de reserva (opcional)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Crear un evento de reserva

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

La API de _Consulta de inventario disponible_ se utiliza para obtener datos del inventario disponible actual para sus productos.

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
        organizationId: string,
        filters: {
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

El siguiente ejemplo muestra el contenido del cuerpo de muestra.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Consulta mediante el método GET

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
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
/api/environment/{environmentId}/onhand/indexquery?organizationId=usmf&productId=T-shirt&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
