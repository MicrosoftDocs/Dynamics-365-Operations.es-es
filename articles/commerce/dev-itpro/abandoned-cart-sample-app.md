---
title: Detectar carros abandonados y enviar notificaciones a los clientes
description: Este tema describe cómo personalizar la aplicación de muestra de conector de carrito abandonado Microsoft Dynamics 365 Commerce para detectar carros abandonados y enviar notificaciones de recordatorio por correo electrónico a los clientes.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1db4e988653aa55db2b18fb201edeafc4d16a1bc
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2022
ms.locfileid: "8489039"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Detectar carros abandonados y enviar notificaciones a los clientes

[!include [banner](../includes/banner.md)]

Este tema describe cómo personalizar la aplicación de muestra de conector de carrito abandonado Microsoft Dynamics 365 Commerce para detectar carros abandonados y enviar notificaciones de recordatorio por correo electrónico a los clientes.

La capacidad de recuperar ingresos y retener clientes a través de notificaciones de carros abandonados es una capacidad importante que Dynamics 365 Commerce admite. Al personalizar la aplicación de muestra del conector de carro abandonado de Commerce, los minoristas pueden acceder a los carros de compras en Retail Server que no se han modificado durante un período de tiempo definido por los minoristas. Luego, esos carros se pueden recuperar, aumentar con datos de productos y clientes, y pasarlos a un proveedor de marketing por correo electrónico externo que puede generar notificaciones por correo electrónico y enviarles clientes.

La notificación por correo electrónico de carro abandonado que los clientes reciben puede contener la siguiente información:

- El nombre del cliente.
- El apellido del cliente.
- La dirección de correo electrónico del cliente.
- Una dirección URL que devuelve al cliente a su carro.
- La divisa de la transacción.
- Una lista de productos en el carro del cliente. Para cada producto, se incluye la siguiente información:

    - El nombre para mostrar del producto.
    - El id. del producto (utilizado para ensamblar una dirección URL a la página de descripción del producto)
    - Una imagen del producto que se puede cambiar de tamaño automáticamente para adaptarse a diferentes tamaños de ventanilla
    - Texto alternativo de la imagen del producto
    - El precio por unidad del producto

## <a name="abandoned-cart-connector-sample"></a>Ejemplo de conector de carro abandonado

