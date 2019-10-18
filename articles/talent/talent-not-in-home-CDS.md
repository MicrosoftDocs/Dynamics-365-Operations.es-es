---
title: Talent no figura entre las aplicaciones de Microsoft Dynamics 365 (Common Data Service 1.0)
description: Este tema explica qué hacer si el cliente no ve la aplicación Microsoft Dynamics 365 Talent entre las aplicaciones de Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 956af80a8ab2f454d9f523d3c74dda754ef0f793
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009386"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Talent no figura entre las aplicaciones de Microsoft Dynamics 365 (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Emisión**

El cliente no consulta la aplicación Microsoft Dynamics 365 Talent entre las aplicaciones de Microsoft Dynamics 365.

**Resolución**

Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft PowerApps.

1. El usuario de gestión que dispone de una licencia de PowerApps Plan 2 debe abrir [Portal de gestión de PowerApps](https://preview.admin.powerapps.com/).
2. Seleccione **Entornos**, y seleccione el entorno correcto para Talent.
3. En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.

    ![Ficha Roles de entorno](media/environment-roles.png)

4. En la pestaña **Usuarios** , agregue el usuario o su organización.

    ![Pestaña usuarios](media/environment-maker.png)

5. Seleccione **Guardar**.
6. Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.

    ![Botón de sincronización](media/get-more.png)

    Una vez que esté completada la sincronización, Talent aparecerá en la página principal.
