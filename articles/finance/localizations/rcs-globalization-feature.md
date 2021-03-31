---
title: 'Servicios de configuración reglamentaria (RCS): características de globalización'
description: Este tema explica cómo usar los Servicios de configuración regulatoria (RCS) de Microsoft y el repositorio global para crear y usar características de globalización.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: d5d42bd076ca77c5d2906593d44ae420d954a0b1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218863"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="7ef73-103">Servicios de configuración reglamentaria (RCS): características de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ef73-104">Puede usar los Servicios de configuración regulatoria (RCS) de Microsoft para crear una característica de globalización que se pueda usar en los servicios de globalización, como un servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="7ef73-105">RCS le permite realizar estas tareas:</span><span class="sxs-lookup"><span data-stu-id="7ef73-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="7ef73-106">Definir componentes relacionados de una característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-106">Define related components of a feature.</span></span>
- <span data-ttu-id="7ef73-107">Administre el ciclo de vida de la característica a través del estado de una característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="7ef73-108">Pong disponible una característica para entornos definidos.</span><span class="sxs-lookup"><span data-stu-id="7ef73-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="7ef73-109">Comparta una característica con otras organizaciones.</span><span class="sxs-lookup"><span data-stu-id="7ef73-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="7ef73-110">Los siguientes procedimientos explican cómo un usuario en RCS puede agregar una característica de Globalización y componentes relacionados, actualizar el estado de la característica y hacer que la característica esté disponible para que pueda usarse en los servicios de Globalización.</span><span class="sxs-lookup"><span data-stu-id="7ef73-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="7ef73-111">Antes de completar los procedimientos, debe completar los pasos relacionados con las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7ef73-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="7ef73-112">Acceso a una instancia RCS.</span><span class="sxs-lookup"><span data-stu-id="7ef73-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="7ef73-113">Creación y activación de un proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="7ef73-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="7ef73-114">Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="7ef73-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="7ef73-115">En su instancia de aplicaciones Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7ef73-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="7ef73-116">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7ef73-117">Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: Configuración** y luego siga las instrucciones para aprovisionar uno.</span><span class="sxs-lookup"><span data-stu-id="7ef73-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef73-118">Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder al entorno, seleccionando la opción de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7ef73-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="7ef73-119">Active las características de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="7ef73-120">En su instancia de RCS, seleccione el mosaico **Gestión de características**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="7ef73-121">En el espacio de trabajo **Administración de características**, seleccione **Características de globalización** en la lista y luego seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Características de globalización en Administración de características](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="7ef73-123">Características de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-123">Globalization features</span></span>

<span data-ttu-id="7ef73-124">Para usar una característica de globalización, primero debe importarla desde el repositorio global y crear su propia versión.</span><span class="sxs-lookup"><span data-stu-id="7ef73-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="7ef73-125">Hay dos formas de agregar características de globalización:</span><span class="sxs-lookup"><span data-stu-id="7ef73-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="7ef73-126">Agregue una característica derivada que se base en una característica existente que ha sido publicada o compartida.</span><span class="sxs-lookup"><span data-stu-id="7ef73-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="7ef73-127">Agregue una nueva característica que haya creado desde cero.</span><span class="sxs-lookup"><span data-stu-id="7ef73-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="7ef73-128">Acceder a características de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-128">Access Globalization features</span></span>

