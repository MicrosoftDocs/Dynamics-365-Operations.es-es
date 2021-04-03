---
title: El enlace de inicio de sesión redirige a un sitio de comercio electrónico
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando un enlace de inicio de sesión redirige al sitio de comercio electrónico en lugar de ir a la página de inicio de sesión.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585511"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>El enlace de inicio de sesión redirige a un sitio de comercio electrónico

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando un enlace de inicio de sesión redirige al sitio de comercio electrónico en lugar de ir a la página de inicio de sesión.

## <a name="description"></a>Descripción

Después de configurar un nuevo inquilino de Microsoft Azure Active Directory B2C (Azure AD B2C) en el creador de sitios de Commerceo, los usuarios que seleccionan el enlace **Iniciar sesión** se redirigen a la página de aterrizaje principal del comercio electrónico sin ir a la página de inicio de sesión.

## <a name="resolution"></a>Resolución

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Confirmar que la URL de respuesta esté configurada correctamente en la aplicación Azure AD B2C

Para confirmar que la URL de respuesta esté configurada correctamente en la aplicación Azure AD B2C, siga estos pasos.

1. Vaya a [Azure Portal](https://portal.azure.com/).
1. Seleccione la aplicación Azure AD B2C que creó para el acceso a su sitio.
1. Seleccione la aplicación que creó durante la configuración de Azure AD B2C.
1. En **URL de respuesta**, asegúrese de que la lista incluya entradas tanto para la URL del dominio del sitio como para la URL generada por comercio electrónico, como se muestra en el ejemplo de la siguiente ilustración.

    ![Entradas de URL de respuesta de Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> Tanto la URL del dominio del sitio como la URL generada por comercio electrónico deben tener un formato de URL válido que no incluya barras al principio ni al final.

## <a name="additional-resources"></a>Recursos adicionales

[Registrar una aplicación conectada en Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md)