Un modelo de conector que Microsoft proporciona a través del kit de desarrollo de software (SDK) para minoristas permite recuperar la información del carro abandonado y enviarla a un proveedor de marketing por correo electrónico externo. Este conector maneja la comunicación con Retail Server, usa Azure Key Vault para la seguridad, maneja la programación de la recuperación del carro para una ventana de tiempo específica y recupera datos de pedidos y productos. También proporciona una implementación de muestra para una integración con un proveedor de marketing por correo electrónico externo. El conector se crea para comunicarse con [Emarsys](https://emarsys.com) listo para usar. Sin embargo, se puede personalizar fácilmente para integrarlo con otras soluciones, como Constant Contact, Mailchimp y SendGrid.

La siguiente ilustración muestra los componentes de la aplicación de muestra del conector de carro abandonado.

![Componentes de la aplicación de muestra del conector del carro abandonado](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> Algunas regiones requieren que los clientes puedan optar por que los datos de su carro no se transfieran a un proveedor de marketing por correo electrónico o solicitar que se eliminen sus datos. Sin embargo, Microsoft no ofrece estas opciones a los clientes. Por lo tanto, si planea hacer negocios en regiones que lo exigen, debe proporcionar la infraestructura y las personalizaciones requeridas para rastrear las preferencias de los clientes y, en función de ellas, evitar que los datos de los clientes se transfieran a su plataforma de correo electrónico. También debe definir un proceso para purgar los datos de los clientes de su proveedor de marketing por correo electrónico a petición del cliente.

## <a name="obtain-the-code-sample"></a>Obtener el ejemplo de código

La aplicación de ejemplo del conector de carro abandonado se incluye en el SDK de Retail a partir de la versión 10.0.16. El código se puede encontrar debajo de **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Para obtener más información sobre el SDK de Retail y dónde desea obtenerlo, consulte [Kit de desarrollo de software (SDK) al por menor](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Aunque el código de ejemplo estuvo disponible por primera vez en las compilaciones de la versión 10.0.16, es compatible con la versión 10.0.13 y las compilaciones posteriores de Retail Server.

## <a name="prerequisites-and-dependencies"></a>Requisitos previos y dependencias

Para que pueda implementar y configurar el código de muestra del conector de carro abandonado, se deben cumplir los siguientes requisitos previos.

### <a name="access-to-commerce-resources"></a>Acceso a los recursos de Commerce

Para configurar e implementar la aplicación de conector de carro abandonado, debe tener acceso a los siguientes recursos de Commerce:

- Acceso de administrador a la sede de Commerce para su entorno
- Acceso al proyecto de Lifecycle Services (LCS) de Microsoft Dynamics para su entorno

### <a name="azure-cosmos-db"></a>Cosmos DB de Azure

La aplicación de conector de carro abandonado usa Cosmos DB de Azure para realizar un seguimiento de los id. y las marcas de tiempo de los carros que se han recuperado anteriormente. Puede usar Cosmos DB de Azure para conservar estos datos, o puede personalizar el ejemplo de código para integrarlo con otra opción de almacenamiento de datos. Para obtener más información sobre Cosmos DB de Azure, consulte [Bienvenido a Cosmos DB de Azure](/azure/cosmos-db/introduction).

Si usa Cosmos DB de Azure, deben cumplirse los siguientes requisitos previos para poder ejecutar la muestra:

- Debe tener una cuenta de Cosmos DB de Azure activa. Si no tiene una cuenta, consulte [Crear una cuenta de base de datos](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Debe recuperar el **URI** y los valores de  **CLAVE PRINCIPAL** (o **CLAVE SECUNDARIA**) de la hoja **Claves** de su cuenta de Cosmos DB de Azure en Azure Portal. Para obtener más información sobre cómo recuperar información de claves y extremos para su cuenta de Azure Cosmos DB, consulte [Ver, copiar y regenerar claves de acceso y contraseñas ](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

La aplicación de conector de carro abandonado usa Key Vault para almacenar los nombres y secretos de los diferentes componentes que requieren un acceso seguro.

Para configurar un almacén de claves, siga estos pasos.

1. Siga las instrucciones en [Administrar Key Vault en Azure Stack Hub mediante el portal](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Crear secretos para la siguiente información:

    - Nombre de usuario de la interfaz de programación de aplicaciones (API) de Emarsys y secreto de API
    - Id. de aplicación y secreto de carro abandonado

El código de ejemplo del conector del carro abandonado usa las credenciales predeterminadas de Azure para obtener acceso a Key Vault. Debes proporcionar permisos de **Lista** y **Lectura** para la identidad que planea usar para obtener acceso a Key Vault.

Para obtener más información sobre las credenciales predeterminadas de Azure, consulte la [Clase DefaultAzureCredential](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Crear un id. de aplicación de ejemplo de conector de carro abandonado para el inquilino de Azure AD

Debe crear un id. de aplicación de ejemplo de conector de carro abandonado para el inquilino de Azure Active Directory (AD). Para obtener información sobre cómo crear un id. de aplicación, consulte [Usar el portal para crear una entidad de servicio y aplicación de Azure AD que pueda acceder a recursos](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Agregar el id. de la aplicación de ejemplo de conector de carro abandonado a la lista de permitidos para la API de Retail Server

A continuación, debe agregar el id. de la aplicación de ejemplo de conector de carro abandonado a la lista de permitidos para la API de Retail Server. Para obtener información sobre cómo agregar un id. de aplicación a la lista de permitidos en Azure, consulte [Compatibilidad con la autenticación de servicio a servicio en Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Configurar la aplicación de ejemplo de conector de carro abandonado

Para configurar la aplicación de muestra de conector de carro abandonado, modifique el archivo de configuración **appSettings.json** que se encuentra en la raíz del directorio **AbandonedCartDetectionSample**. Las siguientes tablas describen las propiedades de archivo de configuración.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Propiedad    | Description |
| ----------- | ----------- |
| KeyVaultURI | El nombre del Sistema de nombres de dominio (DNS) del almacén de claves que está usando en Azure Portal. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Propiedad                                      | Description |
| --------------------------------------------- | ----------- |
| TenantId                                      | El id. de inquilino de Azure AD de inquilino de Azure. |
| RetailServerAudienceId                        | El id. de audiencia de Retail Server. Puede dejar el valor predeterminado. |
| AppIdKeyVaultSecretName                       | El nombre del secreto que ha creado para el id. de aplicación de ejemplo de conector de carro abandonado. |
| AppSecretKeyVaultSecretName                   | El nombre del secreto que almacena el secreto de la aplicación para el id. de aplicación de ejemplo de conector de carro abandonado. |
| RetailServerUrl                               | La URL de su instancia de Retail Server. Puede encontrar este valor en LCS. |
| OperatingUnitNumber                           | El número de unidad operativa (OUN). Puede encontrar este valor en la sede de Commerce. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | El comienzo de la ventana de tiempo para los carros abandonados que desea recuperar. El valor se expresa como un número de minutos antes de la hora actual. Por ejemplo, establezca esta propiedad en **120** para recuperar todos los carros que se modificaron por última vez entre hace 120 minutos y el final de la ventana de tiempo definida por la propiedad **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | El final de la ventana de tiempo para los carros abandonados que desea recuperar. El valor se expresa como un número de minutos antes de la hora actual. Por ejemplo, si la propiedad **IncludeAbandonedCartsModifiedSinceLastMinutes** se establece en **120**, establezca esta propiedad en **30** para recuperar todos los carros que se modificaron entre hace 120 minutos y hace 30 minutos. En la práctica, esta propiedad define la cantidad de tiempo que desea esperar antes de que se declare abandonado un carro. |
| ReturnToCartUrl                               | La URL del carro en su sitio de comercio electrónico, en el formato que se utiliza en el archivo **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

El estado del trabajo de recuperación de carros abandonados, los id. de carros y las marcas de tiempo modificadas se almacenan en Cosmos DB de Azure. De forma predeterminada, la configuración del archivo de configuración apunta a la instancia del emulador local de Cosmos DB de Azure. Cuando implemente el conector en producción, debe actualizar esta configuración para que apunte a la instancia de Cosmos DB de Azure en su suscripción de Azure. Para pruebas locales o de espacio aislado, puede usar el [emulador de Azure Cosmos DB](/azure/cosmos-db/local-emulator).

| Propiedad    | Description |
| ----------- | ----------- |
| EndPointUri | El URI del punto de conexión proporcionado por Azure o el emulador. |
| PrimaryKey  | La clave principal proporcionada por Azure o el emulador. |
| DatabaseId  | Id. de la base de datos. Puede dejar el valor predeterminado o proporcionar el suyo propio. |
| ContainerId | El id. del contenedor. Puede dejar el valor predeterminado o proporcionar el suyo propio. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Si está integrando con un proveedor de marketing por correo electrónico que no sea Emarsys, debe ampliar la interfaz **IEmailProvider** según corresponda para comunicarse con ese proveedor.

| Propiedad                      | Description |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | El id. del registro de evento externo que se crea en Emarsys. Puede encontrar el valor en **Configuración del desencadenador** en la campaña que creó para enviar notificaciones por correo electrónico de carros abandonados. |
| ApiUserNameKeyVaultSecretName | El nombre de la clave donde se almacena el nombre de usuario de la API de Emarsys. |
| ApiSecretKeyVaultSecretName   | El nombre de la clave donde se almacena el secreto de la API de Emarsys. |
| EmarsysContactKeyId           | El id. de la columna de correo electrónico en la base de datos de contactos de Emarsys. El valor predeterminado es **3** y no se debe cambiar. |

### <a name="mediaoptions"></a>MediaOptions

Si usa las capacidades de comercio electrónico en Commerce, puede usar la administración de activos digitales de Commerce para recuperar imágenes de productos. Para obtener más información sobre las funciones de cambio de tamaño de imagen en la gestión de activos digitales, consulte [Configuración de la ventanilla de ImageSettings](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Propiedad                             | Description |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | La URL raíz del administrador de recursos digitales de su sitio. Puede encontrar el valor en la clave de propiedad **Dirección URL base del servidor multimedia** en **Retail y Commerce \> Configuración de canal \> Perfiles de canales** en la sede de Commerce. |
| ImageViewPorts                       | El nodo de contenedor para configuraciones de ventanillas individuales. |
| ImageViewPorts/viewport              | La definición de ventanilla. Utilice esta propiedad para especificar los rangos de ancho de la ventanilla, en píxeles. Para ver un ejemplo que muestra cómo se utiliza esta propiedad, consulte el archivo de configuración **appSettings.json**. |
| ImageViewPorts/imageWidth            | El ancho de la imagen de la ventanilla, en píxeles. |
| imageViewPorts/imageHeight           | El alto de la imagen de la ventanilla, en píxeles. |
| imageViewPorts/useForDefaultImageTag | Un valor **true**/**false** que indica si se deben usar las dimensiones de imagen definidas por la ventanilla si la etiqueta HTML `<picture>` no se admite con un navegador web o un cliente de correo electrónico. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
