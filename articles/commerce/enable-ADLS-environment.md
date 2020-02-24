---
title: Habilitar ADLS en un entorno de Dynamics 365 Commerce
description: Este tema explica cómo habilitar y probar Azure Data Lake Storage (ADLS) para un entorno de Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.
author: bebeale
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 068eb522bd44e02dd31d3337a051691a956637fc
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025278"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="60a48-103">Habilitar ADLS en un entorno de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="60a48-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="60a48-104">Este tema explica cómo habilitar y probar Azure Data Lake Storage (ADLS) para un entorno de Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="60a48-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="60a48-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="60a48-105">Overview</span></span>

<span data-ttu-id="60a48-106">En la solución Dynamics 365 Commerce, toda la información de productos y transacciones se rastrea en el almacén de entidades del entorno.</span><span class="sxs-lookup"><span data-stu-id="60a48-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="60a48-107">Para hacer que estos datos sean accesibles a otros servicios de Dynamics 365, como análisis de datos, inteligencia empresarial y recomendaciones personalizadas, es necesario conectar el entorno a una solución Gen 2 (ADLS) Azure Data Lake Storage del cliente.</span><span class="sxs-lookup"><span data-stu-id="60a48-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="60a48-108">A medida que ADLS se configura en un entorno, todos los datos necesarios se reflejan desde el almacén de entidades mientras se protegen y están bajo el control del cliente.</span><span class="sxs-lookup"><span data-stu-id="60a48-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="60a48-109">Si las recomendaciones del producto o las recomendaciones personalizadas también están habilitadas en el entorno, la pila de recomendaciones del producto tendrá acceso a la carpeta dedicada de ADLS para recuperar los datos del cliente y calcular las recomendaciones a partir de ahí.</span><span class="sxs-lookup"><span data-stu-id="60a48-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60a48-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60a48-110">Prerequisites</span></span>

<span data-ttu-id="60a48-111">Los clientes deben tener ADLS configurado en una suscripción de Azure que posean.</span><span class="sxs-lookup"><span data-stu-id="60a48-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="60a48-112">Este tema no cubre la compra de una suscripción de Azure ni la configuración de una cuenta de almacenamiento habilitada para ADLS.</span><span class="sxs-lookup"><span data-stu-id="60a48-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="60a48-113">Para obtener más información acerca de ADLS, consulte la [documentación oficial de ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="60a48-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="60a48-114">Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="60a48-114">Configuration steps</span></span>

<span data-ttu-id="60a48-115">Esta sección cubre los pasos de configuración necesarios para habilitar ADLS en un entorno.</span><span class="sxs-lookup"><span data-stu-id="60a48-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="60a48-116">Habilitar ADLS en el entorno</span><span class="sxs-lookup"><span data-stu-id="60a48-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="60a48-117">Inicie sesión en el portal de back office del entorno.</span><span class="sxs-lookup"><span data-stu-id="60a48-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="60a48-118">Busque **Parámetros del sistema** y navegar a la pestaña **Conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="60a48-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="60a48-119">Establezca **Habilitar la integración de Data Lake** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="60a48-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="60a48-120">Establezca **Actualización por goteo de Data Lake** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="60a48-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="60a48-121">Especifique la siguiente información necesaria:</span><span class="sxs-lookup"><span data-stu-id="60a48-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="60a48-122">**Id. de aplicación** // **Secreto de la aplicación** // **Nombre DNS** - Necesario para conectarse a KeyVault, donde se almacena el secreto ADLS.</span><span class="sxs-lookup"><span data-stu-id="60a48-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="60a48-123">**Nombre de secreto** - El nombre secreto almacenado en KeyVault que se usa para autenticarse con ADLS.</span><span class="sxs-lookup"><span data-stu-id="60a48-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="60a48-124">Guarde sus cambios en la esquina superior izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="60a48-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="60a48-125">En la imagen siguiente se muestra un ejemplo de configuración de ADLS.</span><span class="sxs-lookup"><span data-stu-id="60a48-125">The following image shows an example ADLS configuration.</span></span>

![Ejemplo de configuración de ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="60a48-127">Probar la conexión ADLS</span><span class="sxs-lookup"><span data-stu-id="60a48-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="60a48-128">Pruebe la conexión con KeyVault utilizando el vínculo **Prueba de Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="60a48-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="60a48-129">Pruebe la conexión con ADLS utilizando el vínculo **Probar Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="60a48-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="60a48-130">Si las pruebas fallan, verifique que toda la información de KeyVault agregada anteriormente sea correcta, luego inténtelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="60a48-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="60a48-131">Una vez que las pruebas de conexión sean exitosas, debe habilitar la actualización automática para el almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="60a48-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="60a48-132">Para habilitar la actualización automática para el almacén de entidades, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="60a48-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="60a48-133">Busque **Almacén de entidades**.</span><span class="sxs-lookup"><span data-stu-id="60a48-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="60a48-134">En la lista de la izquierda, navegue hasta **Ventas al por menor** y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="60a48-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="60a48-135">Asegúrese de que **Actualización automática habilitada** se establece en **Sí**, seleccione **Actualizar** y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="60a48-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="60a48-136">La siguiente imagen muestra un ejemplo de almacén de entidades con la actualización automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="60a48-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Ejemplo de almacén de entidades con actualización automática habilitada](./media/exampleADLSConfig2.png)

<span data-ttu-id="60a48-138">ADLS ahora está configurado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="60a48-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="60a48-139">Si aún no se ha completado, siga los pasos para [habilitar las recomendaciones de productos y la personalización](enable-product-recommendations.md) para el entorno.</span><span class="sxs-lookup"><span data-stu-id="60a48-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60a48-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="60a48-140">Additional resources</span></span>

[<span data-ttu-id="60a48-141">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="60a48-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="60a48-142">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="60a48-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="60a48-143">Agregar listas de recomendaciones a páginas</span><span class="sxs-lookup"><span data-stu-id="60a48-143">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="60a48-144">Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV</span><span class="sxs-lookup"><span data-stu-id="60a48-144">Add a recommendations control to the transaction screen on POS devices</span></span>](../retail/add-recommendations-control-pos-screen.md?toc=/dynamics365/commerce/toc.json)


