---
title: Información de pago del cliente (vista previa)
description: Este tema describe la capacidad de la función de la información de pago que ayuda a mejorar la comprensión de las prácticas más comunes de pago de clientes individuales y puede identificar las circunstancias que justifican el inicio de los procesos de cobro de cobro antes de lo que lo habría hecho de otro modo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774042"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="0ca4c-103">Información de pago del cliente (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0ca4c-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0ca4c-104">Este tema describe la capacidad de la función de la información de pago que ayuda a mejorar la comprensión de las prácticas más comunes de pago de clientes individuales y puede identificar las circunstancias que justifican el inicio de los procesos de cobro de cobro antes de lo que lo habría hecho de otro modo.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="0ca4c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="0ca4c-105">Overview</span></span>

<span data-ttu-id="0ca4c-106">Las organizaciones a menudo encuentran difícil predecir cuándo los clientes pagarán sus facturas.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="0ca4c-107">Esta falta de información conduce a previsiones de flujo de efectivo menos precisas, procesos de cobro que empiezan demasiado tarde y pedidos que se entregan a clientes que podrían no realizar el pago.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="0ca4c-108">La Información de pago del cliente (versión preliminar) ayuda a las organizaciones a predecir cuándo se pagará una factura de cliente y ayuda a las organizaciones a crear estrategias de cobro que mejoren la probabilidad de que se les pague a tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="0ca4c-109">Predicciones</span><span class="sxs-lookup"><span data-stu-id="0ca4c-109">Predictions</span></span>

<span data-ttu-id="0ca4c-110">Las predicciones de pago permitirán a las organizaciones mejorar sus procesos empresariales ayudándolas a identificar fácilmente las facturas que probablemente se pagarán tarde, y tomar las medidas adecuadas que mejoren las posibilidades de cobrar a tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="0ca4c-111">Con el uso de un modelo de aprendizaje automático, que aproveche facturas, pagos y los datos históricos del cliente, la información de los pagos de los clientes (versión preliminar) predice con más precisión cuándo un cliente pagará una factura pendiente.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="0ca4c-112">Para cada factura abierta, la Información de pago del cliente (versión preliminar) predice tres probabilidades de pago:</span><span class="sxs-lookup"><span data-stu-id="0ca4c-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="0ca4c-113">Probabilidad de pago efectuado a tiempo</span><span class="sxs-lookup"><span data-stu-id="0ca4c-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="0ca4c-114">Probabilidad de pago efectuado tarde</span><span class="sxs-lookup"><span data-stu-id="0ca4c-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="0ca4c-115">Probabilidad de pago efectuado muy tarde</span><span class="sxs-lookup"><span data-stu-id="0ca4c-115">Probability of payment being made very late</span></span>

<span data-ttu-id="0ca4c-116">Para ayudar a las organizaciones a comprender el importe total de pago que pueden esperar de un cliente en uno de las tres categoría, a tiempo, tarde y muy tarde, Información de pago del cliente (versión preliminar) también proporcionan una vista agregada de los pagos previstos.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="0ca4c-117">[![Vista agregada de las predicciones de pago](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="0ca4c-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="0ca4c-118">Además, cada factura se asigna a una probabilidad de pago a tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="0ca4c-119">Si la probabilidad de pago a tiempo es inferior al 50 %, las facturas se etiquetan con un círculo rojo para indicar que estas facturas puede requerir la asistencia de cobros.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="0ca4c-120">[![Lista de posibilidades de pago](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="0ca4c-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="0ca4c-121">Información de pago del cliente (versión preliminar) también proporcionan información contextual para explicar la predicción, como los factores de alto nivel que influenciaron las predicciones, el estado actual del negocio con el cliente, y los detalles sobre el comportamiento histórico de pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="0ca4c-122">En muchos negocios, el proceso de cobros se ha sido una actividad reactiva; el proceso de cobros no se inicia hasta que vencen las facturas debidas.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="0ca4c-123">Con Información de pago del cliente (versión preliminar), las organizaciones pueden ser más proactivas respecto a los cobros.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="0ca4c-124">No tienen que esperar más a que las transacciones venzan para iniciar el proceso de cobro.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="0ca4c-125">En su lugar, pueden usar la capacidad de predicción de pago para determinar si los cobros proactivos mejorarán la probabilidad de pagar a tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="0ca4c-126">La predicción de pago también proporciona a las empresas la información necesaria para justificar el inicio del proceso de cobros de forma anticipada.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="0ca4c-127">Metodología</span><span class="sxs-lookup"><span data-stu-id="0ca4c-127">Methodology</span></span>

<span data-ttu-id="0ca4c-128">Desarrollar e implementar una solución de inteligencia artificial es complicado.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="0ca4c-129">Hace falta un equipo de científicos de datos, expertos en la material e ingenieros, que trabajen durante mucho tiempo para formular, desarrollar, implementar y mantener una solución utilizable de inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="0ca4c-130">Estamos haciendo que sea fácil implementar y utilizar soluciones de inteligencia artificial en Finance.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="0ca4c-131">Estamos preempaquetando soluciones de inteligencia artificial en Finance que se incorporan en Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="0ca4c-132">Los usuarios finales, con un solo clic, puede implementar la solución de inteligencia artificial y comenzar aprovechar las prestaciones de las predicciones inteligentes.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="0ca4c-133">Si una organización no está satisfecha con la precisión de las predicciones, un usuario avanzado, otra vez con un único clic, puede especificar la experiencia de la extensión de AI Builder y seleccionar o anular la selección de los campos usados para generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="0ca4c-134">Una vez que están listos, pueden preparar y publicar los cambios y el modelo recién entrenado se seleccionará automáticamente para las predicciones en Finance.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="0ca4c-135">Cómo obtener Información de pago del cliente (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0ca4c-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="0ca4c-136">Si está interesado en probar Información de pago del cliente (versión preliminar), envíe un correo electrónico al [Información de pago del cliente (versión preliminar)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0ca4c-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="0ca4c-137">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="0ca4c-137">Privacy Notice</span></span>

<span data-ttu-id="0ca4c-138">Las versiones preliminares (1) pueden utilizar menos medidas de privacidad y seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) tienen soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="0ca4c-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


