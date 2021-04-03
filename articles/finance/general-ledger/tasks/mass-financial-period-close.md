---
title: Cierre masivo de período financiero
description: En este tema se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4db0f68a22f9129041c7a7c081f397c34c2b07eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254448"
---
# <a name="mass-financial-period-close"></a><span data-ttu-id="a64fe-103">Cierre masivo de período financiero</span><span class="sxs-lookup"><span data-stu-id="a64fe-103">Mass financial period close</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a64fe-104">En este tema se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a64fe-104">This topic shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="a64fe-105">Además, la tarea mostrará cómo restringir el registro del grupo de usuarios a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="a64fe-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="a64fe-106">En el panel de navegación, vaya a **Módulos > Contabilidad general > Cierre de período > Calendarios del libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-106">In the navigation pane, go to **Modules > General ledger > Period close > Ledger calendars**.</span></span> <span data-ttu-id="a64fe-107">Tenga en cuenta que la lista de entidades jurídicas presentadas depende del calendario fiscal seleccionado en la página.</span><span class="sxs-lookup"><span data-stu-id="a64fe-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="a64fe-108">Solo se mostrarán las entidades jurídicas que usan el calendario fiscal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-108">Only legal entities using the selected fiscal calendar will display.</span></span>
2. <span data-ttu-id="a64fe-109">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-109">Select **Edit**.</span></span>
3. <span data-ttu-id="a64fe-110">Seleccione el período para el que desee modificar el estado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="a64fe-111">Seleccione las entidades legales para las que desee actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-111">Select the legal entities for which you want to update the status.</span></span> <span data-ttu-id="a64fe-112">Puede seleccionar rápidamente todas las entidades jurídicas seleccionando la marca de verificación en la parte superior izquierda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a64fe-112">You can quickly select all legal entities by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="a64fe-113">Seleccione **Actualizar acceso al módulo** para definir el acceso de registro a un módulo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-113">Select **Update module access** to define the posting access to a selected module.</span></span> <span data-ttu-id="a64fe-114">El estado del módulo también puede actualizarse uno por uno editando los registros de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a64fe-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="a64fe-115">El botón es útil si desea actualizar rápidamente múltiples registros de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="a64fe-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="a64fe-116">En el módulo **Aplicación**, seleccione el módulo del que desea actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-116">In the **Application** module, select the module that you want to update the status.</span></span> <span data-ttu-id="a64fe-117">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-117">Click **Select**.</span></span>
7. <span data-ttu-id="a64fe-118">En el nivel **Acceso**, seleccione **Todos**, **Ninguno** o un grupo de usuarios específico.</span><span class="sxs-lookup"><span data-stu-id="a64fe-118">In the **Access** level, select **All**, **None**, or a specific user group.</span></span> <span data-ttu-id="a64fe-119">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-119">Click **Select**.</span></span> <span data-ttu-id="a64fe-120">Todo indica que todos los usuarios con acceso de edición al módulo pueden registrar si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="a64fe-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="a64fe-121">Ninguno indica que los usuarios no pueden registrar en el módulo si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="a64fe-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="a64fe-122">Un grupo de usuarios específico indica que solo los usuarios del grupo pueden registrar en el módulo si el período está abierto.</span><span class="sxs-lookup"><span data-stu-id="a64fe-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="a64fe-123">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-123">Select **Update**.</span></span>
9. <span data-ttu-id="a64fe-124">Seleccione otro período para actualizar el estado.</span><span class="sxs-lookup"><span data-stu-id="a64fe-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="a64fe-125">Seleccione las entidades legales para las que desea actualizar el estado del período.</span><span class="sxs-lookup"><span data-stu-id="a64fe-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="a64fe-126">Seleccione **Actualizar estado del período** y establezca el estado **En espera**, **Abierto** o **Cerrado de forma permanente**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-126">Select **Update period status** and set the status of **On hold**, **Open**, or **Permanently closed**.</span></span> <span data-ttu-id="a64fe-127">**Abierto** indica el período en el que se puede registrar, siempre que el usuario tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="a64fe-127">**Open** indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="a64fe-128">**En espera** significa que el período no se puede registrar, pero se puede volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="a64fe-128">**On hold** means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="a64fe-129">**Cerrado de forma permanente** significa que el período está cerrado y no se puede abrir nunca.</span><span class="sxs-lookup"><span data-stu-id="a64fe-129">**Permanently closed** means the period is closed and can never be opened.</span></span> <span data-ttu-id="a64fe-130">No se pueden registrar ajustes.</span><span class="sxs-lookup"><span data-stu-id="a64fe-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="a64fe-131">No se recomienda establecer un período como **Cerrado de forma permanente** hasta que se completen todos los ajustes y las auditorías.</span><span class="sxs-lookup"><span data-stu-id="a64fe-131">We do not recommend setting a period to **Permanently closed** until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="a64fe-132">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-132">Select **Update**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]