---
title: Orientación sobre cómo configurar la doble escritura
description: Este tema describe los escenarios que son compatibles con la configuración de doble escritura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: dee6bc52a0967dfd6134258d3a02dc18feb404a5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560234"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="9329e-103">Orientación sobre cómo configurar la doble escritura</span><span class="sxs-lookup"><span data-stu-id="9329e-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9329e-104">Puede configurar una conexión de doble escritura entre entorno de Finance and Operations y uno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9329e-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="9329e-105">Un **entorno de Finance and Operations** proporciona la plataforma subyacente para las **aplicaciones de Finance and Operations** (por ejemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="9329e-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="9329e-106">Un **entorno Dataverse** proporciona la plataforma subyacente para **aplicaciones de interacción con el cliente** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Column Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="9329e-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9329e-107">El módulo Human Resources en Dynamics 365 Finance admite conexiones de escritura dual, pero la aplicación Dynamics 365 Human Resources no lo hace.</span><span class="sxs-lookup"><span data-stu-id="9329e-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="9329e-108">El mecanismo de configuración varía, dependiendo de su suscripción y el entorno:</span><span class="sxs-lookup"><span data-stu-id="9329e-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="9329e-109">Para nuevas instancias de aplicaciones de Finance and Operations, la configuración de una conexión de doble escritura comienza en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9329e-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9329e-110">Si tiene una licencia para Microsoft Power Platform, obtendrá un entorno nuevo Dataverse entorno si su inquilino no tiene uno.</span><span class="sxs-lookup"><span data-stu-id="9329e-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="9329e-111">Para instancias existentes de aplicaciones Finance and Operations, la configuración de una conexión de doble escritura comienza en el entorno Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9329e-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="9329e-112">Antes de comenzar la doble escritura en una entidad, puede ejecutar una sincronización inicial para procesar los datos existentes en ambos lados: las aplicaciones de Finance and Operations y las aplicaciones de Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="9329e-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="9329e-113">Puede omitir la sincronización inicial si no necesita sincronizar datos entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="9329e-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="9329e-114">Una sincronización inicial le permite copiar datos existentes de una aplicación a otra de forma bidireccional.</span><span class="sxs-lookup"><span data-stu-id="9329e-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="9329e-115">Hay varios escenarios de configuración diferentes según los entornos que ya tenga y el tipo de datos que haya en ellos.</span><span class="sxs-lookup"><span data-stu-id="9329e-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="9329e-116">Se admiten los siguientes escenarios de configuración:</span><span class="sxs-lookup"><span data-stu-id="9329e-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="9329e-117">Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="9329e-118">Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="9329e-119">Una nueva instancia de aplicación Finance and Operations que tenga datos y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="9329e-120">Una nueva instancia de aplicación de Finance and Operations que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="9329e-121">Una instancia de aplicación de Finance and Operations existente y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="9329e-122">Una instancia de aplicación de Finance and Operations existente y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="9329e-123">Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="9329e-124">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que no tiene datos y una nueva instancia de aplicación de Customer Engagement, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9329e-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="9329e-125">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="9329e-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="9329e-126">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="9329e-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="9329e-127">Se aprovisiona una nueva instancia vacía de aplicación de Customer Engagement, donde se instala la solución CRM primaria.</span><span class="sxs-lookup"><span data-stu-id="9329e-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="9329e-128">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="9329e-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="9329e-129">Los mapas de tablas están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="9329e-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="9329e-130">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="9329e-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="9329e-131">Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="9329e-132">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que no tiene datos y una instancia de aplicación de Customer Engagement existente, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9329e-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="9329e-133">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="9329e-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="9329e-134">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="9329e-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="9329e-135">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="9329e-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="9329e-136">Los mapas de tablas están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="9329e-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="9329e-137">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="9329e-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="9329e-138">Para sincronizar los datos existentes de Dataverse con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9329e-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="9329e-139">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9329e-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="9329e-140">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="9329e-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="9329e-141">[Arranque](bootstrap-company-data.md) los datos Dataverse mediante el uso de un código de empresa de tres letras de la Organización Internacional de Normalización (ISO).</span><span class="sxs-lookup"><span data-stu-id="9329e-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="9329e-142">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-143">Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9329e-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="9329e-144">Una nueva instancia de aplicación de Finance and Operations que tenga datos y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="9329e-145">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que tiene datos de demostración y una nueva instancia de aplicación de Customer Engagement, siga los pasos de la sección [Una nueva instancia de aplicación de Finance and Operations y una nueva instancia de aplicación de Customer Engagement](#new-new) más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="9329e-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="9329e-146">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9329e-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="9329e-147">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="9329e-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="9329e-148">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-149">Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9329e-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="9329e-150">Una nueva instancia de aplicación de Finance and Operations que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="9329e-151">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de Finance and Operations que tiene datos de demostración y una instancia de aplicación de Customer Engagement existente, siga los pasos de la sección [Una nueva instancia de aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente](#new-existing) más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="9329e-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="9329e-152">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9329e-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="9329e-153">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="9329e-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="9329e-154">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-155">Para sincronizar los datos existentes de Dataverse con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9329e-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="9329e-156">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9329e-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="9329e-157">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="9329e-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="9329e-158">[Arranque](bootstrap-company-data.md) los datos Dataverse mediante el uso de un código ISO de empresa de tres letras.</span><span class="sxs-lookup"><span data-stu-id="9329e-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="9329e-159">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-160">Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9329e-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="9329e-161">Una instancia de aplicación de Finance and Operations existente y una nueva instancia de aplicación de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9329e-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="9329e-162">La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de Finance and Operations y una instancia nueva de aplicación de Customer Engagement se realiza en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9329e-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="9329e-163">[Configurar la conexión desde la aplicación de Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="9329e-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="9329e-164">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-165">Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9329e-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="9329e-166">Una instancia de aplicación de Finance and Operations existente y una instancia de aplicación de Customer Engagement existente</span><span class="sxs-lookup"><span data-stu-id="9329e-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="9329e-167">La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de Finance and Operations y una instancia de aplicación de Customer Engagement existente se realiza en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9329e-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="9329e-168">[Configurar la conexión desde la aplicación de Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="9329e-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="9329e-169">Para sincronizar lo datos existentes de Dataverse con la aplicación Finance and Operations, [arranque](bootstrap-company-data.md) los datos Dataverse mediante el uso de un código de empresa ISO de tres letras.</span><span class="sxs-lookup"><span data-stu-id="9329e-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="9329e-170">Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="9329e-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="9329e-171">Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9329e-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="9329e-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9329e-172">Example</span></span>

<span data-ttu-id="9329e-173">Por ejemplo, consulte [Habilitar la asignación de tablas Clientes V3—Contactos](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="9329e-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="9329e-174">Para obtener un enfoque alternativo basado en volúmenes de datos en cada entidad en la que hay que ejecutar una sincronización inicial, consulte [Consideraciones para la sincronización inicial](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="9329e-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]