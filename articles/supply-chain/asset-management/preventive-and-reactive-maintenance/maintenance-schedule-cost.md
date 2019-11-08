---
title: Coste del programa de mantenimiento
description: En este tema se explica el coste del programa de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: b30fa3c142057b43202a8f5a323c0b425865e971
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571332"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="c5771-103">Coste del programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5771-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c5771-104">En Administración de activos, puede calcular los costes presupuestarios en las líneas del programa de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5771-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="c5771-105">Esto resulta útil si desea obtener una visión general de los costes previstos, por ejemplo, costes relacionados con trabajos de mantenimiento preventivo planificados para el año próximo.</span><span class="sxs-lookup"><span data-stu-id="c5771-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="c5771-106">Los cálculos se basan en líneas existentes del programa de mantenimiento de tipo "Planes de mantenimiento" y "Rondas de mantenimiento" y "Solicitudes de mantenimiento".</span><span class="sxs-lookup"><span data-stu-id="c5771-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="c5771-107">Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Coste del programa de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5771-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="c5771-108">En el diálogo **Coste del programa de mantenimiento**, puede seleccionar un **Conjunto de dimensiones financieras** si desea ver costes agrupados en dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="c5771-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="c5771-109">Los conjuntos de dimensiones financieras se configuran en **Contabilidad general** > **Plan de cuentas** > **Dimensiones** > **Conjuntos de dimensiones financieras**.</span><span class="sxs-lookup"><span data-stu-id="c5771-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="c5771-110">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas del programa de mantenimiento con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="c5771-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="c5771-111">Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento para una ubicación técnica se mostrarán en el nivel superior. De este modo, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="c5771-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="c5771-112">Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento en todos los niveles de la ubicación técnica con los que están relacionados.</span><span class="sxs-lookup"><span data-stu-id="c5771-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="c5771-113">Si desea hacer un cálculo para determinados activos, haga clic en **Filtro** en la ficha desplegable **Registros que incluir** y seleccione los activos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c5771-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="c5771-114">Si es necesario, también puede especificar una fecha **Inicial prevista** para el cálculo de coste o seleccionar un **Estado** diferente para el cálculo de costes</span><span class="sxs-lookup"><span data-stu-id="c5771-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="c5771-115">Haga clic en **Aceptar** para iniciar el cálculo de costes.</span><span class="sxs-lookup"><span data-stu-id="c5771-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="c5771-116">En la pestaña **Coste del programa de mantenimiento** > en los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo de costes.</span><span class="sxs-lookup"><span data-stu-id="c5771-116">On the **Maintenance schedule cost** tab > in the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="c5771-117">Se resaltarán los botones del grupo de paneles de acciones seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5771-117">The selected action pane group buttons are highlighted.</span></span> <span data-ttu-id="c5771-118">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="c5771-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="c5771-119">Haga clic en el botón **Calcular coste** si desea crear un nuevo cálculo de costes.</span><span class="sxs-lookup"><span data-stu-id="c5771-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="c5771-120">La ilustración siguiente muestra los resultados del cálculo de costes del programa de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5771-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Figura 1](media/17-preventive-maintenance.png)

