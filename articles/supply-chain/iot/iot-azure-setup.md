---
title: Configurar recursos de Azure para Inteligencia IoT
description: Este tema explica cómo crear y configurar los recursos Microsoft Azure que necesita para Inteligencia IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1277d2ab8bb1f2925874f7469250e164f6bde62d
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437167"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="6fcd8-103">Configurar recursos de Azure para Inteligencia IoT</span><span class="sxs-lookup"><span data-stu-id="6fcd8-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6fcd8-104">Este tema explica cómo crear y configurar los recursos Microsoft Azure que necesita para Inteligencia IoT.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="6fcd8-105">Crear recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="6fcd8-105">Create Azure resources</span></span>

<span data-ttu-id="6fcd8-106">Siga estos pasos para crear un centro de IoT, una caché Redis y un almacén de claves al que se pueda acceder mediante Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="6fcd8-107">Verifique que el id. de la aplicación de primera entidad Microsoft Dynamics ERP Microservices está en su inquilino</span><span class="sxs-lookup"><span data-stu-id="6fcd8-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="6fcd8-108">Para verificar que el id. de la aplicación de primera entidad Microsoft Dynamics ERP Microservices está en su inquilino, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-109">Inicie sesión en el portal Azure en <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="6fcd8-110">Ir a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6fcd8-111">Vaya a **Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="6fcd8-112">En el campo **Tipo de aplicacion**, seleccione **Aplicaciones de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="6fcd8-113">En el campo de búsqueda, introduzca **Microsoft Dynamics Microservicios ERP**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="6fcd8-114">Verifique que **Microsoft Dynamics ERP Microservices** está en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="6fcd8-115">Otras aplicaciones tienen nombres similares.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-115">Other applications have similar names.</span></span> <span data-ttu-id="6fcd8-116">Por lo tanto, debe asegurarse de encontrar la aplicación correcta.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="6fcd8-117">El id. de la aplicación es **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="6fcd8-118">Si la aplicación no está en la lista, debe agregarla a su inquilino:</span><span class="sxs-lookup"><span data-stu-id="6fcd8-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="6fcd8-119">En Azure Portal, en la barra de herramientas, seleccione el botón para abrir Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="6fcd8-120">Ejecute el comando **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="6fcd8-121">Introduzca **Y** para instalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="6fcd8-122">Ejecute el comando **Get-InstalledModule -Name "AzureAD"** para verificar que el módulo esté instalado.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="6fcd8-123">Ejecute el comando **Connect-AzureAD -Confirm** para ejecutar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="6fcd8-124">Ejecute el comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="6fcd8-125">Ahora puede repetir los pasos 1 a 6 para verificar que el id. de la aplicación esté en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="6fcd8-126">Crear un recurso de almacén de claves</span><span class="sxs-lookup"><span data-stu-id="6fcd8-126">Create a key vault resource</span></span>

<span data-ttu-id="6fcd8-127">Para crear un recurso de almacén de claves, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-128">En Azure Portal, cree o vaya a un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="6fcd8-129">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-129">Select **Add**.</span></span>
3. <span data-ttu-id="6fcd8-130">En la página **Nuevo**, en el campo de búsqueda, introduzca **Almacén de claves**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="6fcd8-131">Después seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-131">Then select **Create**.</span></span>
4. <span data-ttu-id="6fcd8-132">En la página **Crear almacén de claves**, en el campo **Nombre de almacén de claves**, introduzca un nombre.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="6fcd8-133">Revise los valores predeterminados y luego seleccione **Revisar + crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="6fcd8-134">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-134">Select **Create**.</span></span>

<span data-ttu-id="6fcd8-135">El almacén de claves se crea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="6fcd8-136">Crear un recurso de centro de IoT</span><span class="sxs-lookup"><span data-stu-id="6fcd8-136">Create an IoT hub resource</span></span>

<span data-ttu-id="6fcd8-137">Para crear un recurso de centro de IoT, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-138">Cree un grupo de recursos o vaya a él.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="6fcd8-139">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-139">Select **Add**.</span></span>
3. <span data-ttu-id="6fcd8-140">En la página **Nuevo**, en el campo de búsqueda, introduzca **Centro de IoT**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="6fcd8-141">Después seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-141">Then select **Create**.</span></span>
4. <span data-ttu-id="6fcd8-142">En el campo **Nombre de centro de IoT**, introduzca un nombre.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="6fcd8-143">Revise los valores predeterminados y luego seleccione **Revisar + crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="6fcd8-144">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-144">Select **Create**.</span></span>

