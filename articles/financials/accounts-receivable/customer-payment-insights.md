---
title: Customer payment insights (vista previa)
description: "Este tema describe cómo Customer payment insights puede ayudar a predecir cuándo se pagará una factura y ayuda a las organizaciones a crear estrategias de optimización que mejoren la probabilidad de que se les pague a tiempo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="customer-payment-insights-preview"></a><span data-ttu-id="bbcf5-103">Customer payment insights (vista previa)</span><span class="sxs-lookup"><span data-stu-id="bbcf5-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="bbcf5-104">Esta característica forma parte de una versión de destino y solo está disponible para los usuarios que han optado por participar en la vista previa privada.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="bbcf5-105">Esta característica se incluirá en una próxima versión de disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="bbcf5-106">Información general</span><span class="sxs-lookup"><span data-stu-id="bbcf5-106">Overview</span></span>

<span data-ttu-id="bbcf5-107">Las organizaciones a menudo encuentran difícil predecir cuándo un cliente pagará sus facturas.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="bbcf5-108">Esta falta de información puede llevar a previsiones de flujo de caja inexactos, procesos de cobro ineficientes y la posibilidad de que los pedidos se entreguen a clientes que pueden presentar un riesgo de crédito.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="bbcf5-109">Customer payment insights (vista previa) utiliza el aprendizaje automático para predecir cuándo se pagará una factura.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="bbcf5-110">También proporciona estrategias de optimización que se pueden adaptar para maximizar la probabilidad de que los clientes paguen a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="bbcf5-111">Predicciones</span><span class="sxs-lookup"><span data-stu-id="bbcf5-111">Predictions</span></span>

<span data-ttu-id="bbcf5-112">Las predicciones de pago permiten a las organizaciones mejorar sus procesos empresariales al ayudarles a:</span><span class="sxs-lookup"><span data-stu-id="bbcf5-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="bbcf5-113">Identificar fácilmente las facturas que se prevé que se pagarán con retraso.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="bbcf5-114">Tomar las medidas adecuadas para mejorar las posibilidades de recibir el pago a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="bbcf5-115">Customer payment insights (vista previa) utiliza el aprendizaje automático para predecir cuándo se pagará una factura.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="bbcf5-116">Utiliza datos históricos de facturas, pagos y clientes para crear un modelo de aprendizaje automático que se utiliza para predecir cuándo se pagará una factura.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="bbcf5-117">Para cada factura abierta, Customer payment insights (vista previa) predice tres probabilidades de pago:</span><span class="sxs-lookup"><span data-stu-id="bbcf5-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="bbcf5-118">Probabilidad de que el pago se realice a tiempo (dentro de la fecha de vencimiento de la factura).</span><span class="sxs-lookup"><span data-stu-id="bbcf5-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="bbcf5-119">Probabilidad de que el pago se realice dentro de los 30 días siguientes a la fecha de vencimiento de la factura,</span><span class="sxs-lookup"><span data-stu-id="bbcf5-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="bbcf5-120">Probabilidad de que el pago se realice después de los 30 días siguientes a la fecha de vencimiento de la factura,</span><span class="sxs-lookup"><span data-stu-id="bbcf5-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="bbcf5-121">La probabilidad de pagos se puede ver en la sección de predicciones.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="bbcf5-122">[![Predicciones de pago](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="bbcf5-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="bbcf5-123">A cada factura también se le asigna una probabilidad de pago ganadora utilizando uno de los tres escenarios de probabilidades de pago previstas definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="bbcf5-124">El escenario con mayor probabilidad de pago es el escenario ganador.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="bbcf5-125">Por ejemplo, supongamos que para una factura la predicción muestra un 71 por ciento de probabilidad de que la factura se pague a tiempo, un 13 por ciento de probabilidad de que la factura se pague dentro de los 30 días siguientes a la fecha de vencimiento y un 16 por ciento de probabilidad de que la factura se pague después de los 30 días siguientes a la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="bbcf5-126">La probabilidad más alta muestra que la factura estará en el escenario de pago a tiempo, por lo que la factura se etiquetará con la probabilidad de que se pague a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="bbcf5-127">[![Predicciones de pago](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="bbcf5-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="bbcf5-128">Estrategias de optimización</span><span class="sxs-lookup"><span data-stu-id="bbcf5-128">Optimization strategies</span></span>

<span data-ttu-id="bbcf5-129">Además de las predicciones de pago, Customer payment insights (vista previa) puede utilizar estrategias de optimización para mejorar las posibilidades de recibir el pago a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="bbcf5-130">Esto permite a las organizaciones realizar análisis del tipo "Y si...", por lo que los usuarios pueden ajustar los parámetros de la factura y del cliente y, después, comparar el efecto correspondiente en la probabilidad de recibir a tiempo el pago de las facturas.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="bbcf5-131">Por ejemplo, una organización puede desear evaluar el efecto de actualizar el descuento por pronto pago en las facturas sobre la probabilidad de recibir el pago a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="bbcf5-132">Cuando las facturas están optimizadas para utilizar el nuevo descuento, los usuarios pueden revisar el efecto de aplicar el descuento sobre la probabilidad de recibir los pagos de esas facturas a tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="bbcf5-133">Si el coste de aplicar el descuento es mínimo en comparación con el beneficio de cobrar el pago a tiempo, la organización puede optar por aplicar el descuento seleccionado a todos los pedidos pendientes futuros.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="bbcf5-134">Actualmente, solo el descuento está disponible como una estrategia de optimización para Customer payment insights (vista previa).</span><span class="sxs-lookup"><span data-stu-id="bbcf5-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="bbcf5-135">[![Predicciones optimizadas](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="bbcf5-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="bbcf5-136">Cómo obtener Customer payment insights (vista previa)</span><span class="sxs-lookup"><span data-stu-id="bbcf5-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="bbcf5-137">Si está interesado en probar Customer payment insights (vista previa), envíe un correo electrónico al [equipo de Finance Insights Preview](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bbcf5-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="bbcf5-138">Declaración de privacidad</span><span class="sxs-lookup"><span data-stu-id="bbcf5-138">Privacy Statement</span></span>

<span data-ttu-id="bbcf5-139">Las vistas previas almacenan los datos de los clientes en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="bbcf5-140">Además, las vistas previas (1) pueden utilizar menos medidas de privacidad y seguridad que el servicio Dynamics 365 for Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) tienen soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="bbcf5-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>

