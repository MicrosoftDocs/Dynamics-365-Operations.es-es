---
title: Integración de acuerdos de servicio y proyectos
description: Cuando se trabaja con acuerdos de servicio y líneas de acuerdo de servicio, se usan los datos configurados en las áreas de administración de proyectos y contabilidad.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eab6125dbca1568c06818c8528d1bee4ce6bf53
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974469"
---
# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="849b2-103">Integración de acuerdos de servicio y proyectos</span><span class="sxs-lookup"><span data-stu-id="849b2-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="849b2-104">Cuando se trabaja con acuerdos de servicio y líneas de acuerdo de servicio, se usan los datos configurados en las siguientes áreas en **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="849b2-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="849b2-105">Precios de proyecto</span><span class="sxs-lookup"><span data-stu-id="849b2-105">Project prices</span></span>

<span data-ttu-id="849b2-106">El coste y el precio de ventas de una transacción de acuerdo de servicio derivan de la configuración del precio de coste que se aplica al proyecto asociado con el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="849b2-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="849b2-107">El coste y los precios de ventas se pueden configurar por proyecto, empleado y categoría.</span><span class="sxs-lookup"><span data-stu-id="849b2-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="849b2-108">Validación de proyecto</span><span class="sxs-lookup"><span data-stu-id="849b2-108">Project validation</span></span>

<span data-ttu-id="849b2-109">Los proyectos, empleados y categorías disponibles para la selección de una línea de acuerdo de servicio se pueden limitar mediante la configuración de la validación en **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="849b2-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="849b2-110">Mediante la configuración de validación, se pueden combinar empleados, proyectos y categorías para el acceso de control.</span><span class="sxs-lookup"><span data-stu-id="849b2-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="849b2-111">Propiedades de la línea de proyecto</span><span class="sxs-lookup"><span data-stu-id="849b2-111">Project line properties</span></span>

<span data-ttu-id="849b2-112">Automáticamente se especifica una propiedad de línea para una línea de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="849b2-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="849b2-113">Las propiedades de línea se crean en el formulario **Propiedades de línea** en **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="849b2-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="849b2-114">La propiedad de línea especificada en un acuerdo de servicio se asocia al proyecto seleccionado para el acuerdo de servicio y, consecuentemente, la línea de acuerdo de servicio la hereda.</span><span class="sxs-lookup"><span data-stu-id="849b2-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="849b2-115">Cuentas de contrapartida predeterminadas</span><span class="sxs-lookup"><span data-stu-id="849b2-115">Default offset accounts</span></span>

<span data-ttu-id="849b2-116">Si se especifica una transacción de gastos, automáticamente se seleccionará una cuenta de contrapartida de gastos predeterminada para esa transacción.</span><span class="sxs-lookup"><span data-stu-id="849b2-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="849b2-117">La cuenta de gastos predeterminada se configura para el proyecto asociado al acuerdo de servicio actual.</span><span class="sxs-lookup"><span data-stu-id="849b2-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="849b2-118">Categorías de proyecto</span><span class="sxs-lookup"><span data-stu-id="849b2-118">Project categories</span></span>

<span data-ttu-id="849b2-119">Las categorías disponibles para las líneas de acuerdo de servicio se configuran en el formulario **Categorías de proyecto** en **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="849b2-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="849b2-120">Las categorías con la casilla de verificación <STRONG>Activo en los diarios</STRONG> activada en la ficha <STRONG>Proyecto</STRONG> del formulario <STRONG>Categorías de proyecto</STRONG>, están disponibles para la selección.</span><span class="sxs-lookup"><span data-stu-id="849b2-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="849b2-121">Sin embargo, si se ha activado la casilla de verificación <STRONG>Categorías inactivas</STRONG> en la ficha <STRONG>Diarios</STRONG> del formulario <STRONG>Parámetros de gestión de proyectos y contabilidad</STRONG>, todas las categorías estarán disponibles para la selección.</span><span class="sxs-lookup"><span data-stu-id="849b2-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="849b2-122">Parámetros del proyecto</span><span class="sxs-lookup"><span data-stu-id="849b2-122">Project parameters</span></span>

<span data-ttu-id="849b2-123">Si el campo **Trabajadores terminados** en la pestaña **Diarios** en el formulario **Gestión de proyectos y contabilidad** está activado, se podrán seleccionar empleados inactivos además de empleados activos en los formularios **Acuerdos de servicio** y **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="849b2-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="849b2-124">Asimismo, se pueden habilitar los campos **Hora inicial** y **Hora final** en la ficha **Proyecto** en el formulario **Pedidos de servicio**, para especificar horas de inicio y de fin en las líneas de pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="849b2-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="849b2-125">Habilitar la función de horas de inicio y fin para pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="849b2-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="849b2-126">Haga clic en **Gestión de proyectos y contabilidad** \> **Configurar** \> **Parámetros de gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="849b2-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="849b2-127">Haga clic en la pestaña **Diarios** , y seleccione la casilla de verificación **Mostrar horas de inicio y fin**.</span><span class="sxs-lookup"><span data-stu-id="849b2-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="849b2-128">Haga clic en **Gestión de proyectos y contabilidad** \> **Configuración** \> **Diarios** \> **Nombres de diarios**.</span><span class="sxs-lookup"><span data-stu-id="849b2-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="849b2-129">Seleccione el nombre del diario asociado con el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="849b2-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="849b2-130">Haga clic en la pestaña **General** , y seleccione la casilla de verificación **Mostrar horas de inicio y fin**.</span><span class="sxs-lookup"><span data-stu-id="849b2-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="849b2-131">Seleccione el nombre del diario para el pedido de servicio en el campo <STRONG>Hora</STRONG> de la ficha <STRONG>Diarios</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="849b2-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>





