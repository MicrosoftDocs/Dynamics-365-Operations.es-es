---
title: Configurar SQL Server Reporting Services para implementaciones locales
description: Este tema proporciona información acerca de la configuración de SQL Server Reporting Services (SSRS) para una implementación local.
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: bb6e8a55c9bee4e60c3a627409d2fbe3b8915196
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174245"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Configurar SQL Server Reporting Services para implementaciones locales

[!include [banner](../includes/banner.md)]

Siga los pasos de este tema para configurar SQL Server Reporting Services (SSRS) para una implementación de Microsoft Dynamics 365 Finance + Operations (on-premises).

1. Abra la aplicación de administrador de configuración de Reporting Services.
2. Deje el valor predeterminado **Nombre del servidor**, que debe ser el nombre del equipo actual y la **Instancia del servidor de informes**, **MSSQLSERVER**.
3. Haga clic en **Conectar**.

    [![Administrador de configuración de Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Haga clic en la pestaña **Cuenta de servicio** y compruebe que los valores coincidan con el siguiente gráfico.

    [![Pestaña Cuenta de servicio](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Haga clic en la pestaña **URL de servicio Web** y compruebe que los valores coincidan con el siguiente gráfico.

    [![Pestaña URL de servicio web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Haga clic en la pestaña **Base de datos** y compruebe que **Nombre de la base de datos** y **Valores de credenciales** coincidan con el siguiente gráfico.

    > [!NOTE]
    > Necesitará crear una nueva base de datos. Para ello, haga clic en **Cambiar base de datos** y compruebe que el nuevo nombre de la base de datos sea: **DynamicsAxReportServer**.

    [![Pestaña base de datos](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Haga clic en la pestaña **URL de portal Web** y compruebe que los valores coincidan con el siguiente gráfico.

    > [!NOTE]
    > Debe hacer clic en **Aplicar** para crear y configurar correctamente el portal.

    [![ficha de url de portal Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    Tras configurar el portal, la pestaña **Portal Web** coincidirá el siguiente gráfico.

    [![ficha de portal Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Haga clic en la dirección URL de informes para ver el portal Web de SQL Server Reporting Services.
9. Cuando esté en el portal, cree una nueva carpeta denominada **Dynamics**.

    [![carpeta dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. En **Administrador de configuración de Reporting Services**, haga clic en la pestaña **Configuración de correo electrónico** y compruebe que los valores coincidan con el siguiente gráfico.

    [![pestaña de configuración de correo electrónico](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Haga clic en la pestaña **Cuenta de ejecución** y compruebe que los valores coincidan con el siguiente gráfico.

    [![Pestaña Cuenta de ejecución](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    No cambie la configuración predeterminada en la pestaña **Claves de cifrado**.

    [![pestaña Claves de cifrado](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Haga clic en la pestaña **Configuración de suscripción** y compruebe que los valores coincidan con el siguiente gráfico.

    [![pestaña de configuración de suscripción](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    No cambie la configuración predeterminada en la pestaña **Escala de implementación**.

    [![pestaña de escala de implementación](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    No cambie la configuración predeterminada en la pestaña **Integración de Power BI**.

    [![pestaña Integración de Power BI](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Haga clic en **Salir** para cerrar el **administrador de configuración de Reporting Services**.

    [![cerrar el administrador de configuración de Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)
