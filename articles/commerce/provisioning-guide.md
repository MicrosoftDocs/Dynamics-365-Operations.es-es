---
title: Aprovisionar un entorno de evaluación de Dynamics 365 Commerce
description: En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e5ce2002c66a1c36d5647d3c76684b394fc1ff79
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599859"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="c8e65-103">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c8e65-104">En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c8e65-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="c8e65-105">Antes de comenzar, le recomendamos que lea rápidamente este tema para tener una idea de lo que requiere el proceso.</span><span class="sxs-lookup"><span data-stu-id="c8e65-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e65-106">Los entornos de evaluación de Commerce no suelen estar disponibles y se conceden a socios y clientes por solicitud.</span><span class="sxs-lookup"><span data-stu-id="c8e65-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="c8e65-107">Para obtener más información, póngase en contacto con su partner de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e65-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="c8e65-108">Información general</span><span class="sxs-lookup"><span data-stu-id="c8e65-108">Overview</span></span>

<span data-ttu-id="c8e65-109">Para aprovisionar correctamente un entorno de evaluación de Commerce, debe crear un proyecto que tenga un nombre y tipo de producto específicos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="c8e65-110">El entorno y Commerce Scale Unit (CSU) también tienen algunos parámetros específicos que necesita usar posteriormente cuando prevea el aprovisionamiento de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="c8e65-111">Las instrucciones de este tema describen todos los pasos que son necesarios para completar el aprovisionamiento y los parámetros que debe usar.</span><span class="sxs-lookup"><span data-stu-id="c8e65-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="c8e65-112">Tras el aprovisionamiento correcto del entorno de evaluación de Commerce, debe completar algunos pasos posteriores al aprovisionamiento a fin de prepararse para usarlo.</span><span class="sxs-lookup"><span data-stu-id="c8e65-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="c8e65-113">Algunos pasos son opcionales, en función de los aspectos del sistema que desee evaluar.</span><span class="sxs-lookup"><span data-stu-id="c8e65-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="c8e65-114">Siempre puede completar los pasos opcionales más adelante.</span><span class="sxs-lookup"><span data-stu-id="c8e65-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="c8e65-115">Para obtener información sobre cómo configurar su entorno de evaluación de Commerce después de aprovisionarlo, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c8e65-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="c8e65-116">Para obtener información sobre cómo configurar características opcionales para su entorno de evaluación de Commerce, consulte [Configurar características opcionales para un entorno de evaluación de Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="c8e65-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8e65-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c8e65-117">Prerequisites</span></span>

<span data-ttu-id="c8e65-118">Deben cumplirse los siguientes requisitos previos para poder aprovisionar su entorno de evaluación de Commerce:</span><span class="sxs-lookup"><span data-stu-id="c8e65-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="c8e65-119">Tiene acceso al portal de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c8e65-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="c8e65-120">Usted es un socio o cliente de Microsoft Dynamics 365 existente y puede crear un proyecto de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c8e65-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="c8e65-121">Tiene acceso de administrador a su suscripción de Microsoft Azure o está en contacto con un administrador de suscripción que puede ayudarlo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c8e65-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="c8e65-122">Tiene su id. de suscriptor de Azure Active Directory (Azure AD) disponible.</span><span class="sxs-lookup"><span data-stu-id="c8e65-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="c8e65-123">Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo de administración del sistema de comercio electrónico y tiene su id. disponible</span><span class="sxs-lookup"><span data-stu-id="c8e65-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="c8e65-124">Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo moderador de Clasificaciones y revisiones y tiene su id. disponible.</span><span class="sxs-lookup"><span data-stu-id="c8e65-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="c8e65-125">(Este grupo de seguridad puede ser el mismo que el grupo de administración del sistema de comercio electrónico).</span><span class="sxs-lookup"><span data-stu-id="c8e65-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="c8e65-126">Tenga en cuenta que esta lista no es exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="c8e65-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="c8e65-127">Si tiene algún problema, póngase en contacto con su partner de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="c8e65-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="c8e65-128">Aprovisionar su entorno de evaluación de Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="c8e65-129">Estos procedimientos explican cómo aprovisionar un entorno de evaluación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c8e65-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="c8e65-130">Una vez completados correctamente, el entorno de evaluación de Commerce estará listo para la configuración.</span><span class="sxs-lookup"><span data-stu-id="c8e65-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="c8e65-131">Todas las actividades que se describen aquí tienen lugar en el portal de LCS.</span><span class="sxs-lookup"><span data-stu-id="c8e65-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="c8e65-132">Crear un proyecto nuevo</span><span class="sxs-lookup"><span data-stu-id="c8e65-132">Create a new project</span></span>

<span data-ttu-id="c8e65-133">Para crear un proyecto nuevo en LCS, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="c8e65-134">En la página de inicio de LCS, seleccione el signo más (**+**) para crear un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c8e65-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="c8e65-135">En el panel derecho, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c8e65-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="c8e65-136">Si es un partner, seleccione **Migrar, crear soluciones y obtener información sobre**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="c8e65-137">Si es cliente, seleccione **Preventa de cliente potencial**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="c8e65-138">Escriba un nombre, una descripción y un sector.</span><span class="sxs-lookup"><span data-stu-id="c8e65-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="c8e65-139">En el campo **Nombre del producto**, seleccione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c8e65-140">En el campo **Versión del producto**, seleccione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c8e65-141">En el campo **Metodología**, seleccione **Metodología de implementación de Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="c8e65-142">Opcional: puede importar roles y usuarios de un proyecto existente.</span><span class="sxs-lookup"><span data-stu-id="c8e65-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="c8e65-143">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-143">Select **Create**.</span></span> <span data-ttu-id="c8e65-144">Aparece la vista del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c8e65-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="c8e65-145">Agregar el conector de Azure</span><span class="sxs-lookup"><span data-stu-id="c8e65-145">Add the Azure Connector</span></span>

<span data-ttu-id="c8e65-146">Para agregar Azure Connector a su proyecto LCS, siga los pasos en [Completar el proceso de incorporación de Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="c8e65-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="c8e65-147">Implementar el entorno</span><span class="sxs-lookup"><span data-stu-id="c8e65-147">Deploy the environment</span></span>

<span data-ttu-id="c8e65-148">Para implementar el entorno, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e65-149">Es posible que no tenga que completar los pasos 6, 7 u 8, ya que las páginas que tienen una sola opción se omiten.</span><span class="sxs-lookup"><span data-stu-id="c8e65-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="c8e65-150">Cuando está en la vista **Parámetros del entorno**, confirme que el texto **Dynamics 365 Commerce - Demostración (10.0.* x* con Platform update *xx*)\*\* aparece directamente encima del campo **Nombre del entorno**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="c8e65-151">Para obtener detalles, consulte la ilustración que aparece después del paso 8.</span><span class="sxs-lookup"><span data-stu-id="c8e65-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="c8e65-152">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="c8e65-153">Seleccione **Agregar** para agregar un entorno.</span><span class="sxs-lookup"><span data-stu-id="c8e65-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="c8e65-154">En el campo **Versión de la aplicación**, seleccione la versión más actual.</span><span class="sxs-lookup"><span data-stu-id="c8e65-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="c8e65-155">Si tiene una necesidad específica de seleccionar una versión de la aplicación que no sea la versión más actual, no seleccione una versión anterior a **10.0.8**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="c8e65-156">En el campo **Versión de la plataforma**, use la versión de plataforma que se elige automáticamente para la versión de la aplicación que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c8e65-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Seleccionar las versiones de la aplicación y la plataforma](./media/project1.png)

1. <span data-ttu-id="c8e65-158">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-158">Select **Next**.</span></span>
1. <span data-ttu-id="c8e65-159">Seleccione **Demostración** como topología del entorno.</span><span class="sxs-lookup"><span data-stu-id="c8e65-159">Select **Demo** as the environment topology.</span></span>

    ![Seleccionar la topología del entorno 1](./media/project2.png)

1. <span data-ttu-id="c8e65-161">En la página **Implementar entorno**, escriba un nombre de entorno.</span><span class="sxs-lookup"><span data-stu-id="c8e65-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="c8e65-162">Deje la configuración avanzada tal cual.</span><span class="sxs-lookup"><span data-stu-id="c8e65-162">Leave the advanced settings as they are.</span></span>

    ![Página Implementar entorno](./media/project4.png)

1. <span data-ttu-id="c8e65-164">Ajuste el tamaño de la máquina virtual si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c8e65-164">Adjust the VM size as required.</span></span> <span data-ttu-id="c8e65-165">(Recomendamos la referencia de almacén de VM \[SKU\]**D13 v2**).</span><span class="sxs-lookup"><span data-stu-id="c8e65-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="c8e65-166">Revise los términos de precios y licencias y, a continuación, active la casilla para indicar que los acepta.</span><span class="sxs-lookup"><span data-stu-id="c8e65-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="c8e65-167">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-167">Select **Next**.</span></span>
1. <span data-ttu-id="c8e65-168">En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="c8e65-169">Volverá a la vista **Entornos hospedados en la nube** y su entorno debe aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="c8e65-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="c8e65-170">Su entorno solicitado se mostrará como en cola y, a continuación, en implementación.</span><span class="sxs-lookup"><span data-stu-id="c8e65-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="c8e65-171">Los flujos de trabajo del entorno tardarán un tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="c8e65-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="c8e65-172">Por ello, vuelva a comprobarlo después de aproximadamente seis a nueve horas.</span><span class="sxs-lookup"><span data-stu-id="c8e65-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="c8e65-173">Antes de continuar, asegúrese de que el estado del entorno es **Implementado**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="c8e65-174">Inicializar la Commerce Scale Unit (nube)</span><span class="sxs-lookup"><span data-stu-id="c8e65-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="c8e65-175">Para inicializar CSU, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-175">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="c8e65-176">En la vista **Entornos hospedados en la nube**, seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="c8e65-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="c8e65-177">En la vista del entorno a la derecha, seleccione **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="c8e65-178">Aparecerá la vista de detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="c8e65-178">The environment details view appears.</span></span>
1. <span data-ttu-id="c8e65-179">En **Características del entorno**, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="c8e65-180">En la pestaña **Commerce**, seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="c8e65-181">Aparece la vista de parámetros de inicialización de CSU.</span><span class="sxs-lookup"><span data-stu-id="c8e65-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="c8e65-182">En el campo **Región**, seleccione la región que es la misma o cercana a la región en la que implementó el entorno.</span><span class="sxs-lookup"><span data-stu-id="c8e65-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="c8e65-183">Deje el campo **Versión** tal cual.</span><span class="sxs-lookup"><span data-stu-id="c8e65-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="c8e65-184">Seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="c8e65-185">En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="c8e65-186">La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Commerce** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c8e65-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="c8e65-187">Su CSU ha estado en cola para aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="c8e65-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="c8e65-188">Antes de continuar, asegúrese de que el estado del CSU es **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="c8e65-189">La inicialización dura aproximadamente de dos a cinco horas.</span><span class="sxs-lookup"><span data-stu-id="c8e65-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="c8e65-190">Si no puede encontrar el vínculo **Administrar** en la vista de detalles del entorno, póngase en contacto con su persona de contacto de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="c8e65-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="c8e65-191">Inicializar comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c8e65-191">Initialize e-Commerce</span></span>

<span data-ttu-id="c8e65-192">Para inicializar la plataforma de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-192">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="c8e65-193">En la pestaña **Comercio electrónico**, revise el consentimiento de evaluación y, a continuación, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-193">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="c8e65-194">En el campo **Nombre de entorno de comercio electrónico**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="c8e65-194">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="c8e65-195">Tenga en cuenta que este nombre aparecerá en algunas de las direcciones URL que apuntan a su instancia de la plataforma de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-195">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="c8e65-196">En el campo **Nombre de Commerce Scale Unit**, seleccione su CSU en la lista.</span><span class="sxs-lookup"><span data-stu-id="c8e65-196">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="c8e65-197">(La lista debe tener una sola opción).</span><span class="sxs-lookup"><span data-stu-id="c8e65-197">(The list should have only one option.)</span></span>

    <span data-ttu-id="c8e65-198">El campo **Geografía de comercio electrónico** se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c8e65-198">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="c8e65-199">Seleccione **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="c8e65-199">Select **Next** to continue.</span></span>
1. <span data-ttu-id="c8e65-200">En el campo **Nombres de hosts admitidos**, especifique cualquier dominio válido, como `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="c8e65-200">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="c8e65-201">En el campo **Grupo de seguridad de AAD para administrador del sistema**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8e65-201">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c8e65-202">Seleccione un grupo de seguridad correcto en la lista.</span><span class="sxs-lookup"><span data-stu-id="c8e65-202">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="c8e65-203">En el campo **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8e65-203">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c8e65-204">Seleccione un grupo de seguridad correcto en la lista.</span><span class="sxs-lookup"><span data-stu-id="c8e65-204">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="c8e65-205">Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-205">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="c8e65-206">Seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-206">Select **Initialize**.</span></span> <span data-ttu-id="c8e65-207">La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Comercio electrónico** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c8e65-207">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="c8e65-208">Comienza la inicialización del comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-208">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="c8e65-209">Antes de continuar, espere hasta que el estado de inicialización de comercio electrónico sea **Inicialización correcta**.</span><span class="sxs-lookup"><span data-stu-id="c8e65-209">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="c8e65-210">En **Vínculos**, en la esquina inferior derecha, tome nota de las direcciones URL de los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="c8e65-210">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="c8e65-211">**Sitio de comercio electrónico**: el vínculo a la raíz de su sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-211">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="c8e65-212">**Generador de sitios de Commerce**: el vínculo a la herramienta de administración del sitio.</span><span class="sxs-lookup"><span data-stu-id="c8e65-212">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8e65-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c8e65-213">Next steps</span></span>

<span data-ttu-id="c8e65-214">Para continuar con el proceso de aprovisionamiento y configurar su entorno de evaluación de Commerce, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c8e65-214">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8e65-215">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c8e65-215">Additional resources</span></span>

[<span data-ttu-id="c8e65-216">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-216">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="c8e65-217">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-217">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="c8e65-218">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-218">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="c8e65-219">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-219">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="c8e65-220">Preguntas más frecuentes sobre el entorno de evaluación Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-220">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="c8e65-221">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="c8e65-221">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="c8e65-222">Commerce Scale Unit (nube)</span><span class="sxs-lookup"><span data-stu-id="c8e65-222">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="c8e65-223">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c8e65-223">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="c8e65-224">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c8e65-224">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
