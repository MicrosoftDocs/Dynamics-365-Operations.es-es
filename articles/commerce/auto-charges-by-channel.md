---
title: Habilitar y configurar cargos automáticos por canal
description: Este tema explica cómo habilitar y configurar los cargos automáticos por canal en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d37b2b785dd29850dcd02d0905e5872445384990
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993737"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="ee7ad-103">Habilitar y configurar cargos automáticos por canal</span><span class="sxs-lookup"><span data-stu-id="ee7ad-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="ee7ad-104">Este tema explica cómo habilitar y configurar los cargos automáticos por canal en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ee7ad-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ee7ad-105">Overview</span></span>

<span data-ttu-id="ee7ad-106">Es posible que tenga escenarios en los que se deben aplicar tarifas de reciclaje u otras tarifas a un grupo de productos que se venden en todas o algunas tiendas en un estado específico (por ejemplo, California).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="ee7ad-107">La función **Habilitar cargas automáticas de filtro por canal** en Commerce le permite especificar cargos automáticos por canal (por ejemplo, un canal específico físico).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="ee7ad-108">Esta función está disponible en Dynamics 365 Commerce versión 10.0.10 y posterior.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="ee7ad-109">Para habilitar y configurar los cargos automáticos por canal, debe completar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ee7ad-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="ee7ad-110">Active la característica **Habilitar cargas automáticas de filtro por canal**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="ee7ad-111">Configure el propósito de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="ee7ad-112">Defina cargas automáticas por canal.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="ee7ad-113">La característica **Habilitar cargas automáticas de filtro por canal** solo funciona si la función de carga automática avanzada también está activada.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="ee7ad-114">Para obtener información sobre cómo activar la función de cargos automáticos avanzados, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="ee7ad-115">Active la característica Habilitar cargas automáticas de filtro por canal</span><span class="sxs-lookup"><span data-stu-id="ee7ad-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="ee7ad-116">Para habilitar los cargos automáticos por canal en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ee7ad-117">Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="ee7ad-118">En la pestaña **No habilitada**, en la lista **Nombre de característica**, busque y seleccione **Habilitar cargas automáticas de filtro por canal**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="ee7ad-119">En la esquina inferior derecha, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="ee7ad-120">Después de que la función se haya activado, aparecerá en la lista en la pestaña **Todo**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="ee7ad-121">Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="ee7ad-122">En el panel izquierdo, busque y seleccione el trabajo **1110** (**Configuración global**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="ee7ad-123">En el Panel de acciones, seleccione **Ejecutar ahora** para propagar los cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="ee7ad-124">Si desactiva la característica **Habilitar cargas automáticas de filtro por canal** después de que ya la haya usado, el campo **Relación del canal minorista** bajo **Cargos automáticos** ya no aparecerá y perderá todas las configuraciones existentes.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="ee7ad-125">Si la eliminación de las configuraciones **Relación del canal minorista** harán que las reglas de carga automática se dupliquen, un intento de desactivar la función fallará.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="ee7ad-126">Antes de desactivar la función, asegúrese de revisar todas las reglas de cargos automáticos y realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="ee7ad-127">Configure el propósito de la jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="ee7ad-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="ee7ad-128">Un nuevo propósito de la jerarquía organizativa que se denomina **Cargo de auto minorista** ha sido creado para administrar la jerarquía de cargos automáticos por canal.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="ee7ad-129">Para asignar una jerarquía predeterminada a un propósito de jerarquía de organización en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="ee7ad-130">Vaya a **Administración de la organización \> Organizaciones \> Propósitos de jerarquías organizativas**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="ee7ad-131">En el panel izquierdo, seleccione **Cargo de auto minorista**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="ee7ad-132">En **Jerarquías asignadas**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="ee7ad-133">En el cuadro de diálogo **Jerarquías organizativas**, seleccione una jerarquía organizativa (por ejemplo, **Tiendas minoristas por región**) y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="ee7ad-134">En **Jerarquías asignadas**, seleccione **Establecer como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="ee7ad-135">Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="ee7ad-136">En el panel izquierdo, busque y seleccione el trabajo **1040** (**Productos**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="ee7ad-137">En el panel de acciones, seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="ee7ad-138">Repita los dos pasos anteriores para ejecutar los trabajos **1070** (**Configuración del canal**) y **1110** (**Configuración global**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Configuración del propósito de la jerarquía organizativa de cargo automático minorista](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="ee7ad-140">Defina cargos automáticas por canal</span><span class="sxs-lookup"><span data-stu-id="ee7ad-140">Define auto charges by channel</span></span>

<span data-ttu-id="ee7ad-141">Después de haber activado la característica **Habilitar cargos automáticas de filtro por canal** y configurado el propósito de jerarquía organizativa **Cargo minorista automático**, los cargos automáticos por canal se pueden definir en el nivel de encabezado del pedido o en el nivel de línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="ee7ad-142">Para definir los cargos automáticos por canal en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ee7ad-143">Vaya a **Clientes \> Configuración de cargos \> cargos automáticos**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="ee7ad-144">En el panel izquierdo, en el campo **Nivel**, seleccione **Encabezado** o **Línea**, dependiendo de los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="ee7ad-145">En el campo **Código de canal minorista**, seleccione el código de canal apropiado (por ejemplo, **Tabla** o **Grupo**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="ee7ad-146">Si la configuración predeterminada, **Todos**, se utiliza, las reglas de carga se aplican a todos los canales.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="ee7ad-147">Si selecciona **Grupo**, asegúrese de que se cree un grupo de cargos de canal minorista en **Retail and Commerce \> Configuración del canal \> Cargos \> Grupos de cargos de canales minoristas**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="ee7ad-148">Si selecciona **Tabla**, puede seleccionar un canal específico (por ejemplo, **San Francisco**) en el campo **Relación del canal minorista**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="ee7ad-149">Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="ee7ad-150">En el panel izquierdo, busque y seleccione el trabajo **1040** (**Productos**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="ee7ad-151">En el panel de acciones, seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="ee7ad-152">Repita los dos pasos anteriores para ejecutar los trabajos **1070** (**Configuración del canal**) y **1110** (**Configuración global**).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Cargos automáticos definidos por canal](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="ee7ad-154">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee7ad-154">Example scenario</span></span>

<span data-ttu-id="ee7ad-155">El siguiente ejemplo describe los pasos necesarios para configurar un producto para que se cobren tarifas de reciclaje cuando el producto se vende a través de un canal físico de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="ee7ad-156">El ejemplo también muestra cómo aparecen los cargos automáticos en la aplicación de punto de venta (PDV) de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="ee7ad-157">La organización define un código de cargos que se denomina **RECICLAR**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Código de cargos de RECICLAR](media/Auto-charges-charge-code.png)

