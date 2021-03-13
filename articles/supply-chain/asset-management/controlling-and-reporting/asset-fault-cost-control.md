---
title: Control de costes de defecto de activo
description: Este tema explica el control de costes de los defectos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 597e30db346e882a7002709be52ad1c2d0576099
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019962"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="605cb-103">Control de costes de defecto de activo</span><span class="sxs-lookup"><span data-stu-id="605cb-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="605cb-104">En gestión de activos, puede calcular los costes en los registros de errores del activo para obtener una visión general de los costes reales comparados con los costes del presupuesto.</span><span class="sxs-lookup"><span data-stu-id="605cb-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="605cb-105">Los costes reales se basan en las transacciones registradas.</span><span class="sxs-lookup"><span data-stu-id="605cb-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="605cb-106">La fecha es la fecha del defecto en la que el síntoma se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="605cb-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="605cb-107">Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Control de costes de los defectos de activos** para abrir la lista.</span><span class="sxs-lookup"><span data-stu-id="605cb-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="605cb-108">En el diálogo **Control de costes de los defectos de activos** , seleccione un conjunto de dimensiones financieras que se incluirá en el cálculo, si procede.</span><span class="sxs-lookup"><span data-stu-id="605cb-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="605cb-109">Seleccione "Sí" en el botón de alternar **Omitir cero** si no desea mostrar los resultados con un coste de cero.</span><span class="sxs-lookup"><span data-stu-id="605cb-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="605cb-110">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de control de costes con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="605cb-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="605cb-111">Por ejemplo, si especifica el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas las líneas de control de costes de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="605cb-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="605cb-112">Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de control de costes de los defectos del activo en todos los niveles de la ubicación técnica con los que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="605cb-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="605cb-113">Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de defectos y causas de los defectos en la ficha desplegable **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="605cb-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="605cb-114">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="605cb-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="605cb-115">Haga clic en los botones **Agrupar por** para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="605cb-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="605cb-116">Se resaltarán los botones **Agrupar por** seleccionados.</span><span class="sxs-lookup"><span data-stu-id="605cb-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="605cb-117">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="605cb-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="605cb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="605cb-118">Example</span></span>

<span data-ttu-id="605cb-119">Este ejemplo muestra un cálculo de control de costes de los errores de activos.</span><span class="sxs-lookup"><span data-stu-id="605cb-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="605cb-120">El campo **Presupuesto original** muestra los costes del presupuesto según la previsión de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="605cb-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="605cb-121">El campo **Coste real** muestra los costes registrados en órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="605cb-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="605cb-122">El campo **Gasto comprometido** muestra el total de costes a los que se comprometió la empresa con respecto a las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="605cb-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Figura 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="605cb-124">Para obtener más información sobre cómo configurar errores, consulte el tema [Administración de errores](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="605cb-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