<span data-ttu-id="6fcd8-145">El centro de IoT se crea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="6fcd8-146">Se recomienda crear solo un recurso de centro de IoT por entorno.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="6fcd8-147">Crear un recurso de caché Redis</span><span class="sxs-lookup"><span data-stu-id="6fcd8-147">Create a Redis cache resource</span></span>

<span data-ttu-id="6fcd8-148">Para crear un recurso de caché Redis, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-149">Cree un grupo de recursos o vaya a él.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="6fcd8-150">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-150">Select **Add**.</span></span>
3. <span data-ttu-id="6fcd8-151">En la página **Nuevo**, en el campo de búsqueda, introduzca **Azure Cache para Redis**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="6fcd8-152">Después seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-152">Then select **Create**.</span></span>
4. <span data-ttu-id="6fcd8-153">Introduzca un nombre en el campo **Nombre DNS**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="6fcd8-154">Revise los valores predeterminados y luego seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="6fcd8-155">La caché Redis se crea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="6fcd8-156">Se recomienda crear solo una sola caché Redis por entorno.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="6fcd8-157">Todos los recursos se han creado ya.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="6fcd8-158">Configurar los recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="6fcd8-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="6fcd8-159">Configurar el centro de IoT</span><span class="sxs-lookup"><span data-stu-id="6fcd8-159">Configure the IoT hub</span></span>

<span data-ttu-id="6fcd8-160">Para configurar el centro de IoT, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-161">En sus recursos, seleccione el recurso del centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="6fcd8-162">En el panel de navegación izquierdo, seleccione **Puntos finales incorporados**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="6fcd8-163">En **Grupos de consumidores**, pegue los siguientes grupos de consumidores.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="6fcd8-164">Estos grupos de consumidores corresponden a los escenarios listos para usar.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="6fcd8-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="6fcd8-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="6fcd8-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="6fcd8-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="6fcd8-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="6fcd8-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="6fcd8-168">Configurar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="6fcd8-168">Configure the key vault</span></span>

<span data-ttu-id="6fcd8-169">Para configurar el almacén de claves, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-170">En sus recursos, seleccione el recurso del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="6fcd8-171">En el panel de navegación izquierdo, seleccione **Directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="6fcd8-172">Seleccione **Agregar una directiva de acceso**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="6fcd8-173">En la página **Agregar directiva de acceso**, en el campo **Permisos secretos**, seleccione **Obtener** y **Lista**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="6fcd8-174">Haga clic en **Seleccionar principal**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="6fcd8-175">En el cuadro de diálogo **Principal**, busque y seleccione **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="6fcd8-176">Luego, seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-176">Then select **Select**.</span></span>
7. <span data-ttu-id="6fcd8-177">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-177">Select **Add**.</span></span>
8. <span data-ttu-id="6fcd8-178">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-178">Select **Save**.</span></span>

<span data-ttu-id="6fcd8-179">La aplicación ya tiene acceso a los secretos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="6fcd8-180">Guardar el secreto de cadena de conexión del centro de IoT</span><span class="sxs-lookup"><span data-stu-id="6fcd8-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="6fcd8-181">Para guardar el secreto de la cadena de conexión del centro de IoT, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-182">En sus recursos, seleccione el recurso del centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="6fcd8-183">En el panel de navegación izquierdo, seleccione **Puntos finales incorporados**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="6fcd8-184">Copie el valor en el campo **Punto final compatible con Event Hub**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="6fcd8-185">Vaya al recurso del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="6fcd8-186">En el panel de navegación izquierdo, seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="6fcd8-187">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="6fcd8-188">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="6fcd8-189">En el campo **Valor**, pegue el valor del punto final que copió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="6fcd8-190">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="6fcd8-191">Guardar el secreto de cadena de conexión de la caché Redis</span><span class="sxs-lookup"><span data-stu-id="6fcd8-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="6fcd8-192">Para guardar el secreto de la cadena de conexión de la caché Redis, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="6fcd8-193">En sus recursos, seleccione el recurso de caché Redis.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="6fcd8-194">Seleccione **Claves de acceso**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="6fcd8-195">Copie el valor en el campo **Cadena de conexión primaria**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="6fcd8-196">Vaya al recurso del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="6fcd8-197">En el panel de navegación izquierdo, seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="6fcd8-198">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="6fcd8-199">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="6fcd8-200">En el campo **Valor**, pegue la cadena de conexión que copió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="6fcd8-201">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="6fcd8-202">Siempre que actualice una de las cadenas de conexión, también debe actualizar los valores secretos.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="6fcd8-203">Ya ha terminado de aprovisionar los recursos de Azure necesarios.</span><span class="sxs-lookup"><span data-stu-id="6fcd8-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="6fcd8-204">El siguiente paso es [instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6fcd8-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
