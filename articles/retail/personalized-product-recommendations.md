---
title: "Visión general de recomendaciones de productos personalizados"
description: "En Dynamics 365 for Retail, las recomendaciones de productos se pueden visualizar en el dispositivo de punto de venta (PDV). Las recomendaciones son artículos que pueden interesar al cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas. Para minoristas con grandes catálogos, las recomendaciones ayudan al cliente con el descubrimiento de productos. Al mostrar productos orientados a los intereses y hábitos de compra de un cliente, las recomendaciones de productos pueden ayudar a los minoristas con las ventas verticales y cruzadas, y a mejorar la retención de clientes. En Dynamics 365 for Retail, las recomendaciones de productos son impulsadas por servicios cognitivos y el aprendizaje automático de Microsoft Azure."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 42ffb375d9786b2ac506d6ef06e9da9ee22652a6
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="4c441-107">Visión general de recomendaciones de productos personalizados</span><span class="sxs-lookup"><span data-stu-id="4c441-107">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="4c441-108">Esta característica está disponible en las topologías de implementación (alta disponibilidad) de espacio aislado y producción.</span><span class="sxs-lookup"><span data-stu-id="4c441-108">This feature is currently available on sandbox and production (high-availability) deployment topologies only.</span></span> 

<span data-ttu-id="4c441-109">En Dynamics 365 for Retail, las recomendaciones de productos se pueden visualizar en el dispositivo de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="4c441-109">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="4c441-110">Las recomendaciones son artículos que pueden interesar al cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas.</span><span class="sxs-lookup"><span data-stu-id="4c441-110">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="4c441-111">Para minoristas con grandes catálogos, las recomendaciones ayudan al cliente con el descubrimiento de productos.</span><span class="sxs-lookup"><span data-stu-id="4c441-111">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="4c441-112">Al mostrar productos orientados a los intereses y hábitos de compra de un cliente, las recomendaciones de productos pueden ayudar a los minoristas con las ventas verticales y cruzadas, y a mejorar la retención de clientes.</span><span class="sxs-lookup"><span data-stu-id="4c441-112">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="4c441-113">En Dynamics 365 for Retail, las recomendaciones de productos son impulsadas por servicios cognitivos y el aprendizaje automático de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="4c441-113">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="4c441-114">Situaciones</span><span class="sxs-lookup"><span data-stu-id="4c441-114">Scenarios</span></span>
---------

<span data-ttu-id="4c441-115">Las recomendaciones de productos se habilitan para los siguientes escenarios de PDV.</span><span class="sxs-lookup"><span data-stu-id="4c441-115">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="4c441-116">Están disponibles en PDV en la nube o en PDV moderno (MPOS).</span><span class="sxs-lookup"><span data-stu-id="4c441-116">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="4c441-117">En la página **Detalles del producto**:</span><span class="sxs-lookup"><span data-stu-id="4c441-117">On the **Product details** page:</span></span>

-   <span data-ttu-id="4c441-118">Si un empleado de tienda visita una página de **Detalles del producto** a la hora de buscar transacciones anteriores a través de distintos canales, el motor de recomendación sugiere artículos adicionales que es probable que se adquieran de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="4c441-118">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="4c441-119">Si el empleado de tienda agrega un cliente a la transacción y luego visita a página de **Detalles del producto**, el motor de recomendación proporciona recomendaciones personalizadas mediante el historial de transacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="4c441-119">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="4c441-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="4c441-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="4c441-121">En la página **Transacción**:</span><span class="sxs-lookup"><span data-stu-id="4c441-121">On the **Transaction** page:</span></span>

