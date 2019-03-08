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
ms.openlocfilehash: 166d419f16866f699b96013222ce8da147a5ec21
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315139"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="fcb2d-103">Configurar SQL Server Reporting Services para implementaciones locales</span><span class="sxs-lookup"><span data-stu-id="fcb2d-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fcb2d-104">Siga los pasos de este tema para configurar SQL Server Reporting Services (SSRS) para una implementación de Microsoft Dynamics 365 for Finance and Operations (on-premises).</span><span class="sxs-lookup"><span data-stu-id="fcb2d-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="fcb2d-105">Abra la aplicación de administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="fcb2d-106">Deje el valor predeterminado **Nombre del servidor**, que debe ser el nombre del equipo actual y la **Instancia del servidor de informes**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="fcb2d-107">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-107">Click **Connect**.</span></span>

    <span data-ttu-id="fcb2d-108">[![Administrador de configuración de Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="fcb2d-109">Haga clic en la pestaña **Cuenta de servicio** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-110">[![Pestaña Cuenta de servicio](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="fcb2d-111">Haga clic en la pestaña **URL de servicio Web** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-112">[![Pestaña URL de servicio web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="fcb2d-113">Haga clic en la pestaña **Base de datos** y compruebe que **Nombre de la base de datos** y **Valores de credenciales** coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcb2d-114">Necesitará crear una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-114">You will need to create a new database.</span></span> <span data-ttu-id="fcb2d-115">Para ello, haga clic en **Cambiar base de datos** y compruebe que el nuevo nombre de la base de datos sea: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="fcb2d-116">[![Pestaña base de datos](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="fcb2d-117">Haga clic en la pestaña **URL de portal Web** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcb2d-118">Debe hacer clic en **Aplicar** para crear y configurar correctamente el portal.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="fcb2d-119">[![ficha de url de portal Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="fcb2d-120">Tras configurar el portal, la pestaña **Portal Web** coincidirá el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-121">[![ficha de portal Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="fcb2d-122">Haga clic en la dirección URL de informes para ver el portal Web de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="fcb2d-123">Cuando esté en el portal, cree una nueva carpeta denominada **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="fcb2d-124">[![carpeta dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="fcb2d-125">En **Administrador de configuración de Reporting Services**, haga clic en la pestaña **Configuración de correo electrónico** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-126">[![pestaña de configuración de correo electrónico](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="fcb2d-127">Haga clic en la pestaña **Cuenta de ejecución** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-128">[![Pestaña Cuenta de ejecución](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="fcb2d-129">No cambie la configuración predeterminada en la pestaña **Claves de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="fcb2d-130">[![pestaña Claves de cifrado](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="fcb2d-131">Haga clic en la pestaña **Configuración de suscripción** y compruebe que los valores coincidan con el siguiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="fcb2d-132">[![pestaña de configuración de suscripción](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="fcb2d-133">No cambie la configuración predeterminada en la pestaña **Escala de implementación**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="fcb2d-134">[![pestaña de escala de implementación](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="fcb2d-135">No cambie la configuración predeterminada en la pestaña **Integración de Power BI**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="fcb2d-136">[![pestaña Integración de Power BI](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="fcb2d-137">Haga clic en **Salir** para cerrar el **administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="fcb2d-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="fcb2d-138">[![cerrar el administrador de configuración de Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="fcb2d-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
