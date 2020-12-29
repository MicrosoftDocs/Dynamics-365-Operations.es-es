---
title: Aprovisionar un entorno de evaluación de Dynamics 365 Commerce
description: En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 11/05/2020
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
ms.openlocfilehash: b54216a565c264dfcfe821581fee9df7b5e22323
ms.sourcegitcommit: 715508547f9a71a89a138190e8540686556c753d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "4415690"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="8062f-103">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8062f-104">En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8062f-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="8062f-105">Antes de comenzar, le recomendamos que lea rápidamente este tema para tener una idea de lo que requiere el proceso.</span><span class="sxs-lookup"><span data-stu-id="8062f-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="8062f-106">Los entornos de evaluación de Commerce no suelen estar disponibles y se conceden a socios y clientes por solicitud.</span><span class="sxs-lookup"><span data-stu-id="8062f-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="8062f-107">Para obtener más información, póngase en contacto con su partner de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8062f-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="8062f-108">Información general</span><span class="sxs-lookup"><span data-stu-id="8062f-108">Overview</span></span>

<span data-ttu-id="8062f-109">Para aprovisionar correctamente un entorno de evaluación de Commerce, debe crear un proyecto que tenga un nombre y tipo de producto específicos.</span><span class="sxs-lookup"><span data-stu-id="8062f-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="8062f-110">El entorno y Commerce Scale Unit (CSU) también tienen algunos parámetros específicos que necesita usar posteriormente cuando prevea el aprovisionamiento de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8062f-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="8062f-111">Las instrucciones de este tema describen todos los pasos que son necesarios para completar el aprovisionamiento y los parámetros que debe usar.</span><span class="sxs-lookup"><span data-stu-id="8062f-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="8062f-112">Tras el aprovisionamiento correcto del entorno de evaluación de Commerce, debe completar algunos pasos posteriores al aprovisionamiento a fin de prepararse para usarlo.</span><span class="sxs-lookup"><span data-stu-id="8062f-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="8062f-113">Algunos pasos son opcionales, en función de los aspectos del sistema que desee evaluar.</span><span class="sxs-lookup"><span data-stu-id="8062f-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="8062f-114">Siempre puede completar los pasos opcionales más adelante.</span><span class="sxs-lookup"><span data-stu-id="8062f-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="8062f-115">Para obtener información sobre cómo configurar su entorno de evaluación de Commerce después de aprovisionarlo, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8062f-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="8062f-116">Para obtener información sobre cómo configurar características opcionales para su entorno de evaluación de Commerce, consulte [Configurar características opcionales para un entorno de evaluación de Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="8062f-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8062f-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8062f-117">Prerequisites</span></span>

<span data-ttu-id="8062f-118">Deben cumplirse los siguientes requisitos previos para poder aprovisionar su entorno de evaluación de Commerce:</span><span class="sxs-lookup"><span data-stu-id="8062f-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="8062f-119">Se le ha incorporado al programa de evaluación y se le ha otorgado la capacidad para un entorno de evaluación.</span><span class="sxs-lookup"><span data-stu-id="8062f-119">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="8062f-120">Tiene acceso al portal de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8062f-120">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="8062f-121">Usted es un socio o cliente de Microsoft Dynamics 365 existente y puede crear un proyecto de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8062f-121">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="8062f-122">Tiene acceso de administrador a su suscripción de Microsoft Azure o está en contacto con un administrador de suscripción que puede ayudarlo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8062f-122">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="8062f-123">Tiene su id. de suscriptor de Azure Active Directory (Azure AD) disponible.</span><span class="sxs-lookup"><span data-stu-id="8062f-123">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="8062f-124">Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo de administración del sistema de comercio electrónico y tiene su id. disponible</span><span class="sxs-lookup"><span data-stu-id="8062f-124">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="8062f-125">Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo moderador de Clasificaciones y revisiones y tiene su id. disponible.</span><span class="sxs-lookup"><span data-stu-id="8062f-125">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="8062f-126">(Este grupo de seguridad puede ser el mismo que el grupo de administración del sistema de comercio electrónico).</span><span class="sxs-lookup"><span data-stu-id="8062f-126">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="8062f-127">Tenga en cuenta que esta lista no es exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="8062f-127">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="8062f-128">Si tiene algún problema, póngase en contacto con su partner de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="8062f-128">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="8062f-129">Aprovisionar su entorno de evaluación de Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-129">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="8062f-130">Estos procedimientos explican cómo aprovisionar un entorno de evaluación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8062f-130">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="8062f-131">Una vez completados correctamente, el entorno de evaluación de Commerce estará listo para la configuración.</span><span class="sxs-lookup"><span data-stu-id="8062f-131">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="8062f-132">Todas las actividades que se describen aquí tienen lugar en el portal de LCS.</span><span class="sxs-lookup"><span data-stu-id="8062f-132">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="8062f-133">Crear un proyecto nuevo</span><span class="sxs-lookup"><span data-stu-id="8062f-133">Create a new project</span></span>

