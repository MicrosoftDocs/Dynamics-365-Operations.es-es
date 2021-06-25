---
title: Mejorar el modelo de predicción (versión preliminar)
description: Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186651"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="096be-103">Mejorar el modelo de predicción (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="096be-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="096be-104">Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.</span><span class="sxs-lookup"><span data-stu-id="096be-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="096be-105">Empezará a mejorar tu modelo en el espacio de trabajo **Predicciones de pago de clientes**, en Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="096be-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="096be-106">Luego, los pasos de mejora se completan en AI Builder.</span><span class="sxs-lookup"><span data-stu-id="096be-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="096be-107">Seleccionar resultados históricos</span><span class="sxs-lookup"><span data-stu-id="096be-107">Select historical outcomes</span></span>

<span data-ttu-id="096be-108">Primero seleccione uno o más de los tres posibles resultados para las facturas: **Puntual**, **Tarde** y **Muy tarde**.</span><span class="sxs-lookup"><span data-stu-id="096be-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="096be-109">Deben seleccionarse los tres resultados.</span><span class="sxs-lookup"><span data-stu-id="096be-109">All three outcomes should be selected.</span></span> <span data-ttu-id="096be-110">Si borra la selección de cualquiera de los resultados, las facturas se filtrarán fuera del proceso de capacitación y se reducirá la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="096be-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="096be-111">[![Confirmar resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="096be-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="096be-112">Si su organización requiere solo dos resultados, cambie los umbrales **Tarde** y **Muy tarde** a 0 (cero) días.</span><span class="sxs-lookup"><span data-stu-id="096be-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="096be-113">De esta manera, colapsa efectivamente la predicción a un estado binario de **Puntual** o **Tarde**.</span><span class="sxs-lookup"><span data-stu-id="096be-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="096be-114">Seleccionar campos</span><span class="sxs-lookup"><span data-stu-id="096be-114">Select fields</span></span>

<span data-ttu-id="096be-115">Cuando seleccione campos para incluirlos en el modelo, tenga en cuenta que la lista incluye todos los campos disponibles en la tabla Microsoft Dataverse que se asigna a los datos en el lago de datos de Azure.</span><span class="sxs-lookup"><span data-stu-id="096be-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="096be-116">Algunos de estos campos **no** deberían seleccionarse.</span><span class="sxs-lookup"><span data-stu-id="096be-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="096be-117">Los campos que no deben seleccionarse pertenecen a una de estas tres categorías:</span><span class="sxs-lookup"><span data-stu-id="096be-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="096be-118">El campo es obligatorio para la tabla Dataverse, pero no hay datos de respaldo para ella en el lago de datos.</span><span class="sxs-lookup"><span data-stu-id="096be-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="096be-119">El campo es un id. y, por lo tanto, no tiene sentido para una función de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="096be-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="096be-120">El campo representa información que no estará disponible durante la predicción.</span><span class="sxs-lookup"><span data-stu-id="096be-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="096be-121">Las siguientes secciones muestran los campos que están disponibles para la factura y las entidades del cliente, y enumeran los campos que **no** deben seleccionarse para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="096be-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="096be-122">La categoría que se especifica para cada uno de esos campos se refiere a las categorías de la lista anterior.</span><span class="sxs-lookup"><span data-stu-id="096be-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="096be-123">Tabla de Dataverse de factura</span><span class="sxs-lookup"><span data-stu-id="096be-123">Invoice Dataverse table</span></span>

<span data-ttu-id="096be-124">La siguiente ilustración muestra los campos que están disponibles para la tabla de factura.</span><span class="sxs-lookup"><span data-stu-id="096be-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="096be-125">[![Campos disponibles para la tabla de factura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="096be-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="096be-126">Los siguientes campos no deben seleccionarse para el entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="096be-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="096be-127">**Cuenta de factura** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="096be-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="096be-128">**Está cerrado** (categoría 3): este campo se utiliza para filtrar facturas para entrenamiento (cerrado) y predicción (no cerrado).</span><span class="sxs-lookup"><span data-stu-id="096be-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="096be-129">**Nombre** (categoría 1)</span><span class="sxs-lookup"><span data-stu-id="096be-129">**Name** (category 1)</span></span>
- <span data-ttu-id="096be-130">**Id. de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="096be-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="096be-131">**Registro de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="096be-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="096be-132">**Tabla de origen** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="096be-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="096be-133">Tabla de Dataverse de cliente</span><span class="sxs-lookup"><span data-stu-id="096be-133">Customer Dataverse table</span></span>

<span data-ttu-id="096be-134">La siguiente ilustración muestra los campos que están disponibles para la tabla de cliente.</span><span class="sxs-lookup"><span data-stu-id="096be-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="096be-135">[![Campos disponibles para la tabla de cliente](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="096be-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="096be-136">El campo siguiente no debe seleccionarse para el entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="096be-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="096be-137">**Clave única de fila** (categoría 2)</span><span class="sxs-lookup"><span data-stu-id="096be-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="096be-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="096be-138">Filters</span></span>

<span data-ttu-id="096be-139">Actualmente, los filtros no son compatibles con el escenario del predictor de pagos de clientes.</span><span class="sxs-lookup"><span data-stu-id="096be-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="096be-140">Por lo tanto, seleccione **Omitir este paso** y continúe con la página de resumen.</span><span class="sxs-lookup"><span data-stu-id="096be-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="096be-141">[![Modelo de enfoque con filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="096be-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
