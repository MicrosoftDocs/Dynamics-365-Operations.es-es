---
title: Habilitar la previsión de flujo de efectivo (versión preliminar)
description: Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.
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
ms.openlocfilehash: 1977dac4a3ab66cca2248dc0124d3a06d6963f40
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978773"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="37ea1-103">Habilitar la previsión de flujo de efectivo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="37ea1-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="37ea1-104">Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="37ea1-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="37ea1-105">Para utilizar predicciones de pagos en el flujo de efectivo, debe configurar la característica de predicciones de pagos de clientes como se describe en [Habilitar las predicciones de pagos de clientes](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="37ea1-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="37ea1-106">Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno.</span><span class="sxs-lookup"><span data-stu-id="37ea1-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="37ea1-107">Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="37ea1-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="37ea1-108">(Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="37ea1-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="37ea1-109">Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="37ea1-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="37ea1-110">El equipo de Finance Insights ya debería haber activado el paquete piloto por usted.</span><span class="sxs-lookup"><span data-stu-id="37ea1-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="37ea1-111">Si no ve las características en el espacio de trabajo **Administración de funciones**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="37ea1-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="37ea1-112">Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37ea1-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="37ea1-113">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="37ea1-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="37ea1-114">Active las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="37ea1-114">Turn on the following features:</span></span>

        - <span data-ttu-id="37ea1-115">Nuevo control de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="37ea1-115">New grid control</span></span>
        - <span data-ttu-id="37ea1-116">Agrupación en cuadrículas (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="37ea1-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="37ea1-117">Previsiones de pago de clientes (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="37ea1-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="37ea1-118">Previsiones de flujo de efectivo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="37ea1-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="37ea1-119">Vaya a **Gestión de efectivo y banco \> Configuración de pronóstico de flujo de efectivo** y agregue las cuentas de liquidez que deben incluirse en las previsiones.</span><span class="sxs-lookup"><span data-stu-id="37ea1-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37ea1-120">Si no se configuran cuentas de liquidez, no se puede generar el flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="37ea1-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="37ea1-121">Vaya a **Gestión de efectivo y banco \> Configurar \> Finance Insights (versión preliminar) \> Previsiones de flujo de efectivo (versión preliminar)** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37ea1-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="37ea1-122">En la pestaña **Pronóstico de flujo de efectivo**, seleccione **Habilitar característica**.</span><span class="sxs-lookup"><span data-stu-id="37ea1-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="37ea1-123">Seleccione **Crear modelo de predicción**.</span><span class="sxs-lookup"><span data-stu-id="37ea1-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="37ea1-124">Para obtener más información sobre cómo configurar la capacidad de previsión de flujo de efectivo, consulte [Previsiones de flujo de efectivo](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="37ea1-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="37ea1-125">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="37ea1-125">Privacy notice</span></span>

<span data-ttu-id="37ea1-126">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="37ea1-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
