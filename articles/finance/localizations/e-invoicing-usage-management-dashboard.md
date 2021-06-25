---
title: Panel de administración de uso
description: Este tema explica cómo usar el panel de administración de uso para monitorear el uso del servicio de Facturación Electrónica y seguir cumpliendo con las regulaciones.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130515"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="b10d9-103">Panel de administración de uso</span><span class="sxs-lookup"><span data-stu-id="b10d9-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b10d9-104">El panel de **Gestión de uso** le ayuda a monitorear el uso del servicio de Facturación Electrónica y, por lo tanto, ayuda a su organización a seguir cumpliendo con las regulaciones según su uso mensual.</span><span class="sxs-lookup"><span data-stu-id="b10d9-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="b10d9-105">El cumplimiento se determina calculando el volumen de envío y comparándolo con el volumen adquirido de envíos para identificar cualquier incoherencia entre el volumen adquirido y el volumen usado.</span><span class="sxs-lookup"><span data-stu-id="b10d9-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="b10d9-106">El panel incluye los siguientes indicadores:</span><span class="sxs-lookup"><span data-stu-id="b10d9-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="b10d9-107">Un indicador de costes que puede usar para monitorear el consumo con fines de cumplimiento de licencias:</span><span class="sxs-lookup"><span data-stu-id="b10d9-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="b10d9-108">Utilización mensual (exportación)</span><span class="sxs-lookup"><span data-stu-id="b10d9-108">Usage per month (export)</span></span>

- <span data-ttu-id="b10d9-109">Tres indicadores operativos que puede utilizar para realizar un seguimiento del uso del servicio de Facturación electrónica con fines de gestión:</span><span class="sxs-lookup"><span data-stu-id="b10d9-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="b10d9-110">Uso por característica</span><span class="sxs-lookup"><span data-stu-id="b10d9-110">Usage by feature</span></span>
    - <span data-ttu-id="b10d9-111">Uso por entorno</span><span class="sxs-lookup"><span data-stu-id="b10d9-111">Usage by environment</span></span>
    - <span data-ttu-id="b10d9-112">Utilización mensual (importación)</span><span class="sxs-lookup"><span data-stu-id="b10d9-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="b10d9-113">Ámbito de medidas</span><span class="sxs-lookup"><span data-stu-id="b10d9-113">Measurement scope</span></span>

- <span data-ttu-id="b10d9-114">Unidad de medida:</span><span class="sxs-lookup"><span data-stu-id="b10d9-114">Unit of measure:</span></span> 

    <span data-ttu-id="b10d9-115">El panel de **Gestión de uso** cuenta la presentación de documentos comerciales y facturas electrónicas importadas.</span><span class="sxs-lookup"><span data-stu-id="b10d9-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="b10d9-116">Organización:</span><span class="sxs-lookup"><span data-stu-id="b10d9-116">Organization:</span></span> 

    <span data-ttu-id="b10d9-117">El recuento se resume por el id. del inquilino de su organización, independientemente del número de instancias de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management, o el número de entidades jurídicas donde está habilitado el servicio de Facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="b10d9-118">Indicador: Uso por mes (exportación)</span><span class="sxs-lookup"><span data-stu-id="b10d9-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="b10d9-119">Este indicador proporciona detalles sobre las facturas electrónicas que su organización emite durante un período definido.</span><span class="sxs-lookup"><span data-stu-id="b10d9-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="b10d9-120">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b10d9-120">Scope</span></span>
