---
title: Recursos humanos no aparece en aplicaciones de Microsoft Dynamics 365
description: Este artículo explica lo que hacer si el cliente no ve la aplicación Dynamics 365 Human Resources de Microsoft entre las aplicaciones de Microsoft Dynamics 365.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 658c6a4f17c022c3d0e3e49d16eb89624c4be27c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803978"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Recursos humanos no aparece en aplicaciones de Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emisión**

El cliente no ve Dynamics 365 Human Resources entre las aplicaciones de Microsoft Dynamics 365.

**Resolución**

Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft Power Apps.

1. El usuario de gestión que dispone de una licencia de Power Apps Plan 2 debe abrir [Portal de gestión de Power Apps](https://preview.admin.powerapps.com/).

2. Seleccione **Entornos**, seleccione el entorno correcto para Recursos humanos.

3. En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.

    ![Ficha Roles de entorno](media/environment-roles.png)

4. En la pestaña **Usuarios** , agregue el usuario o su organización.

    ![Pestaña usuarios](media/environment-maker.png)

5. Seleccione **Guardar**.

6. Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.

    ![Botón de sincronización](media/get-more.png)

    Después de terminar la sincronización, los Recursos humanos aparecerán en la página principal.


[!INCLUDE[footer-include](../includes/footer-banner.md)]