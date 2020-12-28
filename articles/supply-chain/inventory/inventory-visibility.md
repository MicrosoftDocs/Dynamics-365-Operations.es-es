---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625074"
---
# <a name="inventory-visibility-add-in"></a>Complemento de visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.

Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel. Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.

Inventory Visibility es un microservicio construido en Common Data Service, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio. También es posible actualizar el índice para realizar consultas de inventario.

Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros. Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.

Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).

## <a name="install-the-inventory-visibility-add-in"></a>Instalar el complemento de visibilidad de inventario

Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS). LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.

Para obtener más información, consulte [Recursos de Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Requisitos previos

Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:

- Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.
- Genere las claves beta para su oferta en LCS.
- Habilite las claves beta para su oferta para su usuario en LCS.
- Póngase en contacto con el equipo de productos de visibilidad de inventario de Microsoft y proporcione un identificador de entorno en el que desea implementar el complemento de visibilidad de inventario.

Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Instalar el complemento

Para instalar el complemento de visibilidad de inventario, haga lo siguiente:

1. Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. En la página de inicio, seleccione el proyecto donde se implementa su entorno.
1. En la página del proyecto, seleccione el entorno donde desea instalar el complemento.
1. En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno**. Si la sección no está visible, asegúrese de que las claves beta de requisito previo se hayan procesado por completo.
1. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
    ![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")
1. Seleccione el vínculo **Instalar un nuevo complemento**. Se abre una lista de complementos disponibles.
1. Seleccione **Servicio de inventario** en la lista. (Tenga en cuenta que esto ahora puede aparecer como **Complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management**).
1. Ingrese valores para los siguientes campos para su entorno:

    - **ID de aplicación de AAD**
    - **Id. de suscriptor de AAD**

    ![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")

1. Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.
1. Seleccione **Instalar**. El estado del complemento se mostrará como **Instalando**. Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.

### <a name="get-a-security-service-token"></a>Obtenga un token de servicio de seguridad

Para obtener un token de servicio de seguridad, haga lo siguiente:

1. Conseguir su `aadToken` y llamar al punto final: https://securityservice.operations365.dynamics.com/token.
1. Reemplace `client_assertion` en el cuerpo con su `aadToken`.
1. Reemplace el contexto en el cuerpo con el entorno donde desea implementar el complemento.
1. Reemplace el alcance en el cuerpo con lo siguiente:

    - Alcance para MCK - "https://inventoryservice.operations365.dynamics.cn/.default"  
    (Puede encontrar el ID de aplicación e ID de inquilino de Azure Active Directory para MCK en `appsettings.mck.json`).
    - Alcance para PROD - "https://inventoryservice.operations365.dynamics.com/.default"  
    (Puede encontrar el ID de aplicación e ID de inquilino de Azure Active Directory para PROD en `appsettings.prod.json`).

    El resultado se parecerá al ejemplo siguiente.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. Obtendrá `access_token` como respuesta. Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario. He aquí un ejemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Desinstalar el complemento

Para desinstalar el complemento, seleccione **Desinstalar**. Actualizar LCS y el complemento de visibilidad de inventario se eliminarán. El proceso de desinstalación eliminará el registro del complemento y también iniciará un trabajo para limpiar todos los datos comerciales almacenados en el servicio.

## <a name="inventory-visibility-add-in-public-api"></a>Complemento de visibilidad de inventario en API pública

La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos de integración. Admite tres tipos principales de interacción:

- Publicar cambios disponibles en el complemento desde un sistema externo.
- Consultar cantidades actuales disponibles desde un sistema externo.
- Sincronización automática con Supply Chain Management disponible.

La sincronización automática no forma parte de la API pública, sino que se gestiona en segundo plano para los entornos que han habilitado el complemento de visibilidad de inventario.

### <a name="authentication"></a>Autentificación

El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario, por lo que debe generar un token de Azure Active Directory usando su aplicación de Azure Active Directory.

Para obtener más información sobre cómo obtener el token de seguridad, consulte [Instalar el complemento de visibilidad de inventario](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Configurar la API de visibilidad de inventario

Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones. La configuración puede variar según los detalles de su entorno. Incluye principalmente cuatro partes:

- [Partición](#partitioning)
- [Configuraciones de dimensiones](#dimension-configurations)
- [Indexación](#indexing)
- [Medida personalizada](#custom-measurement)

#### <a name="partitioning"></a>Partición

El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario. Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.

`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*. Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.

> [!NOTE]
> *Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario. En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configuraciones de dimensiones

Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.

La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.

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

> [!NOTE]
> El tipo de dimensión enumerado en la tabla anterior es solo para referencia. No es necesario definir el tipo de dimensión en Visibilidad de inventario.

Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.

Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados. Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.

Las dimensiones de destino deben ser una de las siguientes:

- Dimensiones predeterminadas en visibilidad de inventario
- Dimensiones personalizadas

El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.

#### <a name="indexing"></a>Indexación

La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.

La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.

> [!NOTE]
> Actualmente, solo puede configurar índices hasta un máximo de cinco. Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales. Por ejemplo, si desea consultar productos de la siguiente manera:

- Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.
- En algunos casos, solo desea consultar el producto en total.

Tendría dos índices definidos de la siguiente manera:

- `["ColorId", "SizeId"]`
- `[]`

El corchete vacío se agregará según el ID del producto dentro de la partición.

La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`. En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`. De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.

Puede poner sus criterios de consulta en el cuerpo de la solicitud.

Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Medida personalizada

Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management; sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las mediciones predeterminadas. Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.

La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.

Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Sistema de consumo | Medidas calculadas | Origen de datos | Modificador | Tipo de cálculo del modificador |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Adición |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Adición |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Resta |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Adición |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Resta |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Adición |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Adición |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Resta |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Resta |

Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Publicar cambios disponibles

La URL exacta en la que se publicará el evento dependerá de su región geográfica. Tomará la forma:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.

Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos. Por ejemplo:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Publicación de cambios disponibles ejemplo de consulta 1

Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.

Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas. El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Publicación de cambios disponibles ejemplo de consulta 2

Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base. Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Propiedades de campo de documento JSON

Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.

| Id. del campo | Descripción |
|---|---|
| `id` | Un ID único para el evento de cambio específico. Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema. |
| `organizationId` | El identificador de la organización vinculada al evento. Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos. |
| `productId` | El identificador del producto en cuestión. |
| `quantity` | La cantidad por la que se debe cambiar el producto disponible. Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10. Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3. |
| `dimensionDataSource` | La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación. Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada. Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales. Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.   |
| `dimensions` | Una bolsa dinámica de pares clave / valor. Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo. |

### <a name="querying-current-on-hand"></a>Consultando la corriente disponible

El punto final para consultar el actual disponible tendrá una URL similar:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Se consultará con el método HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Ejemplo 1 de consulta actual disponible

Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.

Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas. El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base. Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`. El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Ejemplo 2 de consulta actual disponible

Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base. Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Resultado devuelto de ejemplo

Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.
