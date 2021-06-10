---
title: Quitar una instancia
description: Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72a5b99150e5ccdf9a542b569c94c64cb95923fd
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053620"
---
# <a name="remove-an-instance"></a><span data-ttu-id="a97b1-103">Quitar una instancia</span><span class="sxs-lookup"><span data-stu-id="a97b1-103">Remove an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a97b1-104">Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="a97b1-105">Quitar un entorno de unidad de prueba</span><span class="sxs-lookup"><span data-stu-id="a97b1-105">Remove a test drive environment</span></span>

<span data-ttu-id="a97b1-106">Las unidades de prueba de Human Resources se aprovisionan con una directiva de caducidad de 60 días.</span><span class="sxs-lookup"><span data-stu-id="a97b1-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="a97b1-107">Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a97b1-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="a97b1-108">Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a97b1-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="a97b1-109">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-109">Select **Environments**.</span></span>
3. <span data-ttu-id="a97b1-110">Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="a97b1-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="a97b1-111">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="a97b1-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="a97b1-112">El entorno existente de la unidad de prueba se eliminará.</span><span class="sxs-lookup"><span data-stu-id="a97b1-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="a97b1-113">Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba.</span><span class="sxs-lookup"><span data-stu-id="a97b1-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="a97b1-114">Quitar un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="a97b1-114">Remove a production environment</span></span>

<span data-ttu-id="a97b1-115">Este artículo asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA).</span><span class="sxs-lookup"><span data-stu-id="a97b1-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="a97b1-116">Dado que un solo entorno de Human Resources está “contenido” dentro de un único entorno de Power Apps, hay dos opciones que deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="a97b1-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="a97b1-117">La primera opción implica quitar todo el entorno de Power Apps; la segunda opción implica sólo quitar Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="a97b1-118">Se prefiere la primera opción cuando ha creado un entorno de Power Apps expresamente con el fin de aprovisionar Human Resources y que acaba de empezar la implementación, o no tiene ninguna integración establecida.</span><span class="sxs-lookup"><span data-stu-id="a97b1-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="a97b1-119">La segunda opción es adecuada cuando tiene un entorno Power Apps establecido cumplimentado con datos enriquecidos que se optimizan en Power Apps y Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a97b1-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="a97b1-120">Antes de eliminar el entorno de Power Apps, asegúrese de que no se está utilizando para integraciones de datos enriquecidos fuera del ámbito de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="a97b1-121">Tenga también en cuenta que los entornos de Power Apps predeterminados no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="a97b1-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="a97b1-122">Para quitar el entorno completo de Power Apps, incluidos Human Resources y las aplicaciones y los flujos asociados:</span><span class="sxs-lookup"><span data-stu-id="a97b1-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="a97b1-123">Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a97b1-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="a97b1-124">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-124">Select **Environments**.</span></span>
3. <span data-ttu-id="a97b1-125">Seleccione el entorno que se van a eliminar.</span><span class="sxs-lookup"><span data-stu-id="a97b1-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="a97b1-126">Seleccione **Eliminar** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="a97b1-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="a97b1-127">Espere hasta que se complete la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a97b1-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="a97b1-128">Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) mediante la cuenta que ha utilizado para suscribirse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="a97b1-129">Seleccione el proyecto de Human Resources que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="a97b1-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="a97b1-130">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="a97b1-131">Seleccione la instancia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="a97b1-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="a97b1-132">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="a97b1-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="a97b1-133">Para quitar un entorno de Human Resources de un entorno de Power Apps existente, complete estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a97b1-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="a97b1-134">Tenga en cuenta que la necesidad de incluir al soporte y de contactar al equipo de Human Resources DevOps es temporal hasta que esta característica se habilite directamente en el LCS.</span><span class="sxs-lookup"><span data-stu-id="a97b1-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="a97b1-135">Póngase en contacto con el soporte para iniciar una solicitud de eliminación.</span><span class="sxs-lookup"><span data-stu-id="a97b1-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="a97b1-136">El equipo de soporte iniciará una solicitud de eliminación con el equipo de Human Resources DevOps.</span><span class="sxs-lookup"><span data-stu-id="a97b1-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="a97b1-137">Continúe tras recibir notificación de que se ha eliminado el entorno.</span><span class="sxs-lookup"><span data-stu-id="a97b1-137">Continue after you receive word that the environment has been removed.</span></span>
4. <span data-ttu-id="a97b1-138">Inicie sesión en LCS mediante la cuenta que ha utilizado para suscribirse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="a97b1-139">Seleccione el proyecto de Human Resources que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="a97b1-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="a97b1-140">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="a97b1-141">Seleccione la instancia que desea quitar, que debe estar marcada con el estado de implementación **Eliminada**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Deleted**.</span></span>
8. <span data-ttu-id="a97b1-142">Seleccione **Quitar instancia** y confirme la decisión.</span><span class="sxs-lookup"><span data-stu-id="a97b1-142">Select **Remove instance** and confirm your decision.</span></span> 

## <a name="recover-a-soft-deleted-environment"></a><span data-ttu-id="a97b1-143">Recuperar un entorno eliminado temporalmente</span><span class="sxs-lookup"><span data-stu-id="a97b1-143">Recover a soft-deleted environment</span></span>

<span data-ttu-id="a97b1-144">Si elimina el entorno Power Apps al que está conectado su entorno de Human Resources el estado del entorno de Human Resources en Lifecycle Services será **Eliminado temporalmente**.</span><span class="sxs-lookup"><span data-stu-id="a97b1-144">If you delete the Power Apps environment that your Human Resources environment is connected to, the status of the Human Resources environment in Lifecycle Services will be **Soft deleted**.</span></span> <span data-ttu-id="a97b1-145">En este caso, los usuarios no pueden conectarse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-145">In this case, users can't connect to Human Resources.</span></span>

<span data-ttu-id="a97b1-146">Para restaurar el entorno:</span><span class="sxs-lookup"><span data-stu-id="a97b1-146">To restore the environment:</span></span>

1. <span data-ttu-id="a97b1-147">Siga las instrucciones en [Recuperar el entorno de Power Apps](/power-platform/admin/recover-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a97b1-147">Follow the instructions in [Recover the Power Apps environment](/power-platform/admin/recover-environment.md).</span></span>

2. <span data-ttu-id="a97b1-148">Póngase en contacto con el soporte técnico para restaurar el entorno de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a97b1-148">Contact Support to restore the Human Resources environment.</span></span> <span data-ttu-id="a97b1-149">Para obtener más información, consulte [Obtener soporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="a97b1-149">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

> [!Warning]
> <span data-ttu-id="a97b1-150">Los entornos de Power Apps solo se guardan durante siete días después de la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a97b1-150">Power Apps environments are only saved for seven days after deletion.</span></span> <span data-ttu-id="a97b1-151">Debe recuperar el entorno dentro de un período de siete días.</span><span class="sxs-lookup"><span data-stu-id="a97b1-151">You must recover the environment within the seven day period.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]