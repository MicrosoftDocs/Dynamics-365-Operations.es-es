---
title: Agregar error a orden de trabajo
description: Este tema describe cómo agregar registros de error órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875887"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="cb46b-103">Agregar error a orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="cb46b-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="cb46b-104">Puede agregar los errores configurados en el diseñador de errores para una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb46b-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="cb46b-105">El activo seleccionado en la orden de trabajo debe contener tipos de activos con uno o más registros de error conectados con él.</span><span class="sxs-lookup"><span data-stu-id="cb46b-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="cb46b-106">Consulte más información sobre la configuración en la sección [Administración de errores](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="cb46b-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="cb46b-107">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="cb46b-108">En la lista, seleccione la orden de trabajo donde desea crear un registro de error y haga clic en **Defecto de activo**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="cb46b-109">En la ficha desplegable **Síntomas**, haga clic en **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="cb46b-110">Un número secuencial de error se inserta automáticamente en el campo **Error** .</span><span class="sxs-lookup"><span data-stu-id="cb46b-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="cb46b-111">Seleccione el síntoma relevante en el campo **Síntoma del error**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="cb46b-112">Seleccione **Área del error** y **Tipo de error**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="cb46b-113">El campo **Fecha del error**, se inserta automáticamente la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="cb46b-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="cb46b-114">Puede seleccionar otra fecha, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="cb46b-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="cb46b-115">En la ficha desplegable **Causas para el síntoma seleccionado** , agregue una línea que describa el motivo del problema.</span><span class="sxs-lookup"><span data-stu-id="cb46b-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="cb46b-116">En la ficha desplegable **Remedios para el síntoma seleccionado**, agregue una línea que describa una posible solución para el problema.</span><span class="sxs-lookup"><span data-stu-id="cb46b-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="cb46b-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-117">Click **Save**.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="cb46b-119">Ver errores de activos</span><span class="sxs-lookup"><span data-stu-id="cb46b-119">View asset faults</span></span>

<span data-ttu-id="cb46b-120">En la lista **Errores de activo**, puede obtener una visión general de todos los errores registrados en los activos.</span><span class="sxs-lookup"><span data-stu-id="cb46b-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="cb46b-121">Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Defectos de activos** para abrir la lista.</span><span class="sxs-lookup"><span data-stu-id="cb46b-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="cb46b-122">Imprimir informe de errores de activo</span><span class="sxs-lookup"><span data-stu-id="cb46b-122">Print asset fault report</span></span>

<span data-ttu-id="cb46b-123">En la página de la lista **Todos los activos**, puede imprimir un informe de defectos de activos que muestra todos los registros de error junto con una visión general gráfica de las estadísticas del error.</span><span class="sxs-lookup"><span data-stu-id="cb46b-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="cb46b-124">Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="cb46b-125">En la lista **Activos**, seleccione el activo para el que desea imprimir un informe de error.</span><span class="sxs-lookup"><span data-stu-id="cb46b-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="cb46b-126">En la pestaña **General** > **Sección Informes**, haga clic en **Defecto de activo**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="cb46b-127">Inserte un período específico o seleccionar un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="cb46b-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="cb46b-128">Haga clic en **Aceptar** para imprimir el informe.</span><span class="sxs-lookup"><span data-stu-id="cb46b-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="cb46b-129">También puede imprimir un informe de error para varios activos o tipos de activo haciendo clic en **Administración de activos** > **Informes** > **Activos** > **Defecto de activo**.</span><span class="sxs-lookup"><span data-stu-id="cb46b-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

