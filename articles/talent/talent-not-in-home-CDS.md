---
title: Talent no se ve entre las aplicaciones de Microsoft Dynamics 365 (CDS1.0)
description: "Este tema explica qué hacer si el cliente no ve la aplicación Microsoft Dynamics 365 for Talent entre las aplicaciones de Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Talent no se ve entre las aplicaciones de Microsoft Dynamics 365 (CDS1.0)

[!include [banner](includes/banner.md)]

**Emisión**

El cliente no ve la aplicación Microsoft Dynamics 365 for Talent entre las aplicaciones de Microsoft Dynamics 365.

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

