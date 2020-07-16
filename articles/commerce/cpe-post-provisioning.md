---
title: Configurar un entorno de vista previa de Dynamics 365 Commerce
description: Este tema explica cómo configurar una vista previa del entorno de Microsoft Dynamics 365 Commerce tras aprovisionarse.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ad05996eaabd3965308370649a27b8bc3080c7ce
ms.sourcegitcommit: f72e90dccc80718e99cab2752eaf8931dcbb915e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "3534076"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="f0286-103">Configurar un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f0286-104">Este tema explica cómo configurar una vista previa del entorno de Microsoft Dynamics 365 Commerce tras aprovisionarse.</span><span class="sxs-lookup"><span data-stu-id="f0286-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="f0286-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f0286-105">Overview</span></span>

<span data-ttu-id="f0286-106">Complete los procedimientos de este tema solo después de que se haya aprovisionado su entorno de vista previa de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0286-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="f0286-107">Para obtener información sobre cómo aprovisionar su entorno de vista previa de Commerce, vea [Provisión de un entorno de vista previa de Commerce ](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="f0286-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="f0286-108">Después de que su entorno de vista previa de Commerce se haya aprovisionado de principio a fin, se deben completar pasos de configuración posteriores al aprovisionamiento antes de que pueda comenzar a evaluar el entorno.</span><span class="sxs-lookup"><span data-stu-id="f0286-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="f0286-109">Para completar estos pasos, debe usar Microsoft Dynamics Lifecycle Services (LCS) y Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0286-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f0286-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f0286-110">Before you start</span></span>

1. <span data-ttu-id="f0286-111">Inicie sesión en el [portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f0286-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="f0286-112">Vaya a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0286-112">Go to your project.</span></span>
1. <span data-ttu-id="f0286-113">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="f0286-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f0286-114">Seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="f0286-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="f0286-115">En la información del entorno, a la derecha, seleccione **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="f0286-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="f0286-116">Seleccione **Iniciar sesión** para abrir un menú y elija **Iniciar sesión en el entorno**.</span><span class="sxs-lookup"><span data-stu-id="f0286-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="f0286-117">Asegúrese de que la entidad jurídica **USRT** está seleccionada en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="f0286-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="f0286-118">Configurar el punto de venta en LCS</span><span class="sxs-lookup"><span data-stu-id="f0286-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="f0286-119">Asociar un trabajador con su identidad</span><span class="sxs-lookup"><span data-stu-id="f0286-119">Associate a worker with your identity</span></span>

<span data-ttu-id="f0286-120">Para asociar un trabajador con su identidad en LCS, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0286-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="f0286-121">Use el menú de la izquierda para ir a **Módulos \> Retail y Commerce \> Empleados \> Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="f0286-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="f0286-122">En la lista, busque y seleccione el registro siguiente: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="f0286-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="f0286-123">En el panel de acciones, haga clic en **Retail**.</span><span class="sxs-lookup"><span data-stu-id="f0286-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="f0286-124">Seleccione **Asociar identidad existente**.</span><span class="sxs-lookup"><span data-stu-id="f0286-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="f0286-125">En el campo **Correo electrónico** a la derecha de **Buscar mediante correo electrónico**, escriba su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f0286-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="f0286-126">Selección **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-126">Select **Search**.</span></span>
1. <span data-ttu-id="f0286-127">Seleccione el registro con su nombre.</span><span class="sxs-lookup"><span data-stu-id="f0286-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="f0286-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-128">Select **OK**.</span></span>
1. <span data-ttu-id="f0286-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="f0286-130">Activar PDV en la nube</span><span class="sxs-lookup"><span data-stu-id="f0286-130">Activate Cloud POS</span></span>

<span data-ttu-id="f0286-131">Para activar Cloud POS en LCS, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0286-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="f0286-132">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="f0286-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f0286-133">Seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="f0286-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="f0286-134">En la información del entorno, a la derecha, seleccione **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="f0286-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="f0286-135">Seleccione **Iniciar sesión** para abrir un menú y luego seleccione **Iniciar sesión en el punto de venta en la nube** para abrir el punto de venta (POS).</span><span class="sxs-lookup"><span data-stu-id="f0286-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="f0286-136">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f0286-136">Select **Next**.</span></span>
1. <span data-ttu-id="f0286-137">Inicie sesión utilizando su cuenta de Microsoft Azure Active Directory ( Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f0286-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="f0286-138">En **Nombre de tienda**, elija **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="f0286-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="f0286-139">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f0286-139">Select **Next**.</span></span>
1. <span data-ttu-id="f0286-140">En **Caja registradora y dispositivo**, seleccione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="f0286-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="f0286-141">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-141">Select **Activate**.</span></span> <span data-ttu-id="f0286-142">Ha cerrado sesión y ha sido llevado a la página de inicio de sesión de POS.</span><span class="sxs-lookup"><span data-stu-id="f0286-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="f0286-143">Ahora puede iniciar sesión en la experiencia de Cloud PDV mediante el id. de operador **000713** y contraseña **123**.</span><span class="sxs-lookup"><span data-stu-id="f0286-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="f0286-144">Configurar su sitio en Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-144">Set up your site in Commerce</span></span>

<span data-ttu-id="f0286-145">Para comenzar a configurar su sitio de vista previa en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0286-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f0286-146">Inicie sesión en la herramienta de administración del sitio utilizando la URL de la que tomó nota cuando inició el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico ](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="f0286-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="f0286-147">Seleccione el sitio de **Fabrikam** para abrir el cuadro de diálogo de configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="f0286-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="f0286-148">Seleccione el dominio que ingresó cuando inicializó el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="f0286-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="f0286-149">Como canal predeterminado seleccione **Tienda en línea extendida de Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="f0286-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="f0286-150">(Asegúrese de seleccionar la tienda en línea **extendida**).</span><span class="sxs-lookup"><span data-stu-id="f0286-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="f0286-151">Seleccione **es-es** como idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f0286-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="f0286-152">Deje el valor del campo **Ruta** tal cual está.</span><span class="sxs-lookup"><span data-stu-id="f0286-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="f0286-153">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-153">Select **OK**.</span></span> <span data-ttu-id="f0286-154">Aparece la lista de páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="f0286-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="f0286-155">Habilitar trabajos</span><span class="sxs-lookup"><span data-stu-id="f0286-155">Enable jobs</span></span>

<span data-ttu-id="f0286-156">Para activar la gestión de trabajos en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0286-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f0286-157">Inicie sesión en el entorno (sede).</span><span class="sxs-lookup"><span data-stu-id="f0286-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="f0286-158">Use el menú de la izquierda, para ir a **Retail y Commerce \> Consultas e informes \> Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="f0286-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="f0286-159">Los pasos restantes de este procedimiento deben completarse para cada uno de los siguientes trabajos:</span><span class="sxs-lookup"><span data-stu-id="f0286-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="f0286-160">Procesar notificación por correo electrónico de pedido comercial</span><span class="sxs-lookup"><span data-stu-id="f0286-160">Process retail order email notification</span></span>
    * <span data-ttu-id="f0286-161">Disponibilidad del producto</span><span class="sxs-lookup"><span data-stu-id="f0286-161">Product availability</span></span>
    * <span data-ttu-id="f0286-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="f0286-162">P-0001</span></span>
    * <span data-ttu-id="f0286-163">Trabajo de sincronización de pedidos</span><span class="sxs-lookup"><span data-stu-id="f0286-163">Synchronize orders job</span></span>

1. <span data-ttu-id="f0286-164">Use el filtro rápido para buscar el trabajo por su nombre.</span><span class="sxs-lookup"><span data-stu-id="f0286-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="f0286-165">Si el estado del trabajo **Retenido**, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f0286-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="f0286-166">Seleccione el registro.</span><span class="sxs-lookup"><span data-stu-id="f0286-166">Select the record.</span></span>
    1. <span data-ttu-id="f0286-167">En el panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="f0286-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="f0286-168">Seleccione **Esperando** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="f0286-169">Ejecutar sincronización de datos completa</span><span class="sxs-lookup"><span data-stu-id="f0286-169">Run full data synchronization</span></span>

<span data-ttu-id="f0286-170">Para ejecutar la sincronización de datos completa en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0286-170">To run full data synchronization in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f0286-171">Use el menú de la izquierda, para ir a **Módulos \> Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canales**.</span><span class="sxs-lookup"><span data-stu-id="f0286-171">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="f0286-172">El canal **Predeterminado** está seleccionado en la lista de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="f0286-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="f0286-173">Seleccione el otro canal disponible.</span><span class="sxs-lookup"><span data-stu-id="f0286-173">Select the other available channel.</span></span> <span data-ttu-id="f0286-174">Este canal se llama **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="f0286-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="f0286-175">En el panel de acciones, seleccione **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="f0286-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="f0286-176">Introduzca **9999** como la programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="f0286-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="f0286-177">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-177">Select **OK**.</span></span>
1. <span data-ttu-id="f0286-178">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0286-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="f0286-179">Probar la información de la tarjeta de crédito para realizar compras de prueba</span><span class="sxs-lookup"><span data-stu-id="f0286-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="f0286-180">Para realizar transacciones de prueba en el sitio, puede usar esta información de la tarjeta de crédito de prueba:</span><span class="sxs-lookup"><span data-stu-id="f0286-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="f0286-181">**Número de tarjeta:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="f0286-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="f0286-182">**Fecha de vencimiento:** 10/20</span><span class="sxs-lookup"><span data-stu-id="f0286-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="f0286-183">**Código de seguridad de la tarjeta (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="f0286-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0286-184">Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.</span><span class="sxs-lookup"><span data-stu-id="f0286-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0286-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f0286-185">Next steps</span></span>

<span data-ttu-id="f0286-186">Después de completar los pasos de aprovisionamiento y configuración, estará listo para evaluar su entorno de vista previa.</span><span class="sxs-lookup"><span data-stu-id="f0286-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="f0286-187">Use la URL de la herramienta de administración del sitio de Commerce para acceder a la experiencia de creación.</span><span class="sxs-lookup"><span data-stu-id="f0286-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="f0286-188">Use la URL del sitio de Commerce para ir la experiencia del sitio de cliente minorista.</span><span class="sxs-lookup"><span data-stu-id="f0286-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="f0286-189">Para configurar características opcionales para su entorno de vista previa de Commerce, consulte [Configurar características opcionales para un entorno de vista previa de Commerce ](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="f0286-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0286-190">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f0286-190">Additional resources</span></span>

[<span data-ttu-id="f0286-191">Información general del entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="f0286-192">Aprovisionar un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="f0286-193">Configurar características opcionales para un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="f0286-194">Preguntas frecuentes sobre el entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="f0286-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="f0286-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="f0286-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="f0286-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="f0286-197">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f0286-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="f0286-198">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f0286-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
