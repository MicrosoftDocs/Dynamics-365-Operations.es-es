---
title: Comenzar con la administración de servicios de facturación electrónica
description: Este tema explica cómo comenzar con la facturación electrónica.
author: gionoder
ms.date: 03/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: be9e823a0c70aebcfd5353f7b922f8f4b1aa3d73
ms.sourcegitcommit: cc49cf74bd5a34f97a02cdccd473a6479e175a5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2022
ms.locfileid: "8493925"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Comenzar con la administración de servicios de facturación electrónica

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:

- Debe tener acceso a su cuenta de Microsoft Dynamics Lifecycle Services (LCS).
- Debe tener un proyecto LCS que incluya la versión 10.0.17 o posterior de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management. Además, estas aplicaciones deben implementarse en una de las siguientes áreas geográficas de Azure:

    - Estados Unidos
    - Europa
    - Reino Unido
    - Asia

- Debe tener acceso a su cuenta de Dynamics 365 Regulatory Configuration Services (RCS).
- Debe activar la característica de globalización para su cuenta RCS a través del módulo de administración de características. Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).
- Debe crear un almacén de claves y una cuenta de almacenamiento en Azure. Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Instalar el complemento para microservicios en Lifecycle Services

1. Inicie sesión en su cuenta de LCS y en el panel de proyecto de LCS, seleccione un proyecto de LCS.
2. En el proyecto, en el panel **Entornos**, seleccione su entorno implementado. El entorno que seleccione debe estar ejecutándose.
3. En la pestaña **Integración de Power Platform**, en el grupo de campo **Complementos del entorno**, seleccione **Instalar un nuevo complemento**.
4. Seleccione **Facturacion electrónica**.
5. En el campo **Id. de la aplicación AAD**, introduzca **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Este valor es fijo.
6. En el campo **Id. de inquilino de AAD**, introduzca el id. de su cuenta de suscripción de Azure. El inquilino de Azure Active Directory (Azure AD) que especifique debe ser el mismo inquilino que se utiliza para RCS.
7. Revise los términos y condiciones, y luego seleccione la casilla.
8. Seleccione **Instalar**. La instalación puede tardar varios minutos.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configurar los parámetros para la integración de RCS con la facturación electrónica

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Configuración relacionada**, seleccione **Parámetros de informes electrónicos**.
3. En la pestaña **Facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.

    | Geografía de centros de datos de Azure | Identificador URI de extremo de servicio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japón                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suiza                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emiratos Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australia                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Francia                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | India                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |


4. Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Este valor es un valor fijo.
5. En el campo **Id. de entorno de LCS**, introduzca el id. de su ambiente de LCS.
6. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-key-vault-references"></a>Crear referencias de Key Vault

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Configuraciones de entorno**, en el Panel de acciones, seleccione **Entornos de servicio** y luego seleccione **Parámetros de Key Vault**.
4. Seleccione **Nuevo** para crear una referencia de almacén de claves.
5. En el campo **Nombre**, especifique el nombre de la referencia del almacén de claves. En el campo **Descripción**, escriba una descripción.
6. En el campo **URI de Key Vault**, pegue el secreto del almacén de claves de Azure Key Vault. Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).
7. Seleccione **Guardar**.

## <a name="create-storage-account-secret"></a>Crear secreto de cuenta de almacenamiento

1. En la página **Configuraciones de ambiente**, en el panel de acciones, seleccione **Entorno de servicio** > **Parámetros de Key Vault**.
2. Seleccione una **Referencia de Key Vault** y, en la sección **Certificados**, seleccione **Agregar**.
3. En el campo **Nombre**, introduzca el nombre del secreto de la cuenta de almacenamiento. Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).
4. En el campo **Descripción**, escriba una descripción.
5. En el campo **Tipo**, seleccione **Secreto**.
6. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-a-digital-certificate-secret"></a>Crear un secreto de certificado digital

1. En la página **Configuraciones de entorno**, en el Panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.
2. Seleccione una **Referencia de Key Vault** y luego, en la sección **Certificados**, seleccione **Agregar**.
3. En el campo **Nombre**, introduzca el nombre del secreto del certificado digital. Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).
4. En el campo **Descripción**, escriba una descripción.
5. En el campo **Tipo**, seleccione **Certificado**.
6. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-a-service-environment"></a>Crear un entorno de servicio

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio**.
4. Seleccione **Nuevo** para crear un nuevo entorno de servicio.
5. En el campo **Nombre**, especifique el nombre del entorno de facturación electrónica. En el campo **Descripción**, escriba una descripción.
6. En el campo **Secreto de token SAS de almacenamiento**, seleccione el nombre del secreto de cuenta de almacenamiento que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.
7. En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y también conectarse a la cuenta de almacenamiento.
8. En el campo **Id. de usuario**, introduzca el alias del usuario. En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.
9. Seleccione **Guardar**.
10. Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales, seleccione **Parámetros del almacén de claves** en el Panel de acciones y luego seleccione **Cadena de certificados** y siga estos pasos:

    1. Seleccione **Nuevo** para crear una cadena de certificados.
    2. En el campo **Nombre**, introduzca el nombre de la cadena de certificado. En el campo **Descripción**, escriba una descripción.
    3. En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.
    4. Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena.
    5. Haga clic en **Guardar** y, a continuación, cierre la página.
    6. Cierre la página.

11. En la página **Entorno de servicio**, seleccione **Publicar** en el panel de acciones para publicar el entorno en la nube. El valor del campo **Estado** se cambia a **Publicado**.

## <a name="create-a-connected-application"></a>Crear una aplicación conectada

1. En la página **Configuración de entornos**, en el Panel de acciones, seleccione **Aplicaciones conectadas**.
2. Seleccione **Nuevo** para crear una aplicación conectada.
3. En el campo **Nombre**, especifique el nombre de la aplicación a conectar.
4. En el campo **Aplicación**, introduzca la URL del entorno de administración de Finance y Supply Chain Management para conectarse.
4. En el campo **Inquilino**, introduzca el inquilino del entorno de administración de Finance y Supply Chain Management para conectarse.
5. Seleccione **Guardar**.
6. En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno. A continuación, cierre la página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicaciones conectadas a entornos

1. En la página **Configuración de entornos**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.
2. En el campo **Aplicación conectada**, seleccione una aplicación conectada.
3. En el campo **Entorno de servicio**, seleccione un entorno de servicio.
4. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Configurar la integración de la facturación electrónica en Finance y Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Active la característica de integración de la facturación electrónica

1. Inicie sesión en su instancia de Finance o Supply Chain Management.
2. En el espacio de trabajo **Administración de características**, busque la característica, **Integración de facturación electrónica**. Si esta característica no aparece en la página, seleccione **Buscar actualizaciones**.
3. Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar la URL del punto de conexión de servicio

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Facturación electrónica**, en el campo **URL de punto de conexión**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.

    | Geografía de centros de datos de Azure | Identificador URI de extremo de servicio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japón                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suiza                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emiratos Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australia                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Francia                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | India                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. En el campo **Ambiente**, especifique el nombre del ambiente de servicio publicado en facturación electrónica.
4. Haga clic en **Guardar** y, a continuación, cierre la página.

### <a name="enable-flighting-keys-for-finance-or-supply-chain-management-version-10017"></a>Habilitar claves de tramos para Finance o Supply Chain Management versión 10.0.17

1. Ejecute el siguiente comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. Ejecute un comando IISreset para todos los AOS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