<span data-ttu-id="ee7ad-159">Se crea un cargo automático al nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="ee7ad-160">Tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ee7ad-160">It has the following configuration:</span></span>

- <span data-ttu-id="ee7ad-161">El campo **Código de cuenta** se establece en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="ee7ad-162">El campo **Código de artículo** se establece en **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="ee7ad-163">El campo **Relación del artículo** se establece en Id. de producto **91001**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="ee7ad-164">El campo **Código modo de entrega** se establece en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="ee7ad-165">El campo **Código de canal minorista** se establece en **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="ee7ad-166">El campo **Relación del canal minorista** se establece en tienda **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="ee7ad-167">Se crea una línea de cargos automáticos.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-167">An auto charges line is created.</span></span> <span data-ttu-id="ee7ad-168">Tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ee7ad-168">It has the following configuration:</span></span>

- <span data-ttu-id="ee7ad-169">El campo **Divisa** se establece en **USD**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="ee7ad-170">El campo **Código de cargos** se establece en **RECICLAR**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="ee7ad-171">El campo **Categoría** se establece en **Fijo**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="ee7ad-172">El campo **Cargos** se establece en **6,25 $**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-172">The **Charges** field is set to **$6.25**.</span></span>

![Configuración del cargo automática de nivel de línea y la línea de cargo automática](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="ee7ad-174">En la aplicación PDV, se crea un pedido de ventas en el canal de la tienda **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="ee7ad-175">La línea **Cargos** línea muestra la tarifa de reciclaje de **6,25 $**.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="ee7ad-176">Seleccionando **Opciones de transacción \> Cargos \> Administrar cargos** en la aplicación PDV, puede ver el código de cargos y la descripción de la tarifa de reciclaje.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Tarifa de reciclaje en la aplicación PDV](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="ee7ad-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ee7ad-178">Additional resources</span></span>

[<span data-ttu-id="ee7ad-179">Cargos automáticos avanzados omnicanal</span><span class="sxs-lookup"><span data-stu-id="ee7ad-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="ee7ad-180">Prorratear los cargos de encabezado con las líneas de ventas coincidentes</span><span class="sxs-lookup"><span data-stu-id="ee7ad-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)