1. <span data-ttu-id="7ef73-129">Asegúrese de que la característica **Características de globalización** está activada en Administración de características, como se describió anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="7ef73-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="7ef73-130">Abra el nuevo espacio de trabajo **Características de globalización**, y luego, en **Caracteristicas**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Espacio de trabajo Características globales](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="7ef73-132">Se abre la página **Funciones de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Página de características de facturación electrónica](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="7ef73-134">Agregar una característica de globalización derivada</span><span class="sxs-lookup"><span data-stu-id="7ef73-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="7ef73-135">Puede agregar una nueva característica de Globalización derivándola de una característica existente que se ha publicado o compartido.</span><span class="sxs-lookup"><span data-stu-id="7ef73-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="7ef73-136">Seleccione **Importar** para abrir la página **Importar característica del repositorio global**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Importar característica de la página del repositorio global](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="7ef73-138">Seleccione **Sincronizar** para obtener las últimas características.</span><span class="sxs-lookup"><span data-stu-id="7ef73-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="7ef73-139">La lista sincronizada incluye características que están disponibles para usted, ya sea porque fueron publicadas por Microsoft o porque fueron compartidas con usted por otro proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="7ef73-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Lista sincronizada de características](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="7ef73-141">En la lista, seleccione las características para importar y luego seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="7ef73-142">Recibirá un mensaje cuando las características seleccionadas se hayan importado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ef73-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Mensaje de importación correcta](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="7ef73-144">Seleccione **Añadir** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Basado en la versión existente**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="7ef73-145">Especifique un nombre y descripción para la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="7ef73-146">En la lista de características disponibles, seleccione la versión base de la característica y luego seleccione **Crear característica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Agregar una característica derivada](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="7ef73-148">La característica que agregó se crea y tiene un estado de **Borrador**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Característica derivada que tiene estado Borrador](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="7ef73-150">Revise los componentes de la característica para determinar si se requieren actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="7ef73-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="7ef73-151">Revise las configuraciones, en caso de que necesite personalizar los formatos de informes electrónicos (ER) y su vínculo con asignaciones de formatos para la versión de la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="7ef73-152">Revise la configuración, en caso de que necesite personalizar la pestaña **Acciones**, la pestaña **Reglas de aplicabilidad** o la pestaña **Variables** para la versión de la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="7ef73-153">En la pestaña **Versiones**, seleccione una fecha **Válido desde** e introduzca una descripción si el campo **Descripción** está en blanco.</span><span class="sxs-lookup"><span data-stu-id="7ef73-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="7ef73-154">Seleccione **Cambiar Estado** para completar la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="7ef73-155">Las características completas pueden estar disponibles para un entorno específico para que puedan usarse en los servicios de globalización, o pueden publicarse en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="7ef73-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef73-156">Las características que tienen un valor de **Estado de la versión de la característica** en **Publicado** se pueden compartir con organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="7ef73-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="7ef73-157">Agregar una nueva característica de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-157">Add a new Globalization feature</span></span>

