---
title: Comenzar con la administración de servicios de facturación electrónica
description: Este tema explica cómo comenzar con la facturación electrónica.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840157"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="ad310-103">Comenzar con la administración de servicios de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="ad310-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="ad310-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ad310-104">Prerequisites</span></span>

<span data-ttu-id="ad310-105">Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="ad310-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="ad310-106">Debe tener acceso a su cuenta de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="ad310-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="ad310-107">Debe tener un proyecto LCS que incluya la versión 10.0.17 o posterior de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ad310-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="ad310-108">Además, estas aplicaciones deben implementarse en una de las siguientes áreas geográficas de Azure:</span><span class="sxs-lookup"><span data-stu-id="ad310-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="ad310-109">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-109">East US</span></span>
    - <span data-ttu-id="ad310-110">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-110">West US</span></span>
    - <span data-ttu-id="ad310-111">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-111">North EU</span></span>
    - <span data-ttu-id="ad310-112">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-112">West EU</span></span>

- <span data-ttu-id="ad310-113">Debe tener acceso a su cuenta de Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="ad310-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="ad310-114">Debe activar la característica de globalización para su cuenta RCS a través del módulo de administración de características.</span><span class="sxs-lookup"><span data-stu-id="ad310-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="ad310-115">Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="ad310-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="ad310-116">Debe crear un almacén de claves y una cuenta de almacenamiento en Azure.</span><span class="sxs-lookup"><span data-stu-id="ad310-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="ad310-117">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="ad310-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="ad310-118">Instalar el complemento para microservicios en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="ad310-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="ad310-119">Inicie sesión en su cuenta de LCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="ad310-120">Seleccione el mosaico **Gestión de características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="ad310-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="ad310-121">En la sección **Funciones de versión preliminar pública**, seleccione **Servicio de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ad310-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="ad310-122">Compruebe que la opción **Característica en vista previa** esté establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ad310-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="ad310-123">En su panel de LCS, seleccione su proyecto de implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="ad310-124">El proyecto LCS debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad310-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="ad310-125">En la pestaña **Complementos de ambiente**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="ad310-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="ad310-126">Seleccione **Servicios de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ad310-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="ad310-127">En el campo **Id. de la aplicación AAD**, introduzca **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="ad310-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="ad310-128">Este valor es fijo.</span><span class="sxs-lookup"><span data-stu-id="ad310-128">This is a fixed value.</span></span>
10. <span data-ttu-id="ad310-129">En el campo **Id. de inquilino de AAD**, introduzca el id. de su cuenta de suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="ad310-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="ad310-130">Revise los términos y condiciones, y luego seleccione la casilla.</span><span class="sxs-lookup"><span data-stu-id="ad310-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="ad310-131">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="ad310-132">Configurar los parámetros para la integración de RCS con la facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="ad310-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="ad310-133">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="ad310-134">En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="ad310-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="ad310-135">En la pestaña **Servicio de facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ad310-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="ad310-136">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="ad310-136">Datacenter Azure geography</span></span> | <span data-ttu-id="ad310-137">Identificador URI de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="ad310-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="ad310-138">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-139">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-140">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-141">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="ad310-142">Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="ad310-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="ad310-143">Este valor es un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="ad310-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="ad310-144">En el campo **Id. de entorno de LCS**, introduzca el id. de su ambiente de LCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="ad310-145">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="ad310-146">Crear referencias de Key Vault</span><span class="sxs-lookup"><span data-stu-id="ad310-146">Create Key Vault references</span></span>

1. <span data-ttu-id="ad310-147">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="ad310-148">En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ad310-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="ad310-149">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="ad310-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="ad310-150">Seleccione **Nuevo** para crear una referencia de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="ad310-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="ad310-151">En el campo **Nombre**, especifique el nombre de la referencia del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="ad310-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="ad310-152">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ad310-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="ad310-153">En el campo **URI de Key Vault**, pegue el secreto del almacén de claves de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="ad310-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="ad310-154">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="ad310-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="ad310-155">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="ad310-156">Crear secreto de cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="ad310-156">Create Storage account secret</span></span>

1. <span data-ttu-id="ad310-157">En la página **Configuraciones de ambiente**, en el panel de acciones, seleccione **Entorno de servicio** > **Parámetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="ad310-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="ad310-158">Seleccione una **Referencia de Key Vault** y, en la sección **Certificados**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="ad310-159">En el campo **Nombre**, introduzca el nombre del secreto de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ad310-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="ad310-160">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="ad310-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="ad310-161">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ad310-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ad310-162">En el campo **Tipo**, seleccione **Secreto**.</span><span class="sxs-lookup"><span data-stu-id="ad310-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="ad310-163">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="ad310-164">Crear un secreto de certificado digital</span><span class="sxs-lookup"><span data-stu-id="ad310-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="ad310-165">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="ad310-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="ad310-166">Seleccione una **Referencia de Key Vault** y luego, en la sección **Certificados**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="ad310-167">En el campo **Nombre**, introduzca el nombre del secreto del certificado digital.</span><span class="sxs-lookup"><span data-stu-id="ad310-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="ad310-168">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="ad310-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="ad310-169">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ad310-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ad310-170">En el campo **Tipo**, seleccione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="ad310-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="ad310-171">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="ad310-172">Crear un entorno de servicio</span><span class="sxs-lookup"><span data-stu-id="ad310-172">Create a service environment</span></span>