<span data-ttu-id="8062f-134">Para crear un proyecto nuevo en LCS, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8062f-134">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="8062f-135">En la página de inicio de LCS, seleccione el signo más (**+**) para crear un proyecto.</span><span class="sxs-lookup"><span data-stu-id="8062f-135">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="8062f-136">En el panel derecho, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8062f-136">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="8062f-137">Si es un partner, seleccione **Migrar, crear soluciones y obtener información sobre**.</span><span class="sxs-lookup"><span data-stu-id="8062f-137">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="8062f-138">Si es cliente, seleccione **Preventa de cliente potencial**.</span><span class="sxs-lookup"><span data-stu-id="8062f-138">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="8062f-139">Escriba un nombre, una descripción y un sector.</span><span class="sxs-lookup"><span data-stu-id="8062f-139">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="8062f-140">En el campo **Nombre del producto**, seleccione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="8062f-140">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="8062f-141">En el campo **Versión del producto**, seleccione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="8062f-141">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="8062f-142">En el campo **Metodología**, seleccione **Metodología de implementación de Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="8062f-142">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="8062f-143">Opcional: puede importar roles y usuarios de un proyecto existente.</span><span class="sxs-lookup"><span data-stu-id="8062f-143">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="8062f-144">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="8062f-144">Select **Create**.</span></span> <span data-ttu-id="8062f-145">Aparece la vista del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8062f-145">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="8062f-146">Agregar el conector de Azure</span><span class="sxs-lookup"><span data-stu-id="8062f-146">Add the Azure Connector</span></span>

<span data-ttu-id="8062f-147">Para agregar Azure Connector a su proyecto LCS, siga los pasos en [Completar el proceso de incorporación de Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="8062f-147">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="8062f-148">Implementar el entorno</span><span class="sxs-lookup"><span data-stu-id="8062f-148">Deploy the environment</span></span>

<span data-ttu-id="8062f-149">Para implementar el entorno, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8062f-149">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="8062f-150">Es posible que no tenga que completar los pasos 6, 7 u 8, ya que las páginas que tienen una sola opción se omiten.</span><span class="sxs-lookup"><span data-stu-id="8062f-150">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="8062f-151">Cuando está en la vista **Parámetros del entorno**, confirme que el texto **Dynamics 365 Commerce - Demostración (10.0.* x* con Platform update *xx*)\*\* aparece directamente encima del campo **Nombre del entorno**.</span><span class="sxs-lookup"><span data-stu-id="8062f-151">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="8062f-152">Para obtener detalles, consulte la ilustración que aparece después del paso 8.</span><span class="sxs-lookup"><span data-stu-id="8062f-152">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="8062f-153">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="8062f-153">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="8062f-154">Seleccione **Agregar** para agregar un entorno.</span><span class="sxs-lookup"><span data-stu-id="8062f-154">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="8062f-155">En el campo **Versión de la aplicación**, seleccione la versión más actual.</span><span class="sxs-lookup"><span data-stu-id="8062f-155">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="8062f-156">Si tiene una necesidad específica de seleccionar una versión de la aplicación que no sea la versión más actual, no seleccione una versión anterior a **10.0.14**.</span><span class="sxs-lookup"><span data-stu-id="8062f-156">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="8062f-157">En el campo **Versión de la plataforma**, use la versión de plataforma que se elige automáticamente para la versión de la aplicación que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8062f-157">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Seleccionar las versiones de la aplicación y la plataforma](./media/project1.png)