<span data-ttu-id="7ef73-158">Puede agregar una nueva característica de Globalización creándola desde cero.</span><span class="sxs-lookup"><span data-stu-id="7ef73-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="7ef73-159">En la página **Importar característica del repositorio global**, seleccione **Añadir** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Nueva característica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="7ef73-160">Especifique un nombre y descripción para la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="7ef73-161">Seleccione **Crear característica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-161">Select **Create feature**.</span></span>

    ![Agregar una nueva característica](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="7ef73-163">En la pestaña **Versiones**, seleccione una fecha **Válido desde** y luego seleccione **Cambiar Estado** para completar la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="7ef73-164">Las características completas pueden estar disponibles para un entorno específico para que puedan usarse en los servicios de globalización, o pueden publicarse en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="7ef73-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef73-165">Las características que tienen un valor de **Estado de la versión de la característica** en **Publicado** se pueden compartir con organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="7ef73-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="7ef73-166">Visión general de componentes de características</span><span class="sxs-lookup"><span data-stu-id="7ef73-166">Feature component overview</span></span>

<span data-ttu-id="7ef73-167">Las características de globalización tienen varios componentes:</span><span class="sxs-lookup"><span data-stu-id="7ef73-167">Globalization features have several components:</span></span>

- <span data-ttu-id="7ef73-168">**Versión**: este componente admite la gestión del ciclo de vida de la característica y permite a los usuarios administrar el estado de las diferentes versiones de la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="7ef73-169">**Configuraciones**: este componente permite a los usuarios administrar, ver y editar formatos ER relacionados y mapeos de formatos.</span><span class="sxs-lookup"><span data-stu-id="7ef73-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="7ef73-170">**Configuraciones**: este componente permite a los usuarios de servicios de globalización, como un servicio de facturación electrónica, administrar la configuración de la versión de la característica relacionada.</span><span class="sxs-lookup"><span data-stu-id="7ef73-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="7ef73-171">Por lo tanto, apoya la construcción flexible de reglas de comunicación y respuestas.</span><span class="sxs-lookup"><span data-stu-id="7ef73-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="7ef73-172">**Entorno**: este componente permite a los usuarios de los servicios de globalización, como un servicio de facturación electrónica, gestionar el entorno donde se utiliza la configuración de la versión de la característica y otorgar autorización a los usuarios que tendrán acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="7ef73-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="7ef73-173">**Organizaciones**: este componente permite a los usuarios compartir la característica con organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="7ef73-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="7ef73-174">Configurar componentes de características</span><span class="sxs-lookup"><span data-stu-id="7ef73-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="7ef73-175">Estado y versión</span><span class="sxs-lookup"><span data-stu-id="7ef73-175">Version and status</span></span>

<span data-ttu-id="7ef73-176">La versión se utiliza para administrar el ciclo de vida de la característica de globalización.</span><span class="sxs-lookup"><span data-stu-id="7ef73-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="7ef73-177">El estado se puede cambiar en el campo **Estado**, en la pestaña **Versión**. Los siguientes estados están disponibles:</span><span class="sxs-lookup"><span data-stu-id="7ef73-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="7ef73-178">**Borrador**: la característica solo se puede editar cuando está en este estado.</span><span class="sxs-lookup"><span data-stu-id="7ef73-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="7ef73-179">**Completa**: la característica y todos los componentes relacionados se han finalizado (completado) y no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="7ef73-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="7ef73-180">**Publicado**: la característica y todos los componentes relacionados se han publicado en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="7ef73-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="7ef73-181">**Compartido**: la característica y todos los componentes relacionados se han compartido con organizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="7ef73-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="7ef73-182">**Habilitado**: la característica y todos los componentes relacionados se han habilitado para su uso en un servicio de globalización, como un servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef73-183">Las características deben moverse secuencialmente a través de algunos de estos estados.</span><span class="sxs-lookup"><span data-stu-id="7ef73-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="7ef73-184">Por lo tanto, no todos los estados pueden estar disponibles en todas las etapas del ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7ef73-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="7ef73-185">Configuraciones</span><span class="sxs-lookup"><span data-stu-id="7ef73-185">Configurations</span></span>

<span data-ttu-id="7ef73-186">Las siguientes acciones están disponibles para configuraciones:</span><span class="sxs-lookup"><span data-stu-id="7ef73-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="7ef73-187">**Ver**: ver las configuraciones de características subyacentes que no requieren ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="7ef73-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="7ef73-188">**Editar**: cree una versión de borrador de una configuración seleccionada para que pueda editar el formato o la asignación de formato en el Diseñador de formatos.</span><span class="sxs-lookup"><span data-stu-id="7ef73-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="7ef73-189">**Eliminar**: eliminar una configuración seleccionada de la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="7ef73-190">**Cambiar**: cambiar la base de la característica.</span><span class="sxs-lookup"><span data-stu-id="7ef73-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="7ef73-191">Para obtener más información, consulte la sección [Cambiar la base de características de globalización rerivadas](#rebase), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7ef73-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="7ef73-192">Configuraciones</span><span class="sxs-lookup"><span data-stu-id="7ef73-192">Setups</span></span>

<span data-ttu-id="7ef73-193">Las siguientes acciones están disponibles para configuraciones de características:</span><span class="sxs-lookup"><span data-stu-id="7ef73-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="7ef73-194">**Añadir**: crear una nueva configuración de características.</span><span class="sxs-lookup"><span data-stu-id="7ef73-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="7ef73-195">Esta configuración de características puede derivarse de una configuración de características existente o crearse desde cero.</span><span class="sxs-lookup"><span data-stu-id="7ef73-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="7ef73-196">**Eliminar**: eliminar una configuración de característica seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7ef73-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="7ef73-197">**Ver**: ver una configuración de características subyacente que no requiere ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="7ef73-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="7ef73-198">**Editar**: cree, elimine o modifique los atributos de los tres componentes principales de una configuración de características:</span><span class="sxs-lookup"><span data-stu-id="7ef73-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="7ef73-199">Acciones y sus parámetros</span><span class="sxs-lookup"><span data-stu-id="7ef73-199">Actions and their parameters</span></span>
    - <span data-ttu-id="7ef73-200">Reglas de aplicabilidad</span><span class="sxs-lookup"><span data-stu-id="7ef73-200">Applicability rules</span></span>
    - <span data-ttu-id="7ef73-201">Variables</span><span class="sxs-lookup"><span data-stu-id="7ef73-201">Variables</span></span>

![Página de configuración de versión de características](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="7ef73-203">Entornos</span><span class="sxs-lookup"><span data-stu-id="7ef73-203">Environments</span></span>

<span data-ttu-id="7ef73-204">Las siguientes acciones están disponibles para entornos:</span><span class="sxs-lookup"><span data-stu-id="7ef73-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="7ef73-205">**Habilitar**: para una versión de característica seleccionada, seleccione un entorno publicado y seleccione una fecha **Válido desde** en que debería estar disponible.</span><span class="sxs-lookup"><span data-stu-id="7ef73-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="7ef73-206">Para obtener más información, consulte la sección [Configurar entornos para habilitación](#configureenvironment), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7ef73-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="7ef73-207">**Cancelar**: eliminar un entorno para una configuración de características.</span><span class="sxs-lookup"><span data-stu-id="7ef73-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="7ef73-208">Organizaciones</span><span class="sxs-lookup"><span data-stu-id="7ef73-208">Organizations</span></span>

<span data-ttu-id="7ef73-209">Siga estos pasos para compartir una característica de globalización con una organización externa.</span><span class="sxs-lookup"><span data-stu-id="7ef73-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="7ef73-210">En la página **Funciones de facturación electrónica**, seleccione la característica y la versión de la característica para compartir.</span><span class="sxs-lookup"><span data-stu-id="7ef73-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="7ef73-211">En la pestaña **Organizaciones**, seleccione **Compartir con**, y luego, en el cuadro de diálogo desplegable, introduzca el nombre de dominio de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ef73-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="7ef73-212">Seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-212">Select **Share**.</span></span>

    ![Compartir una característica con una organización](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="7ef73-214">La característica se comparte con la organización seleccionada y está disponible para esa organización en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="7ef73-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="7ef73-215">A partir de ahí, la característica se puede importar a la instancia de RCS de la organización o Dynamics 365 Finance para que pueda usarse.</span><span class="sxs-lookup"><span data-stu-id="7ef73-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="7ef73-216">Cambiar la base de características de globalización derivadas</span><span class="sxs-lookup"><span data-stu-id="7ef73-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="7ef73-217">Puede cambiar la base de una característica de Globalización derivada a la versión de característica base nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="7ef73-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="7ef73-218">De esta manera, los cambios que se han producido en la versión base se pueden actualizar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7ef73-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="7ef73-219">La versión de la característica base actualizada la crea el proveedor de configuración de origen, y luego se publica o comparte.</span><span class="sxs-lookup"><span data-stu-id="7ef73-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Versión de característica base actualizada](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="7ef73-221">Por ejemplo, si desea cambiar la base de la versión derivada de una característica que creó, primero debe obtener la última versión de la característica importándola del repositorio global.</span><span class="sxs-lookup"><span data-stu-id="7ef73-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="7ef73-222">En la página **Funciones de facturación electrónica**, seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="7ef73-223">Seleccione **Sincronizar** para obtener las últimas características.</span><span class="sxs-lookup"><span data-stu-id="7ef73-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="7ef73-224">En la lista de características, seleccione las características para importar y luego seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importación de la última versión de una característica](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="7ef73-226">En la lista de características, seleccione la característica para cambiar de base.</span><span class="sxs-lookup"><span data-stu-id="7ef73-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="7ef73-227">En la pestaña **Versión**, seleccione **Nuevo** para crear una versión de borrador.</span><span class="sxs-lookup"><span data-stu-id="7ef73-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Nueva versión de borrador creada](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="7ef73-229">Seleccione **Cambiar de basee**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="7ef73-230">En el cuadro de diálogo **Cambiar de base**, seleccione la última versión de la característica a cambiar de base.</span><span class="sxs-lookup"><span data-stu-id="7ef73-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Cuadro de diálogo Cambiar de base](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="7ef73-232">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-232">Select **OK**.</span></span>
9. <span data-ttu-id="7ef73-233">Revise los componentes de la característica y realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="7ef73-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="7ef73-234">Seleccione **Cambiar Estado** para completar la característica cambiada de base.</span><span class="sxs-lookup"><span data-stu-id="7ef73-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="7ef73-235">Cuando se completa el cambio de base, puede realizar acciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="7ef73-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="7ef73-236">Por ejemplo, puede publicar la característica y ponerla a disposición para su uso en los servicios de globalización.</span><span class="sxs-lookup"><span data-stu-id="7ef73-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Estado de la característica actualizado a Completado](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="7ef73-238">Configurar entornos para características de globalización</span><span class="sxs-lookup"><span data-stu-id="7ef73-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="7ef73-239">Los usuarios de los servicios de globalización pueden administrar el entorno para configurar una característica de globalización y otorgar autorización a otros usuarios que tendrán acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="7ef73-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="7ef73-240">En el espacio de trabajo **Características de globalización**, en **Entornos**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="7ef73-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Espacio de trabajo Características de globalización](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="7ef73-242">Seleccione **Parámetros clave del almacén** y luego seleccione **Nuevo** para crear un almacén de claves de Azure.</span><span class="sxs-lookup"><span data-stu-id="7ef73-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="7ef73-243">Introduzca un nombre y una descripción para el almacén de claves y luego, en el campo **URI de almacén de claves**, introduzca la URL que identifica el recurso de almacén de claves en Azure.</span><span class="sxs-lookup"><span data-stu-id="7ef73-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="7ef73-244">En la ficha desplegable **Certificados**, seleccione **Añadir** para agregar el certificado e introduzca un nombre y una descripción para cada certificado.</span><span class="sxs-lookup"><span data-stu-id="7ef73-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Certificado agregado](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="7ef73-246">Seleccione **Nuevo** para crear un nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="7ef73-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="7ef73-247">introduzca un nombre, una descripción y el secreto de token de firma de acceso compartido requerido para el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="7ef73-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="7ef73-248">En la ficha desplegable **Usuarios**, seleccione **Nuevo** para agregar un usuario que tendrá permiso para acceder a este entorno.</span><span class="sxs-lookup"><span data-stu-id="7ef73-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="7ef73-249">introduzca el id. y la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="7ef73-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="7ef73-250">Repita los pasos 7 y 8 para agregar más usuarios.</span><span class="sxs-lookup"><span data-stu-id="7ef73-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="7ef73-251">Seleccione **Publicar** para publicar el entorno.</span><span class="sxs-lookup"><span data-stu-id="7ef73-251">Select **Publish** to publish the environment.</span></span>

    ![Entorno publicado](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]