- <span data-ttu-id="b10d9-121">La cantidad de documentos comerciales que se envían desde Finance and Supply Chain Management al servicio de Facturación electrónica, independientemente del número de líneas que contengan esos documentos comerciales.</span><span class="sxs-lookup"><span data-stu-id="b10d9-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="b10d9-122">La cantidad de documentos comerciales enviados que el servicio de Facturación electrónica procesa con éxito.</span><span class="sxs-lookup"><span data-stu-id="b10d9-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="b10d9-123">Un documento se considera procesado correctamente cuando se completa el flujo de acciones que se definen en la configuración de funciones.</span><span class="sxs-lookup"><span data-stu-id="b10d9-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="b10d9-124">Cuando se envía una factura electrónica a un servicio web externo, el recuento es independiente de los resultados del procesamiento del servicio web (aceptado, rechazado o error de validación del esquema).</span><span class="sxs-lookup"><span data-stu-id="b10d9-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="b10d9-125">Si el servicio web recibió y respondió a la solicitud del servicio de Facturación Electrónica, el envío se considera un recuento válido.</span><span class="sxs-lookup"><span data-stu-id="b10d9-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="b10d9-126">**Excepción:** Los documentos comerciales no se cuentan si se vuelven a enviar desde Finance and Supply Chain Management al servicio de Facturación electrónica, como en los escenarios en los que se requiere un nuevo envío del mismo documento comercial para cambiar el estado de la factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="b10d9-127">Por ejemplo, la emisión de una factura electrónica brasileña (documento fiscal) se cuenta como válida, pero la solicitud de cancelación no se cuenta.</span><span class="sxs-lookup"><span data-stu-id="b10d9-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="b10d9-128">Cálculo</span><span class="sxs-lookup"><span data-stu-id="b10d9-128">Calculation</span></span>

<span data-ttu-id="b10d9-129">El cálculo del saldo se calcula de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b10d9-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="b10d9-130">Saldo = Gratis + Comprado - Usado</span><span class="sxs-lookup"><span data-stu-id="b10d9-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="b10d9-131">Donde:</span><span class="sxs-lookup"><span data-stu-id="b10d9-131">Where:</span></span>

- <span data-ttu-id="b10d9-132">Gratis:</span><span class="sxs-lookup"><span data-stu-id="b10d9-132">Free:</span></span>
  
    <span data-ttu-id="b10d9-133">Un volumen gratuito de documentos comerciales que el cliente puede enviar por mes.</span><span class="sxs-lookup"><span data-stu-id="b10d9-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="b10d9-134">Incluye un paquete de 100 documentos comerciales que se pueden enviar al servicio de Facturación Electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="b10d9-135">El volumen libre no es acumulativo y el saldo restante no se transfiere al siguiente período.</span><span class="sxs-lookup"><span data-stu-id="b10d9-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="b10d9-136">Comprado:</span><span class="sxs-lookup"><span data-stu-id="b10d9-136">Purchased:</span></span>
  
    <span data-ttu-id="b10d9-137">Un paquete de 1000 documentos comerciales que se pueden enviar al servicio de Facturación Electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="b10d9-138">Este paquete debe adquirirse para su organización mensualmente.</span><span class="sxs-lookup"><span data-stu-id="b10d9-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="b10d9-139">El volumen comprado no es acumulativo y el saldo restante no se transfiere al siguiente período.</span><span class="sxs-lookup"><span data-stu-id="b10d9-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="b10d9-140">Utilizado:</span><span class="sxs-lookup"><span data-stu-id="b10d9-140">Used:</span></span> 

    <span data-ttu-id="b10d9-141">El recuento de envíos de documentos comerciales al servicio de Facturación Electrónica según criterios definidos.</span><span class="sxs-lookup"><span data-stu-id="b10d9-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="b10d9-142">Si su organización planea exceder el volumen mensual de 100 envíos gratuitos, compre el volumen máximo para asegurarse de cumplir con la política de licencias de Microsoft para el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="b10d9-143">Actualmente, el volumen comprado debe ingresarse manualmente, de acuerdo con la fecha de adquisición, como paquetes múltiples de 1000 envíos.</span><span class="sxs-lookup"><span data-stu-id="b10d9-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="b10d9-144">Indicador: uso por función</span><span class="sxs-lookup"><span data-stu-id="b10d9-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="b10d9-145">Este indicador muestra el uso de funciones de facturación electrónica para la emisión de facturas electrónicas durante un período definido.</span><span class="sxs-lookup"><span data-stu-id="b10d9-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="b10d9-146">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="b10d9-146">Calculation:</span></span>
  
    <span data-ttu-id="b10d9-147">Usado = El recuento de cuántas veces se usó cada función de facturación electrónica durante el envío de documentos comerciales al servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="b10d9-148">Indicador: uso por entorno</span><span class="sxs-lookup"><span data-stu-id="b10d9-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="b10d9-149">Este indicador muestra el uso de entornos de servicio de facturación electrónica durante un período definido.</span><span class="sxs-lookup"><span data-stu-id="b10d9-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="b10d9-150">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="b10d9-150">Calculation:</span></span>
    
    <span data-ttu-id="b10d9-151">Usado = El recuento de cuántas veces se usó cada entorno de servicio de facturación electrónica durante el envío de documentos comerciales al servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="b10d9-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="b10d9-152">Indicador: Uso por mes (importación)</span><span class="sxs-lookup"><span data-stu-id="b10d9-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="b10d9-153">Este indicador muestra el volumen de importación de facturas electrónicas por el servicio de Facturación Electrónica a Finance and Supply Chain Management durante un período definido.</span><span class="sxs-lookup"><span data-stu-id="b10d9-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="b10d9-154">Ámbito:</span><span class="sxs-lookup"><span data-stu-id="b10d9-154">Scope:</span></span>

    <span data-ttu-id="b10d9-155">Facturas electrónicas que se importan a Finance and Supply Chain Management, independientemente del número de líneas que contengan esas facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="b10d9-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="b10d9-156">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="b10d9-156">Calculation:</span></span>

    <span data-ttu-id="b10d9-157">Recibido = El recuento de facturas electrónicas importadas en Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b10d9-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="b10d9-158">Funciones</span><span class="sxs-lookup"><span data-stu-id="b10d9-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="b10d9-159">Compra</span><span class="sxs-lookup"><span data-stu-id="b10d9-159">Purchase</span></span>

