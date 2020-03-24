---
title: Quitar una instancia
description: Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a40b9619e92b81272208ad4241a2455330a342a7
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124437"
---
# <a name="remove-an-instance"></a><span data-ttu-id="570f3-103">Quitar una instancia</span><span class="sxs-lookup"><span data-stu-id="570f3-103">Remove an instance</span></span>

<span data-ttu-id="570f3-104">Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="570f3-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="570f3-105">Quitar un entorno de unidad de prueba</span><span class="sxs-lookup"><span data-stu-id="570f3-105">Remove a test drive environment</span></span>

<span data-ttu-id="570f3-106">Las unidades de prueba de Human Resources se aprovisionan con una directiva de caducidad de 60 días.</span><span class="sxs-lookup"><span data-stu-id="570f3-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="570f3-107">Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="570f3-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="570f3-108">Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="570f3-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="570f3-109">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="570f3-109">Select **Environments**.</span></span>
3. <span data-ttu-id="570f3-110">Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="570f3-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="570f3-111">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="570f3-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="570f3-112">El entorno existente de la unidad de prueba se eliminará.</span><span class="sxs-lookup"><span data-stu-id="570f3-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="570f3-113">Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba.</span><span class="sxs-lookup"><span data-stu-id="570f3-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="570f3-114">Quitar un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="570f3-114">Remove a production environment</span></span>

<span data-ttu-id="570f3-115">Este artículo asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA).</span><span class="sxs-lookup"><span data-stu-id="570f3-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="570f3-116">Dado que un solo entorno de Human Resources está “contenido” dentro de un único entorno de Power Apps, hay dos opciones que deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="570f3-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="570f3-117">La primera opción implica quitar todo el entorno de Power Apps; la segunda opción implica sólo quitar Human Resources.</span><span class="sxs-lookup"><span data-stu-id="570f3-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="570f3-118">Se prefiere la primera opción cuando ha creado un entorno de Power Apps expresamente con el fin de aprovisionar Human Resources y que acaba de empezar la implementación, o no tiene ninguna integración establecida.</span><span class="sxs-lookup"><span data-stu-id="570f3-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="570f3-119">La segunda opción es adecuada cuando tiene un entorno Power Apps establecido cumplimentado con datos enriquecidos que se optimizan en Power Apps y Power Automate.</span><span class="sxs-lookup"><span data-stu-id="570f3-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="570f3-120">Antes de eliminar el entorno de Power Apps, asegúrese de que no se está utilizando para integraciones de datos enriquecidos fuera del ámbito de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="570f3-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="570f3-121">Tenga también en cuenta que los entornos de Power Apps predeterminados no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="570f3-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="570f3-122">Para quitar el entorno completo de Power Apps, incluidos Human Resources y las aplicaciones y los flujos asociados:</span><span class="sxs-lookup"><span data-stu-id="570f3-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="570f3-123">Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="570f3-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="570f3-124">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="570f3-124">Select **Environments**.</span></span>
3. <span data-ttu-id="570f3-125">Seleccione el entorno que se van a eliminar.</span><span class="sxs-lookup"><span data-stu-id="570f3-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="570f3-126">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="570f3-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="570f3-127">Espere hasta que se complete la eliminación.</span><span class="sxs-lookup"><span data-stu-id="570f3-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="570f3-128">Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) mediante la cuenta que ha utilizado para suscribirse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="570f3-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="570f3-129">Seleccione el proyecto de Human Resources que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="570f3-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="570f3-130">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="570f3-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="570f3-131">Seleccione la instancia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="570f3-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="570f3-132">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="570f3-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="570f3-133">Para quitar un entorno de Human Resources de un entorno de Power Apps existente, complete estos pasos.</span><span class="sxs-lookup"><span data-stu-id="570f3-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="570f3-134">Tenga en cuenta que la necesidad de incluir al soporte y de contactar al equipo de Human Resources DevOps es temporal hasta que esta característica se habilite directamente en el LCS.</span><span class="sxs-lookup"><span data-stu-id="570f3-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="570f3-135">Póngase en contacto con el soporte para iniciar una solicitud de eliminación.</span><span class="sxs-lookup"><span data-stu-id="570f3-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="570f3-136">El equipo de soporte iniciará una solicitud de eliminación con el equipo de Human Resources DevOps.</span><span class="sxs-lookup"><span data-stu-id="570f3-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="570f3-137">Continúe tras recibir notificación de que se ha eliminado el entorno.</span><span class="sxs-lookup"><span data-stu-id="570f3-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="570f3-138">Inicie sesión en LCS mediante la cuenta que ha utilizado para suscribirse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="570f3-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="570f3-139">Seleccione el proyecto de Human Resources que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="570f3-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="570f3-140">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="570f3-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="570f3-141">Seleccione la instancia que desea quitar, que debe estar marcada con un estado de implementación **No superado**.</span><span class="sxs-lookup"><span data-stu-id="570f3-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="570f3-142">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="570f3-142">Select **Remove instance** and confirm your decision.</span></span> 
