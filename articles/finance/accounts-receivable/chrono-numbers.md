---
title: Numeración cronológica de documentos y vales
description: Este tema explica cómo configurar y utilizar números cronológicos para documentos aplicables y vales relacionados.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: fe533052b0e5b04a7d27b954ba644761c631d6d7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838870"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="aece6-103">Numeración cronológica de documentos y vales</span><span class="sxs-lookup"><span data-stu-id="aece6-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="aece6-104">En algunos países, existe el requisito legal de numerar los documentos y los vales relacionados en orden cronológico.</span><span class="sxs-lookup"><span data-stu-id="aece6-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="aece6-105">La cronología debe estar organizada por períodos.</span><span class="sxs-lookup"><span data-stu-id="aece6-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="aece6-106">Todos los números que pertenecen a períodos anteriores deben ser menores que los números que pertenecen a períodos posteriores.</span><span class="sxs-lookup"><span data-stu-id="aece6-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="aece6-107">Para cumplir con este requisito, se ha implementado la funcionalidad de numeración cronológica.</span><span class="sxs-lookup"><span data-stu-id="aece6-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="aece6-108">Este tema explica cómo configurar y utilizar números cronológicos para documentos aplicables y vales relacionados.</span><span class="sxs-lookup"><span data-stu-id="aece6-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aece6-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aece6-109">Prerequisites</span></span>

<span data-ttu-id="aece6-110">En el espacio de trabajo Administración de funciones, active la característica **Numeración cronológica**.</span><span class="sxs-lookup"><span data-stu-id="aece6-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="aece6-111">Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aece6-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="aece6-112">Configurar la numeración cronológica</span><span class="sxs-lookup"><span data-stu-id="aece6-112">Configure chronological numbering</span></span>

<span data-ttu-id="aece6-113">La numeración cronológica afecta a los siguientes documentos.</span><span class="sxs-lookup"><span data-stu-id="aece6-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="aece6-114">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="aece6-114">**Accounts receivable**</span></span>
- <span data-ttu-id="aece6-115">Factura de cliente</span><span class="sxs-lookup"><span data-stu-id="aece6-115">Customer invoice</span></span>
- <span data-ttu-id="aece6-116">Asiento de la factura de cliente</span><span class="sxs-lookup"><span data-stu-id="aece6-116">Customer invoice voucher</span></span>
- <span data-ttu-id="aece6-117">Nota de abono de ventas</span><span class="sxs-lookup"><span data-stu-id="aece6-117">Sales credit note</span></span>
- <span data-ttu-id="aece6-118">Asiento de la nota de abono de ventas</span><span class="sxs-lookup"><span data-stu-id="aece6-118">Sales credit note voucher</span></span>
- <span data-ttu-id="aece6-119">Factura de servicios</span><span class="sxs-lookup"><span data-stu-id="aece6-119">Free text invoice</span></span>
- <span data-ttu-id="aece6-120">Asiento de servicio</span><span class="sxs-lookup"><span data-stu-id="aece6-120">Free text invoice voucher</span></span>
- <span data-ttu-id="aece6-121">Nota de abono de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="aece6-121">Free text credit note</span></span>
- <span data-ttu-id="aece6-122">asiento de la nota de abono de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="aece6-122">Free text credit note voucher</span></span>
- <span data-ttu-id="aece6-123">Traslado</span><span class="sxs-lookup"><span data-stu-id="aece6-123">Packing slip</span></span>
- <span data-ttu-id="aece6-124">Nº Asiento del albarán</span><span class="sxs-lookup"><span data-stu-id="aece6-124">Packing slip voucher</span></span>
- <span data-ttu-id="aece6-125">Asiento de corrección del albarán</span><span class="sxs-lookup"><span data-stu-id="aece6-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="aece6-126">Asiento de la nota de interés</span><span class="sxs-lookup"><span data-stu-id="aece6-126">Interest note voucher</span></span>
- <span data-ttu-id="aece6-127">Asiento de la carta de cobro</span><span class="sxs-lookup"><span data-stu-id="aece6-127">Collection letter voucher</span></span>

<span data-ttu-id="aece6-128">**Proveedores**</span><span class="sxs-lookup"><span data-stu-id="aece6-128">**Accounts payable**</span></span>
- <span data-ttu-id="aece6-129">Nº Asiento de la factura</span><span class="sxs-lookup"><span data-stu-id="aece6-129">Invoice voucher</span></span>
- <span data-ttu-id="aece6-130">Nº Asiento de la nota de abono</span><span class="sxs-lookup"><span data-stu-id="aece6-130">Credit note voucher</span></span>
- <span data-ttu-id="aece6-131">Asiento de recepción de producto</span><span class="sxs-lookup"><span data-stu-id="aece6-131">Product receipt voucher</span></span>

<span data-ttu-id="aece6-132">**Administración de proyectos**</span><span class="sxs-lookup"><span data-stu-id="aece6-132">**Project management**</span></span>
- <span data-ttu-id="aece6-133">Factura</span><span class="sxs-lookup"><span data-stu-id="aece6-133">Invoice</span></span>
- <span data-ttu-id="aece6-134">Nº Asiento de la factura</span><span class="sxs-lookup"><span data-stu-id="aece6-134">Invoice voucher</span></span>
- <span data-ttu-id="aece6-135">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="aece6-135">Credit note</span></span>
- <span data-ttu-id="aece6-136">Nº Asiento de la nota de abono</span><span class="sxs-lookup"><span data-stu-id="aece6-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="aece6-137">Definir secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="aece6-137">Define number sequences</span></span>

