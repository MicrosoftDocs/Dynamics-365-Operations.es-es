--- 
title: "Cierre masivo de período financiero"
description: "Este procedimiento muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cafd837be054e96afc10d3b78402bdcc67c43c33
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="c8a18-103">Cierre masivo de período financiero</span><span class="sxs-lookup"><span data-stu-id="c8a18-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8a18-104">Este procedimiento muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c8a18-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="c8a18-105">Además, la tarea mostrará cómo restringir el registro del grupo de usuarios a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="c8a18-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="c8a18-106">Vaya a Contabilidad general > Cierre de período > Calendarios del libro mayor.</span><span class="sxs-lookup"><span data-stu-id="c8a18-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="c8a18-107">Tenga en cuenta que la lista de entidades jurídicas presentadas depende del calendario fiscal seleccionado en la página.</span><span class="sxs-lookup"><span data-stu-id="c8a18-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="c8a18-108">Solo se mostrarán las entidades jurídicas que usan el calendario fiscal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="c8a18-109">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c8a18-109">Click Edit.</span></span>
3. <span data-ttu-id="c8a18-110">Seleccione el período para el que desee modificar el estado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="c8a18-111">Seleccione las entidades legales para las que desee actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="c8a18-112">Puede seleccionar rápidamente todas las entidades jurídicas seleccionando la marca de verificación en la parte superior izquierda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="c8a18-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="c8a18-113">Seleccione Actualizar acceso al módulo para definir el acceso de registro a un módulo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="c8a18-114">El estado del módulo también puede actualizarse uno por uno editando los registros de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="c8a18-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="c8a18-115">El botón es útil si desea actualizar rápidamente múltiples registros de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="c8a18-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="c8a18-116">En el módulo Aplicación, seleccione el módulo del que desea actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="c8a18-117">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="c8a18-117">Click Select.</span></span>
7. <span data-ttu-id="c8a18-118">En el nivel Acceso, seleccione Todos, Ninguno o un grupo de usuarios específico.</span><span class="sxs-lookup"><span data-stu-id="c8a18-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="c8a18-119">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="c8a18-119">Click Select.</span></span>
    * <span data-ttu-id="c8a18-120">Todo indica que todos los usuarios con acceso de edición al módulo pueden registrar si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="c8a18-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="c8a18-121">Ninguno indica que los usuarios no pueden registrar en el módulo si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="c8a18-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="c8a18-122">Un grupo de usuarios específico indica que solo los usuarios del grupo pueden registrar en el módulo si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="c8a18-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="c8a18-123">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="c8a18-123">Click Update.</span></span>
9. <span data-ttu-id="c8a18-124">Seleccione otro período para actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="c8a18-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="c8a18-125">Seleccione las entidades legales para las que desea actualizar el estado del período.</span><span class="sxs-lookup"><span data-stu-id="c8a18-125">Select the legal entities for which you want to update the period status.</span></span>
11. <span data-ttu-id="c8a18-126">Seleccione Actualizar estado del período y establezca el estado En espera, Abierto o Cerrado de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="c8a18-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="c8a18-127">Abierto indica el período en el que se puede registrar, siempre que el usuario tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="c8a18-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="c8a18-128">En espera significa que el período no se pueden registrar, pero el período se puede volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="c8a18-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="c8a18-129">Cerrado de forma permanente significa que el período está cerrado y no se puede abrir nunca.</span><span class="sxs-lookup"><span data-stu-id="c8a18-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="c8a18-130">No se pueden registrar ajustes.</span><span class="sxs-lookup"><span data-stu-id="c8a18-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="c8a18-131">No se recomienda establecer un período como Cerrado de forma permanente hasta que se completen todos los ajustes y las auditorías.</span><span class="sxs-lookup"><span data-stu-id="c8a18-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="c8a18-132">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="c8a18-132">Click Update.</span></span>


