---
title: Tipos de orden de trabajo
description: En este tema se explican los tipos de órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8e43908e3f13c9e4fd6fab6f1e17a171866b803
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888794"
---
# <a name="work-order-types"></a><span data-ttu-id="4c505-103">Tipos de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="4c505-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4c505-104">Los tipos de pedido de trabajo se usan para clasificar órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c505-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="4c505-105">Por ejemplo, puede que tenga órdenes de trabajo relacionadas con el mantenimiento preventivo o el mantenimiento correctivo.</span><span class="sxs-lookup"><span data-stu-id="4c505-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="4c505-106">Un tipo de pedido de trabajo define una afiliación a un modelo del ciclo de vida de pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c505-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="4c505-107">Un modelo del ciclo de vida de la orden de trabajo define los estados del ciclo de vida de la orden de trabajo que se pueden configurar en un pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c505-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="4c505-108">(Ejemplos de estados de ciclo de vida de vida de orden de trabajo son **Creado**, **En proceso** y **Finalizado**).</span><span class="sxs-lookup"><span data-stu-id="4c505-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="4c505-109">Para obtener más información sobre estados y etapas de proyecto del ciclo de vida de la orden de trabajo, consulte [Estados del ciclo de vida de la orden de trabajo](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="4c505-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="4c505-110">Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Tipos de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4c505-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="4c505-111">Seleccione **Nuevo** para crear un tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c505-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="4c505-112">En el campo **Tipo de orden de trabajo**, especifique un identificador para el tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c505-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="4c505-113">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4c505-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="4c505-114">En el campo **Modelo de ciclo de vida de orden de trabajo**, seleccione un modelo del ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="4c505-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="4c505-115">Establezca la opción **Un trabajador de mantenimiento** en **Sí** si todos los trabajos de pedido de trabajo relacionados con un pedido de trabajo de este tipo tienen que programarse con el mismo trabajador mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4c505-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="4c505-116">En el campo **Tipo de coste**, seleccione **Correctivo**, **Preventivo**, o **Inversión**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="4c505-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="4c505-117">Todos los trabajos de un pedido de trabajo deben tener el mismo tipo de coste.</span><span class="sxs-lookup"><span data-stu-id="4c505-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="4c505-118">En la sección **Obligatorio**, establezca las opciones relevantes en **Sí** para especificar qué información de tiempo de inactividad o de error se agrega a un pedido de trabajo de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4c505-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c505-119">Las opciones de la sección **Obligatorio** están relacionadas con las opciones de la ficha desplegable **Validar** de la página **Estado del ciclo de vida de la orden de trabajo** (**Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Estados del ciclo de vida**).</span><span class="sxs-lookup"><span data-stu-id="4c505-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="4c505-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4c505-120">Select **Save**.</span></span>

![Tipos de orden de trabajo](media/16-setup-for-work-orders.png)
