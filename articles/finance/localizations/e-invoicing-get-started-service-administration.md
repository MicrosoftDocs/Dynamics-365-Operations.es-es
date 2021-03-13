---
title: Comenzar con la administración del servicio del complemento de facturación electrónica
description: Este tema explica cómo comenzar con el complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104433"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="f9863-103">Comenzar con la administración del servicio del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="f9863-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="f9863-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9863-104">Prerequisites</span></span>

<span data-ttu-id="f9863-105">Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f9863-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="f9863-106">Debe tener acceso a su cuenta de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f9863-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="f9863-107">Debe tener un proyecto LCS que incluya la versión 10.0.13 o posterior de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9863-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f9863-108">Además, estas aplicaciones deben implementarse en una de las siguientes áreas geográficas de Azure:</span><span class="sxs-lookup"><span data-stu-id="f9863-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="f9863-109">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-109">East US</span></span>
    - <span data-ttu-id="f9863-110">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-110">West US</span></span>
    - <span data-ttu-id="f9863-111">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-111">North EU</span></span>
    - <span data-ttu-id="f9863-112">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-112">West EU</span></span>

- <span data-ttu-id="f9863-113">Debe tener acceso a su cuenta de Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="f9863-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="f9863-114">Debe activar la característica de globalización para su cuenta RCS a través del módulo de administración de características.</span><span class="sxs-lookup"><span data-stu-id="f9863-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="f9863-115">Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="f9863-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="f9863-116">Debe crear un almacén de claves y una cuenta de almacenamiento en Azure.</span><span class="sxs-lookup"><span data-stu-id="f9863-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="f9863-117">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="f9863-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="f9863-118">Instalar el complemento para microservicios en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="f9863-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="f9863-119">Inicie sesión en su cuenta de LCS.</span><span class="sxs-lookup"><span data-stu-id="f9863-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="f9863-120">Seleccione el mosaico **Gestión de características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="f9863-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="f9863-121">En la sección **Funciones de versión preliminar pública**, seleccione **Servicio de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="f9863-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="f9863-122">Compruebe que la opción **Característica en vista previa** esté establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f9863-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="f9863-123">Configurar los parámetros para la integración de RCS con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="f9863-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="f9863-124">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="f9863-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="f9863-125">En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="f9863-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="f9863-126">En la pestaña **Servicio de facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="f9863-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="f9863-127">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="f9863-127">Datacenter Azure geography</span></span> | <span data-ttu-id="f9863-128">Identificador URI de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="f9863-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="f9863-129">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-130">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-131">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-132">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="f9863-133">Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="f9863-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="f9863-134">Este valor es un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="f9863-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="f9863-135">En el campo **Id. de entorno de LCS**, introduzca el id. de su cuenta de suscripción de LCS.</span><span class="sxs-lookup"><span data-stu-id="f9863-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="f9863-136">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="f9863-137">Crear secretos de Key Vault</span><span class="sxs-lookup"><span data-stu-id="f9863-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="f9863-138">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="f9863-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="f9863-139">En el espacio de trabajo **Característica de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="f9863-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="f9863-140">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio** y luego seleccione **Parámetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="f9863-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="f9863-141">Seleccione **Nuevo** para crear un secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="f9863-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="f9863-142">En el campo **Nombre**, especifique el nombre del secreto de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="f9863-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="f9863-143">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f9863-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="f9863-144">En el campo **URI de Key Vault**, pegue el secreto de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="f9863-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="f9863-145">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f9863-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="f9863-146">Crear secreto de cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="f9863-146">Create Storage account secret</span></span>

1. <span data-ttu-id="f9863-147">En la página **Parámetros de almacén de claves**, en la sección **Certificados**, seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="f9863-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="f9863-148">En el campo **Nombre**, especifique el nombre del secreto de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f9863-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="f9863-149">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f9863-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="f9863-150">En el campo **Tipo**, seleccione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="f9863-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="f9863-151">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="f9863-152">Crear un entorno del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="f9863-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="f9863-153">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="f9863-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="f9863-154">En el espacio de trabajo **Característica de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="f9863-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="f9863-155">Crear un entorno de servicio</span><span class="sxs-lookup"><span data-stu-id="f9863-155">Create a service environment</span></span>

