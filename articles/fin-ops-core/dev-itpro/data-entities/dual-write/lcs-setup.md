---
title: Configuración de doble escritura desde Lifecycle Services
description: Este tema explica cómo configurar una conexión de doble escritura entre un entorno nuevo de Finance and Operations y un entorno nuevo de Dataverse desde Microsoft Dynamics Lifecycle Services (LCS).
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 25db9c58c3d09e44dcf11b48cae1a9eda4241c35
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683534"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="c9277-103">Configuración de doble escritura desde Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c9277-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c9277-104">Este tema explica cómo configurar una conexión de doble escritura entre un entorno nuevo de Finance and Operations y un entorno nuevo de Dataverse desde Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c9277-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9277-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c9277-105">Prerequisites</span></span>

<span data-ttu-id="c9277-106">Debe ser administrador para configurar una conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c9277-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="c9277-107">Debe tener acceso al inquilino.</span><span class="sxs-lookup"><span data-stu-id="c9277-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="c9277-108">Debes ser administrador tanto en entornos Finance and Operations y entornos Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c9277-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="c9277-109">Configurar una conexión de doble escritura</span><span class="sxs-lookup"><span data-stu-id="c9277-109">Set up a dual-write connection</span></span>

<span data-ttu-id="c9277-110">Siga estos pasos para configurar una conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c9277-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="c9277-111">En LCS, vaya a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="c9277-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="c9277-112">Seleccione **Configurar** para implementar un nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="c9277-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="c9277-113">Seleccione la versión.</span><span class="sxs-lookup"><span data-stu-id="c9277-113">Select the version.</span></span> 
4. <span data-ttu-id="c9277-114">Seleccione la topología.</span><span class="sxs-lookup"><span data-stu-id="c9277-114">Select the topology.</span></span> <span data-ttu-id="c9277-115">Si solo hay una topología disponible, se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c9277-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="c9277-116">Complete los primeros pasos en el asistente **Configuraciones de implementación**.</span><span class="sxs-lookup"><span data-stu-id="c9277-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="c9277-117">En la pestaña **Dataverse**, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c9277-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="c9277-118">Si un entorno Dataverse ya está aprovisionado para su inquilino, puede seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="c9277-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="c9277-119">Establezca la opción **Configurar Dataverse** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c9277-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="c9277-120">En el campo **Entornos disponibles**, seleccione el entorno para integrar con sus datos Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9277-120">In the **Available environments** field, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="c9277-121">La lista incluye todos los entornos donde tiene privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c9277-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="c9277-122">Selecciona la casilla de verificación **De acuerdo** para indicar que está de acuerdo con los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="c9277-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Pestaña Dataverse cuando un entorno Dataverse ya está aprovisionado para su inquilino](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="c9277-124">Si su inquilino aún no tiene un entorno Dataverse, se proporcionará un nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="c9277-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="c9277-125">Establezca la opción **Configurar Dataverse** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c9277-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="c9277-126">Escriba un nombre para el entorno Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c9277-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="c9277-127">Seleccione la región para implementar el entorno.</span><span class="sxs-lookup"><span data-stu-id="c9277-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="c9277-128">Seleccione el idioma y la divisa predeterminados para el entorno.</span><span class="sxs-lookup"><span data-stu-id="c9277-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="c9277-129">No puede cambiar el idioma y la moneda más tarde.</span><span class="sxs-lookup"><span data-stu-id="c9277-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="c9277-130">Selecciona la casilla de verificación **De acuerdo** para indicar que está de acuerdo con los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="c9277-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Pestaña Dataverse cuando su inquilino aún no tiene un entorno Dataverse](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="c9277-132">Complete los pasos restantes en el asistente **Configuraciones de implementación**.</span><span class="sxs-lookup"><span data-stu-id="c9277-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="c9277-133">Después de que el entorno tenga un estado de **Implementado**, abra la página de detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="c9277-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="c9277-134">La sección **Información del entorno de Dataverse** muestra los nombres de entorno Finance and Operations y el entorno Dataverse que están vinculados.</span><span class="sxs-lookup"><span data-stu-id="c9277-134">The **Dataverse environment information** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Sección de información de entorno de Dataverse](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="c9277-136">Un administrador del entorno de Finance and Operations debe iniciar sesión en LCS y seleccionar **Enlazar a CDS para aplicaciones** para completar el enlace.</span><span class="sxs-lookup"><span data-stu-id="c9277-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="c9277-137">La página de detalles del entorno muestra la información de contacto del administrador.</span><span class="sxs-lookup"><span data-stu-id="c9277-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="c9277-138">Una vez que se completa el enlace, el estado se actualiza a **Enlace de entorno completado con éxito**.</span><span class="sxs-lookup"><span data-stu-id="c9277-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="c9277-139">Para abrir el espacio de trabajo **Integración de datos** en el entorno Finance and Operations y controlar de las plantillas disponibles, seleccione **Enlazar a CDS para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c9277-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Enlace al botón CDS para aplicaciones en la sección de información del entorno de Dataverse](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="c9277-141">No puede desvincular entornos utilizando LCS.</span><span class="sxs-lookup"><span data-stu-id="c9277-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="c9277-142">Para desvincular un entorno, abra el espacio de trabajo **Integración de datos** en el entorno Finance and Operations, y luego seleccione **Desvincular**.</span><span class="sxs-lookup"><span data-stu-id="c9277-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>
