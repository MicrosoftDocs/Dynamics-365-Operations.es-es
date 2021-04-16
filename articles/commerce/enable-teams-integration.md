---
title: Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842738"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="633ab-103">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="633ab-104">Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="633ab-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="633ab-105">Para proporcionar a Teams con información de Dynamics 365 Commerce y sincronizar las funciones de administración de tareas entre Teams y la aplicación de punto de venta (PDV), debe habilitar las funciones de integración en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="633ab-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="633ab-106">Cuando habilita la integración de Teams, acepta compartir sus datos con Teams.</span><span class="sxs-lookup"><span data-stu-id="633ab-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="633ab-107">Los datos que se comparten con Teams pueden residir en un país diferente al de sus datos de Commerce y pueden estar sujetos a diferentes estándares de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="633ab-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="633ab-108">Para obtener más información, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="633ab-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="633ab-109">Para obtener información sobre las políticas de privacidad de Microsoft, consulte la [Declaración de privacidad de Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="633ab-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="633ab-110">Habilitar la integración Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-110">Enable Teams integration</span></span>

<span data-ttu-id="633ab-111">Antes de que pueda habilitar la integración de Microsoft Teams con Commerce, debe registrar la aplicación Teams con su inquilino en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="633ab-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="633ab-112">Para registrar la aplicación Teams con su inquilino en Azure Portal, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="633ab-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="633ab-113">Siga los pasos en [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) para registrar la aplicación de Teams con su inquilino en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="633ab-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="633ab-114">Copie el valor **Identificador de aplicación (cliente)** de la página **Visión general** de la aplicación registrada.</span><span class="sxs-lookup"><span data-stu-id="633ab-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="633ab-115">Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="633ab-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="633ab-116">Copie el valor del certificado que introdujo cuando [agregó un certificado](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="633ab-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="633ab-117">El certificado también se conoce como clave pública o clave de aplicación.</span><span class="sxs-lookup"><span data-stu-id="633ab-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="633ab-118">Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="633ab-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="633ab-119">Para habilitar la integración de Teams en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="633ab-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="633ab-120">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="633ab-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="633ab-121">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="633ab-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="633ab-122">Establezca la opción **Habilitar integración con Microsoft Teams** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="633ab-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="633ab-123">En los campos **Identificación de aplicación** y **Clave de aplicación**, introduzca los valores que obtuvo cuando registró la aplicación Teams en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="633ab-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="633ab-124">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="633ab-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="633ab-125">La siguiente ilustración muestra un ejemplo de la configuración de la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="633ab-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configuración de integración de Teams en la sede de Commerce](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="633ab-127">Deshabilitar la integración Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-127">Disable Teams integration</span></span>

<span data-ttu-id="633ab-128">Para deshabilitar la integración de Microsoft Teams en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="633ab-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="633ab-129">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="633ab-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="633ab-130">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="633ab-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="633ab-131">Establezca la opción **Habilitar integración con Microsoft Teams** a **No**.</span><span class="sxs-lookup"><span data-stu-id="633ab-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="633ab-132">Borre los valores de los campos **Identificación de aplicación** y **Clave de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="633ab-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="633ab-133">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="633ab-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="633ab-134">Después de deshabilitar la integración de Teams con Commerce, los terminales PDV ya no mostrarán las tareas publicadas desde la aplicación Teams.</span><span class="sxs-lookup"><span data-stu-id="633ab-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="633ab-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="633ab-135">Additional resources</span></span>

[<span data-ttu-id="633ab-136">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="633ab-137">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="633ab-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="633ab-138">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="633ab-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="633ab-139">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="633ab-140">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="633ab-141">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="633ab-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
