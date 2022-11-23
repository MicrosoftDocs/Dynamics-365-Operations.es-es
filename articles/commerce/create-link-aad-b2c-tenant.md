---
title: Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure
description: Este artículo describe cómo crear o vincular a un inquilino de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) en el portal de Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785296"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear o vincular a un inquilino de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) en el portal de Microsoft Azure. Para obtener más información, consulte [Tutorial: Crear un inquilino de Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-create-tenant).

Para crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure, siga estos pasos.

1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).
1. En el menú del portal de Azure, seleccione **Crear un recurso**. Asegúrese de utilizar la suscripción y el directorio que se conectarán con su entorno de Commerce.

    ![Crear un recurso en el portal de Azure.](./media/B2CImage_1.png)

1. Vaya a **Identidad \> Azure Active Directory B2C**.
1. Cuando esté en la página **Crear o vincular un inquilino de AAD B2C existente en el portal de Azure**, utilice de las opciones siguientes la que mejor se adapte a las necesidades de su empresa:

    - **Crear un nuevo inquilino de Azure AD B2C**: use esta opción para crear un nuevo inquilino de Azure AD B2C.
        1. Seleccione **Crear un nuevo inquilino de Azure AD B2C**.
        1. En **Nombre de la organización**, escriba el nombre de la organización.
        1. En **Nombre de dominio inicial**, escriba el nombre de dominio inicial.
        1. En **País o región**, seleccione el país o región.
        1. Seleccione **Crear** para crear el inquilino.

     ![Crear un nuevo inquilino de Azure AD.](./media/B2CImage_2.png)

     - **Vincular un inquilino de Azure AD B2C existente a mi suscripción de Azure**: use esta opción si ya tiene un inquilino de Azure AD B2C al que desee vincularse.
        1. Seleccione **Vincular un inquilino de Azure AD B2C existente a mi suscripción de Azure**.
        1. Para **Inquilino de Azure AD B2C**, seleccione el inquilino de B2C apropiado. Si aparece el mensaje "No se encontraron inquilinos B2C válidos" en el cuadro de selección, significa que no tiene ningún inquilino de B2C válido, por lo que deberá crear uno nuevo.
        1. Para **Grupo de recursos**, seleccione **Crear nuevo**. Introduzca un **Nombre** para el grupo de recursos que contendrá el inquilino, seleccione **Ubicación del grupo de recursos** y, a continuación, seleccione **Crear**.

    ![Vincular un inquilino de Azure AD B2C existente a la suscripción de Azure.](./media/B2CImage_3.png)

1. Una vez creado el nuevo directorio de Azure AD B2C (puede tardar unos minutos), aparecerá un vínculo al nuevo directorio en el panel de información. Este vínculo le dirigirá a la página "Esto es Azure Active Directory B2C".

    ![Vínculo al nuevo directorio de Azure AD](./media/B2CImage_4.png)

> [!NOTE]
> Si tiene varias suscripciones en su cuenta de Azure o ha configurado el inquilino de B2C sin vincularlo a una suscripción activa, un encabezado **Solución de problemas** le dirigirá en el proceso de vincular el inquilino a una suscripción. Seleccione el mensaje de solución de problemas y siga las instrucciones para resolver el problema de suscripción.

La siguiente imagen muestra un ejemplo de encabezado **Solución de problemas** de Azure AD B2C.

![Advertencia que indica que el directorio no tiene una suscripción activa.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un arrendatario B2C en Commerce, vaya a [Crear la aplicación B2C](create-b2c-app.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
