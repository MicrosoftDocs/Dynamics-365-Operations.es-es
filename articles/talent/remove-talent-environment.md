---
title: Quitar entornos de Talent
description: Este tema recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: e0422a5b7ac227ad03ccafb4e34e614dc770a363
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306187"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="74832-103">Quitar entornos de Talent</span><span class="sxs-lookup"><span data-stu-id="74832-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="74832-104">Este tema recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="74832-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 for Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="74832-105">Quitar un entorno de unidad de prueba</span><span class="sxs-lookup"><span data-stu-id="74832-105">Removing a test drive environment</span></span>

<span data-ttu-id="74832-106">Las unidades de prueba de Talent se aprovisionan con una directiva de caducidad de 60 días.</span><span class="sxs-lookup"><span data-stu-id="74832-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="74832-107">Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="74832-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="74832-108">Vaya al [Centro de administración de PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="74832-108">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="74832-109">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="74832-109">Select **Environments**.</span></span>
3. <span data-ttu-id="74832-110">Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="74832-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="74832-111">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="74832-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="74832-112">El entorno existente de la unidad de prueba se eliminará.</span><span class="sxs-lookup"><span data-stu-id="74832-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="74832-113">Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba.</span><span class="sxs-lookup"><span data-stu-id="74832-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="74832-114">Quitar un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="74832-114">Removing a production environment</span></span>

<span data-ttu-id="74832-115">Este tema asume que ha comprado Talent a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA).</span><span class="sxs-lookup"><span data-stu-id="74832-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="74832-116">Dado que un solo entorno de Talent está “contenido” dentro de un único entorno de PowerApps, hay dos opciones que deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="74832-116">Since a single Talent environment is “contained” within a single PowerApps environment, there are two options to consider.</span></span> <span data-ttu-id="74832-117">La primera opción implica quitar todo el entorno de PowerApps; la segunda opción implica sólo quitar Talent.</span><span class="sxs-lookup"><span data-stu-id="74832-117">The first option involves removing the entire PowerApps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="74832-118">Se prefiere la primera opción cuando ha creado un entorno de PowerApps expresamente con el fin de aprovisionar Talent y que acaba de empezar la implementación, o no tiene ninguna integración establecida.</span><span class="sxs-lookup"><span data-stu-id="74832-118">The first option is preferred when you have created a PowerApps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="74832-119">La segunda opción es adecuada cuando tiene un entorno PowerApps establecido cumplimentado con datos enriquecidos que se optimizan en PowerApps y flujos.</span><span class="sxs-lookup"><span data-stu-id="74832-119">The second option is appropriate when you have an established PowerApps environment populated with rich data that's leveraged in PowerApps and Flows.</span></span>

> [!Important]
> <span data-ttu-id="74832-120">Antes de eliminar el entorno de PowerApps, asegúrese de que no se está utilizando para integraciones de datos enriquecidos fuera del ámbito de Talent.</span><span class="sxs-lookup"><span data-stu-id="74832-120">Before removing the PowerApps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="74832-121">Tenga también en cuenta que los entornos de PowerApps predeterminados no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="74832-121">Also note that the default PowerApps environments cannot be removed.</span></span> 

<span data-ttu-id="74832-122">Para quitar el entorno completo de PowerApps, incluidos Talent y las aplicaciones y los flujos asociados:</span><span class="sxs-lookup"><span data-stu-id="74832-122">To remove the entire PowerApps environment, including Talent and the associated Apps and Flows:</span></span>

1. <span data-ttu-id="74832-123">Vaya al [Centro de administración de PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="74832-123">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="74832-124">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="74832-124">Select **Environments**.</span></span>
3. <span data-ttu-id="74832-125">Seleccione el entorno que se van a eliminar.</span><span class="sxs-lookup"><span data-stu-id="74832-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="74832-126">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="74832-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="74832-127">Espere hasta que se complete la eliminación.</span><span class="sxs-lookup"><span data-stu-id="74832-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="74832-128">Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) mediante la cuenta que ha utilizado para suscribirse a Talent.</span><span class="sxs-lookup"><span data-stu-id="74832-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="74832-129">Seleccione el proyecto de Talent que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="74832-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="74832-130">En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**.</span><span class="sxs-lookup"><span data-stu-id="74832-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="74832-131">Seleccione la instancia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="74832-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="74832-132">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="74832-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="74832-133">Para quitar un entorno de Talent de un entorno de PowerApps existente, complete estos pasos.</span><span class="sxs-lookup"><span data-stu-id="74832-133">To remove a Talent environment from an existing PowerApps environment, complete the following steps.</span></span> <span data-ttu-id="74832-134">Tenga en cuenta que la necesidad de incluir al soporte y de contactar al equipo de Talent DevOps es temporal hasta que esta característica se habilite directamente en el LCS.</span><span class="sxs-lookup"><span data-stu-id="74832-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="74832-135">Póngase en contacto con el soporte para iniciar una solicitud de eliminación.</span><span class="sxs-lookup"><span data-stu-id="74832-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="74832-136">El equipo de soporte iniciará una solicitud de eliminación con el equipo de Talent DevOps.</span><span class="sxs-lookup"><span data-stu-id="74832-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="74832-137">Continúe tras recibir notificación de que se ha eliminado el entorno.</span><span class="sxs-lookup"><span data-stu-id="74832-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="74832-138">Inicie sesión en LCS mediante la cuenta que ha utilizado para suscribirse a Talent.</span><span class="sxs-lookup"><span data-stu-id="74832-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="74832-139">Seleccione el proyecto de Talent que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="74832-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="74832-140">En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**.</span><span class="sxs-lookup"><span data-stu-id="74832-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="74832-141">Seleccione la instancia que desea quitar, que debe estar marcada con un estado de implementación **No superado**.</span><span class="sxs-lookup"><span data-stu-id="74832-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="74832-142">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="74832-142">Select **Remove instance** and confirm your decision.</span></span> 