1. <span data-ttu-id="8062f-159">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8062f-159">Select **Next**.</span></span>
1. <span data-ttu-id="8062f-160">Seleccione **Demostración** como topología del entorno.</span><span class="sxs-lookup"><span data-stu-id="8062f-160">Select **Demo** as the environment topology.</span></span>

    ![Seleccionar la topología del entorno 1](./media/project2.png)

1. <span data-ttu-id="8062f-162">En la página **Implementar entorno**, escriba un nombre de entorno.</span><span class="sxs-lookup"><span data-stu-id="8062f-162">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="8062f-163">Deje la configuración avanzada tal cual.</span><span class="sxs-lookup"><span data-stu-id="8062f-163">Leave the advanced settings as they are.</span></span>

    ![Página Implementar entorno](./media/project4.png)

1. <span data-ttu-id="8062f-165">Ajuste el tamaño de la máquina virtual si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8062f-165">Adjust the VM size as required.</span></span> <span data-ttu-id="8062f-166">(Recomendamos la referencia de almacén de VM \[SKU\]**D13 v2**).</span><span class="sxs-lookup"><span data-stu-id="8062f-166">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="8062f-167">Revise los términos de precios y licencias y, a continuación, active la casilla para indicar que los acepta.</span><span class="sxs-lookup"><span data-stu-id="8062f-167">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="8062f-168">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8062f-168">Select **Next**.</span></span>
1. <span data-ttu-id="8062f-169">En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="8062f-169">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="8062f-170">Volverá a la vista **Entornos hospedados en la nube** y su entorno debe aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="8062f-170">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="8062f-171">Su entorno solicitado se mostrará como en cola y, a continuación, en implementación.</span><span class="sxs-lookup"><span data-stu-id="8062f-171">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="8062f-172">Los flujos de trabajo del entorno tardarán un tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="8062f-172">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="8062f-173">Por ello, vuelva a comprobarlo después de aproximadamente seis a nueve horas.</span><span class="sxs-lookup"><span data-stu-id="8062f-173">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="8062f-174">Antes de continuar, asegúrese de que el estado del entorno es **Implementado**.</span><span class="sxs-lookup"><span data-stu-id="8062f-174">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="8062f-175">Inicializar la Commerce Scale Unit (nube)</span><span class="sxs-lookup"><span data-stu-id="8062f-175">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="8062f-176">Para inicializar CSU, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8062f-176">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="8062f-177">En la vista **Entornos hospedados en la nube**, seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="8062f-177">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="8062f-178">En la vista del entorno a la derecha, seleccione **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="8062f-178">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="8062f-179">Aparecerá la vista de detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="8062f-179">The environment details view appears.</span></span>
1. <span data-ttu-id="8062f-180">En **Características del entorno**, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="8062f-180">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="8062f-181">En la pestaña **Commerce**, seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="8062f-181">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="8062f-182">Aparece la vista de parámetros de inicialización de CSU.</span><span class="sxs-lookup"><span data-stu-id="8062f-182">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="8062f-183">En el campo **Región**, seleccione la región que es la misma o cercana a la región en la que implementó el entorno.</span><span class="sxs-lookup"><span data-stu-id="8062f-183">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="8062f-184">Deje el campo **Versión** tal cual.</span><span class="sxs-lookup"><span data-stu-id="8062f-184">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="8062f-185">Seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="8062f-185">Select **Initialize**.</span></span>
1. <span data-ttu-id="8062f-186">En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8062f-186">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="8062f-187">La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Commerce** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8062f-187">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="8062f-188">Su CSU ha estado en cola para aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8062f-188">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="8062f-189">Antes de continuar, asegúrese de que el estado del CSU es **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="8062f-189">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="8062f-190">La inicialización dura aproximadamente de dos a cinco horas.</span><span class="sxs-lookup"><span data-stu-id="8062f-190">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="8062f-191">Si no puede encontrar el vínculo **Administrar** en la vista de detalles del entorno, póngase en contacto con su persona de contacto de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="8062f-191">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="8062f-192">Inicializar comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="8062f-192">Initialize e-Commerce</span></span>

