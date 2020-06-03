---
title: Compartir configuraciones de ER en RCS/repositorio global con organizaciones externas
description: Este tema explica cómo compartir configuraciones de informes electrónicos (ER) en los Regulatory Configuration Service (RCS) de Microsoft/repositorio global directamente con organizaciones externas.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 04c46824123906eccbfff18a03974c8043729e0a
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371266"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="e87e2-103">Compartir configuraciones de informes electrónicos (ER) en el repositorio global de Regulatory Configuration Service (RCS) con organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="e87e2-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e87e2-104">Puede usar los Regulatory Configuration Services (RCS) de Microsoft para compartir configuraciones de informes electrónicos (ER) y luego publicarlas en organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="e87e2-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="e87e2-105">Los siguientes procedimientos explican cómo un usuario de RCS puede compartir una versión de una configuración de ER que se ha configurado en una instancia de RCS con una organización externa.</span><span class="sxs-lookup"><span data-stu-id="e87e2-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="e87e2-106">Para poder completar estos procedimientos, primero debe completar los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="e87e2-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="e87e2-107">Acceda a una instancia RCS.</span><span class="sxs-lookup"><span data-stu-id="e87e2-107">Access an RCS instance.</span></span>
- <span data-ttu-id="e87e2-108">Cree un proveedor de configuración activo.</span><span class="sxs-lookup"><span data-stu-id="e87e2-108">Create an active configuration provider.</span></span> <span data-ttu-id="e87e2-109">Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e87e2-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="e87e2-110">Cree y cargue una nueva versión de una configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="e87e2-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="e87e2-111">Para obtener más información, consulte [Crear y cargar una nueva versión de una configuración de informes electrónicos (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="e87e2-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="e87e2-112">También debe asegurarse de que se aprovisione un entorno RCS para su empresa.</span><span class="sxs-lookup"><span data-stu-id="e87e2-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="e87e2-113">En una aplicación de Finance and Operations, vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="e87e2-114">Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: configuración externa** y luego siga las instrucciones para aprovisionar uno.</span><span class="sxs-lookup"><span data-stu-id="e87e2-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="e87e2-115">Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder a él seleccionando la opción de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e87e2-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="e87e2-116">Verificar la configuración que se desea compartir</span><span class="sxs-lookup"><span data-stu-id="e87e2-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="e87e2-117">Siga estos pasos para verificar que la configuración que desea compartir ya se haya cargado en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="e87e2-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="e87e2-118">En el espacio de trabajo **Informes electrónicos**, seleccione **Repositorios** para su proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="e87e2-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Proveedores de configuración](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="e87e2-120">Seleccione **Repositorio global** \> **Abierto**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="e87e2-121">Busque la configuración que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="e87e2-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="e87e2-122">Puede utilizar el campo de filtro para precisar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e87e2-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="e87e2-123">Si no puede encontrar la configuración en el repositorio global, siga los pasos de [Crear y cargar una nueva versión de una configuración de informes electrónicos (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="e87e2-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="e87e2-124">Compartir configuraciones de ER con organizaciones externas</span><span class="sxs-lookup"><span data-stu-id="e87e2-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="e87e2-125">Después de crear una configuración con su proveedor de configuración, puede compartirla directamente con organizaciones externas utilizando la ficha desplegable **Compartido con** en la página **Repositorio de configuración global**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="e87e2-126">En el espacio de trabajo **Informes electrónicos**, seleccione **Repositorios** para su proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="e87e2-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="e87e2-127">Seleccione **Repositorio global** \> **Abierto**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="e87e2-128">Seleccione la configuración que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="e87e2-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="e87e2-129">En la ficha desplegable , **Compartido con**, seleccione **Organización**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Ficha desplegable Compartido con](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="e87e2-131">En el cuadro de diálogo, introduzca el nombre de dominio para la organización externa y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e87e2-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Cuadro de diálogo Compartir versión de configuración con organización externa](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="e87e2-133">La configuración se comparte con la organización externa y está disponible para esa organización en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="e87e2-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="e87e2-134">A partir de ahí, se puede importar a la instancia de RCS de la organización o a sus instancias de las aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e87e2-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

![Configuración compartida con una organización externa](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_test.com)

6. <span data-ttu-id="e87e2-136">Para dejar de compartir una configuración que se ha compartido previamente con una organización externa, seleccione la configuración y haga clic en **Dejar de compartir** y luego seleccione **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="e87e2-136">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>
