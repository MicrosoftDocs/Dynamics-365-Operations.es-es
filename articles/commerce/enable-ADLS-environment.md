---
title: 'Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce '
description: Este tema explica cómo habilitar y probar Azure Data Lake Storage para un entorno Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.
author: bebeale
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792616"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="5fda3-103">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce </span><span class="sxs-lookup"><span data-stu-id="5fda3-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5fda3-104">Este tema explica cómo habilitar y probar Azure Data Lake Storage para un entorno Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="5fda3-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

<span data-ttu-id="5fda3-105">En la solución Dynamics 365 Commerce, toda la información de productos y transacciones se rastrea en el almacén de entidades del entorno.</span><span class="sxs-lookup"><span data-stu-id="5fda3-105">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="5fda3-106">Para hacer que estos datos sean accesibles a otros servicios de Dynamics 365, como análisis de datos, inteligencia empresarial y recomendaciones personalizadas, es necesario conectar el entorno a una solución Gen 2 de Azure Data Lake Storage propiedad del cliente.</span><span class="sxs-lookup"><span data-stu-id="5fda3-106">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="5fda3-107">A medida que Azure Data Lake Storage se configura en un entorno, todos los datos necesarios se reflejan desde el almacén de entidades mientras siguen estando protegidos y bajo el control del cliente.</span><span class="sxs-lookup"><span data-stu-id="5fda3-107">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="5fda3-108">Si las recomendaciones del producto o las recomendaciones personalizadas también están habilitadas en el entorno, la pila de recomendaciones del producto tendrá acceso a la carpeta dedicada de Azure Data Lake Storage para recuperar los datos del cliente y calcular las recomendaciones a partir de ahí.</span><span class="sxs-lookup"><span data-stu-id="5fda3-108">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5fda3-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5fda3-109">Prerequisites</span></span>

<span data-ttu-id="5fda3-110">Los clientes deben tener Azure Data Lake Storage configurado en una suscripción de Azure que posean.</span><span class="sxs-lookup"><span data-stu-id="5fda3-110">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="5fda3-111">Este tema no cubre la compra de una suscripción de Azure ni la configuración de una cuenta de almacenamiento habilitada para Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5fda3-111">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="5fda3-112">Para obtener más información acerca de Azure Data Lake Storage, consulte la [Documentación oficial Gen2 de Azure Data Lake Storage](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="5fda3-112">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="5fda3-113">Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="5fda3-113">Configuration steps</span></span>

<span data-ttu-id="5fda3-114">Esta sección cubre los pasos de configuración necesarios para habilitar Azure Data Lake Storage en un entorno en relación con las recomendaciones del producto.</span><span class="sxs-lookup"><span data-stu-id="5fda3-114">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="5fda3-115">Para obtener una descripción más detallada de los pasos necesarios para habilitar Azure Data Lake Storage, consulte [Hacer que el almacén de entidades esté disponible como Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="5fda3-115">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="5fda3-116">Habilitar Azure Data Lake Storage en el entorno</span><span class="sxs-lookup"><span data-stu-id="5fda3-116">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="5fda3-117">Inicie sesión en el portal de back office del entorno.</span><span class="sxs-lookup"><span data-stu-id="5fda3-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="5fda3-118">Busque **Parámetros del sistema** y navegar a la pestaña **Conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="5fda3-119">Establezca **Habilitar la integración de Data Lake** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="5fda3-120">Establezca **Actualización por goteo de Data Lake** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="5fda3-121">Especifique la siguiente información necesaria:</span><span class="sxs-lookup"><span data-stu-id="5fda3-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="5fda3-122">**Id. de aplicación** // **Secreto de la aplicación** // **Nombre DNS**: necesario para conectarse a KeyVault, donde se almacena el secreto de Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5fda3-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="5fda3-123">**Nombre secreto**: nombre secreto almacenado en KeyVault que se usa para autenticarse con Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5fda3-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="5fda3-124">Guarde sus cambios en la esquina superior izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="5fda3-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="5fda3-125">En la imagen siguiente se muestra un ejemplo de configuración de Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5fda3-125">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Ejemplo de configuración de Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="5fda3-127">Probar la conexión de Azure Data Lake Storage</span><span class="sxs-lookup"><span data-stu-id="5fda3-127">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="5fda3-128">Pruebe la conexión con KeyVault utilizando el vínculo **Prueba de Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="5fda3-129">Pruebe la conexión con Azure Data Lake Storage utilizando el vínculo **Probar Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-129">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="5fda3-130">Si las pruebas fallan, verifique que toda la información de KeyVault agregada anteriormente sea correcta, luego inténtelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="5fda3-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="5fda3-131">Una vez que las pruebas de conexión sean exitosas, debe habilitar la actualización automática para el almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="5fda3-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="5fda3-132">Para habilitar la actualización automática para el almacén de entidades, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5fda3-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="5fda3-133">Busque **Almacén de entidades**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="5fda3-134">En la lista de la izquierda, navegue hasta **Ventas al por menor** y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="5fda3-135">Asegúrese de que **Actualización automática habilitada** se establece en **Sí**, seleccione **Actualizar** y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5fda3-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="5fda3-136">La siguiente imagen muestra un ejemplo de almacén de entidades con la actualización automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="5fda3-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Ejemplo de almacén de entidades con actualización automática habilitada](./media/exampleADLSConfig2.png)

<span data-ttu-id="5fda3-138">Azure Data Lake Storage ya está configurado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="5fda3-138">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="5fda3-139">Si aún no se ha completado, siga los pasos para [habilitar las recomendaciones de productos y la personalización](enable-product-recommendations.md) para el entorno.</span><span class="sxs-lookup"><span data-stu-id="5fda3-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5fda3-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5fda3-140">Additional resources</span></span>

[<span data-ttu-id="5fda3-141">Hacer que un almacén de entidades esté disponible como un Data Lake</span><span class="sxs-lookup"><span data-stu-id="5fda3-141">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="5fda3-142">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="5fda3-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="5fda3-143">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="5fda3-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="5fda3-144">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="5fda3-144">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="5fda3-145">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="5fda3-145">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="5fda3-146">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="5fda3-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="5fda3-147">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="5fda3-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="5fda3-148">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="5fda3-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="5fda3-149">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="5fda3-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="5fda3-150">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="5fda3-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="5fda3-151">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="5fda3-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="5fda3-152">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="5fda3-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
