---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017015"
---
# <a name="inventory-visibility-add-in"></a>Complemento de visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.

Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel. Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.

Inventory Visibility es un microservicio construido en Microsoft Dataverse, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio. También es posible actualizar el índice para realizar consultas de inventario.

Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros. Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.

Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).

## <a name="install-the-inventory-visibility-add-in"></a>Instalar el complemento de visibilidad de inventario

Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS). LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.

Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="inventory-visibility-add-in-prerequisites"></a>Requisitos previos del complemento de visibilidad de inventario

Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:

- Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.
- Asegúrese de que los requisitos previos para configurar complementos proporcionados en [Descripción general de los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ha sido completado. La visibilidad de inventario no requiere vinculación de escritura dual.
- Póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los siguientes tres archivos obligatorios:
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - `Inventory Visibility Integration.zip` (si la versión de Supply Chain Management que está ejecutando es anterior a la versión 10.0.18)
- De forma alternativa, póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los paquetes de Package Deployer. Estos paquetes pueden ser utilizados en una herramienta oficial de Package Deployer.
  - `InventoryServiceBase.PackageDeployer.zip`
  - `InventoryServiceApplication.PackageDeployer.zip` (este paquete contiene todos los cambios en el paquete `InventoryServiceBase`, además de componentes adicionales de la aplicación de interfaz de usuario)
- Siga las instrucciones dadas en [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar una aplicación y agregar un secreto de cliente a AAD bajo su suscripción azure.
  - [Registrar una aplicación](/azure/active-directory/develop/quickstart-register-app)
  - [Agregar un secreto de lciente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - El **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino** se utilizarán en los siguientes pasos.

> [!NOTE]
> Los países y regiones admitidos actualmente incluyen Canadá, Estados Unidos y la Unión Europea (UE).

Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Configurar Dataverse

Para configurar Dataverse para usarlo con visibilidad de inventario, primero debe preparar los requisitos previos y luego decidir si desea configurar Dataverse utilizando la herramienta Package Deployer o importando manualmente las soluciones (no tiene que hacer ambas cosas). Después, instale el complemento de visibilidad de inventario. En las siguientes subsecciones, se describe cómo completar cada tarea.

#### <a name="prepare-dataverse-prerequisites"></a>Preparar los requisitos previos de Dataverse

Antes de comenzar a configurar Dataverse, agregue un principio de servicio a su inquilino haciendo lo siguiente:

1. Instale Azure AD PowerShell Module v2 como se describe en [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).

1. Ejecute el siguiente comando de PowerShell:

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a>Configurar Dataverse usando la herramienta Package Deployer

Una vez que haya cumplido los requisitos previos, utilice el siguiente procedimiento si prefiere configurar Dataverse utilizando la herramienta Package Deployer. Consulte la siguiente sección para obtener detalles sobre cómo importar las soluciones manualmente (no haga ambas cosas).

1. Instale las herramientas de desarrollo como se describe en [Descargar herramientas de NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).

1. Según los requisitos de su negocio, elija el paquete `InventoryServiceBase` o `InventoryServiceApplication`.

1. Importe las soluciones:
    1. Para el paquete `InventoryServiceBase`:
        - Descomprima `InventoryServiceBase.PackageDeployer.zip`
        - Busque la carpeta `InventoryServiceBase`, el archivo `[Content_Types].xml`, el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` y el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`. 
        - Copie cada una de estas carpetas y archivos en el directorio `.\Tools\PackageDeployment`, que se creó cuando instaló las herramientas de desarrollo.
    1. Para el paquete `InventoryServiceApplication`:
        - Descomprima `InventoryServiceApplication.PackageDeployer.zip`
        - Busque la carpeta `InventoryServiceApplication`, el archivo `[Content_Types].xml`, el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` y el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.
        - Copie cada una de estas carpetas y archivos en el directorio `.\Tools\PackageDeployment`, que se creó cuando instaló las herramientas de desarrollo.
    1. Ejecute `.\Tools\PackageDeployment\PackageDeployer.exe`. Siga las instrucciones en su pantalla para importar las soluciones.

1. Asigne roles de seguridad al usuario de la aplicación.
    1. Abra la URL de su entorno de Dataverse.
    1. Vaya a **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y busque el usuario llamado **#InventoryVisibility**.
    1. Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**. Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a>Configurar Dataverse manualmente importando soluciones

Una vez que haya cumplido los requisitos previos, utilice el siguiente procedimiento si prefiere configurar Dataverse importanto soluciones manualmente. Consulte la sección anterior para obtener detalles sobre cómo usar la herramienta Package Deployer en su lugar (no haga ambas cosas).

1. Cree un usuario de la aplicación para la visibilidad del inventario en Dataverse:

    1. Abra la URL de su entorno de Dataverse.
    1. Ir **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y cree un usuario de la aplicación. Use el menú de vista para cambiar la vista de página a **Usuarios de la aplicación**.
    1. Seleccione **Nuevo**. Establezca el Id. de aplicación en *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*. (El ID del objeto se cargará automáticamente cuando guarde los cambios). Puede personalizar el nombre. Por ejemplo, puede cambiarlo a *Visibilidad de inventario*. Cuando haya terminado, haga clic en **Guardar**.
    1. Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**. Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.

    Para obtener más información, consulte [Crear un usuario de aplicación](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Si el idioma predeterminado de Dataverse no es **inglés**:

    1. Ir **Configuración avanzada \> Administración \> Idiomas**,
    1. Seleccione **Inglés (LanguageCode = 1033)** y seleccione **Solicitar**.

1. Importe el archivo `Inventory Visibility Dataverse Solution.zip`, que incluye las entidades relacionadas con la configuración de Dataverse y Power Apps:

    1. Vaya a la página **Soluciones**.
    1. Seleccione **Importar**.

1. Importe el flujo de activación de la actualización de la configuración:

    1. Vaya a la página de Microsoft Flow.
    1. Asegúrese de que la conexión que se denomina *Dataverse (heredado)* existe. (Si no existe, créela).
    1. Importe el archivo `Inventory Visibility Configuration Trigger.zip`. Una vez importado, el disparador aparecerá debajo de **Mis flujos**.
    1. Inicialice las siguientes cuatro variables, según la información del entorno:

        - Id. de inquilino de Azure
        - Id. de cliente de aplicación de Azure
        - Secreto de cliente de aplicación de Azure
        - Punto de conexión de Visibilidad de inventario

            Para obtener más información sobre esta variable, consulte la sección [Configurar la integración de visibilidad de inventario](#setup-inventory-visibility-integration) más adelante en este tema.

        ![Desencadenador de configuración](media/configuration-trigger.png "Desencadenador de configuración")

    1. Seleccione **Encender**.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Instalar el complemento

Para instalar el complemento de visibilidad de inventario, haga lo siguiente:

1. Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. En la página de inicio, seleccione el proyecto donde se implementa su entorno.
1. En la página del proyecto, seleccione el entorno donde desea instalar el complemento.
1. En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno** en la sección **Integración de Power Platform**, donde puede encontrar el nombre del entorno Dataverse.
1. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.

    ![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")

1. Seleccione el vínculo **Instalar un nuevo complemento**. Se abre una lista de complementos disponibles.
1. En la lista, seleccione **Visibilidad de inventario**.
1. Ingrese valores para los siguientes campos para su entorno:

    - **ID de aplicación de AAD (cliente)**
    - **Id. de suscriptor de AAD**

    ![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")

1. Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.
1. Seleccione **Instalar**. El estado del complemento se mostrará como **Instalando**. Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a>Desinstalar el complemento

Para desinstalar el complemento, seleccione **Desinstalar**. Cuando actualice LCS, el complemento de visibilidad de inventario se eliminarán. El proceso de desinstalación elimina el registro del complemento y también inicia un trabajo para limpiar todos los datos comerciales almacenados en el servicio.

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a>Consumir datos de inventario disponibles de Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implementar el paquete de integración de visibilidad de inventario

Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete. Luego implemente el paquete en LCS.

> [!NOTE]
> Si se produce un error de discrepancia de versión durante la implementación, debe importar manualmente el proyecto X ++ a su entorno de desarrollo. Luego, cree el paquete implementable en su entorno de desarrollo e impleméntelo en su entorno de producción.
> 
> El código se incluye con Supply Chain Management versión 10.0.18. Si está ejecutando esa versión o una posterior, la implementación no es necesaria.

Asegúrese de que las siguientes funciones estén activadas en su entorno de Supply Chain Management. (De forma predeterminada, están activadas).

| Descripción de la característica | Versión de código | Alternar clase |
|---|---|---|
| Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSum | 10.0.11 | InventUseDimOfInventSumToggle |
| Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurar integración de Visibilidad de inventario

1. En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active la caracterísica **Integración de visibilidad de inventario**.
1. Ir **Gestión del inventario \> Configurar \> Parámetros de integración de visibilidad de inventario** e ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario.

    Busque la región de Azure de su entorno LCS y luego ingrese la URL. La URL tiene el formato siguiente:

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    Por ejemplo, si se encuentra en Europa, su entorno tendrá una de las siguientes URL:

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    Tiene a su disposición las siguientes regiones:

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

1. Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo. Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a>API pública de complemento de visibilidad de inventario

La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos para integración. Admite tres tipos principales de interacción:

- Publicar cambios de inventario disponible en el complemento desde un sistema externo
- Consultar cantidades actuales disponibles desde un sistema externo
- Sincronización automática con el inventario disponible de Supply Chain Management

La sincronización automática no forma parte de la API pública. En su lugar, se maneja en segundo plano para entornos en los que el complemento de visibilidad de inventario está habilitado.

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autentificación

El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario. Por lo tanto, debe generar un *token de Azure Active Directory (Azure AD)* usando su aploicación de Azure AD. A continuación, debe utilizar el token de Azure AD para obtener el *token de acceso* del servicio de seguridad.

Obtenga un token de servicio de seguridad de la siguiente forma:

1. Inicie sesión en Azure Portal y utilícelo para encontrar el `clientId` y el `clientSecret` para su aplicación Supply Chain Management.
1. Busque un token Azure Active Directory (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Método** - `GET`
    - **Contenido del cuerpo (datos del formulario)**:

        | key | valor |
        | --- | --- |
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resource | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Debería recibir un `aadToken` en respuesta, que se parece al siguiente ejemplo.

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

1. Formule una solicitud JSON similar a la siguiente:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Donde:
    - El valor `client_assertion` debe ser el `aadToken` que recibió en el paso anterior.
    - El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.
    - Configure todos los demás valores como se muestra en el ejemplo.

1. Envíe una solicitud HTTP con las siguientes propiedades:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Método** - `POST`
    - **Encabezado HTTP** - Incluya la versión de API (la clave es `Api-Version` y el valor es `1.0`)
    - **Contenido del cuerpo** - Incluya la solicitud JSON que creó en el paso anterior.

1. Obtendrá `access_token` como respuesta. Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario. He aquí un ejemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a>Solicitud de muestra

Para su referencia, aquí hay una solicitud http de muestra, puede usar cualquier herramienta o lenguaje de codificación para enviar esta solicitud, como ``Postman``.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a>Configurar la API de visibilidad de inventario

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
        "ProductId": ["MyProduct1", "MyProduct2"],
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

Para el campo `filters`, actualmente solo `ProductId` admite varios valores. Si `ProductId` es una matriz vacía, se consultarán todos los productos.

#### <a name="custom-measurement"></a>Medida personalizada

Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management. Sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las medidas predeterminadas. Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
