---
title: Previsión de flujo de efectivo (versión preliminar)
description: Este tema describe la capacidad de pronóstico de flujos de efectivo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
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
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3e9237980144ea65e1ff5135e277151970dbfdbb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208614"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="be430-103">Previsión de flujo de efectivo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="be430-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="be430-104">El flujo de efectivo es crítico para cualquier negocio.</span><span class="sxs-lookup"><span data-stu-id="be430-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="be430-105">Incluso las empresas rentables pueden enfrentarse a la insolvencia si no mantienen el flujo de efectivo para satisfacer las necesidades inmediatas.</span><span class="sxs-lookup"><span data-stu-id="be430-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="be430-106">La capacidad de previsión de flujo de efectivo en las informaciones de Finance puede ayudar a las empresas a monitorear y administrar sus saldos de efectivo de manera efectiva.</span><span class="sxs-lookup"><span data-stu-id="be430-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="be430-107">Esta característica utiliza el aprendizaje automático para ayudar a las empresas a pronosticar los flujos de efectivo con mayor precisión que antes.</span><span class="sxs-lookup"><span data-stu-id="be430-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="be430-108">También puede ayudar a los gerentes a tomar decisiones que optimicen las oportunidades en el contexto de su posición de efectivo actual.</span><span class="sxs-lookup"><span data-stu-id="be430-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="be430-109">Para la mayoría de las empresas, administrar el flujo de efectivo y ejecutar la previsión del flujo de efectivo es un proceso tedioso, repetitivo y manual.</span><span class="sxs-lookup"><span data-stu-id="be430-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="be430-110">La mayoría de las empresas confían en soluciones de Microsoft Excel que tienen diversos grados de complejidad.</span><span class="sxs-lookup"><span data-stu-id="be430-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="be430-111">Los desafíos de pronosticar con precisión el flujo de efectivo incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="be430-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="be430-112">Los datos no están disponibles para los tomadores de decisiones porque están dispersos en varios lugares, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="be430-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="be430-113">El sistema de planificación contable o de recursos empresariales</span><span class="sxs-lookup"><span data-stu-id="be430-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="be430-114">El software de planificación financiera</span><span class="sxs-lookup"><span data-stu-id="be430-114">Financial planning software</span></span>
  - <span data-ttu-id="be430-115">Excel</span><span class="sxs-lookup"><span data-stu-id="be430-115">Excel</span></span>
  - <span data-ttu-id="be430-116">Aplicaciones de software adicionales</span><span class="sxs-lookup"><span data-stu-id="be430-116">Additional software applications</span></span> 
- <span data-ttu-id="be430-117">La previsión se basa en el conocimiento interno que reside en "silos" dentro de cada dominio o departamento.</span><span class="sxs-lookup"><span data-stu-id="be430-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="be430-118">Medir la precisión de la previsión del flujo de efectivo una vez que se han materializado las finanzas es incierto y difícil.</span><span class="sxs-lookup"><span data-stu-id="be430-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="be430-119">Detalles de la capacidad de pronóstico de flujo de efectivo</span><span class="sxs-lookup"><span data-stu-id="be430-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="be430-120">La función de pronóstico de flujo de efectivo incluye la siguiente funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="be430-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="be430-121">Facilita la integración de datos de flujo de efectivo de sistemas externos en Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="be430-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="be430-122">Los pronósticos de flujo de efectivo también pueden utilizar el marco de importación y exportación de datos.</span><span class="sxs-lookup"><span data-stu-id="be430-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="be430-123">Este marco facilita la integración con Excel OData.</span><span class="sxs-lookup"><span data-stu-id="be430-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="be430-124">También puede combinar datos de varias fuentes para crear una solución integral de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="be430-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="be430-125">Introduce una posición de efectivo inteligente.</span><span class="sxs-lookup"><span data-stu-id="be430-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="be430-126">La posición de efectivo se crea en función del comportamiento de pago del cliente para predecir cuándo una empresa puede esperar que llegue efectivo a sus cuentas.</span><span class="sxs-lookup"><span data-stu-id="be430-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="be430-127">También analiza los patrones históricos de pago a los proveedores para predecir cuándo es probable que se paguen las facturas y los pedidos futuros.</span><span class="sxs-lookup"><span data-stu-id="be430-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="be430-128">Introduce el pronóstico de flujo de efectivo inteligente para pronósticos a largo plazo, utilizando un pronóstico de serie temporal a través de la integración automatizada con AI Builder.</span><span class="sxs-lookup"><span data-stu-id="be430-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="be430-129">Brinda la capacidad de guardar posiciones específicas de flujo de efectivo o pronósticos, editarlos y luego comparar y medir fácilmente el rendimiento del pronóstico con las finanzas reales.</span><span class="sxs-lookup"><span data-stu-id="be430-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="be430-130">Permite el análisis hipotético mediante la comparación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="be430-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="be430-131">Por ejemplo, puede crear varias instantáneas que representen puntos de vista optimistas, pesimistas y más realistas de su flujo de efectivo y luego comparar y ver las diferencias.</span><span class="sxs-lookup"><span data-stu-id="be430-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="be430-132">Brinda la capacidad de ver el pronóstico de flujo de efectivo en múltiples divisas, en las entidades jurídicas, y filtrar y ver el flujo de efectivo relacionado con una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="be430-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="be430-133">Le permite filtrar y ver las cuentas bancarias relacionadas con las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="be430-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="be430-134">La funcionalidad de pronóstico de flujo de efectivo de Dynamics 365 Finance permitirá a su organización transformar la proyección de flujo de efectivo tediosa y compleja, aunque repetitiva, en un proceso simple y automatizado.</span><span class="sxs-lookup"><span data-stu-id="be430-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="be430-135">Automatizar los aspectos más tediosos de la previsión del flujo de efectivo le permite concentrarse en la toma de decisiones críticas para impulsar los resultados comerciales deseados.</span><span class="sxs-lookup"><span data-stu-id="be430-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="be430-136">Configurar dimensiones para la previsión del flujo de efectivo</span><span class="sxs-lookup"><span data-stu-id="be430-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="be430-137">Una nueva pestaña de la página **Configuración de pronósticos de flujo de efectivo** le permite controlar qué dimensiones financieras utilizar para filtrar en el espacio de trabajo **Previsión de flujo de efectivo**.</span><span class="sxs-lookup"><span data-stu-id="be430-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="be430-138">Esta pestaña solo aparecerá cuando la función de pronósticos de flujo de efectivo esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="be430-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="be430-139">En la pestaña **Dimensiones**, elija de la lista de dimensiones que se utilizarán para el filtrado y utilice las teclas de flecha para moverlas a la columna de la derecha.</span><span class="sxs-lookup"><span data-stu-id="be430-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="be430-140">Solo se pueden seleccionar dos dimensiones para filtrar los datos de pronósticos de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="be430-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

#### <a name="privacy-notice"></a><span data-ttu-id="be430-141">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="be430-141">Privacy notice</span></span>
<span data-ttu-id="be430-142">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="be430-142">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]