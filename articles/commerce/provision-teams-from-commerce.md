---
title: Aprovisionar Microsoft Teams desde Dynamics 365 Commerce
description: Este artículo describe cómo aprovisionar Microsoft Teams mediante el uso de datos organizativos de Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 56d7cb6da5c359d3e93553adbdc70a4786c42648
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268983"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Aprovisionar Microsoft Teams desde Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo describe cómo aprovisionar Microsoft Teams mediante el uso de datos organizativos de Dynamics 365 Commerce.

Dynamics 365 Commerce ofrece una manera fácil de aprovisionar Teams si aún no ha configurado equipos para sus tiendas minoristas allí. Al aprovechar la información bien definida de Commerce que desea usar en Teams, puede ayudar a los empleados de su tienda a comenzar en Teams. Esta información incluye la jerarquía organizativa, los nombres de las tiendas, la información de los empleados y cuentas Azure Active Directory (Azure AD). 

El proceso de aprovisionamiento de Teams tiene dos pasos principales:

1. En Teams, cree un equipo para cada tienda minorista y agregue trabajadores de la tienda como miembros del equipo apropiado. Si un empleado está asociado con más de una tienda minorista, la pertenencia del equipo reflejará ese hecho. Se creará un equipo de comunicaciones que incluye administradores regionales como miembros para ayudar a publicar tareas de Teams.
1. Suba su jerarquía organizativa de Commerce a Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Equipos de aprovisionamiento en la sede de Commerce

Antes de aprovisionar Microsoft Teams, complete estas tareas:

- Confirme que todos los gerentes regionales se hayan convertido en gerentes de comunicaciones.
- Confirme que la cuenta de Azure de cada gerente y trabajador de la tienda se haya asociado con el registro de trabajador de ese gerente o trabajador en la sede de Commerce.

Para aprovisionar Teams en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.
1. En el panel Acciones, seleccione **Aprovisionar equipos**. Un trabajo por lotes que se denomina **Provisión de equipos** es creado.
1. Vaya a **Administración del sistema \> Consultas \> Trabajos por lotes** y busque el trabajo más reciente que tenga la descripción **Provisión de equipos**. Espere hasta que este trabajo termine de ejecutarse.

> [!TIP]
> Si ninguno de sus gerentes regionales, gerentes de tienda y trabajadores de la tienda se ha asociado con una licencia de Teams, es posible que reciba el siguiente mensaje de error: "No se pudieron recuperar las categorías de Sku aplicables para el usuario". Para corregir el problema, seleccione **Sincronizar equipos y miembros** en el Panel de acciones.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Valide el aprovisionamiento de Teams en el centro de administración de Teams

Para validar el aprovisionamiento de Microsoft Teams en el centro de administración de Microsoft Teams, siga estos pasos.
    
1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com/) e inicie sesión como administrador de su inquilino de comercio electrónico.
1. En el panel de navegación izquierdo, seleccione **Teams** para expandirlo y luego seleccione **Administrar equipos**.
1. Confirme que se haya creado un equipo para cada tienda minorista Commerce.
1. Seleccione un equipo y confirme que los trabajadores de la tienda se hayan agregado como miembros.
1. En el panel de navegación izquierdo, seleccione **Usuarios** y confirme que todos los empleados de la tienda en todas las tiendas se hayan agregado como usuarios.

La siguiente ilustración muestra un ejemplo de la página **Administrar equipos** en el centro de administración de Teams.

![Ejemplo de la página Administrar equipos en el centro de administración de Teams.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Suba una jerarquía organizativa de Commerce a Teams
    
La jerarquía organizativa de Commerce se puede utilizar en Microsoft Teams para publicar tareas en todas las tiendas o en tiendas seleccionadas que utilizan la misma estructura jerárquica.

Para subir un jerarquía organizativa de Commerce a Teams, siga estos pasos.
    
1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Configuración de integración de Microsoft Teams**.
1. Seleccione **Descargar la jerarquía de destino** y luego seleccione **Tiendas minoristas por región** para descargar un archivo de valores separados por comas (CSV) de la jerarquía organizativa.
1. Instale el módulo Microsoft Teams PowerShell siguiendo los pasos en [Instalar Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).
1. Cuando se le solicite en la ventana de Teams PowerShell, inicie sesión con la cuenta de administrador para su inquilino de Azure AD.
1. Siga los pasos en [Configurar la jerarquía de orientación de su equipo](/microsoftteams/set-up-your-team-hierarchy) para cargar el archivo CSV para la jerarquía de orientación.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Verifique que la jerarquía organizativa se cargó en Teams

Para verificar que la jerarquía organizativa se cargó en Microsoft Teams, siga estos pasos.

1. Inicie sesión en el Teams como director de comunicaciones.
1. En el panel de navegación izquierdo, seleccione **Tareas por planificador**.
1. En la pestaña **Listas publicadas**, cree una nueva lista que tenga una tarea ficticia.
1. Seleccione **Publicar**. La jerarquía organizativa debe aparecer en el cuadro de diálogo **Seleccione a quién publicar**, como se muestra en el ejemplo de la siguiente ilustración.

![Ejemplo de una jerarquía organizativa en el cuadro de diálogo Seleccionar a quién publicar.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams](commerce-teams-integration.md)

[Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams](enable-teams-integration.md)

[Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV](synchronize-tasks-teams-pos.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams](map-stores-existing-teams.md)

[Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams](teams-integration-faq.md)
