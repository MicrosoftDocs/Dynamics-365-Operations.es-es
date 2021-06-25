---
title: Habilitar propuestas de presupuesto (versión preliminar)
description: Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222543"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="13769-103">Habilitar propuestas de presupuesto (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="13769-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="13769-104">Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="13769-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="13769-105">Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno.</span><span class="sxs-lookup"><span data-stu-id="13769-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="13769-106">Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="13769-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="13769-107">(Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="13769-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="13769-108">Omita este paso si usa la versión 10.0.20 o posterior, o si usa una implementación de Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="13769-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="13769-109">El equipo de información financiera ya debería haber activado el paquete piloto por usted.</span><span class="sxs-lookup"><span data-stu-id="13769-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="13769-110">Si no ve la característica en el espacio de trabajo **Administración de características**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="13769-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="13769-111">Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="13769-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="13769-112">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="13769-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="13769-113">Busque **Propuesta de presupuesto** y active esa característica.</span><span class="sxs-lookup"><span data-stu-id="13769-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="13769-114">Vaya a **Presupuestación \> Configurar \> Presupuesto básico \> Propuesta de presupuesto (versión preliminar)** y seleccione **Habilitar característica**.</span><span class="sxs-lookup"><span data-stu-id="13769-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