<span data-ttu-id="aece6-138">Para definir secuencias numéricas, vaya a **Administración de la organización** > **Secuencias numéricas** > **Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="aece6-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="aece6-139">Puede definir tantas secuencias numéricas como sea necesario para cubrir los períodos afectados para los documentos requeridos.</span><span class="sxs-lookup"><span data-stu-id="aece6-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="aece6-140">Especifique una empresa para cada secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="aece6-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="aece6-141">Los segmentos de las secuencias numéricas deben definirse de modo que proporcionen un orden cronológico a los períodos.</span><span class="sxs-lookup"><span data-stu-id="aece6-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="aece6-142">Por ejemplo, los nombres de los segmentos pueden contener un prefijo especial que identifique un período específico.</span><span class="sxs-lookup"><span data-stu-id="aece6-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Configurar secuencia numérica](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="aece6-144">Configurar grupos de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="aece6-144">Configure number sequence groups</span></span>

<span data-ttu-id="aece6-145">Para configurar grupos de secuencias numéricas, vaya a **Clientes** > **Configuración** > **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="aece6-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="aece6-146">En la pestaña **Secuencias numéricas**, defina tantos grupos de secuencias numéricas como sea necesario para cubrir los períodos afectados.</span><span class="sxs-lookup"><span data-stu-id="aece6-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="aece6-147">Para cada grupo, en la sección **Referencia**, seleccione una de las referencias de documentos compatibles y, en el campo **Código de secuencia numérica**, haga referencia a una secuencia numérica que se creó previamente para el período relacionado.</span><span class="sxs-lookup"><span data-stu-id="aece6-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Configurar grupo de secuencias numéricas](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="aece6-149">De manera similar, configure grupos de secuencias numéricas en los módulos **Proveedores** y **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="aece6-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="aece6-150">Configurar la cronología de grupos de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="aece6-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="aece6-151">Para configurar la cronología de los grupos de secuencias numéricas, vaya a **Administración de la organización** > **Secuencias numéricas** > **Grupos de secuencias numéricas cronológicas**.</span><span class="sxs-lookup"><span data-stu-id="aece6-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="aece6-152">Defina las condiciones de aplicabilidad para grupos de secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="aece6-152">Define the applicability conditions for number sequence groups.</span></span>

![Configuración de números cronológicos](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="aece6-154">Campo</span><span class="sxs-lookup"><span data-stu-id="aece6-154">Field</span></span>            | <span data-ttu-id="aece6-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="aece6-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="aece6-156">Vigente</span><span class="sxs-lookup"><span data-stu-id="aece6-156">Effective</span></span>  | <span data-ttu-id="aece6-157">La fecha de inicio de la aplicabilidad del grupo de secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="aece6-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="aece6-158">Caducidad</span><span class="sxs-lookup"><span data-stu-id="aece6-158">Expiration</span></span>      | <span data-ttu-id="aece6-159">La fecha de finalización de la aplicabilidad del grupo de secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="aece6-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="aece6-160">Si no se aplica una fecha de finalización, seleccione **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="aece6-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="aece6-161">Grupo de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="aece6-161">Number sequence group</span></span> | <span data-ttu-id="aece6-162">Grupo de secuencias numéricas que se utilizará para generar números de documentos durante el período.</span><span class="sxs-lookup"><span data-stu-id="aece6-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="aece6-163">Grupo de secuencias numéricas original</span><span class="sxs-lookup"><span data-stu-id="aece6-163">Original number sequence group</span></span> | <span data-ttu-id="aece6-164">Este código de grupo de secuencias numéricas se utiliza para un filtrado adicional para los casos en los que los documentos ya tienen un grupo de secuencias numéricas *permanente* asignado.</span><span class="sxs-lookup"><span data-stu-id="aece6-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="aece6-165">Un valor vacío se considera un valor específico.</span><span class="sxs-lookup"><span data-stu-id="aece6-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="aece6-166">Si necesita ignorar un grupo asignado preliminarmente, use la opción **Predeterminado** para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="aece6-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="aece6-167">Predeterminada</span><span class="sxs-lookup"><span data-stu-id="aece6-167">Default</span></span> | <span data-ttu-id="aece6-168">Si está activado, el sistema ignora el grupo de secuencias numéricas de documentos asignado preliminarmente y usa solo las fechas de inicio y finalización de los períodos para el análisis de aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="aece6-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="aece6-169">Si se desactiva, el sistema usa la combinación completa **En vigor desde** + **Vencimiento** + **Grupo de secuencia numérica original** para la selección.</span><span class="sxs-lookup"><span data-stu-id="aece6-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="aece6-170">Contabilización de documentos</span><span class="sxs-lookup"><span data-stu-id="aece6-170">Document posting</span></span>
<span data-ttu-id="aece6-171">Al registrar un documento, el grupo de secuencias numéricas apropiado se asigna al documento, según la fecha de contabilidad del documento, y luego se usa para generar un número de documento basado en la secuencia numérica detectada.</span><span class="sxs-lookup"><span data-stu-id="aece6-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="aece6-172">El sistema proporciona un mensaje sobre la asignación del grupo de secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="aece6-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Número de documento](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="aece6-174">Para algunos países, ya existe una lógica específica implementada para la numeración de documentos.</span><span class="sxs-lookup"><span data-stu-id="aece6-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="aece6-175">En este caso, la lógica específica del país anulará la característica **Numeración cronológica**.</span><span class="sxs-lookup"><span data-stu-id="aece6-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
