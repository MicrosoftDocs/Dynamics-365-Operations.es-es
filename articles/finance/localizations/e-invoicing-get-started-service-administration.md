---
title: Comenzar con la administración del servicio del complemento de facturación electrónica
description: Este tema explica cómo comenzar con el complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592535"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="98b96-103">Comenzar con la administración del servicio del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="98b96-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="98b96-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="98b96-104">Prerequisites</span></span>

<span data-ttu-id="98b96-105">Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="98b96-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="98b96-106">Debe tener acceso a su cuenta de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="98b96-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="98b96-107">Debe tener un proyecto LCS que incluya la versión 10.0.17 o posterior de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="98b96-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="98b96-108">Además, estas aplicaciones deben implementarse en una de las siguientes áreas geográficas de Azure:</span><span class="sxs-lookup"><span data-stu-id="98b96-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="98b96-109">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-109">East US</span></span>
    - <span data-ttu-id="98b96-110">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-110">West US</span></span>
    - <span data-ttu-id="98b96-111">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-111">North EU</span></span>
    - <span data-ttu-id="98b96-112">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-112">West EU</span></span>

- <span data-ttu-id="98b96-113">Debe tener acceso a su cuenta de Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="98b96-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="98b96-114">Debe activar la característica de globalización para su cuenta RCS a través del módulo de administración de características.</span><span class="sxs-lookup"><span data-stu-id="98b96-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="98b96-115">Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="98b96-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="98b96-116">Debe crear un almacén de claves y una cuenta de almacenamiento en Azure.</span><span class="sxs-lookup"><span data-stu-id="98b96-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="98b96-117">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="98b96-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="98b96-118">Instalar el complemento para microservicios en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="98b96-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="98b96-119">Inicie sesión en su cuenta de LCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="98b96-120">Seleccione el mosaico **Gestión de características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="98b96-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="98b96-121">En la sección **Funciones de versión preliminar pública**, seleccione **Servicio de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="98b96-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="98b96-122">Compruebe que la opción **Característica en vista previa** esté establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="98b96-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="98b96-123">En su panel de LCS, seleccione su proyecto de implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="98b96-124">El proyecto LCS debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="98b96-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="98b96-125">En la pestaña **Complementos de ambiente**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="98b96-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="98b96-126">Seleccione **Servicios de facturación electrónica** y, en el **Id. de la aplicación AAD**, introduzca **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="98b96-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="98b96-127">Este valor es fijo.</span><span class="sxs-lookup"><span data-stu-id="98b96-127">This is a fixed value.</span></span>
10. <span data-ttu-id="98b96-128">En el campo **Id. de inquilino de AAD**, introduzca el id. de su cuenta de suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="98b96-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="98b96-129">Revise los términos y condiciones, y luego seleccione la casilla.</span><span class="sxs-lookup"><span data-stu-id="98b96-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="98b96-130">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="98b96-131">Configurar los parámetros para la integración de RCS con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="98b96-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="98b96-132">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98b96-133">En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="98b96-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="98b96-134">En la pestaña **Servicio de facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="98b96-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="98b96-135">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="98b96-135">Datacenter Azure geography</span></span> | <span data-ttu-id="98b96-136">Identificador URI de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="98b96-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="98b96-137">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-138">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-139">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-140">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="98b96-141">Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="98b96-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="98b96-142">Este valor es un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="98b96-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="98b96-143">En el campo **Id. de entorno de LCS**, introduzca el id. de su cuenta de suscripción de LCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="98b96-144">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="98b96-145">Crear secretos de Key Vault</span><span class="sxs-lookup"><span data-stu-id="98b96-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="98b96-146">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98b96-147">En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Complemento de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="98b96-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="98b96-148">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="98b96-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="98b96-149">Seleccione **Nuevo** para crear un secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="98b96-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="98b96-150">En el campo **Nombre**, especifique el nombre del secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="98b96-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="98b96-151">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="98b96-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="98b96-152">En el campo **URI de Key Vault**, pegue el secreto de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="98b96-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="98b96-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="98b96-154">Crear secreto de cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="98b96-154">Create Storage account secret</span></span>

