---
title: Configuración de la doble escritura de Lifecycle Services
description: Este tema explica cómo configurar una conexión de escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103578"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="d5477-103">Configuración de la doble escritura de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="d5477-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d5477-104">Este tema explica cómo habilitar escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d5477-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5477-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d5477-105">Prerequisites</span></span>

<span data-ttu-id="d5477-106">Debe completar la integración de Power Platform como se describe en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d5477-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="d5477-107">Integración de Power Platform: habilitar durante la implementación del entorno</span><span class="sxs-lookup"><span data-stu-id="d5477-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="d5477-108">Integración de Power Platform: configurará tras la implementación del entorno</span><span class="sxs-lookup"><span data-stu-id="d5477-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="d5477-109">Configurar escritura dual para nuevos entornos de Dataverse</span><span class="sxs-lookup"><span data-stu-id="d5477-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="d5477-110">Siga estos pasos para configurar la escritura dual desde la página de LCS **Detalles del entorno**:</span><span class="sxs-lookup"><span data-stu-id="d5477-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="d5477-111">En la página **Detalles del entorno**, expanda la sección **Integración de Power Platform**.</span><span class="sxs-lookup"><span data-stu-id="d5477-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="d5477-112">Seleccione el botón **Aplicación de escritura dual**.</span><span class="sxs-lookup"><span data-stu-id="d5477-112">Select the **Dual-write application** button.</span></span>

    ![Integración de Power Platform](media/powerplat_integration_step2.png)

3. <span data-ttu-id="d5477-114">Revise los términos y condiciones, y luego seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d5477-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="d5477-115">Seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="d5477-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="d5477-116">Puede supervisar el progreso actualizando periódicamente la página de detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="d5477-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="d5477-117">La configuración suele tardar 30 minutos o menos.</span><span class="sxs-lookup"><span data-stu-id="d5477-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="d5477-118">Cuando se complete la configuración, un mensaje le informará si el proceso tuvo éxito o si hubo un error.</span><span class="sxs-lookup"><span data-stu-id="d5477-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="d5477-119">Si la configuración falla, se muestra un mensaje de error relacionado.</span><span class="sxs-lookup"><span data-stu-id="d5477-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="d5477-120">Debe corregir cualquier error antes de pasar al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="d5477-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="d5477-121">Seleccione **Enlazar al entorno de Power Platform** para crear un vínculo entre Dataverse y las bases de datos del entorno actual.</span><span class="sxs-lookup"><span data-stu-id="d5477-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="d5477-122">Esto suele tardar menos de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="d5477-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular al entorno de Power Platform":::

8. <span data-ttu-id="d5477-124">Cuando se completa el vínculo, se muestra un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="d5477-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="d5477-125">Utilice el enlace para iniciar sesión en el área de administración de escritura dual en el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d5477-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="d5477-126">Desde allí, puede configurar asignaciones de entidades.</span><span class="sxs-lookup"><span data-stu-id="d5477-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="d5477-127">Configurar escritura dual para un entorno de Dataverse ya existente</span><span class="sxs-lookup"><span data-stu-id="d5477-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="d5477-128">Para configurar la escritura dual para un entorno de Dataverse, debe crear una [incidencia de soporte técnico](../../lifecycle-services/lcs-support.md) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5477-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="d5477-129">La incidencia debe incluir:</span><span class="sxs-lookup"><span data-stu-id="d5477-129">The ticket must include:</span></span>

+ <span data-ttu-id="d5477-130">Su Id. de entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d5477-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="d5477-131">El nombre de su entorno de Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="d5477-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="d5477-132">La ID de organización de Dataverse la ID de entorno de Power Platform del Centro de administración de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="d5477-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="d5477-133">En su ticket, solicite que el ID sea la instancia utilizada para la integración de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="d5477-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="d5477-134">No puede desvincular entornos utilizando LCS.</span><span class="sxs-lookup"><span data-stu-id="d5477-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="d5477-135">Para desvincular un entorno, abra el espacio de trabajo **Integración de datos** en el entorno Finance and Operations, y luego seleccione **Desvincular**.</span><span class="sxs-lookup"><span data-stu-id="d5477-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
