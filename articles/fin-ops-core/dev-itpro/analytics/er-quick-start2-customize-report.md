---
title: Ajustar un formato ER para generar un documento electrónico personalizado
description: Este tema explica cómo ajustar un formato de informe electrónico (ER) proporcionado por Microsoft para que genere un documento electrónico personalizado.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7355fbb3321a6b5707ab561e88aed2d22cc967cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743662"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="d2834-103">Ajustar un formato ER para generar un documento electrónico personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d2834-104">Los procedimientos en este tema explican cómo un usuario con el rol de administrador del sistema o consultor funcional de informes electrónicos puede realizar estas tareas:</span><span class="sxs-lookup"><span data-stu-id="d2834-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="d2834-105">Configurar los parámetros para el [marco de informes electrónicos (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="d2834-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="d2834-106">Importe configuraciones de ER proporcionadas por Microsoft y utilizadas para generar un archivo de pago mientras se procesa un [pago del vendedor](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d2834-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="d2834-107">Cree una versión personalizada de una configuración de formato ER estándar proporcionada por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2834-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="d2834-108">Modifique la configuración del formato ER personalizado para que genere archivos de pago que cumplan con los requisitos de un banco específico.</span><span class="sxs-lookup"><span data-stu-id="d2834-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="d2834-109">Adopte los cambios realizados en la configuración de formato ER estándar en la configuración de formato ER personalizada.</span><span class="sxs-lookup"><span data-stu-id="d2834-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="d2834-110">Todos los siguientes procedimientos se pueden hacer en el **GBSI** de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d2834-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="d2834-111">No se requiere codificación.</span><span class="sxs-lookup"><span data-stu-id="d2834-111">No coding is required.</span></span>

- [<span data-ttu-id="d2834-112">Configurar el marco ER</span><span class="sxs-lookup"><span data-stu-id="d2834-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="d2834-113">Configurar los parámetros de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="d2834-114">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="d2834-115">Revise la lista de proveedores de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="d2834-116">Añada una nueva configuración para el proveedor de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="d2834-117">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="d2834-118">Importar configuraciones del formato estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="d2834-119">Importar configuraciones estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="d2834-120">Revisar las configuraciones importadas de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="d2834-121">Preparar un pago a proveedor para el procesado</span><span class="sxs-lookup"><span data-stu-id="d2834-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="d2834-122">Agregar información bancaria a una cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="d2834-123">Introducir un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="d2834-124">Procesar un pago de proveedor utilizando el formato ER estándar</span><span class="sxs-lookup"><span data-stu-id="d2834-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="d2834-125">Configurar la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="d2834-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="d2834-126">Procesar un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="d2834-127">Personalizar el formato ER estándar</span><span class="sxs-lookup"><span data-stu-id="d2834-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="d2834-128">Crear un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="d2834-129">Editar un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="d2834-130">Marcar un formato personalizado como ejecutable</span><span class="sxs-lookup"><span data-stu-id="d2834-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="d2834-131">Procesar un pago de proveedor utilizando el formato ER personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="d2834-132">Configurar la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="d2834-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="d2834-133">Procesar un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="d2834-134">Importar nuevas versiones de las configuraciones del formato estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="d2834-135">Importar nuevas versiones de las configuraciones estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="d2834-136">Revisar las configuraciones de formato importadas de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="d2834-137">Adoptar los cambios en la nueva versión de un formato importado en un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="d2834-138">Completar la versión actual de borrador de un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="d2834-139">Reorganizar un formato personalizado a una nueva versión base</span><span class="sxs-lookup"><span data-stu-id="d2834-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="d2834-140">Procesar un pago de proveedor utilizando un formato de ER reorganizado</span><span class="sxs-lookup"><span data-stu-id="d2834-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="d2834-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d2834-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="d2834-142">Configurar el marco ER</span><span class="sxs-lookup"><span data-stu-id="d2834-142">Configure the ER framework</span></span>

<span data-ttu-id="d2834-143">Como usuario en el rol de Consultor Funcional de Informes Electrónicos, debe configurar el conjunto mínimo de parámetros de ER antes de comenzar a usar el marco de ER para diseñar una versión personalizada de un formato de ER estándar.</span><span class="sxs-lookup"><span data-stu-id="d2834-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="d2834-144">Configurar los parámetros de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-144">Configure ER parameters</span></span>

1. <span data-ttu-id="d2834-145">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-146">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="d2834-147">En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="d2834-148">En la pestaña **Adjuntos**, establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2834-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="d2834-149">En el campo **Configuraciones**, seleccione el tipo **Archivo** para el **USMF** de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d2834-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="d2834-150">En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="d2834-151">Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d2834-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="d2834-152">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="d2834-153">Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="d2834-154">El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito.</span><span class="sxs-lookup"><span data-stu-id="d2834-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="d2834-155">Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="d2834-156">Solo el propietario de una configuración de ER puede editarla.</span><span class="sxs-lookup"><span data-stu-id="d2834-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="d2834-157">Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="d2834-158">Revise la lista de proveedores de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="d2834-159">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-160">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="d2834-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="d2834-161">En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos.</span><span class="sxs-lookup"><span data-stu-id="d2834-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="d2834-162">Revise el contenido de esta página.</span><span class="sxs-lookup"><span data-stu-id="d2834-162">Review the contents of this page.</span></span> <span data-ttu-id="d2834-163">Si un registro para **Litware, Inc.** (`https://www.litware.com`) ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="d2834-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="d2834-164">Añada una nueva configuración para el proveedor de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="d2834-165">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-166">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="d2834-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="d2834-167">En la página **Proveedores de configuración**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="d2834-168">En el campo **Nombre**, introduzca **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="d2834-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="d2834-169">En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="d2834-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="d2834-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="d2834-171">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="d2834-172">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-173">En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="d2834-174">Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="d2834-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="d2834-175">Importar configuraciones del formato estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="d2834-176">Importar configuraciones estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-176">Import the standard ER configurations</span></span>

<span data-ttu-id="d2834-177">Para agregar las configuraciones ER estándar a su instancia actual de Microsoft Dynamics 365 Finance, debe importarlos desde el [repositorio](general-electronic-reporting.md#Repository) de ER que se configuró para esa instancia.</span><span class="sxs-lookup"><span data-stu-id="d2834-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="d2834-178">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-179">En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2834-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="d2834-180">En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d2834-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="d2834-181">Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.</span><span class="sxs-lookup"><span data-stu-id="d2834-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="d2834-182">En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="d2834-183">En la ficha desplegable **Versiones**, seleccione la versión **1.1** de la configuración de ER seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2834-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="d2834-184">Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="d2834-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Página de configuración del repositorio](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="d2834-186">Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de Microsoft Dynamics Lifecycle Services (LCS) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d2834-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="d2834-187">Revisar las configuraciones importadas de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="d2834-188">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-189">En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="d2834-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d2834-190">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="d2834-191">Tenga en cuenta que, además del formato de ER **BACS (Reino Unido)**, se importaron otras configuraciones ER necesarias.</span><span class="sxs-lookup"><span data-stu-id="d2834-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="d2834-192">Asegúrese de que las siguientes configuraciones de ER estén disponibles en el árbol de configuración:</span><span class="sxs-lookup"><span data-stu-id="d2834-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="d2834-193">**Modelo de pago** - Esta configuración contiene el [modelo de datos](general-electronic-reporting.md#data-model-and-model-mapping-components) del componente ER que representa la estructura de datos del dominio comercial de pago.</span><span class="sxs-lookup"><span data-stu-id="d2834-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="d2834-194">**Asignación del modelo de pago 1611** - Esta configuración contiene el [asignado de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) del componente ER que describe cómo se completa el modelo de datos con los datos de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2834-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="d2834-195">**BACS (Reino Unido)** - Esta configuración contiene el [formato](general-electronic-reporting.md#FormatComponentOutbound) y asignación de formato de componentes ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="d2834-196">El componente de formato especifica el diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="d2834-196">The format component specifies the report layout.</span></span> <span data-ttu-id="d2834-197">El componente de asignación de formato contiene la fuente de datos del modelo y especifica cómo se completa el diseño del informe utilizando esta fuente de datos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2834-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Página Configuraciones](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="d2834-199">Preparar un pago a proveedor para el procesado</span><span class="sxs-lookup"><span data-stu-id="d2834-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="d2834-200">Agregar información bancaria a una cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="d2834-201">Debe agregar información bancaria para una cuenta de proveedor a la que se hará referencia más adelante en un pago registrado.</span><span class="sxs-lookup"><span data-stu-id="d2834-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="d2834-202">Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="d2834-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="d2834-203">En la página **Todos los proveedores**, seleccione la cuenta de proveedor **GB_SI_000001**, y luego, en el panel de acciones, en la pestaña **Proveedor**, en el grupo **Configurar**, seleccione **cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="d2834-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="d2834-204">En la página **Cuentas bancarias de proveedores**, seleccione **Nueva** y luego introduzca la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d2834-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="d2834-205">En el campo **Cuenta bancaria**, introduzca **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="d2834-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="d2834-206">En el **Grupos de bancos** campo, introduzca **BankGBP**.</span><span class="sxs-lookup"><span data-stu-id="d2834-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="d2834-207">En el campo **Número de cuenta bancaria** introduzca **202015**.</span><span class="sxs-lookup"><span data-stu-id="d2834-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="d2834-208">En el campo **Código SWIFT**, introduzca <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span><span class="sxs-lookup"><span data-stu-id="d2834-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="d2834-209">En el campo **IBAN**, introduzca **GB33BUKB20201555555555**.</span><span class="sxs-lookup"><span data-stu-id="d2834-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="d2834-210">En el campo **Número de ruta**, conserve el valor predeterminado <a id="DefineRoutingNumber"></a>**123456**.</span><span class="sxs-lookup"><span data-stu-id="d2834-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Página de cuentas bancarias del proveedor](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="d2834-212">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-212">Select **Save**.</span></span>
5. <span data-ttu-id="d2834-213">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d2834-213">Close the page.</span></span>
6. <span data-ttu-id="d2834-214">En la página **Todos los proveedores**, abra la cuenta de proveedor **GB_SI_000001**.</span><span class="sxs-lookup"><span data-stu-id="d2834-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="d2834-215">En la página de detalles del proveedor, seleccione **Editar** para hacer que la página sea editable, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d2834-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="d2834-216">En la ficha desplegable **Pago**, en el campo **Cuenta bancaria**, seleccione **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="d2834-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Página de detalles del proveedor](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="d2834-218">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-218">Select **Save**.</span></span>
10. <span data-ttu-id="d2834-219">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d2834-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="d2834-220">Introducir un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-220">Enter a vendor payment</span></span>

<span data-ttu-id="d2834-221">Debe introducir un pago de proveedor nuevo usando una [propuesta de pago](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span><span class="sxs-lookup"><span data-stu-id="d2834-221">You must enter a new vendor payment by using a [payment proposal](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span></span>

1. <span data-ttu-id="d2834-222">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="d2834-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d2834-223">En la página **Diario de pago de proveedor**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="d2834-224">En el campo **Nombre**, seleccione **VendPay**.</span><span class="sxs-lookup"><span data-stu-id="d2834-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="d2834-225">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="d2834-225">Select **Lines**.</span></span>
5. <span data-ttu-id="d2834-226">Seleccione **Propuesta de pago** \> **Crear propuesta de pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="d2834-227">En el cuadro de diálogo **Propuesta de pago del proveedor**, configure condiciones para filtrar registros para solo la cuenta de proveedor **GB_SI_000001** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="d2834-228">Seleccione la línea para la factura **00000007_Inv** y luego seleccione **Crear pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Ventana de diálogo de propuesta de pago de proveedor](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="d2834-230">Verifique que el pago introducido esté configurado para usar la forma de pago **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d2834-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Página Pagos a proveedores](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="d2834-232">Procesar un pago de proveedor utilizando el formato ER estándar</span><span class="sxs-lookup"><span data-stu-id="d2834-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="d2834-233">Configurar la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="d2834-233">Set up the electronic payment method</span></span>

<span data-ttu-id="d2834-234">Debe configurar el método de pago electrónico para que use la configuración de formato ER importada.</span><span class="sxs-lookup"><span data-stu-id="d2834-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="d2834-235">Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="d2834-236">En la página **Métodos de pago - proveedores**, seleccione el método de pago **Electrónico** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d2834-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="d2834-237">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-237">Select **Edit**.</span></span>
4. <span data-ttu-id="d2834-238">En la ficha desplegable **Formatos de archivo**, establezca la opción **Formato de exportación electrónica general** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="d2834-239">En el campo **Configuración de formato de exportación**, seleccione la configuración de formato **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Métodos de pago - página de proveedores](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="d2834-241">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="d2834-242">Procesar un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-242">Process a vendor payment</span></span>

1. <span data-ttu-id="d2834-243">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="d2834-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d2834-244">En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que agregó anteriormente y luego seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="d2834-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="d2834-245">En la página **Pagos de proveedores** página, seleccione **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="d2834-246">En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d2834-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d2834-247">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d2834-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d2834-248">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d2834-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="d2834-249">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-249">Select **OK**.</span></span>
6. <span data-ttu-id="d2834-250">En el cuadro de diálogo **Parámetros de informes electrónicos**, establezca la opción **Imprimir informe de control** a **Sí** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Página Parámetros de notificación electrónica](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="d2834-252">Además del archivo de pago, ahora puede generar el informe de control.</span><span class="sxs-lookup"><span data-stu-id="d2834-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="d2834-253">Descargue el archivo zip y luego extraiga los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="d2834-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d2834-254">El informe de control en formato Excel</span><span class="sxs-lookup"><span data-stu-id="d2834-254">The control report in Excel format</span></span>
    - <span data-ttu-id="d2834-255">El archivo de pago en formato TXT</span><span class="sxs-lookup"><span data-stu-id="d2834-255">The payment file in TXT format</span></span>

        <span data-ttu-id="d2834-256">Tenga en cuenta que según la [estructura](#PositionRoutingNumber) del formato ER proporcionado, la línea de pago en el archivo generado comienza con el número de ruta que fue [definido](#DefineRoutingNumber) para la cuenta bancaria configurada.</span><span class="sxs-lookup"><span data-stu-id="d2834-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="d2834-258">Personalizar el formato ER estándar</span><span class="sxs-lookup"><span data-stu-id="d2834-258">Customize the standard ER format</span></span>

<span data-ttu-id="d2834-259">Para el ejemplo que se muestra en esta sección, desea utilizar las configuraciones de ER que proporciona Microsoft para generar archivos de pago de proveedores en formato BACS, pero debe agregar una personalización para admitir los requisitos de un banco específico.</span><span class="sxs-lookup"><span data-stu-id="d2834-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="d2834-260">También desea poder actualizar su formato personalizado cuando estén disponibles nuevas versiones de configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="d2834-261">Sin embargo, desea poder realizar la actualización al menor costo.</span><span class="sxs-lookup"><span data-stu-id="d2834-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="d2834-262">En este caso, como representante de Litware, Inc., debe crear (derivar) una nueva configuración de formato ER utilizando **BACS (Reino Unido)**, configuración proporcionada por Microsoft como base.</span><span class="sxs-lookup"><span data-stu-id="d2834-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="d2834-263">Crear un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-263">Create a custom format</span></span>

1. <span data-ttu-id="d2834-264">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="d2834-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d2834-265">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="d2834-266">Litware, Inc. utilizará la versión 1.1 de esta configuración de formato ER como base para la versión personalizada.</span><span class="sxs-lookup"><span data-stu-id="d2834-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="d2834-267">Seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d2834-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="d2834-268">Puede usar este cuadro de diálogo para crear una nueva configuración para un formato de pago personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2834-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="d2834-269">En el grupo de campos **Nuevo**, seleccione la opción **Derivar del nombre: BACS (Reino Unido), Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d2834-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="d2834-270">En el campo **Nombre**, introduzca **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Cuadro de diálogo desplegable Crear configuración](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="d2834-272">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="d2834-272">Select **Create configuration**.</span></span>

<span data-ttu-id="d2834-273">Se creará la versión 1.1.1 del formato de configuración de ER **BACS (personalizado del Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="d2834-274">Esta versión tiene un [estado](general-electronic-reporting.md#component-versioning) de **Borrador** y puede editarse.</span><span class="sxs-lookup"><span data-stu-id="d2834-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="d2834-275">El contenido actual de su formato ER personalizado coincide con el contenido del formato proporcionado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2834-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Página Configuraciones](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="d2834-277">Editar un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-277">Edit a custom format</span></span>

<span data-ttu-id="d2834-278">Debe configurar su formato personalizado para que cumpla con los requisitos específicos del banco.</span><span class="sxs-lookup"><span data-stu-id="d2834-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="d2834-279">Por ejemplo, un banco puede requerir que los archivos de pago que se generan incluyan el código SWIFT (Society for Worldwide Interbank Financial Telecommunication) de un banco al que se le asigna la función de agente en el pago del proveedor procesado.</span><span class="sxs-lookup"><span data-stu-id="d2834-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="d2834-280">Los códigos SWIFT son códigos bancarios internacionales que identifican bancos específicos en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="d2834-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="d2834-281">También se conocen como códigos de identificación bancaria (BIC).</span><span class="sxs-lookup"><span data-stu-id="d2834-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="d2834-282">El código SWIFT debe tener 11 caracteres y debe introducirse al comienzo de cada línea de pago en un archivo de pago generado.</span><span class="sxs-lookup"><span data-stu-id="d2834-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="d2834-283">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="d2834-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d2834-284">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="d2834-285">En la ficha desplegable **Versiones**, seleccione la versión **1.1.1** de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2834-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="d2834-286">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="d2834-286">Select **Designer**.</span></span>
5. <span data-ttu-id="d2834-287">En la página del **Diseñador de formato**, seleccione **Mostrar detalles** para ver más información sobre los elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="d2834-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="d2834-288">Expanda y revise los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="d2834-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="d2834-289">El elemento **BACSReportsFolder** del tipo **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="d2834-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="d2834-290">Este elemento se utiliza para generar resultados en formato ZIP.</span><span class="sxs-lookup"><span data-stu-id="d2834-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="d2834-291">El elemento **archivo** del tipo **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="d2834-292">Este elemento se utiliza para generar un archivo de pago en formato TXT.</span><span class="sxs-lookup"><span data-stu-id="d2834-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="d2834-293">El elemento **transacciones** del tipo **Secuencia**.</span><span class="sxs-lookup"><span data-stu-id="d2834-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="d2834-294">Este elemento se utiliza para generar una línea de pago único en archivo de pago.</span><span class="sxs-lookup"><span data-stu-id="d2834-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="d2834-295">El elemento **transacción** del tipo **Secuencia**.</span><span class="sxs-lookup"><span data-stu-id="d2834-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="d2834-296">Este elemento se utiliza para generar campos individuales de una línea de pago único.</span><span class="sxs-lookup"><span data-stu-id="d2834-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="d2834-297">Seleccione el elemento **transacción**.</span><span class="sxs-lookup"><span data-stu-id="d2834-297">Select the **transaction** element.</span></span>

    ![Elemento de transacción en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="d2834-299">El informe proporcionado se configura de modo que <a id="PositionRoutingNumber"></a>cada línea de pago comienza con el número de ruta bancaria.</span><span class="sxs-lookup"><span data-stu-id="d2834-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="d2834-300">El elemento de formato **vendBankRouteNum** se utiliza para este propósito.</span><span class="sxs-lookup"><span data-stu-id="d2834-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="d2834-301">Seleccione **Agregar** y luego seleccione el tipo **Texto\\Cadena** del elemento de formato que está agregando:</span><span class="sxs-lookup"><span data-stu-id="d2834-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="d2834-302">En el campo **Nombre**, introduzca **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="d2834-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="d2834-303">En el campo **Longitud mínima**, introduzca **11**.</span><span class="sxs-lookup"><span data-stu-id="d2834-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="d2834-304">En el campo **Longitud máxima**, introduzca **11**.</span><span class="sxs-lookup"><span data-stu-id="d2834-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="d2834-305">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2834-306">El elemento **vendBankSWIFT** se usará para introducir el código SWIFT de un banco de proveedores en los archivos generados.</span><span class="sxs-lookup"><span data-stu-id="d2834-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="d2834-307">En el árbol de estructura de formato, seleccione **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="d2834-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="d2834-308">Seleccione **Ascender** para mover el elemento de formato seleccionado un nivel hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="d2834-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="d2834-309">Repita este paso hasta que el elemento **vendBankSWIFT** es el <a id="PositionSWIFTCode"></a>primer elemento debajo del elemento primario **transacción**.</span><span class="sxs-lookup"><span data-stu-id="d2834-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT como el primer elemento bajo transacción en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="d2834-311">Mientras **vendBankSWIFT** está todavía está seleccionado en el árbol de estructura de formato, seleccione la pestaña **Asignación** y luego expanda la fuente de datos **modelo**.</span><span class="sxs-lookup"><span data-stu-id="d2834-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="d2834-312">Expanda **model.Payment** \> **model.Payment.CreditorAgent** y seleccione el campo de fuente de datos **model.Payment.CreditorAgent.BICFI**.</span><span class="sxs-lookup"><span data-stu-id="d2834-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="d2834-313">Este campo de fuente de datos expone el código SWIFT de un banco proveedor al que se le asigna el rol de agente en el pago del proveedor procesado.</span><span class="sxs-lookup"><span data-stu-id="d2834-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="d2834-314">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-314">Select **Bind**.</span></span> <span data-ttu-id="d2834-315">El elemento de formato **vendBankSWIFT** ahora está vinculado con el campo de fuente de datos **model.Payment.CreditorAgent.BICFI** para que los códigos SWIFT se introduzcan en los archivos de pago generados.</span><span class="sxs-lookup"><span data-stu-id="d2834-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![El elemento de formato vendBankSWIFT vinculado con el campo de origen de datos model.Payment.CreditorAgent.BICFI en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="d2834-317">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-317">Select **Save**.</span></span>
15. <span data-ttu-id="d2834-318">Cierre la página del diseñador.</span><span class="sxs-lookup"><span data-stu-id="d2834-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="d2834-319">Marcar un formato personalizado como ejecutable</span><span class="sxs-lookup"><span data-stu-id="d2834-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="d2834-320">Ahora que se ha creado la primera versión de su formato personalizado y tiene un estado de **Borrador**, puede ejecutarlo con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="d2834-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="d2834-321">Para ejecutar el informe, debe procesar un pago de proveedor utilizando el método de pago que se refiere a su formato ER personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2834-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="d2834-322">De forma predeterminada, cuando llama a un formato de ER desde la aplicación, las únicas versiones que tienen un estado de **Completado** o **Compartido** son las que se [consideran](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="d2834-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="d2834-323">Este comportamiento ayuda a evitar el uso de formatos ER que tienen diseños inacabados.</span><span class="sxs-lookup"><span data-stu-id="d2834-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="d2834-324">Sin embargo, para sus ejecuciones de prueba, puede obligar a la aplicación a usar la versión de su formato ER que tenga un estado de **Borrador**.</span><span class="sxs-lookup"><span data-stu-id="d2834-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="d2834-325">De esta manera, puede ajustar la versión del formato actual si se requieren modificaciones.</span><span class="sxs-lookup"><span data-stu-id="d2834-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="d2834-326">Para obtener más información, consulte [Aplicabilidad](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="d2834-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="d2834-327">Para utilizar la versión borrador de un formato ER, debe marcar de forma explícita el formato ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="d2834-328">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="d2834-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d2834-329">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d2834-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="d2834-330">En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="d2834-331">Seleccione **Editar** para hacer que la página actual sea editable, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d2834-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="d2834-332">En el árbol de configuración en el panel izquierdo, seleccione **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="d2834-333">Establezca la opción **Ejecutar borrador** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Opción Ejecutar borrador en la página Configuraciones](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="d2834-335">Procesar un pago de proveedor utilizando el formato ER personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="d2834-336">Configurar la forma de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="d2834-336">Set up the electronic payment method</span></span>

<span data-ttu-id="d2834-337">Debe configurar el método de pago electrónico para que se utilice su formato ER personalizado para procesar los pagos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d2834-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="d2834-338">Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="d2834-339">En la página **Métodos de pago - proveedores**, seleccione el método de pago **Electrónico** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d2834-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="d2834-340">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-340">Select **Edit**.</span></span>
4. <span data-ttu-id="d2834-341">En la ficha desplegable **Formato de archivo**, establezca la opción **Formato de exportación electrónica general** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="d2834-342">En el campo **Configuración de formato de exportación**, seleccione la configuración de formato **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Métodos de pago - página de proveedores](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="d2834-344">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="d2834-345">Procesar un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d2834-345">Process a vendor payment</span></span>

1. <span data-ttu-id="d2834-346">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="d2834-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d2834-347">En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d2834-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="d2834-348">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="d2834-348">Select **Lines**.</span></span>
4. <span data-ttu-id="d2834-349">En la página **Pagos de proveedores**, sobre la cuadrícula, seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="d2834-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="d2834-350">Seleccione **Generar pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="d2834-351">En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d2834-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d2834-352">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d2834-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d2834-353">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d2834-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="d2834-354">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-354">Select **OK**.</span></span>
8. <span data-ttu-id="d2834-355">En el cuadro de diálogo **Parámetros de informes electrónicos**, establezca la opción **Imprimir informe de control** a **Sí** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2834-356">Además del archivo de pago, solo puede generar el informe de control.</span><span class="sxs-lookup"><span data-stu-id="d2834-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="d2834-357">Descargue el archivo zip y luego extraiga los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="d2834-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d2834-358">El informe de control en formato Excel</span><span class="sxs-lookup"><span data-stu-id="d2834-358">The control report in Excel format</span></span>
    - <span data-ttu-id="d2834-359">El archivo de pago en formato TXT</span><span class="sxs-lookup"><span data-stu-id="d2834-359">The payment file in TXT format</span></span>

        <span data-ttu-id="d2834-360">Observe que, de acuerdo con la estructura de su formato ER personalizado, la línea de pago en el archivo generado ahora [empieza](#PositionSWIFTCode) con el código SWIFT que [introdujo](#DefineSWIFTCode) para la cuenta bancaria del proveedor cuyo pago ha sido procesado.</span><span class="sxs-lookup"><span data-stu-id="d2834-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="d2834-362">Importar nuevas versiones de las configuraciones del formato estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="d2834-363">Para el ejemplo que se muestra en esta sección, recibirá una notificación sobre el artículo de Knowledge Base [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="d2834-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="d2834-364">Esta notificación le informa sobre la nueva versión del formato de ER **BACS (Reino Unido)** que ha sido publicado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2834-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="d2834-365">Además del informe de control, esta nueva versión permite a los usuarios generar el informe de aviso de pago y el informe de la nota de asistencia mientras se procesa el pago de un proveedor.</span><span class="sxs-lookup"><span data-stu-id="d2834-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="d2834-366">Desea comenzar a usar esa funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d2834-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="d2834-367">Importar nuevas versiones de las configuraciones estándar de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="d2834-368">Para agregar nuevas versiones de las configuraciones ER a su instancia actual de Finance, debe importarlos desde el [repositorio](general-electronic-reporting.md#Repository) de ER que configuró para esa instancia.</span><span class="sxs-lookup"><span data-stu-id="d2834-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="d2834-369">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-370">En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2834-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="d2834-371">En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d2834-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="d2834-372">Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.</span><span class="sxs-lookup"><span data-stu-id="d2834-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="d2834-373">En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="d2834-374">En la ficha desplegable **Versiones**, seleccione la versión **3.3** de la configuración de ER seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2834-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="d2834-375">Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="d2834-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Página de configuración del repositorio](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="d2834-377">Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de LCS en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d2834-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="d2834-378">Revisar las configuraciones de formato importadas de ER</span><span class="sxs-lookup"><span data-stu-id="d2834-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="d2834-379">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-380">En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="d2834-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d2834-381">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="d2834-382">En la ficha desplegable **Versiones**, seleccione la versión **3.3**.</span><span class="sxs-lookup"><span data-stu-id="d2834-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="d2834-383">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="d2834-383">Select **Designer**.</span></span>
6. <span data-ttu-id="d2834-384">Sobre la página **Diseñador de formatos** página, expanda el elemento de formato **BACSReportsFolder**.</span><span class="sxs-lookup"><span data-stu-id="d2834-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="d2834-385">Tenga en cuenta que la versión 3.3 contiene el elemento de formato **PaymentAdviceReport** que se utiliza para generar un informe de aviso de pago cuando se procesa un pago de proveedor.</span><span class="sxs-lookup"><span data-stu-id="d2834-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![Elemento de formato PaymentAdviceReport en el diseñador de operaciones de ER](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="d2834-387">Cierre la página del diseñador.</span><span class="sxs-lookup"><span data-stu-id="d2834-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="d2834-388">Adoptar los cambios en la nueva versión de un formato importado en un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="d2834-389">Completar la versión actual de borrador de un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d2834-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="d2834-390">Si desea mantener el estado actual de su formato personalizado, complete el borrador de la versión 1.1.1 cambiando su estado de **Borrador** a **Completado**.</span><span class="sxs-lookup"><span data-stu-id="d2834-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="d2834-391">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="d2834-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d2834-392">En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="d2834-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d2834-393">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago**, expanda **BACS (Reino Unido)** y seleccione **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="d2834-394">En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="d2834-395">El estado de la versión 1.1.1 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura.</span><span class="sxs-lookup"><span data-stu-id="d2834-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="d2834-396">Se ha agregado una nueva versión editable, 1.1.2, y tiene un estado de **Borrador**.</span><span class="sxs-lookup"><span data-stu-id="d2834-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="d2834-397">Puede usar esta versión para realizar más cambios en su formato ER personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2834-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="d2834-398">Reorganizar un formato personalizado a una nueva versión base</span><span class="sxs-lookup"><span data-stu-id="d2834-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="d2834-399">Para comenzar a utilizar la nueva funcionalidad de la versión 3.3 del formato **BACS (Reino Unido)** en su personalización, debe cambiar la versión de configuración básica para la configuración personalizada, **BACS (personalizado del Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="d2834-400">Este proceso se conoce como [reorganización](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span><span class="sxs-lookup"><span data-stu-id="d2834-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="d2834-401">En lugar de la versión 1.1 de **BACS (Reino Unido)**, use la nueva versión 3.3.</span><span class="sxs-lookup"><span data-stu-id="d2834-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="d2834-402">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="d2834-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d2834-403">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="d2834-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="d2834-404">En la ficha desplegable **Versiones**, seleccione versión **1.1.2** y luego seleccione **Reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="d2834-405">En el cuadro de diálogo **Reorganizar**, en el campo **Versión de destino**, seleccione la versión **3.3** de la configuración base para aplicarla como la nueva base y usarla para actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="d2834-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Cuadro de diálogo Cambiar de base](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="d2834-407">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-407">Select **OK**.</span></span>
6. <span data-ttu-id="d2834-408">Observe que el número de la versión borrador ha cambiado de **1.1.2** a **3.3.2** para reflejar el cambio en la versión base.</span><span class="sxs-lookup"><span data-stu-id="d2834-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="d2834-409">Cuando se combinaron la versión personalizada y la nueva versión base, puede que se hayan descubierto algunos conflictos debidos a los cambios de formato que no se pueden combinar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d2834-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Configuración reorganizada con conflictos en la página Configuraciones](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="d2834-411">Si se descubren conflictos, deben resolverse manualmente en el diseñador de formatos.</span><span class="sxs-lookup"><span data-stu-id="d2834-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="d2834-412">En la ficha desplegable **Versiones**, seleccione la versión **3.3.2**.</span><span class="sxs-lookup"><span data-stu-id="d2834-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="d2834-413">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="d2834-413">Select **Designer**.</span></span>
9. <span data-ttu-id="d2834-414">En la página **Diseñador de formatos**, en la ficha desplegable **Detalles**, seleccione un registro de conflicto de reorganización y luego seleccione **Aplicar valor base**.</span><span class="sxs-lookup"><span data-stu-id="d2834-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Registro de conflicto de reorganización en el diseñador de operaciones de ER](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="d2834-416">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-416">Select **Save**.</span></span>

    <span data-ttu-id="d2834-417">El registro de conflicto de reorganización ya no debería aparecer en la ficha desplegable **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d2834-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Conflicto resuelto en el diseñador de operaciones de ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="d2834-419">Usted resolvió el conflicto confirmando que la versión 3 del modelo base debe usarse en este formato ER.</span><span class="sxs-lookup"><span data-stu-id="d2834-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="d2834-420">Expandir **BACSReportsFolder** \> **archivo** \> **transacciones** \> **transacción**.</span><span class="sxs-lookup"><span data-stu-id="d2834-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="d2834-421">En la pestaña **Asignación**, observe que la versión 3.3.2 de su formato ER personalizado contiene tanto su personalización (el elemento de formato **vendBankSWIFT** y su vinculación) y la nueva funcionalidad de la versión 3.3 del formato ER básico que proporcionó Microsoft (el elemento de formato **PaymentAdviceReport** junto con sus elementos anidados y enlaces configurados).</span><span class="sxs-lookup"><span data-stu-id="d2834-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="d2834-422">Con solo unas pocas pulsaciones del ratón, adoptó las modificaciones de una nueva versión base fusionándolas con su personalización.</span><span class="sxs-lookup"><span data-stu-id="d2834-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Formato combinado en el diseñador de operaciones ER](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="d2834-424">Cierre la página del diseñador.</span><span class="sxs-lookup"><span data-stu-id="d2834-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="d2834-425">La acción de reorganización es reversible.</span><span class="sxs-lookup"><span data-stu-id="d2834-425">The rebase action is reversible.</span></span> <span data-ttu-id="d2834-426">Para cancelar esta reorganización, seleccione la versión **1.1.1** del formato **BACS (Reino Unido personalizado)** en la ficha desplegable **Versiones** y luego seleccione **Obtener esta versión**.</span><span class="sxs-lookup"><span data-stu-id="d2834-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="d2834-427">La versión 3.3.2 se volverá a numerar 1.1.2 y el contenido de la versión borrador 1.1.2 coincidirá con el contenido de la versión 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="d2834-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="d2834-428">Procesar un pago de proveedor utilizando un formato de ER reorganizado</span><span class="sxs-lookup"><span data-stu-id="d2834-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="d2834-429">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="d2834-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d2834-430">En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d2834-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="d2834-431">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="d2834-431">Select **Lines**.</span></span>
4. <span data-ttu-id="d2834-432">En la página **Pagos de proveedores**, sobre la cuadrícula, seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="d2834-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="d2834-433">Seleccione **Generar pago**.</span><span class="sxs-lookup"><span data-stu-id="d2834-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="d2834-434">En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d2834-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d2834-435">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d2834-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d2834-436">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d2834-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="d2834-437">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-437">Select **OK**.</span></span>
8. <span data-ttu-id="d2834-438">En el cuadro de diálogo **Parámetros de informe electrónico**, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d2834-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d2834-439">Establezca la opción **Imprimir informe de control** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="d2834-440">Establezca la opción **Imprimir** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2834-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Cuadro de diálogo Parámetros de notificación electrónica](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="d2834-442">Además del archivo de pago, ahora puede generar tanto el informe de control como el informe de aviso de pago.</span><span class="sxs-lookup"><span data-stu-id="d2834-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="d2834-443">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2834-443">Select **OK**.</span></span>
10. <span data-ttu-id="d2834-444">Descargue el archivo zip y luego extraiga los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="d2834-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d2834-445">El informe de control en formato Excel</span><span class="sxs-lookup"><span data-stu-id="d2834-445">The control report in Excel format</span></span>
    - <span data-ttu-id="d2834-446">El informe de aviso de pago en formato Excel</span><span class="sxs-lookup"><span data-stu-id="d2834-446">The payment advice report in Excel format</span></span>

        ![Informe de aviso de pago en formato Excel](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="d2834-448">El archivo de pago en formato TXT</span><span class="sxs-lookup"><span data-stu-id="d2834-448">The payment file in TXT format</span></span>

        <span data-ttu-id="d2834-449">Observe que la línea de pago en el archivo generado ahora empieza con el código SWIFT que introdujo para la cuenta bancaria de un proveedor cuyo pago ha sido procesado.</span><span class="sxs-lookup"><span data-stu-id="d2834-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="d2834-451">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d2834-451">Additional resources</span></span>

- [<span data-ttu-id="d2834-452">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d2834-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="d2834-453">Descargar configuraciones ER de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="d2834-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="d2834-454">Descargue las configuraciones de ER del repositorio global del servicio de configuración</span><span class="sxs-lookup"><span data-stu-id="d2834-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]