1. <span data-ttu-id="ad310-173">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="ad310-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="ad310-174">En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ad310-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="ad310-175">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio**.</span><span class="sxs-lookup"><span data-stu-id="ad310-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="ad310-176">Seleccione **Nuevo** para crear un nuevo entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="ad310-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="ad310-177">En el campo **Nombre**, especifique el nombre del entorno de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="ad310-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="ad310-178">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ad310-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="ad310-179">En el campo **Secreto de token SAS de almacenamiento**, seleccione el nombre del secreto de cuenta de almacenamiento que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ad310-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="ad310-180">En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y también conectarse a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ad310-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="ad310-181">En el campo **Id. de usuario**, introduzca el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="ad310-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="ad310-182">En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="ad310-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="ad310-183">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-183">Select **Save**.</span></span>
10. <span data-ttu-id="ad310-184">Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales, seleccione **Parámetros del almacén de claves** en el Panel de acciones y luego seleccione **Cadena de certificados** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ad310-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="ad310-185">Seleccione **Nuevo** para crear una cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="ad310-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="ad310-186">En el campo **Nombre**, introduzca el nombre de la cadena de certificado.</span><span class="sxs-lookup"><span data-stu-id="ad310-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="ad310-187">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ad310-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="ad310-188">En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.</span><span class="sxs-lookup"><span data-stu-id="ad310-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="ad310-189">Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena.</span><span class="sxs-lookup"><span data-stu-id="ad310-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="ad310-190">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="ad310-191">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-191">Close the page.</span></span>
11. <span data-ttu-id="ad310-192">En la página **Entorno de servicio**, seleccione **Publicar** en el panel de acciones para publicar el entorno en la nube.</span><span class="sxs-lookup"><span data-stu-id="ad310-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="ad310-193">El valor del campo **Estado** se cambia a **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="ad310-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="ad310-194">Crear una aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="ad310-194">Create a connected application</span></span>

1. <span data-ttu-id="ad310-195">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="ad310-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="ad310-196">Seleccione **Nuevo** para crear una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="ad310-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="ad310-197">En el campo **Nombre**, especifique el nombre de la aplicación a conectar.</span><span class="sxs-lookup"><span data-stu-id="ad310-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="ad310-198">En el campo **Aplicación**, introduzca la URL del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="ad310-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="ad310-199">En el campo **Inquilino**, introduzca el inquilino del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="ad310-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="ad310-200">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad310-200">Select **Save**.</span></span>
6. <span data-ttu-id="ad310-201">En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno.</span><span class="sxs-lookup"><span data-stu-id="ad310-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="ad310-202">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="ad310-203">Vincular aplicaciones conectadas a entornos</span><span class="sxs-lookup"><span data-stu-id="ad310-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="ad310-204">En la página **Configuraciones de entorno**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.</span><span class="sxs-lookup"><span data-stu-id="ad310-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="ad310-205">En el campo **Aplicación conectada**, seleccione una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="ad310-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="ad310-206">En el campo **Entorno de servicio**, seleccione un entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="ad310-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="ad310-207">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="ad310-208">Configurar la integración de la facturación electrónica en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ad310-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="ad310-209">Active la característica de integración de la facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="ad310-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="ad310-210">Inicie sesión en su instancia de Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ad310-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="ad310-211">En el espacio de trabajo **Administración de características**, busque la característica, **Integración de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ad310-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="ad310-212">Si esta característica no aparece en la página, seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="ad310-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="ad310-213">Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="ad310-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="ad310-214">Configurar la URL del punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="ad310-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="ad310-215">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="ad310-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="ad310-216">En la pestaña **Servicio de envío**, en el campo **URL de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ad310-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="ad310-217">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="ad310-217">Datacenter Azure geography</span></span> | <span data-ttu-id="ad310-218">URL de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="ad310-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="ad310-219">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-220">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ad310-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-221">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="ad310-222">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="ad310-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="ad310-223">En el campo **Ambiente**, especifique el nombre del ambiente de servicio publicado en facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="ad310-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="ad310-224">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad310-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="ad310-225">Habilitar claves de tramo</span><span class="sxs-lookup"><span data-stu-id="ad310-225">Enable Flighting keys</span></span>

<span data-ttu-id="ad310-226">Habilite las claves de tramo para Microsoft Dynamics 365 Finance o Microsoft Dynamics 365 Supply Chain Management, versiones 10.0.17 o anteriores.</span><span class="sxs-lookup"><span data-stu-id="ad310-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="ad310-227">Ejecute el siguiente comando SQL:</span><span class="sxs-lookup"><span data-stu-id="ad310-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="ad310-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="ad310-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="ad310-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="ad310-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="ad310-230">Ejecute un comando IISreset para todos los Microsoft Dynamics AX Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="ad310-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