1. <span data-ttu-id="f9863-156">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Entorno de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f9863-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="f9863-157">Seleccione **Nuevo** para crear un nuevo entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="f9863-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="f9863-158">En el campo **Nombre**, especifique el nombre del entorno de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="f9863-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="f9863-159">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f9863-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="f9863-160">En el **Secreto de token de SAS de almacenamiento**, seleccione el nombre del certificado que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f9863-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="f9863-161">En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y también conectarse a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f9863-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="f9863-162">En el campo **Id. de usuario**, introduzca el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9863-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="f9863-163">En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9863-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="f9863-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f9863-164">Select **Save**.</span></span>
8. <span data-ttu-id="f9863-165">Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales, seleccione **Parámetros del almacén de claves** en el Panel de acciones y luego seleccione **Cadena de certificados** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f9863-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="f9863-166">Seleccione **Nuevo** para crear una cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="f9863-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="f9863-167">En el campo **Nombre**, introduzca el nombre de la cadena de certificado.</span><span class="sxs-lookup"><span data-stu-id="f9863-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="f9863-168">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="f9863-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="f9863-169">En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.</span><span class="sxs-lookup"><span data-stu-id="f9863-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="f9863-170">Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena.</span><span class="sxs-lookup"><span data-stu-id="f9863-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="f9863-171">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="f9863-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-172">Close the page.</span></span>
9. <span data-ttu-id="f9863-173">En la página **Entorno de servicio**, seleccione **Publicar** en el panel de acciones para publicar el entorno en la nube.</span><span class="sxs-lookup"><span data-stu-id="f9863-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="f9863-174">El valor del campo **Estado** se cambia a **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="f9863-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="f9863-175">Crear una aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="f9863-175">Create a connected application</span></span>

1. <span data-ttu-id="f9863-176">En la página **Configuraciones de entorno**, en el panel de acciones, seleccione **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="f9863-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="f9863-177">Seleccione **Nuevo** para crear una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="f9863-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="f9863-178">En el campo **Nombre**, especifique el nombre de la aplicación a conectar.</span><span class="sxs-lookup"><span data-stu-id="f9863-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="f9863-179">En el campo **Aplicación**, introduzca la URL del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="f9863-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="f9863-180">En el campo **Inquilino**, introduzca el inquilino del entorno de administración de Finance y Supply Chain Management para conectarse.</span><span class="sxs-lookup"><span data-stu-id="f9863-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="f9863-181">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f9863-181">Select **Save**.</span></span>
6. <span data-ttu-id="f9863-182">En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno.</span><span class="sxs-lookup"><span data-stu-id="f9863-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="f9863-183">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="f9863-184">Vincular aplicaciones conectadas a entornos</span><span class="sxs-lookup"><span data-stu-id="f9863-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="f9863-185">En la página **Configuraciones de entorno**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.</span><span class="sxs-lookup"><span data-stu-id="f9863-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="f9863-186">En el campo **Aplicación conectada**, seleccione una aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="f9863-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="f9863-187">En el campo **Entorno de servicio**, seleccione un entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="f9863-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="f9863-188">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="f9863-189">Configurar la integración del complemento de facturación electrónica en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f9863-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="f9863-190">Active la característica de integración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="f9863-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="f9863-191">Inicie sesión en su instancia de Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9863-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="f9863-192">En el espacio de trabajo **Administración de características**, busque la nueva característica, **Integración de complemento de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="f9863-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="f9863-193">Si esta característica no aparece en la página, seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="f9863-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="f9863-194">Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f9863-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="f9863-195">Configurar la URL del punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="f9863-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="f9863-196">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="f9863-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="f9863-197">En la pestaña **Servicio de envío**, en el campo **URL de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Azure, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="f9863-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="f9863-198">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="f9863-198">Datacenter Azure geography</span></span> | <span data-ttu-id="f9863-199">URL de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="f9863-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="f9863-200">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-201">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="f9863-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-202">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="f9863-203">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="f9863-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="f9863-204">En el campo **Entorno**, especifique el nombre del entorno del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="f9863-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="f9863-205">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f9863-205">Select **Save**, and then close the page.</span></span>
