---
title: Mejorar el modelo de predicción (versión preliminar)
description: Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646088"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="fdc1b-103">Mejorar el modelo de predicción (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fdc1b-104">Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="fdc1b-105">Empezará a mejorar tu modelo en el espacio de trabajo **Predicciones de pago de clientes**, en Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="fdc1b-106">Luego, los pasos de mejora se completan en AI Builder.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="fdc1b-107">Seleccionar resultados históricos</span><span class="sxs-lookup"><span data-stu-id="fdc1b-107">Select historical outcomes</span></span>

<span data-ttu-id="fdc1b-108">Primero seleccione uno o más de los tres posibles resultados para las facturas: **Puntual**, **Tarde** y **Muy tarde**.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="fdc1b-109">Deben seleccionarse los tres resultados.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-109">All three outcomes should be selected.</span></span> <span data-ttu-id="fdc1b-110">Si borra la selección de cualquiera de los resultados, las facturas se filtrarán fuera del proceso de capacitación y se reducirá la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="fdc1b-111">[![Confirmar resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="fdc1b-112">Si su organización requiere solo dos resultados, cambie los umbrales **Tarde** y **Muy tarde** a 0 (cero) días.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="fdc1b-113">De esta manera, colapsa efectivamente la predicción a un estado binario de **Puntual** o **Tarde**.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="fdc1b-114">Seleccionar campos</span><span class="sxs-lookup"><span data-stu-id="fdc1b-114">Select fields</span></span>

<span data-ttu-id="fdc1b-115">Cuando seleccione campos para incluir en el modelo, tenga en cuenta que la lista incluye todos los campos disponibles en la entidad Common Data Service que se asigna a los datos en el lago de datos de Azure.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Common Data Service entity that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="fdc1b-116">Algunos de estos campos **no** deberían seleccionarse.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="fdc1b-117">Los campos que no deben seleccionarse pertenecen a una de estas tres categorías:</span><span class="sxs-lookup"><span data-stu-id="fdc1b-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="fdc1b-118">El campo es obligatorio para la entidad Common Data Service, pero no hay datos de respaldo para ella en el lago de datos.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-118">The field is required for the Common Data Service entity, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="fdc1b-119">El campo es un id. y, por lo tanto, no tiene sentido para una función de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="fdc1b-120">El campo representa información que no estará disponible durante la predicción.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="fdc1b-121">Las siguientes secciones muestran los campos que están disponibles para la factura y las entidades del cliente, y enumeran los campos que **no** deben seleccionarse para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="fdc1b-122">La categoría que se especifica para cada uno de esos campos se refiere a las categorías de la lista anterior.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-common-data-model-entity"></a><span data-ttu-id="fdc1b-123">Entidad de factura de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fdc1b-123">Invoice Common Data Model entity</span></span>

<span data-ttu-id="fdc1b-124">La siguiente ilustración muestra los campos que están disponibles para la entidad de factura.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-124">The following illustration shows the fields that are available for the invoice entity.</span></span>

<span data-ttu-id="fdc1b-125">[![Campos disponibles para la entidad de factura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-125">[![Available fields for the invoice entity](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="fdc1b-126">Los siguientes campos no deben seleccionarse para el entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="fdc1b-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="fdc1b-127">**Cuenta de factura** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="fdc1b-128">**Está cerrado** (categoría 3): este campo se utiliza para filtrar facturas para entrenamiento (cerrado) y predicción (no cerrado).</span><span class="sxs-lookup"><span data-stu-id="fdc1b-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="fdc1b-129">**Nombre** (categoría 1)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-129">**Name** (category 1)</span></span>
- <span data-ttu-id="fdc1b-130">**Id. de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="fdc1b-131">**Registro de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="fdc1b-132">**Tabla de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-132">**Source table** (category 2)</span></span>

### <a name="customer-common-data-model-entity"></a><span data-ttu-id="fdc1b-133">Entidad de cliente de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fdc1b-133">Customer Common Data Model entity</span></span>

<span data-ttu-id="fdc1b-134">La siguiente ilustración muestra los campos que están disponibles para la entidad de cliente.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-134">The following illustration shows the fields that are available for the customer entity.</span></span>

<span data-ttu-id="fdc1b-135">[![Campos disponibles para la entidad de cliente](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-135">[![Available fields for the customer entity](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="fdc1b-136">El campo siguiente no debe seleccionarse para el entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="fdc1b-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="fdc1b-137">**Clave única de fila** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="fdc1b-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="fdc1b-138">Filters</span></span>

<span data-ttu-id="fdc1b-139">Actualmente, los filtros no son compatibles con el escenario del predictor de pagos de clientes.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="fdc1b-140">Por lo tanto, seleccione **Omitir este paso** y continúe con la página de resumen.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="fdc1b-141">[![Modelo de enfoque con filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="fdc1b-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="fdc1b-142">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="fdc1b-142">Privacy notice</span></span>
<span data-ttu-id="fdc1b-143">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="fdc1b-143">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
