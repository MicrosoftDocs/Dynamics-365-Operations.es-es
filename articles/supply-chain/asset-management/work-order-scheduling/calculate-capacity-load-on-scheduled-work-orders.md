---
title: Calcular la carga de capacidad en órdenes de trabajo programadas
description: En este tema se explica cómo calcular la carga de capacidad en órdenes de pedido programadas en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
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
ms.openlocfilehash: 5a6063db7a63975f439da9f20adec07de9103014
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264907"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="9febf-103">Calcular la carga de capacidad en órdenes de trabajo programadas</span><span class="sxs-lookup"><span data-stu-id="9febf-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9febf-104">Puede calcular la carga de capacidad en órdenes de trabajo programadas para obtener una visión general de la carga de trabajo en los recursos durante un período específico.</span><span class="sxs-lookup"><span data-stu-id="9febf-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="9febf-105">Los cálculos se pueden realizar para los siguientes recursos: trabajadores de mantenimiento, grupos de trabajadores, herramientas y activos.</span><span class="sxs-lookup"><span data-stu-id="9febf-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="9febf-106">Haga clic en **Administración de activos** > **Consultas** > **Programación** > **Carga de capacidad**.</span><span class="sxs-lookup"><span data-stu-id="9febf-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="9febf-107">En el cuadro de diálogo **Calcular carga de capacidad** > campo **Mostrar**, seleccione el tipo de carga desea calcular: **Capacidad**, **Reservada** o **Restante**.</span><span class="sxs-lookup"><span data-stu-id="9febf-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="9febf-108">Seleccione **Sí** en el botón de alternar **Omitir cero** si no desea mostrar los resultados que contengan el valor cero.</span><span class="sxs-lookup"><span data-stu-id="9febf-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="9febf-109">Seleccione los tipos de recurso para los que desea calcular la carga de capacidad seleccionando **Sí** en los botones de alternar relevantes: **Trabajador**, **Grupo del trabajador de mantenimiento**, **Herramienta** y **Activo**.</span><span class="sxs-lookup"><span data-stu-id="9febf-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="9febf-110">Seleccione la fecha de inicio para el cálculo en el campo **Desde fecha**.</span><span class="sxs-lookup"><span data-stu-id="9febf-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="9febf-111">En el campo **Tipo de intervalo**, seleccione el intervalo para el cálculo: **Día**, **Semana**, **Mes** o **Trimestre**.</span><span class="sxs-lookup"><span data-stu-id="9febf-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="9febf-112">En el campo **Frecuencia de períodos**, inserte el número de intervalos que desee calcular.</span><span class="sxs-lookup"><span data-stu-id="9febf-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="9febf-113">Por ejemplo, si se ha seleccionado **Día** como el tipo de intervalo e introduzca el número "5 "en este campo, se realizará un cálculo de cinco días desde la fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="9febf-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="9febf-114">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="9febf-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="9febf-115">La ilustración siguiente muestra el resultado de un cálculo que cubre tres semanas para el tipo de carga **Reservada**.</span><span class="sxs-lookup"><span data-stu-id="9febf-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![Figura 1](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="9febf-117">Si selecciona los tipos de carga **Capacidad** o **Restante** para el cálculo, aparecerá el mismo resultado si no se han realizado reservas para los recursos en el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9febf-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="9febf-118">Para obtener información sobre cómo calcular la carga de capacidad en las líneas de la programación de mantenimiento y las órdenes de trabajo no programadas, consulte [Calcular la carga de capacidad](../capacity-planning/calculate-capacity-load.md).</span><span class="sxs-lookup"><span data-stu-id="9febf-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]