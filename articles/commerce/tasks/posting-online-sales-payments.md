---
title: Registro de ventas y pagos en línea
description: Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbc85b957e716d07d9073d889c47f157ea0ead01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982301"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="41533-103">Registro de ventas y pagos en línea</span><span class="sxs-lookup"><span data-stu-id="41533-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41533-104">Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="41533-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="41533-105">El registro ventas y pagos en línea es un proceso de dos etapas.</span><span class="sxs-lookup"><span data-stu-id="41533-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="41533-106">Extraer los datos de transacción de Commerce en línea en la sede.</span><span class="sxs-lookup"><span data-stu-id="41533-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="41533-107">Sincronizar pedidos para crear pedidos de ventas en la sede.</span><span class="sxs-lookup"><span data-stu-id="41533-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="41533-108">La extracción de los datos de transacción en línea se puede hacer manualmente ejecutando el trabajo P o creando un trabajo por lotes periódico.</span><span class="sxs-lookup"><span data-stu-id="41533-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="41533-109">Ejecutar manualmente el trabajo P</span><span class="sxs-lookup"><span data-stu-id="41533-109">Manually running the P-job</span></span>

1. <span data-ttu-id="41533-110">Vaya a Todos los espacios de trabajo > TI de Retail y Commerce.</span><span class="sxs-lookup"><span data-stu-id="41533-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="41533-111">Haga clic en Programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="41533-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="41533-112">Seleccione P-0001.</span><span class="sxs-lookup"><span data-stu-id="41533-112">Select P-0001.</span></span>
4. <span data-ttu-id="41533-113">Ajuste los grupos de la base de datos del canal, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="41533-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="41533-114">Haga clic en Ejecutar ahora.</span><span class="sxs-lookup"><span data-stu-id="41533-114">Click Run now.</span></span>
6. <span data-ttu-id="41533-115">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="41533-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="41533-116">Programar un trabajo P periódico</span><span class="sxs-lookup"><span data-stu-id="41533-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="41533-117">Vaya a Todos los espacios de trabajo > TI de Retail y Commerce.</span><span class="sxs-lookup"><span data-stu-id="41533-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="41533-118">Haga clic en Programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="41533-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="41533-119">Seleccione P-0001.</span><span class="sxs-lookup"><span data-stu-id="41533-119">Select P-0001.</span></span>
4. <span data-ttu-id="41533-120">Haga clic en Crear trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="41533-120">Click Create batch job.</span></span>
5. <span data-ttu-id="41533-121">Haga clic en Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="41533-121">Click Run in the background.</span></span>
5. <span data-ttu-id="41533-122">Habilite Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="41533-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="41533-123">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="41533-123">Click Recurrence..</span></span>
7. <span data-ttu-id="41533-124">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="41533-124">Select the No end date option.</span></span>
8. <span data-ttu-id="41533-125">En el campo Recuento, introduzca el intervalo entre las ejecuciones en minutos.</span><span class="sxs-lookup"><span data-stu-id="41533-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="41533-126">Normalmente, este sería 5-10.</span><span class="sxs-lookup"><span data-stu-id="41533-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="41533-127">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-127">Click OK.</span></span>
10. <span data-ttu-id="41533-128">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-128">Click OK.</span></span>

<span data-ttu-id="41533-129">Los pedidos se pueden sincronizar manualmente ejecutando el trabajo "Sincronizan pedidos" o creando un trabajo por lotes periódico.</span><span class="sxs-lookup"><span data-stu-id="41533-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="41533-130">Ejecutar manualmente la sincronización de pedidos</span><span class="sxs-lookup"><span data-stu-id="41533-130">Manually running order synchronization</span></span> 

<span data-ttu-id="41533-131">Siga estos pasos para ejecutar manualmente el trabajo "sincronizar pedidos" una vez.</span><span class="sxs-lookup"><span data-stu-id="41533-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="41533-132">Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.</span><span class="sxs-lookup"><span data-stu-id="41533-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="41533-133">Haga clic en Sincronizar pedidos.</span><span class="sxs-lookup"><span data-stu-id="41533-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="41533-134">En el campo Jerarquía organizativa, seleccione "Tiendas por región".</span><span class="sxs-lookup"><span data-stu-id="41533-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="41533-135">Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="41533-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="41533-136">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="41533-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="41533-137">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="41533-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="41533-138">Deshabilite Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="41533-138">Disable Batch processing</span></span>
6. <span data-ttu-id="41533-139">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="41533-139">Click Recurrence.</span></span>
7. <span data-ttu-id="41533-140">Seleccione la opción Finalizar tras</span><span class="sxs-lookup"><span data-stu-id="41533-140">Select End After option</span></span>
8. <span data-ttu-id="41533-141">En el campo Finalizar tras, introduzca 1.</span><span class="sxs-lookup"><span data-stu-id="41533-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="41533-142">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-142">Click OK.</span></span>
10. <span data-ttu-id="41533-143">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="41533-144">Programar sincronización de pedidos periódica</span><span class="sxs-lookup"><span data-stu-id="41533-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="41533-145">Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="41533-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="41533-146">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="41533-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="41533-147">Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.</span><span class="sxs-lookup"><span data-stu-id="41533-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="41533-148">Haga clic en Sincronizar pedidos.</span><span class="sxs-lookup"><span data-stu-id="41533-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="41533-149">En el campo Jerarquía organizativa, seleccione "Tiendas por región".</span><span class="sxs-lookup"><span data-stu-id="41533-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="41533-150">Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="41533-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="41533-151">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="41533-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="41533-152">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="41533-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="41533-153">Habilite Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="41533-153">Enable Batch processing</span></span>
6. <span data-ttu-id="41533-154">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="41533-154">Click Recurrence.</span></span>
7. <span data-ttu-id="41533-155">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="41533-155">Select the No end date option.</span></span>
8. <span data-ttu-id="41533-156">En el campo Recuento, introduzca el intervalo entre las ejecuciones en minutos.</span><span class="sxs-lookup"><span data-stu-id="41533-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="41533-157">Normalmente, este sería 2-20</span><span class="sxs-lookup"><span data-stu-id="41533-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="41533-158">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-158">Click OK.</span></span>
10. <span data-ttu-id="41533-159">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="41533-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="41533-160">Entidades de datos implicadas en el proceso</span><span class="sxs-lookup"><span data-stu-id="41533-160">Data entities involved in the process</span></span>

- <span data-ttu-id="41533-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="41533-161">RetailTransactionTable</span></span>
- <span data-ttu-id="41533-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="41533-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="41533-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="41533-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="41533-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="41533-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="41533-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="41533-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="41533-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="41533-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="41533-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="41533-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="41533-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="41533-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="41533-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="41533-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="41533-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="41533-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="41533-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="41533-171">RetailTransactionAttributeTrans</span></span>