1. <span data-ttu-id="98b96-155">Vaya a **Administracion del sistema** > **Configuración** > **Parámetros de Key Vault** y seleccione un secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="98b96-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="98b96-156">En la sección **Certificados**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="98b96-157">En el campo **Nombre**, introduzca el nombre del secreto de la cuenta de almacenamiento y, en el campo **Descripción**, introduzca una descripción.</span><span class="sxs-lookup"><span data-stu-id="98b96-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="98b96-158">En el campo **Tipo**, seleccione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="98b96-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="98b96-159">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="98b96-160">Crear un secreto de certificado digital</span><span class="sxs-lookup"><span data-stu-id="98b96-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="98b96-161">Vaya a **Administracion del sistema** > **Configuración** > **Parámetros de Key Vault** y seleccione un secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="98b96-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="98b96-162">En la sección **Certificados**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="98b96-163">En el campo **Nombre**, introduzca el nombre del secreto del certificado digital y, en el campo **Descripción**, introduzca una descripción.</span><span class="sxs-lookup"><span data-stu-id="98b96-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="98b96-164">En el campo **Tipo**, seleccione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="98b96-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="98b96-165">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="98b96-166">Crear un entorno del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="98b96-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="98b96-167">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="98b96-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98b96-168">En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Complemento de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="98b96-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="98b96-169">Crear un entorno de servicio</span><span class="sxs-lookup"><span data-stu-id="98b96-169">Create a service environment</span></span>

1. <span data-ttu-id="98b96-170">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio**.</span><span class="sxs-lookup"><span data-stu-id="98b96-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="98b96-171">Seleccione **Nuevo** para crear un nuevo entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="98b96-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="98b96-172">En el campo **Nombre**, especifique el nombre del entorno de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="98b96-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="98b96-173">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="98b96-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="98b96-174">En el campo **Secreto de token SAS de almacenamiento**, seleccione el nombre del secreto de cuenta de almacenamiento que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="98b96-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="98b96-175">En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y también conectarse a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="98b96-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="98b96-176">En el campo **Id. de usuario**, introduzca el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="98b96-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="98b96-177">En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="98b96-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="98b96-178">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-178">Select **Save**.</span></span>
8. <span data-ttu-id="98b96-179">Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales, seleccione **Parámetros del almacén de claves** en el Panel de acciones y luego seleccione **Cadena de certificados** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98b96-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="98b96-180">Seleccione **Nuevo** para crear una cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="98b96-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="98b96-181">En el campo **Nombre**, introduzca el nombre de la cadena de certificado.</span><span class="sxs-lookup"><span data-stu-id="98b96-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="98b96-182">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="98b96-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="98b96-183">En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.</span><span class="sxs-lookup"><span data-stu-id="98b96-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="98b96-184">Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena.</span><span class="sxs-lookup"><span data-stu-id="98b96-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="98b96-185">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="98b96-186">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-186">Close the page.</span></span>
9. <span data-ttu-id="98b96-187">En la página **Entorno de servicio**, seleccione **Publicar** en el panel de acciones para publicar el entorno en la nube.</span><span class="sxs-lookup"><span data-stu-id="98b96-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="98b96-188">El valor del campo **Estado** se cambia a **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="98b96-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="98b96-189">Crear una aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="98b96-189">Create a connected application</span></span>

1. <span data-ttu-id="98b96-190">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="98b96-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="98b96-191">Seleccione **Nuevo** para crear una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="98b96-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="98b96-192">En el campo **Nombre**, especifique el nombre de la aplicación a conectar.</span><span class="sxs-lookup"><span data-stu-id="98b96-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="98b96-193">En el campo **Aplicación**, introduzca la URL del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="98b96-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="98b96-194">En el campo **Inquilino**, introduzca el inquilino del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="98b96-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="98b96-195">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98b96-195">Select **Save**.</span></span>
6. <span data-ttu-id="98b96-196">En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno.</span><span class="sxs-lookup"><span data-stu-id="98b96-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="98b96-197">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="98b96-198">Vincular aplicaciones conectadas a entornos</span><span class="sxs-lookup"><span data-stu-id="98b96-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="98b96-199">En la página **Configuraciones de entorno**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.</span><span class="sxs-lookup"><span data-stu-id="98b96-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="98b96-200">En el campo **Aplicación conectada**, seleccione una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="98b96-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="98b96-201">En el campo **Entorno de servicio**, seleccione un entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="98b96-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="98b96-202">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="98b96-203">Configurar la integración del complemento de facturación electrónica en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="98b96-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="98b96-204">Active la característica de integración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="98b96-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="98b96-205">Inicie sesión en su instancia de Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="98b96-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="98b96-206">En el espacio de trabajo **Administración de características**, busque la nueva característica, **Integración de complemento de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="98b96-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="98b96-207">Si esta característica no aparece en la página, seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="98b96-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="98b96-208">Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="98b96-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="98b96-209">Configurar la URL del punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="98b96-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="98b96-210">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="98b96-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="98b96-211">En la pestaña **Servicio de envío**, en el campo **URL de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="98b96-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="98b96-212">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="98b96-212">Datacenter Azure geography</span></span> | <span data-ttu-id="98b96-213">URL de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="98b96-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="98b96-214">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-215">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="98b96-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-216">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98b96-217">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="98b96-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="98b96-218">En el campo **Entorno**, especifique el nombre del entorno del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="98b96-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="98b96-219">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98b96-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
