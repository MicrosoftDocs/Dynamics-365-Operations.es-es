---
title: Confirmar envíos salientes de trabajos por lotes
description: Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 48257967ce360b1d4969124411d5976b807bf9e4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996310"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="fde09-103">Confirmar envíos salientes de trabajos por lotes</span><span class="sxs-lookup"><span data-stu-id="fde09-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fde09-104">Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar.</span><span class="sxs-lookup"><span data-stu-id="fde09-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="fde09-105">El trabajo por lotes descrito aquí solo se aplica a los envíos de pedidos de transferencia, no a los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="fde09-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="fde09-106">Habilitar la característica Confirmar envíos salientes desde trabajos por lotes</span><span class="sxs-lookup"><span data-stu-id="fde09-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="fde09-107">Antes de poder usar esta característica, debe estar habilitada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="fde09-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="fde09-108">Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fde09-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="fde09-109">La característica aparece como:</span><span class="sxs-lookup"><span data-stu-id="fde09-109">The feature is listed as:</span></span>

- <span data-ttu-id="fde09-110">**Módulo**: *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="fde09-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="fde09-111">**Nombre de la característica**: *Confirmar envíos salientes desde trabajos por lotes*</span><span class="sxs-lookup"><span data-stu-id="fde09-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="fde09-112">Procesar envíos salientes</span><span class="sxs-lookup"><span data-stu-id="fde09-112">Process outbound shipments</span></span>

<span data-ttu-id="fde09-113">Para configurar un trabajo por lotes programado para ejecutar la confirmación de envío saliente para las cargas que están listas para enviar:</span><span class="sxs-lookup"><span data-stu-id="fde09-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="fde09-114">Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar envíos salientes**.</span><span class="sxs-lookup"><span data-stu-id="fde09-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="fde09-115">El cuadro de diálogo **Confirmar envío** se abre.</span><span class="sxs-lookup"><span data-stu-id="fde09-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="fde09-116">En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="fde09-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="fde09-117">El cuadro de diálogo del editor de consultas se abre.</span><span class="sxs-lookup"><span data-stu-id="fde09-117">The query editor dialog box opens.</span></span> <span data-ttu-id="fde09-118">En la pestaña **Intervalo**, agregue una fila con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fde09-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="fde09-119">**Tabla**: *Cargas*</span><span class="sxs-lookup"><span data-stu-id="fde09-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="fde09-120">**Tabla derivada**: *Cargas*</span><span class="sxs-lookup"><span data-stu-id="fde09-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="fde09-121">**Campo**: *Estado de carga*</span><span class="sxs-lookup"><span data-stu-id="fde09-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="fde09-122">**Criterios**: *Cargado*</span><span class="sxs-lookup"><span data-stu-id="fde09-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="fde09-123">Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.</span><span class="sxs-lookup"><span data-stu-id="fde09-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="fde09-124">En la ficha desplegable **Ejecutar en segundo plano**, establezca **Procesamiento por lotes** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fde09-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="fde09-125">En la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="fde09-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="fde09-126">Se abre el cuadro de diálogo **Definir recurrencia**.</span><span class="sxs-lookup"><span data-stu-id="fde09-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="fde09-127">Establezca el programa de ejecución según sea necesario para su empresa.</span><span class="sxs-lookup"><span data-stu-id="fde09-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="fde09-128">Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.</span><span class="sxs-lookup"><span data-stu-id="fde09-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="fde09-129">Seleccione **Aceptar** en el cuadro de diálogo **Confirmar envío** para agregar el trabajo por lotes a la cola de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="fde09-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="fde09-130">Para obtener más información, vea [Descripción general del procesamiento por lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fde09-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>
