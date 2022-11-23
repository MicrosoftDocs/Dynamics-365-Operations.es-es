---
title: Configurar un inquilino B2C en Commerce
description: En este artículo se describe cómo configurar los inquilinos de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) para la autenticación del sitio del usuario en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785153"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurar un inquilino B2C en Commerce

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar los inquilinos de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) para la autenticación del sitio del usuario en Dynamics 365 Commerce.

Dynamics 365 Commerce usa Azure AD B2C para admitir credenciales de usuario y flujos de autenticación. Un usuario puede registrarse, iniciar sesión y restablecer su contraseña a través de estos flujos. Azure AD B2C almacena información confidencial de autenticación de usuarios, como el nombre de usuario y la contraseña. El registro de usuario en el inquilino B2C almacenará un registro de cuenta local de B2C o un registro de proveedor de identidad social de B2C. Estos registros de B2C se vincularán de nuevo con el registro del cliente en el entorno de Commerce.

> [!WARNING] 
> Azure AD B2C retirará los flujos de usuarios antiguos (heredados) antes del 1 de agosto de 2021. Por lo tanto, debe planear migrar sus flujos de usuarios a la nueva versión recomendada. La nueva versión proporciona paridad de funciones y nuevas funciones. La biblioteca de módulos para Commerce versión 10.0.15 o superior debe usarse con los flujos de usuarios B2C recomendados. Para obtener más información, vea [Flujos de usuario en Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Los entornos de evaluación de comercio vienen con un inquilino de Azure AD B2C cargado previamente con fines de demostración. Cargar su propio inquilino Azure AD B2C con los pasos a continuación no es necesario para entornos de evaluación.

> [!TIP]
> Puede proteger aún más a los usuarios de su sitio y mejorar la seguridad de sus inquilinos B2C de Azure AD con Protección de identidad y acceso condicional de Azure AD. Para revisar las capacidades disponibles para Inquilinos de B2C Premium P1 y Premium P2 de Azure AD, consulte [Protección de identidad y acceso condicional para B2C de Azure AD](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Requisitos previos del entorno dinámico

Antes de comenzar, asegúrese de que su entorno de Dynamics 365 Commerce y el canal de comercio electrónico se configuran de forma adecuada mediante el cumplimiento de los siguientes requisitos previos.

- Configure el valor de las operaciones de PDV **AllowAnonymousAccess** en "1" en Commerce Headquarters:
    1. Vaya a **Operaciones de PDV**.
    1. En la cuadrícula de operaciones, haga clic con el botón derecho y seleccione **Personalizar**.
    1. Seleccione **Agregar un campo**.
    1. En la lista de columnas disponibles, seleccione la columna **AllowAnonymousAccess** para agregarlo.
    1. Seleccione **Actualizar**.
    1. Para la operación **612** "Agregar cliente", cambie **AllowAnonymousAccess** a "1".
    1. Ejecute el trabajo **1090 (registros)**.
- Configure el atributo **Manual** de la cuenta de cliente de secuencia numérica **No** en Commerce Headquarters:
    1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de clientes**.
    1. Seleccione **Secuencias numéricas**.
    1. En la fila **Cuenta de cliente**, haga doble clic en el valor **Código de secuencia numérica**.
    1. Sobre la ficha desplegable **General** de la secuencia numérica, establezca **Manual** en **No**.

Después del despliegue de su entorno de Dynamics 365 Commerce, también se recomienda [inicializar datos semilla](enable-configure-retail-functionality.md) en el entorno.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un inquilino B2C en Commerce, continúe con [Crear o vincular a uno inquilino B2C de Azure AD existente en Azure Portal](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Recursos adicionales

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
