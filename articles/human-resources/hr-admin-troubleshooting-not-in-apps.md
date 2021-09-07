---
title: Recursos humanos no aparece en aplicaciones de Microsoft Dynamics 365
description: En este tema se explica qué hacer si Microsoft Dynamics 365 Human Resources no figura entre las aplicaciones de Microsoft Dynamics 365.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfed82463eece882bed66c7b2dac1dd30e04720e
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413410"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>La aplicación Human Resources no aparece en las aplicaciones de Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

El cliente no ve Dynamics 365 Human Resources entre las aplicaciones de Microsoft Dynamics 365.

**Resolución**

Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft Power Apps.

1. El usuario administrador que dispone de una licencia de Power Apps Plan 2 debe abrir el [Portal de administración de Power Apps](https://preview.admin.powerapps.com/).

2. Seleccione **Entornos**, seleccione el entorno correcto para Recursos humanos.

3. En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.

    ![Ficha Roles de entorno.](media/environment-roles.png)

4. En la pestaña **Usuarios** , agregue el usuario o su organización.

    ![Pestaña usuarios.](media/environment-maker.png)

5. Seleccione **Guardar**.

6. Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.

    ![Botón de sincronización.](media/get-more.png)

    Después de terminar la sincronización, los Recursos humanos aparecerán en la página principal.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
