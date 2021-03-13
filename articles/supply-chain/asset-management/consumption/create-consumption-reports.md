---
title: Crear informes de consumo
description: En este tema se explica cómo crear informes de consumo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e32924c71fd221caee4a7f413908120014ec8c5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022542"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="6ab69-103">Crear informes de consumo</span><span class="sxs-lookup"><span data-stu-id="6ab69-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6ab69-104">Cuando haya creado y publicado registros de consumo en órdenes de trabajo en Administración de activos, estarán dos informes disponibles para mostrar los detalles de consumo.</span><span class="sxs-lookup"><span data-stu-id="6ab69-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="6ab69-105">Informe de consumo de activos</span><span class="sxs-lookup"><span data-stu-id="6ab69-105">Asset consumption report</span></span>

<span data-ttu-id="6ab69-106">Cuando haya registrado el consumo en las órdenes de trabajo, podrá imprimir un informe de consumo de activos.</span><span class="sxs-lookup"><span data-stu-id="6ab69-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="6ab69-107">El informe muestra las horas, los costes por hora, los costes de artículo y los gastos registrados en los activos.</span><span class="sxs-lookup"><span data-stu-id="6ab69-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="6ab69-108">Haga clic en **Administración de activos** > **Informes** > **Activos** > **Consumo de activos**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="6ab69-109">En el cuadro de diálogo **Consumo de activos**, seleccione los parámetros y el nivel de detalle que desea ver seleccionando **Sí** en los botones de alternar relevantes e insertando un nivel de ubicación técnica en la sección **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="6ab69-110">Puede usar el campo **Niveles** para indicar el nivel de detalle que desea para las líneas de activos con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="6ab69-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="6ab69-111">Por ejemplo, si introduce el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todos los activos para una ubicación técnica se mostrarán en el nivel superior, y por tanto, se puede agregar una línea desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="6ab69-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="6ab69-112">Si introduce el número "0 "en el campo **Niveles** , verá un resultado detallado que muestra todos los activos en todos los niveles de la ubicación técnica con el que están relacionados.</span><span class="sxs-lookup"><span data-stu-id="6ab69-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="6ab69-113">Seleccione **Sí** en el botón de alternar **Sumar en todos los activos secundarios** para ver las sumas para cada activo secundario en el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="6ab69-114">Seleccione un intervalo de fechas en la sección **Fechas**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="6ab69-115">En la ficha desplegable **Destino**, seleccione si desea visualizar el informe en la pantalla, imprímalo o guárdelo como archivo o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ab69-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="6ab69-116">Si es necesario, puede seleccionar activos específicos que se mostrarán en el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="6ab69-117">En la ficha desplegable **Registros que incluir**, haga clic en **Filtrar** y agregue los activos que desea incluir en el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="6ab69-118">Haga clic en **Aceptar** para generar el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="6ab69-119">Informe de consumo de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="6ab69-119">Work order consumption report</span></span>

<span data-ttu-id="6ab69-120">Cuando haya registrado el consumo en las órdenes de trabajo, podrá imprimir un informe de consumo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ab69-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="6ab69-121">El informe muestra las horas, los costes por hora, los costes de artículo y los gastos registrados en las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ab69-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="6ab69-122">Haga clic en **Administración de activos** > **Informes** > **Órdenes de trabajo** > **Consumo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="6ab69-123">En el cuadro de diálogo **Consumo de órdenes de trabajo**, seleccione los parámetros que desea incluir en el informe seleccionando **Sí** en los botones de alternar relevantes en la sección **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="6ab69-124">Seleccione un intervalo de fechas en la sección **Fechas**.</span><span class="sxs-lookup"><span data-stu-id="6ab69-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="6ab69-125">En la ficha desplegable **Destino**, seleccione si desea visualizar el informe en la pantalla, imprímalo o guárdelo como archivo o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ab69-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="6ab69-126">Si es necesario, puede seleccionar órdenes de trabajo específicas que se mostrarán en el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="6ab69-127">En la ficha desplegable **Registros que incluir**, haga clic en **Filtrar** y agregue las órdenes de trabajo que desea incluir en el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="6ab69-128">Haga clic en **Aceptar** para generar el informe.</span><span class="sxs-lookup"><span data-stu-id="6ab69-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="6ab69-129">También puede generar un [informe de órdenes de trabajo](../work-orders/work-order-report.md), que contiene más detalles sobre la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ab69-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