<span data-ttu-id="8062f-193">Para inicializar la plataforma de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8062f-193">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8062f-194">En la pestaña **Comercio electrónico**, revise el consentimiento de evaluación y, a continuación, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="8062f-194">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="8062f-195">En el campo **Nombre de entorno de comercio electrónico**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="8062f-195">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="8062f-196">Tenga en cuenta que este nombre aparecerá en algunas de las direcciones URL que apuntan a su instancia de la plataforma de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8062f-196">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="8062f-197">En el campo **Nombre de Commerce Scale Unit**, seleccione su CSU en la lista.</span><span class="sxs-lookup"><span data-stu-id="8062f-197">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="8062f-198">(La lista debe tener una sola opción).</span><span class="sxs-lookup"><span data-stu-id="8062f-198">(The list should have only one option.)</span></span>

    <span data-ttu-id="8062f-199">El campo **Geografía de comercio electrónico** se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8062f-199">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="8062f-200">Seleccione **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="8062f-200">Select **Next** to continue.</span></span>
1. <span data-ttu-id="8062f-201">En el campo **Nombres de hosts admitidos**, especifique cualquier dominio válido, como `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="8062f-201">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="8062f-202">En el campo **Grupo de seguridad de AAD para administrador del sistema**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8062f-202">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="8062f-203">Seleccione un grupo de seguridad correcto en la lista.</span><span class="sxs-lookup"><span data-stu-id="8062f-203">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="8062f-204">En el campo **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8062f-204">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="8062f-205">Seleccione un grupo de seguridad correcto en la lista.</span><span class="sxs-lookup"><span data-stu-id="8062f-205">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="8062f-206">Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8062f-206">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="8062f-207">Seleccione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="8062f-207">Select **Initialize**.</span></span> <span data-ttu-id="8062f-208">La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Comercio electrónico** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8062f-208">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="8062f-209">Comienza la inicialización del comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8062f-209">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="8062f-210">Antes de continuar, espere hasta que el estado de inicialización de comercio electrónico sea **Inicialización correcta**.</span><span class="sxs-lookup"><span data-stu-id="8062f-210">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="8062f-211">En **Vínculos**, en la esquina inferior derecha, tome nota de las direcciones URL de los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="8062f-211">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="8062f-212">**Sitio de comercio electrónico**: el vínculo a la raíz de su sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8062f-212">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="8062f-213">**Generador de sitios de Commerce**: el vínculo a la herramienta de administración del sitio.</span><span class="sxs-lookup"><span data-stu-id="8062f-213">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8062f-214">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8062f-214">Next steps</span></span>

<span data-ttu-id="8062f-215">Para continuar con el proceso de aprovisionamiento y configurar su entorno de evaluación de Commerce, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8062f-215">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8062f-216">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8062f-216">Additional resources</span></span>

[<span data-ttu-id="8062f-217">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-217">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="8062f-218">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-218">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="8062f-219">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-219">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="8062f-220">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-220">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="8062f-221">Preguntas más frecuentes sobre el entorno de evaluación Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-221">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="8062f-222">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="8062f-222">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="8062f-223">Commerce Scale Unit (nube)</span><span class="sxs-lookup"><span data-stu-id="8062f-223">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="8062f-224">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8062f-224">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="8062f-225">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8062f-225">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
