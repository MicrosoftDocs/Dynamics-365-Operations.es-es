---
title: Configurar un entorno de evaluación de Dynamics 365 Commerce
description: Este tema explica cómo configurar un entorno de evaluación de Microsoft Dynamics 365 Commerce tras aprovisionarlo.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e80830a1cb0864c7eef19857b91e36ad27cdef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795868"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="8ee8f-103">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8ee8f-104">Este tema explica cómo configurar un entorno de evaluación de Microsoft Dynamics 365 Commerce tras aprovisionarlo.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="8ee8f-105">Complete los procedimientos de este tema solo después de aprovisionar el entorno de evaluación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="8ee8f-106">Para obtener información sobre cómo aprovisionar su entorno de evaluación de Commerce, vea [Provisión de un entorno de evaluación de Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="8ee8f-107">Después de que su entorno de evaluación de Commerce se haya aprovisionado de principio a fin, se deben completar pasos de configuración posteriores al aprovisionamiento para poder comenzar a evaluar el entorno.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="8ee8f-108">Para completar estos pasos, debe usar Microsoft Dynamics Lifecycle Services (LCS) y Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8ee8f-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8ee8f-109">Before you start</span></span>

1. <span data-ttu-id="8ee8f-110">Inicie sesión en el [portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="8ee8f-111">Vaya a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-111">Go to your project.</span></span>
1. <span data-ttu-id="8ee8f-112">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="8ee8f-113">Seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="8ee8f-114">En la información del entorno, a la derecha, seleccione **Iniciar sesión en entorno**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="8ee8f-115">Se le enviará a la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="8ee8f-116">Asegúrese de que la entidad jurídica **USRT** está seleccionada en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="8ee8f-117">Durante las actividades posteriores al aprovisionamiento en la sede de Commerce, asegúrese de que la entidad jurídica **USRT** siempre esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="8ee8f-118">Configurar el punto de venta</span><span class="sxs-lookup"><span data-stu-id="8ee8f-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="8ee8f-119">Asociar un trabajador con su identidad</span><span class="sxs-lookup"><span data-stu-id="8ee8f-119">Associate a worker with your identity</span></span>

<span data-ttu-id="8ee8f-120">Para asociar un trabajador con su identidad, siga estos pasos la central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="8ee8f-121">Use el menú de la izquierda para ir a **Módulos \> Retail y Commerce \> Empleados \> Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="8ee8f-122">En la lista, busque y seleccione el registro siguiente: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="8ee8f-123">En el panel Acciones, seleccione **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="8ee8f-124">Seleccione **Asociar identidad existente**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="8ee8f-125">En el campo **Correo electrónico** a la derecha de **Buscar mediante correo electrónico**, escriba su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="8ee8f-126">Selección **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-126">Select **Search**.</span></span>
1. <span data-ttu-id="8ee8f-127">Seleccione el registro con su nombre.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="8ee8f-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-128">Select **OK**.</span></span>
1. <span data-ttu-id="8ee8f-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="8ee8f-130">Activar PDV en la nube</span><span class="sxs-lookup"><span data-stu-id="8ee8f-130">Activate Cloud POS</span></span>

<span data-ttu-id="8ee8f-131">Para activar Cloud PDV, siga estos pasos en LCS.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="8ee8f-132">En el menú superior, seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="8ee8f-133">Seleccione el entorno en la lista.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="8ee8f-134">En la información del entorno, a la derecha, seleccione **Iniciar sesión punto de venta en la nube**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="8ee8f-135">Seleccione **Siguiente** para abrir el cuadro de diálogo **Antes de empezar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="8ee8f-136">Deje el campo **URL de servidor** tal cual.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="8ee8f-137">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-137">Select **Next**.</span></span>
1. <span data-ttu-id="8ee8f-138">Inicie sesión utilizando su cuenta de Microsoft Azure Active Directory ( Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="8ee8f-139">Debajo de **Nombre de la tienda**, seleccione **San Francisco** y luego **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="8ee8f-140">En **Caja registradora y dispositivo**, seleccione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="8ee8f-141">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-141">Select **Activate**.</span></span> <span data-ttu-id="8ee8f-142">Ha cerrado sesión y ha sido llevado a la página de inicio de sesión de POS.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="8ee8f-143">Ahora puede iniciar sesión en la experiencia de Cloud PDV mediante el id. de operador **000713** y contraseña **123**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="8ee8f-144">Configurar su sitio en Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-144">Set up your site in Commerce</span></span>

<span data-ttu-id="8ee8f-145">Para comenzar a configurar su sitio de evaluación en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8ee8f-146">Inicie sesión en el generador de sitios utilizando la URL de la que tomó nota cuando inicializó el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="8ee8f-147">Seleccione el sitio de **Fabrikam** para abrir el cuadro de diálogo de configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="8ee8f-148">Seleccione el dominio que ingresó cuando inicializó el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="8ee8f-149">Como canal predeterminado seleccione **Tienda en línea extendida de Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="8ee8f-150">(Asegúrese de seleccionar la tienda en línea **extendida**).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="8ee8f-151">Seleccione **es-es** como idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="8ee8f-152">Deje el valor del campo **Ruta** tal cual está.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="8ee8f-153">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-153">Select **OK**.</span></span> <span data-ttu-id="8ee8f-154">Aparece la lista de páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="8ee8f-155">Habilitar trabajos</span><span class="sxs-lookup"><span data-stu-id="8ee8f-155">Enable jobs</span></span>

<span data-ttu-id="8ee8f-156">Para activar la gestión de trabajos en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8ee8f-157">Inicie sesión en el entorno (sede).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="8ee8f-158">Use el menú de la izquierda, para ir a **Retail y Commerce \> Consultas e informes \> Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="8ee8f-159">Los pasos restantes de este procedimiento deben completarse para cada uno de los siguientes trabajos:</span><span class="sxs-lookup"><span data-stu-id="8ee8f-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="8ee8f-160">Procesar notificación por correo electrónico de pedido comercial</span><span class="sxs-lookup"><span data-stu-id="8ee8f-160">Process retail order email notification</span></span>
    * <span data-ttu-id="8ee8f-161">Disponibilidad del producto</span><span class="sxs-lookup"><span data-stu-id="8ee8f-161">Product availability</span></span>
    * <span data-ttu-id="8ee8f-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="8ee8f-162">P-0001</span></span>
    * <span data-ttu-id="8ee8f-163">Trabajo de sincronización de pedidos</span><span class="sxs-lookup"><span data-stu-id="8ee8f-163">Synchronize orders job</span></span>

1. <span data-ttu-id="8ee8f-164">Use el filtro rápido para buscar el trabajo por su nombre.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="8ee8f-165">Si el estado del trabajo es **En ejecución**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8ee8f-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="8ee8f-166">Seleccione el registro.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-166">Select the record.</span></span>
    1. <span data-ttu-id="8ee8f-167">En el panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="8ee8f-168">Haga clic en **Cancelar** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="8ee8f-169">Opcionalmente, también puede establecer el intervalo de recurrencia en un (1) minuto para los siguientes trabajos:</span><span class="sxs-lookup"><span data-stu-id="8ee8f-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="8ee8f-170">Procesar trabajo de notificación por correo electrónico de pedido comercial</span><span class="sxs-lookup"><span data-stu-id="8ee8f-170">Process retail order email notification job</span></span>
* <span data-ttu-id="8ee8f-171">Trabajo P-0001</span><span class="sxs-lookup"><span data-stu-id="8ee8f-171">P-0001 job</span></span>
* <span data-ttu-id="8ee8f-172">Trabajo de sincronización de pedidos</span><span class="sxs-lookup"><span data-stu-id="8ee8f-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="8ee8f-173">Ejecutar sincronización de datos completa</span><span class="sxs-lookup"><span data-stu-id="8ee8f-173">Run full data synchronization</span></span>

<span data-ttu-id="8ee8f-174">Para ejecutar la sincronización de datos completa en Commerce, siga estos pasos en la central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="8ee8f-175">Use el menú de la izquierda, para ir a **Módulos \> Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canales**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="8ee8f-176">Seleccione el canal denominado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="8ee8f-177">En el panel de acciones, seleccione **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="8ee8f-178">Introduzca **9999** como la programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="8ee8f-179">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-179">Select **OK**.</span></span>
1. <span data-ttu-id="8ee8f-180">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="8ee8f-181">Probar la información de la tarjeta de crédito para realizar compras de prueba</span><span class="sxs-lookup"><span data-stu-id="8ee8f-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="8ee8f-182">Para realizar transacciones de prueba en el sitio, puede usar esta información de la tarjeta de crédito de prueba:</span><span class="sxs-lookup"><span data-stu-id="8ee8f-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="8ee8f-183">**Número de tarjeta:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="8ee8f-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="8ee8f-184">**Fecha de vencimiento:** 10/20</span><span class="sxs-lookup"><span data-stu-id="8ee8f-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="8ee8f-185">**Código de seguridad de la tarjeta (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="8ee8f-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ee8f-186">Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ee8f-187">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ee8f-187">Next steps</span></span>

<span data-ttu-id="8ee8f-188">Después de completar los pasos de aprovisionamiento y configuración, podrá comenzar a usar su entorno de evaluación.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="8ee8f-189">Use la URL del creador de sitios de Commerce para acceder a la experiencia de creación.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="8ee8f-190">Use la URL del sitio de Commerce para ir la experiencia del sitio de cliente minorista.</span><span class="sxs-lookup"><span data-stu-id="8ee8f-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="8ee8f-191">Para configurar características opcionales para su entorno de evaluación de Commerce, consulte [Configurar características opcionales para un entorno de evaluación de Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="8ee8f-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ee8f-192">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8ee8f-192">Additional resources</span></span>

[<span data-ttu-id="8ee8f-193">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="8ee8f-194">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="8ee8f-195">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="8ee8f-196">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="8ee8f-197">Preguntas frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="8ee8f-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="8ee8f-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="8ee8f-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="8ee8f-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="8ee8f-200">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8ee8f-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="8ee8f-201">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8ee8f-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
