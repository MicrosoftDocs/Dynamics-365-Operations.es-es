---
title: Instalar el complemento Inteligencia IoT en LCS
description: Este tema explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad8b33633646f27bc368dc4bbedc1eb64c150a9f
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437165"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="04c1d-103">Instalar el complemento Inteligencia IoT en LCS</span><span class="sxs-lookup"><span data-stu-id="04c1d-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04c1d-104">Este tema explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="04c1d-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="04c1d-105">Tenga en cuenta que los complementos no se pueden instalar en un entorno de demostración/prueba.</span><span class="sxs-lookup"><span data-stu-id="04c1d-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="04c1d-106">Para poder instalar el complemento, debe [crear los recursos de Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="04c1d-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="04c1d-107">Configurar el entorno LCS</span><span class="sxs-lookup"><span data-stu-id="04c1d-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="04c1d-108">Abra LCS y vaya a su entorno Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="04c1d-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="04c1d-109">Desplácese a la sección **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="04c1d-110">Seleccione **Instalar un nuevo complemento** para mostrar la lista de complementos que se han habilitado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="04c1d-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="04c1d-111">En el cuadro de diálogo **Seleccionar un complemento para instalar**, seleccione **Inteligencia IoT**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="04c1d-112">En el cuadro de diálogo **Configurar complemento**, proporcione los detalles de su centro de IoT y caché Redis.</span><span class="sxs-lookup"><span data-stu-id="04c1d-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="04c1d-113">Puede encontrar los valores necesarios en el almacén de claves que creó en [Crear recursos de Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="04c1d-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="04c1d-114">**Id. de inquilino**: en Azure Portal, vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Id. de directorio**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="04c1d-115">Pegue ese valor en el cuadro de diálogo **Configurar complemento**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="04c1d-116">**URI de almacén de claves de punto final compatible con IoT Event Hub**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Nombre DNS**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="04c1d-117">Pegue ese valor en el cuadro de diálogo **Configurar complemento**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="04c1d-118">**Nombre secreto de punto final compatible con IoT Event Hub**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Secretos** y copie el nombre del secreto donde se almacena la cadena de conexión del centro de eventos para el centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="04c1d-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="04c1d-119">Pegue ese valor en el cuadro de diálogo **Configurar complemento**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="04c1d-120">**URI de almacén de claves de caché Redis**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Nombre DNS**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="04c1d-121">Pegue ese valor en el cuadro de diálogo **Configurar complemento**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="04c1d-122">**Nombre secreto de punto final de caché Redis**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Secretos** y copie el nombre del secreto donde se almacena la cadena de la caché Redis.</span><span class="sxs-lookup"><span data-stu-id="04c1d-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="04c1d-123">Pegue ese valor en el cuadro de diálogo **Configurar complemento**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="04c1d-124">Seleccione la casilla de verificación para aceptar los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="04c1d-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="04c1d-125">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-125">Select **Install**.</span></span>
8. <span data-ttu-id="04c1d-126">Aparece un cuadro de mensaje que dice: "El complemento se ha activado correctamente para la instalación".</span><span class="sxs-lookup"><span data-stu-id="04c1d-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="04c1d-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-127">Select **OK**.</span></span>

<span data-ttu-id="04c1d-128">La configuración de LCS ya está completa.</span><span class="sxs-lookup"><span data-stu-id="04c1d-128">LCS setup is now completed.</span></span> <span data-ttu-id="04c1d-129">El siguiente paso es [configurar los escenarios](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="04c1d-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="04c1d-130">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="04c1d-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="04c1d-131">En Supply Chain Management, [desactive los escenarios](iot-scenario-setup.md#disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="04c1d-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#disable-a-scenario).</span></span>
2. <span data-ttu-id="04c1d-132">En LCS, vaya a sus detalles de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="04c1d-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="04c1d-133">Desplácese a la sección **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="04c1d-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="04c1d-134">Seleccione **Desinstalar** para el complemento Inteligencia IoT.</span><span class="sxs-lookup"><span data-stu-id="04c1d-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
