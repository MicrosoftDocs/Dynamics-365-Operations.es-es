---
title: Escenarios admitidos para la configuración de doble escritura
description: Este tema describe los escenarios que son compatibles con la configuración de doble escritura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 1319f1228b635e207754f7c2516cb2b5353a9edd
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112514"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="79161-103">Escenarios admitidos para la configuración de doble escritura</span><span class="sxs-lookup"><span data-stu-id="79161-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="79161-104">Puede configurar una conexión de doble escritura entre entorno de Finance and Operations y uno de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="79161-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="79161-105">Un **entorno de Finance and Operations** proporciona la plataforma subyacente para las **aplicaciones de Finance and Operations** (por ejemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail y Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="79161-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="79161-106">Un **entorno Common Data Service** proporciona la plataforma subyacente para **aplicaciones basadas en modelos en Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="79161-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="79161-107">El mecanismo de configuración varía, dependiendo de su suscripción y el entorno.</span><span class="sxs-lookup"><span data-stu-id="79161-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="79161-108">Para nuevas instancias de aplicaciones de Finance and Operations, la configuración de una conexión de doble escritura comienza en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="79161-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="79161-109">Si tiene una licencia para Microsoft Power Platform, obtendrá un entorno nuevo Common Data Service entorno si su inquilino no tiene uno.</span><span class="sxs-lookup"><span data-stu-id="79161-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="79161-110">Para instancias existentes de aplicaciones Finance and Operations, la configuración de una conexión de doble escritura comienza en el entorno Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="79161-111">Se admiten los siguientes escenarios de configuración:</span><span class="sxs-lookup"><span data-stu-id="79161-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="79161-112">Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos nueva</span><span class="sxs-lookup"><span data-stu-id="79161-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="79161-113">Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="79161-114">Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos nueva</span><span class="sxs-lookup"><span data-stu-id="79161-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="79161-115">Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="79161-116">Una instancia de aplicación Finance and Operations ya existente y una instancia de aplicación basada en modelos nueva o ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="79161-117">Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos nueva</span><span class="sxs-lookup"><span data-stu-id="79161-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="79161-118">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que no tiene datos y una nueva instancia de una aplicación basada en modelos en Dynamics 365, siga los pasos en [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="79161-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="79161-119">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="79161-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="79161-120">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="79161-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="79161-121">Se aprovisiona una nueva instancia vacía de una aplicación basada en modelos, donde se instala la solución CRM primaria.</span><span class="sxs-lookup"><span data-stu-id="79161-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="79161-122">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="79161-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="79161-123">Los mapas de entidades están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="79161-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="79161-124">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="79161-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="79161-125">Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="79161-126">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que no tiene datos y una instancia ya existente de una aplicación basada en modelos en Dynamics 365, siga los pasos en [Configuración de doble escritura de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="79161-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="79161-127">Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:</span><span class="sxs-lookup"><span data-stu-id="79161-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="79161-128">Se aprovisiona un entorno de Finance and Operations nuevo y vacío.</span><span class="sxs-lookup"><span data-stu-id="79161-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="79161-129">Se establece una conexión de doble escritura para los datos de la compañía DAT.</span><span class="sxs-lookup"><span data-stu-id="79161-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="79161-130">Los mapas de entidades están habilitados para la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="79161-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="79161-131">Ambos entornos están listos para la sincronización de datos en vivo.</span><span class="sxs-lookup"><span data-stu-id="79161-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="79161-132">Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="79161-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="79161-133">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="79161-134">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="79161-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="79161-135">[Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa de tres letras de la Organización Internacional de Normalización (ISO).</span><span class="sxs-lookup"><span data-stu-id="79161-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="79161-136">Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="79161-137">Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos nueva</span><span class="sxs-lookup"><span data-stu-id="79161-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="79161-138">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que tiene datos de demostración y una nueva instancia de una aplicación basada en modelos en Dynamics 365, siga los pasos en la sección [Una instancia de aplicación Finance and Operations nueva y una nueva instancia de aplicación basada en modelos](#new-new) anterior en este tema.</span><span class="sxs-lookup"><span data-stu-id="79161-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="79161-139">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación basada en modelos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="79161-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="79161-140">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="79161-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="79161-141">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="79161-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="79161-142">Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="79161-143">Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que tiene datos de demostración y una instancia ya existente de una aplicación basada en modelos en Dynamics 365, siga los pasos en la sección [Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente](#new-existing) anterior en este tema.</span><span class="sxs-lookup"><span data-stu-id="79161-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="79161-144">Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación basada en modelos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="79161-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="79161-145">Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="79161-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="79161-146">Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.</span><span class="sxs-lookup"><span data-stu-id="79161-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="79161-147">Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="79161-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="79161-148">Cree una nueva empresa en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="79161-149">Agregue la compañía a la configuración de conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="79161-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="79161-150">[Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código ISO de empresa de tres letras.</span><span class="sxs-lookup"><span data-stu-id="79161-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="79161-151">Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="79161-152">Una instancia de aplicación Finance and Operations ya existente y una instancia de aplicación basada en modelos nueva o ya existente</span><span class="sxs-lookup"><span data-stu-id="79161-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="79161-153">La configuración de una conexión de doble escritura entre una instancia existente de una aplicación Finance and Operations y una instancia nueva o existente de una aplicación basada en modelos en Dynamics 365 se produce en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="79161-154">Configure la conexión desde la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="79161-155">Para sincronizar lo datos existentes de Common Data Service con la aplicación Finance and Operations, [arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa ISO de tres letras.</span><span class="sxs-lookup"><span data-stu-id="79161-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="79161-156">Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79161-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