<span data-ttu-id="b10d9-160">En la pestaña **Uso por mes (exportación)**, seleccione **Compra** para registrar manualmente la cantidad de envíos adquiridos.</span><span class="sxs-lookup"><span data-stu-id="b10d9-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="b10d9-161">Para una fecha determinada, seleccione **Nuevo** e ingrese el número de **Paquetes** adquiridos en esa fecha.</span><span class="sxs-lookup"><span data-stu-id="b10d9-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="b10d9-162">La **Cantidad** se calcula del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b10d9-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="b10d9-163">Cantidad = Paquetes \* 1000</span><span class="sxs-lookup"><span data-stu-id="b10d9-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="b10d9-164">La **Cantidad** calculada se refleja en **Comprado** desde el indicador **Uso por mes (exportación)**.</span><span class="sxs-lookup"><span data-stu-id="b10d9-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="b10d9-165">Actualización</span><span class="sxs-lookup"><span data-stu-id="b10d9-165">Update</span></span>

<span data-ttu-id="b10d9-166">En el panel de acciones, seleccione **Actualizar** para actualizar el cálculo y actualizar los datos que se muestran en la página y en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="b10d9-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="b10d9-167">Restablecer datos de historial</span><span class="sxs-lookup"><span data-stu-id="b10d9-167">Reset history data</span></span>

<span data-ttu-id="b10d9-168">En el panel de acciones, seleccione **Restablecer los datos del historial** para actualizar la base de datos desde donde se calculan los indicadores.</span><span class="sxs-lookup"><span data-stu-id="b10d9-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="b10d9-169">El panel de **Gestión de uso** no muestra importes monetarios.</span><span class="sxs-lookup"><span data-stu-id="b10d9-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="b10d9-170">En cambio, muestra solo el volumen de envíos contados y documentos importados.</span><span class="sxs-lookup"><span data-stu-id="b10d9-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
