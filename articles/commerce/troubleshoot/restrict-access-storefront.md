---
title: Restringir el acceso a un escaparate durante las pruebas o el desarrollo
description: Este tema explica cómo restringir el acceso a un escaparate de Microsoft Dynamics 365 Commerce mientras se realizan las pruebas internas o el desarrollo.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: cdc9b6af55bcba98f5ea7607bb1847f61a707778
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018347"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Restringir el acceso a un escaparate durante las pruebas o el desarrollo

[!include [banner](../../includes/banner.md)]

Este tema explica cómo restringir el acceso a un escaparate de Microsoft Dynamics 365 Commerce mientras se realizan las pruebas internas o el desarrollo.

## <a name="description"></a>Descripción

Durante las pruebas internas o el desarrollo activo, es posible que desee restringir el acceso a su sitio para evitar que los usuarios externos accedan a las páginas publicadas del escaparate.

## <a name="resolution"></a>Resolución

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Configurar Azure AD B2C mediante el uso de flujos de usuarios estándar

Para obtener información sobre cómo configurar Azure Active Directory B2C (Azure AD B2C) para su sitio de comercio electrónico, consulte [Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Restrinja el acceso de los usuarios a las páginas del escaparate y bloquee la creación de nuevos usuarios

Para restringir el acceso de los usuarios a las páginas del escaparate en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a su sitio.
1. Seleccione **Paginas** y luego seleccione la página a la que restringir el acceso de los usuarios.
1. Seleccione el módulo o el espacio de fragmentos y luego seleccione **Editar**.
1. En el panel de propiedades, seleccione **¿Requiere iniciar sesión?** y luego seleccione **Terminar de editar**.
1. Seleccione **Publicar**.

Para bloquear la creación de nuevos usuarios en Azure AD, siga estos pasos.

1. Vaya a [Azure Portal](https://portal.azure.com/).
1. Seleccione la aplicación Azure AD B2C que creó para el acceso a su sitio.
1. En el panel de navegación izquierdo, seleccione **Flujos de usuarios**.
1. En la parte superior de **Flujos de usuarios**, seleccione **Nuevo flujo de usuario**.
1. En la página **Seleccionar un tipo de flujo de usuario**, seleccione **Versión preliminar**.
1. En el medio de la página, seleccione **iniciar sesión v2**. Luego, siga los pasos en [Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md) para configurar el flujo como el flujo de usuario estándar de su sitio para Azure AD B2C durante las pruebas o el desarrollo.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](../custom-pages-user-logins.md)