-   <span data-ttu-id="4c441-122">El motor de recomendación sugiere los artículos en base a la lista completa de artículos en la cesta.</span><span class="sxs-lookup"><span data-stu-id="4c441-122">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="4c441-123">Si el empleado de tienda agrega un cliente a la transacción, el motor de recomendación proporciona recomendaciones personales mediante el historial de transacción del cliente y la lista de artículos en la cesta.</span><span class="sxs-lookup"><span data-stu-id="4c441-123">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="4c441-124">Para mostrar recomendaciones en la página **Transacción**, el minorista tiene que actualizar el diseño de la pantalla en Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="4c441-124">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="4c441-125">El control **Recomendaciones** debe quitarse de la página **Transacción**.</span><span class="sxs-lookup"><span data-stu-id="4c441-125">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="4c441-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="4c441-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="4c441-127">En la página **Detalles del cliente**:</span><span class="sxs-lookup"><span data-stu-id="4c441-127">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="4c441-128">El motor de recomendación sugiere los artículos en base al id. de usuario y los artículos en la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="4c441-128">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="4c441-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="4c441-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="4c441-130">Configure Dynamics 365 for Retail para habilitar las recomendaciones de PDV</span><span class="sxs-lookup"><span data-stu-id="4c441-130">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="4c441-131">Para configurar las recomendaciones de productos, tiene que hacer lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c441-131">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="4c441-132">Asegúrese de que ha seleccionado la **Entidad jurídica** correcta.</span><span class="sxs-lookup"><span data-stu-id="4c441-132">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="4c441-133">Vaya a **Almacén de entidades**, seleccione **Ventas minoristas** y luego haga clic en **Actualizar**. Esto utilizará los datos de demostración (o sus datos) de su base de datos operativa y los moverá al almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="4c441-133">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="4c441-134">Opcional: para mostrar recomendaciones en la pantalla de transacción, vaya a **Diseño de pantalla**, elija su diseño de pantalla, inicie el **Diseñador de pantalla** y quite el control de **recomendaciones** cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4c441-134">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**,and then drop the **recommendations** control where needed.</span></span>
4.  <span data-ttu-id="4c441-135">Vaya a **Parámetros de ventas al por menor** seleccione **Aprendizaje automático** y seleccione **Sí** en **Habilitar recomendaciones de PDV**.</span><span class="sxs-lookup"><span data-stu-id="4c441-135">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="4c441-136">Para ver recomendaciones sobre el PDV, ejecute el trabajo de configuración global **1110**.</span><span class="sxs-lookup"><span data-stu-id="4c441-136">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="4c441-137">Para reflejar los cambios realizados en el diseñador de pantalla del PVD, ejecute el trabajo de configuración de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="4c441-137">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="4c441-138">[]()¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="4c441-138">[]()How does it work?</span></span>
<span data-ttu-id="4c441-139">Al actualizar la entidad **Almacén de entidades**, tienen lugar las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="4c441-139">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="4c441-140">Los datos en el formato requerido por los servicios cognitivos se extraen de la base de datos operativa Dynamics 365 for Retail y se envían al almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="4c441-140">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="4c441-141">Azure Data Factory (ADF) utiliza los datos para filtrarlos mediante secuencias de comandos de Hive como parte de las actividades de ADF.</span><span class="sxs-lookup"><span data-stu-id="4c441-141">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="4c441-142">Los datos filtrados se guardan en un almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="4c441-142">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="4c441-143">La API de servicio cognitivos utilizan los datos de almacenamiento de blobs para preparar a un modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="4c441-143">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="4c441-144">Al activar **Habilitar recomendaciones del permiso** y ejecutar los trabajos de configuración, tienen lugar las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="4c441-144">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="4c441-145">Las credenciales del modelo y la id. se seleccionan desde la API y se guardan en la base de datos operativa de Dynamics 365 for Retail, en el web.config para AOS y también en el Retail Server.</span><span class="sxs-lookup"><span data-stu-id="4c441-145">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="4c441-146">Las credenciales del modelo y el id. se ponen a disposición de CRT para que se puedan aplicar llamadas para recomendaciones de productos desde el PDV en la nube y el MPOS en modo en línea.</span><span class="sxs-lookup"><span data-stu-id="4c441-146">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="4c441-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c441-147">See also</span></span>
--------

[<span data-ttu-id="4c441-148">Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV</span><span class="sxs-lookup"><span data-stu-id="4c441-148">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




