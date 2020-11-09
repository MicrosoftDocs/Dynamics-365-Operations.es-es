---
title: Orientación sobre cómo configurar la doble escritura
description: Este tema describe los escenarios que son compatibles con la configuración de doble escritura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088515"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a><span data-ttu-id="89d53-103">Orientación sobre cómo configurar la doble escritura</span><span class="sxs-lookup"><span data-stu-id="89d53-103">Guidance for how to set up dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="89d53-104">Puede configurar una conexión de doble escritura entre entorno de Finance and Operations y uno de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89d53-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="89d53-105">Un **entorno de Finance and Operations** proporciona la plataforma subyacente para las **aplicaciones de Finance and Operations** (por ejemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management y Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="89d53-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="89d53-106">Un **entorno Common Data Service** proporciona la plataforma subyacente para **aplicaciones de Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="89d53-106">A **Common Data Service environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="89d53-107">Human Resources en Finance and Operations admite conexiones de escritura dual, pero la aplicación Dynamics 365 Human Resources no lo hace.</span><span class="sxs-lookup"><span data-stu-id="89d53-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="89d53-108">El mecanismo de configuración varía, dependiendo de su suscripción y el entorno.</span><span class="sxs-lookup"><span data-stu-id="89d53-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="89d53-109">Para nuevas instancias de aplicaciones de Finance and Operations, la configuración de una conexión de doble escritura comienza en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="89d53-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="89d53-110">Si tiene una licencia para Power Platform, obtendrá un entorno nuevo Common Data Service entorno si su inquilino no tiene uno.</span><span class="sxs-lookup"><span data-stu-id="89d53-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="89d53-111">Para instancias existentes de aplicaciones Finance and Operations, la configuración de una conexión de doble escritura comienza en el entorno Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="89d53-112">Antes de comenzar la doble escritura en una entidad, puede ejecutar una sincronización inicial para procesar los datos existentes en ambos lados de las aplicaciones de Finance and Operations y las aplicaciones de Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="89d53-112">Before you start dual-write on an entity, you can run an initial sync to handle existing data on both sides of Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="89d53-113">Puede omitir la sincronización inicial si no necesita sincronizar datos entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="89d53-113">You can skip the initial sync if you don't need to synchronize data between the two environments.</span></span>

<span data-ttu-id="89d53-114">Una sincronización inicial le permite copiar datos existentes de una aplicación a otra de forma bidireccional.</span><span class="sxs-lookup"><span data-stu-id="89d53-114">An initial sync lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="89d53-115">Hay varios escenarios de configuración diferentes según los entornos que ya tenga y el tipo de datos que haya en los entornos.</span><span class="sxs-lookup"><span data-stu-id="89d53-115">There are several different setup scenarios depending on which environments you already have and what type of data is in the environments.</span></span>

<span data-ttu-id="89d53-116">Se admiten los siguientes escenarios de configuración:</span><span class="sxs-lookup"><span data-stu-id="89d53-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="89d53-117">Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="89d53-118">Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="89d53-119">Una nueva instancia de aplicación Finance and Operations que tenga datos y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="89d53-120">Una nueva instancia de aplicación de Finance and Operations que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="89d53-121">Una instancia de aplicación de Finance and Operations existente y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="89d53-122">Una instancia de aplicación de Finance and Operations existente y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="89d53-123">Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="89d53-124">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que no tiene datos y una nueva instancia de aplicación de Customer Engagement, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="89d53-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="89d53-125">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="89d53-125">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="89d53-126">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="89d53-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="89d53-127">Se aprovisiona una nueva instancia vacía de aplicación de Customer Engagement, donde se instala la solución CRM primaria.</span><span class="sxs-lookup"><span data-stu-id="89d53-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="89d53-128">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="89d53-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="89d53-129">Los mapas de entidades están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="89d53-129">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="89d53-130">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="89d53-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="89d53-131">Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="89d53-132">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que no tiene datos y una instancia de aplicación de Customer Engagement existente, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="89d53-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="89d53-133">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="89d53-133">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="89d53-134">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="89d53-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="89d53-135">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="89d53-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="89d53-136">Los mapas de entidades están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="89d53-136">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="89d53-137">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="89d53-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="89d53-138">Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="89d53-138">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="89d53-139">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="89d53-140">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="89d53-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="89d53-141">[Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa de tres letras de la Organización Internacional de Normalización (ISO).</span><span class="sxs-lookup"><span data-stu-id="89d53-141">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="89d53-142">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-143">Para ver un ejemplo y un enfoque alternativo, consulte [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="89d53-143">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="89d53-144">Una nueva instancia de aplicación de Finance and Operations que tenga datos y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="89d53-145">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que tiene datos de demostración y una nueva instancia de aplicación de Customer Engagement, siga los pasos de la sección [Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement](#new-new) más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="89d53-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="89d53-146">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="89d53-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="89d53-147">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="89d53-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="89d53-148">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-148">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-149">Para ver un ejemplo y un enfoque alternativo, consulte [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="89d53-149">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="89d53-150">Una nueva instancia de aplicación de Finance and Operations que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="89d53-151">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que tiene datos de demostración y una instancia de aplicación de Customer Engagement existente, siga los pasos de la sección [Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente](#new-existing) más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="89d53-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="89d53-152">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="89d53-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="89d53-153">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="89d53-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="89d53-154">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-154">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-155">Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="89d53-155">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="89d53-156">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="89d53-157">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="89d53-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="89d53-158">[Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código ISO de empresa de tres letras.</span><span class="sxs-lookup"><span data-stu-id="89d53-158">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="89d53-159">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-159">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-160">Para ver un ejemplo y un enfoque alternativo, consulte [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="89d53-160">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="89d53-161">Una instancia de aplicación de Finance and Operations existente y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="89d53-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="89d53-162">La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de Finance and Operations y una instancia nueva de aplicación de Customer Engagement se realiza en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="89d53-163">[Configurar la conexión desde la aplicación de Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="89d53-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="89d53-164">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-164">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-165">Para ver un ejemplo y un enfoque alternativo, consulte [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="89d53-165">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="89d53-166">Una instancia de aplicación de Finance and Operations existente y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="89d53-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="89d53-167">La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente se realiza en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app  occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="89d53-168">Configure la conexión desde la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="89d53-168">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="89d53-169">Para sincronizar lo datos existentes de Common Data Service con la aplicación Finance and Operations, [arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa ISO de tres letras.</span><span class="sxs-lookup"><span data-stu-id="89d53-169">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="89d53-170">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="89d53-170">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="89d53-171">Para ver un ejemplo y un enfoque alternativo, consulte [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="89d53-171">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="example"></a><span data-ttu-id="89d53-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89d53-172">Example</span></span>

<span data-ttu-id="89d53-173">Por ejemplo, consulte [Habilitar la asignación de entidades Clientes V3—Contactos](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span><span class="sxs-lookup"><span data-stu-id="89d53-173">For an example, see [Enabling the Customers V3—Contacts entity map](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span></span>

<span data-ttu-id="89d53-174">Para obtener un enfoque alternativo basado en volúmenes de datos en cada entidad en la que hay que ejecutar una sincronización inicial, consulte [Consideraciones para la sincronización inicial](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="89d53-174">For an alternative approach based on data volumes in each entity that need to run initial sync, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
