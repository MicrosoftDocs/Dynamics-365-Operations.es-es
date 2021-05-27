---
title: Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eb0b8b419b302fbd0bc107bca22f8b26774ba3c7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019844"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="02c4d-103">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02c4d-104">Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="02c4d-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="02c4d-105">Para proporcionar a Teams con información de Dynamics 365 Commerce y sincronizar las funciones de administración de tareas entre Teams y la aplicación de punto de venta (PDV), debe habilitar las funciones de integración en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="02c4d-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="02c4d-106">Cuando habilita la integración de Teams, acepta compartir sus datos con Teams.</span><span class="sxs-lookup"><span data-stu-id="02c4d-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="02c4d-107">Los datos que se comparten con Teams pueden residir en un país diferente al de sus datos de Commerce y pueden estar sujetos a diferentes estándares de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="02c4d-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="02c4d-108">Para obtener más información, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="02c4d-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="02c4d-109">Para obtener información sobre las políticas de privacidad de Microsoft, consulte la [Declaración de privacidad de Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="02c4d-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="02c4d-110">Habilitar la integración Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-110">Enable Teams integration</span></span>

<span data-ttu-id="02c4d-111">Antes de que pueda habilitar la integración de Microsoft Teams con Commerce, debe registrar la aplicación Teams con su inquilino en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="02c4d-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="02c4d-112">Para registrar la aplicación Teams con su inquilino en Azure Portal, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="02c4d-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="02c4d-113">Siga los pasos en [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar la aplicación de Teams con su inquilino en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="02c4d-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="02c4d-114">Copie el valor **Identificador de aplicación (cliente)** de la página **Visión general** de la aplicación registrada.</span><span class="sxs-lookup"><span data-stu-id="02c4d-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="02c4d-115">Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="02c4d-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="02c4d-116">Copie el valor del certificado que introdujo cuando [agregó un certificado](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="02c4d-116">Copy the certificate value that was entered when you [added a certificate](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="02c4d-117">El certificado también se conoce como clave pública o clave de aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c4d-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="02c4d-118">Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="02c4d-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="02c4d-119">Para habilitar la integración de Teams en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="02c4d-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="02c4d-120">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="02c4d-121">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="02c4d-122">Establezca la opción **Habilitar integración con Microsoft Teams** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="02c4d-123">En los campos **Identificación de aplicación** y **Clave de aplicación**, introduzca los valores que obtuvo cuando registró la aplicación Teams en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="02c4d-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="02c4d-124">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="02c4d-125">La siguiente ilustración muestra un ejemplo de la configuración de la integración de Teams en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="02c4d-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configuración de integración de Teams en la sede de Commerce](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="02c4d-127">Deshabilitar la integración Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-127">Disable Teams integration</span></span>

<span data-ttu-id="02c4d-128">Para deshabilitar la integración de Microsoft Teams en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="02c4d-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="02c4d-129">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="02c4d-130">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="02c4d-131">Establezca la opción **Habilitar integración con Microsoft Teams** a **No**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="02c4d-132">Borre los valores de los campos **Identificación de aplicación** y **Clave de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="02c4d-133">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02c4d-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="02c4d-134">Después de deshabilitar la integración de Teams con Commerce, los terminales PDV ya no mostrarán las tareas publicadas desde la aplicación Teams.</span><span class="sxs-lookup"><span data-stu-id="02c4d-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02c4d-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="02c4d-135">Additional resources</span></span>

[<span data-ttu-id="02c4d-136">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="02c4d-137">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="02c4d-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="02c4d-138">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="02c4d-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="02c4d-139">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="02c4d-140">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="02c4d-141">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c4d-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)