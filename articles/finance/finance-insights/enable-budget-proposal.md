---
title: Habilitar propuestas de presupuesto (versión preliminar)
description: Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 3a2060d082ed55e3b6fac506898916942ccc9db7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208494"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="88460-103">Habilitar propuestas de presupuesto (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="88460-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="88460-104">Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="88460-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="88460-105">Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno.</span><span class="sxs-lookup"><span data-stu-id="88460-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="88460-106">Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="88460-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="88460-107">(Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="88460-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="88460-108">Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="88460-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="88460-109">El equipo de Finance Insights ya debería haber activado el paquete piloto por usted.</span><span class="sxs-lookup"><span data-stu-id="88460-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="88460-110">Si no ve la característica en el espacio de trabajo **Administración de características**, o si tiene problemas cuando intenta activarla, envíe un correo electrónico al [equipo de Vista previa de la aplicación Finance Insights](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="88460-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="88460-111">Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="88460-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="88460-112">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="88460-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="88460-113">Busque **Propuesta de presupuesto** y active esa característica.</span><span class="sxs-lookup"><span data-stu-id="88460-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="88460-114">Vaya a **Presupuestación \> Configurar \> Presupuesto básico \> Propuesta de presupuesto (versión preliminar)** y seleccione **Habilitar característica**.</span><span class="sxs-lookup"><span data-stu-id="88460-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="88460-115">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="88460-115">Privacy notice</span></span>
<span data-ttu-id="88460-116">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="88460-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]