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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436618"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="f222c-103">Confirmar envíos salientes de trabajos por lotes</span><span class="sxs-lookup"><span data-stu-id="f222c-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f222c-104">Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar.</span><span class="sxs-lookup"><span data-stu-id="f222c-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="f222c-105">El trabajo por lotes descrito aquí solo se aplica a los envíos de pedidos de transferencia, no a los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="f222c-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="f222c-106">Habilitar la característica Confirmar envíos salientes desde trabajos por lotes</span><span class="sxs-lookup"><span data-stu-id="f222c-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="f222c-107">Antes de poder usar esta característica, debe estar habilitada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="f222c-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="f222c-108">Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f222c-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="f222c-109">La característica aparece como:</span><span class="sxs-lookup"><span data-stu-id="f222c-109">The feature is listed as:</span></span>

- <span data-ttu-id="f222c-110">**Módulo**: *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="f222c-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="f222c-111">**Nombre de la característica**: *Confirmar envíos salientes desde trabajos por lotes*</span><span class="sxs-lookup"><span data-stu-id="f222c-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="f222c-112">Procesar envíos salientes</span><span class="sxs-lookup"><span data-stu-id="f222c-112">Process outbound shipments</span></span>

<span data-ttu-id="f222c-113">Para configurar un trabajo por lotes programado para ejecutar la confirmación de envío saliente para las cargas que están listas para enviar:</span><span class="sxs-lookup"><span data-stu-id="f222c-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="f222c-114">Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar envíos salientes**.</span><span class="sxs-lookup"><span data-stu-id="f222c-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="f222c-115">El cuadro de diálogo **Confirmar envío** se abre.</span><span class="sxs-lookup"><span data-stu-id="f222c-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="f222c-116">En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f222c-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="f222c-117">El cuadro de diálogo del editor de consultas se abre.</span><span class="sxs-lookup"><span data-stu-id="f222c-117">The query editor dialog box opens.</span></span> <span data-ttu-id="f222c-118">En la pestaña **Intervalo**, agregue una fila con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f222c-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="f222c-119">**Tabla**: *Cargas*</span><span class="sxs-lookup"><span data-stu-id="f222c-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="f222c-120">**Tabla derivada**: *Cargas*</span><span class="sxs-lookup"><span data-stu-id="f222c-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="f222c-121">**Campo**: *Estado de carga*</span><span class="sxs-lookup"><span data-stu-id="f222c-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="f222c-122">**Criterios**: *Cargado*</span><span class="sxs-lookup"><span data-stu-id="f222c-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="f222c-123">Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.</span><span class="sxs-lookup"><span data-stu-id="f222c-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="f222c-124">En la ficha desplegable **Ejecutar en segundo plano**, establezca **Procesamiento por lotes** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f222c-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="f222c-125">En la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="f222c-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="f222c-126">Se abre el cuadro de diálogo **Definir recurrencia**.</span><span class="sxs-lookup"><span data-stu-id="f222c-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="f222c-127">Establezca el programa de ejecución según sea necesario para su empresa.</span><span class="sxs-lookup"><span data-stu-id="f222c-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="f222c-128">Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.</span><span class="sxs-lookup"><span data-stu-id="f222c-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="f222c-129">Seleccione **Aceptar** en el cuadro de diálogo **Confirmar envío** para agregar el trabajo por lotes a la cola de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="f222c-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="f222c-130">Para obtener más información, vea [Descripción general del procesamiento por lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f222c-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>
