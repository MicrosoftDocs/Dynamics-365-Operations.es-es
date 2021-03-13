---
title: Comenzar con la administración del servicio del complemento de facturación electrónica
description: Este tema explica cómo comenzar con el complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104433"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Comenzar con la administración del servicio del complemento de facturación electrónica

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:

- Debe tener acceso a su cuenta de Microsoft Dynamics Lifecycle Services (LCS).
- Debe tener un proyecto LCS que incluya la versión 10.0.13 o posterior de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management. Además, estas aplicaciones deben implementarse en una de las siguientes áreas geográficas de Azure:

    - Este de EE. UU.
    - Oeste de EE. UU.
    - Norte de la UE
    - Oeste de la UE

- Debe tener acceso a su cuenta de Dynamics 365 Regulatory Configuration Services (RCS).
- Debe activar la característica de globalización para su cuenta RCS a través del módulo de administración de características. Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).
- Debe crear un almacén de claves y una cuenta de almacenamiento en Azure. Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Instalar el complemento para microservicios en Lifecycle Services

1. Inicie sesión en su cuenta de LCS.
2. Seleccione el mosaico **Gestión de características de vista previa**.
3. En la sección **Funciones de versión preliminar pública**, seleccione **Servicio de facturación electrónica**.
4. Compruebe que la opción **Característica en vista previa** esté establecida en **Sí**.

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Configurar los parámetros para la integración de RCS con el complemento de facturación electrónica

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la pestaña **Servicio de facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.

    | Geografía de centros de datos de Azure | Identificador URI de extremo de servicio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Este de EE. UU.                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Oeste de EE. UU.                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norte de la UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Oeste de la UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Este valor es un valor fijo.
5. En el campo **Id. de entorno de LCS**, introduzca el id. de su cuenta de suscripción de LCS.
6. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-key-vault-secret"></a>Crear secretos de Key Vault

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Característica de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.
4. Seleccione **Nuevo** para crear un secreto de almacén de claves.
5. En el campo **Nombre**, especifique el nombre del secreto de almacén de claves. En el campo **Descripción**, escriba una descripción.
6. En el campo **URI de Key Vault**, pegue el secreto de Azure Key Vault.
7. Seleccione **Guardar**.

## <a name="create-storage-account-secret"></a>Crear secreto de cuenta de almacenamiento

1. En la página **Parámetros de almacén de claves**, en la sección **Certificados**, seleccione **Añadir**.
2. En el campo **Nombre**, especifique el nombre del secreto de la cuenta de almacenamiento. En el campo **Descripción**, escriba una descripción.
3. En el campo **Tipo**, seleccione **Certificado**.
4. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Crear un entorno del complemento de facturación electrónica

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Característica de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.

## <a name="create-a-service-environment"></a>Crear un entorno de servicio

1. En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio**.
2. Seleccione **Nuevo** para crear un nuevo entorno de servicio.
3. En el campo **Nombre**, especifique el nombre del entorno de facturación electrónica. En el campo **Descripción**, escriba una descripción.
4. En el **Secreto de token de SAS de almacenamiento**, seleccione el nombre del certificado que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.
5. En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y también conectarse a la cuenta de almacenamiento.
6. En el campo **Id. de usuario**, introduzca el alias del usuario. En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.
7. Seleccione **Guardar**.
8. Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales, seleccione **Parámetros del almacén de claves** en el Panel de acciones y luego seleccione **Cadena de certificados** y siga estos pasos:

    1. Seleccione **Nuevo** para crear una cadena de certificados.
    2. En el campo **Nombre**, introduzca el nombre de la cadena de certificado. En el campo **Descripción**, escriba una descripción.
    3. En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.
    4. Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena.
    5. Haga clic en **Guardar** y, a continuación, cierre la página.
    6. Cierre la página.
9. En la página **Entorno de servicio**, seleccione **Publicar** en el panel de acciones para publicar el entorno en la nube. El valor del campo **Estado** se cambia a **Publicado**.

## <a name="create-a-connected-application"></a>Crear una aplicación conectada

1. En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Aplicaciones conectadas**.
2. Seleccione **Nuevo** para crear una aplicación conectada.
3. En el campo **Nombre**, especifique el nombre de la aplicación a conectar.
4. En el campo **Aplicación**, introduzca la URL del entorno de administración de Finance y Supply Chain Management para conectarse.
4. En el campo **Inquilino**, introduzca el inquilino del entorno de administración de Finance y Supply Chain Management para conectarse.
5. Seleccione **Guardar**.
6. En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno. A continuación, cierre la página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicaciones conectadas a entornos

1. En la página **Configuraciones de entorno**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.
2. En el campo **Aplicación conectada**, seleccione una aplicación conectada.
3. En el campo **Entorno de servicio**, seleccione un entorno de servicio.
4. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Configurar la integración del complemento de facturación electrónica en Finance y Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Active la característica de integración del complemento de facturación electrónica

1. Inicie sesión en su instancia de Finance o Supply Chain Management.
2. En el espacio de trabajo **Administración de características**, busque la nueva característica, **Integración de complemento de facturación electrónica**. Si esta característica no aparece en la página, seleccione **Buscar actualizaciones**.
3. Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar la URL del punto de conexión de servicio

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Servicio de envío**, en el campo **URL de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.

    | Geografía de centros de datos de Azure | URL de extremo de servicio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Este de EE. UU.                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Oeste de EE. UU.                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norte de la UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Oeste de la UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. En el campo **Entorno**, especifique el nombre del entorno del complemento de facturación electrónica.
4. Haga clic en **Guardar** y, a continuación, cierre la página.
