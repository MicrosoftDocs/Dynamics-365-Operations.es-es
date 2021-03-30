---
title: Configurar y procesar facturas periódicas
description: Este artículo explica cómo configurar y procesar las facturas periódicas. Puede usar facturas periódicas si debe factura a los clientes por el mismo importe periódicamente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b1d36262c35210e183e92c10f69e8511280443b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228085"
---
# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="23ee6-104">Configurar y procesar facturas periódicas</span><span class="sxs-lookup"><span data-stu-id="23ee6-104">Set up and process recurring invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23ee6-105">Este artículo explica cómo configurar y procesar las facturas periódicas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="23ee6-106">Puede usar facturas periódicas si debe factura a los clientes por el mismo importe periódicamente.</span><span class="sxs-lookup"><span data-stu-id="23ee6-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="23ee6-107">Crear una plantilla de factura de servicios recurrente</span><span class="sxs-lookup"><span data-stu-id="23ee6-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="23ee6-108">Para facturar a los clientes por los mismos servicios periódicamente, debe definir una plantilla de factura de servicios que se puede volver a usar para crear las facturas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="23ee6-109">Esta plantilla contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="23ee6-109">This template contains the following information:</span></span>

-   <span data-ttu-id="23ee6-110">Información de encabezado, como grupos de impuestos, condiciones de pago y el método de pago</span><span class="sxs-lookup"><span data-stu-id="23ee6-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="23ee6-111">Información de línea, como la descripción del servicio, las cuentas de ingresos, el precio unitario y el importe de la factura</span><span class="sxs-lookup"><span data-stu-id="23ee6-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="23ee6-112">Gastos de envío o gestión</span><span class="sxs-lookup"><span data-stu-id="23ee6-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="23ee6-113">Distribuciones contables junto con la información de dimensión financiera, como centros de costes y unidades de negocio</span><span class="sxs-lookup"><span data-stu-id="23ee6-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="23ee6-114">De hecho, crea una factura completa y la guarda como plantilla.</span><span class="sxs-lookup"><span data-stu-id="23ee6-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="23ee6-115">Puede configurar las plantillas con la página **Facturas periódicas**.</span><span class="sxs-lookup"><span data-stu-id="23ee6-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="23ee6-116">Asignar una plantilla de factura de servicios a un cliente y especificar los detalles de periodicidad</span><span class="sxs-lookup"><span data-stu-id="23ee6-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="23ee6-117">Después de crear la plantilla, debe asignar la plantilla a los clientes que desea facturar.</span><span class="sxs-lookup"><span data-stu-id="23ee6-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="23ee6-118">Además, debe especificar cuándo y con qué frecuencia se usará la factura.</span><span class="sxs-lookup"><span data-stu-id="23ee6-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="23ee6-119">Puede asignar las plantillas en la pestaña **Factura** de la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="23ee6-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="23ee6-120">Agregue la plantilla a la lista y actualizar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="23ee6-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="23ee6-121">La fecha inicial y, opcionalmente, la fecha final de la facturación periódica</span><span class="sxs-lookup"><span data-stu-id="23ee6-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="23ee6-122">La frecuencia de facturación periódica (por ejemplo, cada día o una vez al mes)</span><span class="sxs-lookup"><span data-stu-id="23ee6-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="23ee6-123">El importe de facturación máximo (si se requiere esta información)</span><span class="sxs-lookup"><span data-stu-id="23ee6-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="23ee6-124">Un cliente puede tener varias plantillas con diferentes frecuencias.</span><span class="sxs-lookup"><span data-stu-id="23ee6-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="23ee6-125">Generar las facturas periódicas</span><span class="sxs-lookup"><span data-stu-id="23ee6-125">Generate the recurring invoices</span></span>
<span data-ttu-id="23ee6-126">En la página **Facturas periódicas**, hay una tarea que procesa las plantillas de facturas periódicas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="23ee6-127">Especifique la fecha de la factura y la plantilla desde la que desea generar las facturas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="23ee6-128">Las facturas se generarán y se le asignarán un número de id. de periodicidad único para cada grupo de facturas que se procese.</span><span class="sxs-lookup"><span data-stu-id="23ee6-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>

<a name="post-recurring-free-text-invoices"></a><span data-ttu-id="23ee6-129">Registrar facturas de servicios periódicas</span><span class="sxs-lookup"><span data-stu-id="23ee6-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="23ee6-130">Después de que se generen las facturas periódicas, los identificadores de periodicidad de factura aparecen en una tarea de registro en la página **Facturas periódicas**.</span><span class="sxs-lookup"><span data-stu-id="23ee6-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="23ee6-131">Para ver todas las facturas para un id. de periodicidad, haga clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="23ee6-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="23ee6-132">Durante su revisión de las facturas para el id. de periodicidad, puede eliminar facturas individuales.</span><span class="sxs-lookup"><span data-stu-id="23ee6-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="23ee6-133">La configuración de la periodicidad del cliente se restablecerá para esa plantilla, para que se pueda volver a generar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="23ee6-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="23ee6-134">Puede registrar una, muchas o todas las facturas para un id. de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="23ee6-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="23ee6-135">Si se habilitan los flujos de trabajo, debe hacer clic en **Enviar** para poder registrar las facturas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>

<a name="print-recurring-free-text-invoices"></a><span data-ttu-id="23ee6-136">Imprimir facturas de servicios periódicas</span><span class="sxs-lookup"><span data-stu-id="23ee6-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="23ee6-137">Después de registrar las facturas periódicas, puede imprimir las facturas desde la página de lista de facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="23ee6-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="23ee6-138">Puede imprimir las facturas seleccionadas o puede seleccionar un intervalo de facturas para imprimirlas.</span><span class="sxs-lookup"><span data-stu-id="23ee6-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]