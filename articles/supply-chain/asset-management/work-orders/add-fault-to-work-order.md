---
title: Agregar error a orden de trabajo
description: Este tema describe cómo agregar registros de error órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 489add5befe3660ad49e238b659bc8adbe1418a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263767"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="f4bcf-103">Agregar error a orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="f4bcf-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="f4bcf-104">Puede agregar los errores que se configuraron en el diseñador de errores para una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="f4bcf-105">Deben conectarse uno o más registros de error a los tipos de activos que se usan para el activo que está seleccionado en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="f4bcf-106">Para obtener más información sobre la configuración, consulte [Gestión de errores](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="f4bcf-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="f4bcf-107">Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f4bcf-108">Seleccione la orden de trabajo para realizar un registro de errores y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Activo**, seleccione **Error de activo**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="f4bcf-109">En la ficha desplegable **Síntomas**, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="f4bcf-110">Un número secuencial de error se introduce automáticamente en el campo **Error**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="f4bcf-111">En el campo **Síntoma del error**, seleccione el síntoma relevante.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="f4bcf-112">En los campos **Área del error** y **Tipo de error**, seleccione los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="f4bcf-113">El campo **Fecha del error**, se inserta automáticamente la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="f4bcf-114">Puede seleccionar una fecha diferente cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="f4bcf-115">En la ficha desplegable **Causas para el síntoma seleccionado**, agregue una línea para describir el motivo del problema.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="f4bcf-116">En la ficha desplegable **Remedios para el síntoma seleccionado**, agregue una línea para describir una posible solución para el problema.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="f4bcf-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-117">Select **Save**.</span></span>

<span data-ttu-id="f4bcf-118">En la ilustración siguiente se muestra un ejemplo de un registro de errores.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-118">The illustration below shows an example of a fault registration.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="f4bcf-120">Ver errores de activos</span><span class="sxs-lookup"><span data-stu-id="f4bcf-120">View asset faults</span></span>

<span data-ttu-id="f4bcf-121">En la lista **Errores de activo**, puede obtener una visión general de todos los errores registrados en los activos.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="f4bcf-122">En la página de lista **Errores de activo**, puede obtener una visión general de todos los errores que se han registrado en los activos.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="f4bcf-123">Para abrir la página, seleccione **Administración de activos** > **Consultas** > **Error de activo** > **Errores de activos**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="f4bcf-124">Imprimir informe de errores de activo</span><span class="sxs-lookup"><span data-stu-id="f4bcf-124">Print asset fault report</span></span>

<span data-ttu-id="f4bcf-125">En la página de la lista **Todos los activos**, puede imprimir un informe de errores de activos que muestra todos los registros de error y una visión general gráfica de las estadísticas del error.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="f4bcf-126">Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="f4bcf-127">Seleccione los activos para los que se imprimirá un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="f4bcf-128">En el panel de acciones, en la pestaña **General**, en el grupo **Informes**, seleccione **Error de activo**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="f4bcf-129">Introduzca un período específico o seleccione un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="f4bcf-130">Seleccione **Aceptar** para imprimir el informe.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="f4bcf-131">Para imprimir un informe de error para varios activos o tipos de activo, seleccione **Administración de activos** > **Informes** > **Activos** > **Error de activo**.</span><span class="sxs-lookup"><span data-stu-id="f4bcf-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]