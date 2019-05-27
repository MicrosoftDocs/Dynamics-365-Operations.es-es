---
title: Configurar permisos para pedir productos en nombre de otro usuario
description: Este procedimiento muestra cómo conceder a los trabajadores permiso para preparar solicitudes de la compra en nombre de otros trabajadores.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35688d191cef06cc15251a6e10a2e8c9afb0e08b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571872"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="39549-103">Configurar permisos para pedir productos en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="39549-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39549-104">Este procedimiento muestra cómo conceder a los trabajadores permiso para preparar solicitudes de la compra en nombre de otros trabajadores.</span><span class="sxs-lookup"><span data-stu-id="39549-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="39549-105">Es decir, un “preparador” de una solicitud de compra puede crear una solicitud para otro “solicitante.”</span><span class="sxs-lookup"><span data-stu-id="39549-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="39549-106">El procedimiento también muestra cómo conceder permisos a un trabajador para que pida los artículos y los servicios en diferentes entidades jurídicas o unidades operativas.</span><span class="sxs-lookup"><span data-stu-id="39549-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="39549-107">Normalmente, estas tareas las realiza el administrador de compras.</span><span class="sxs-lookup"><span data-stu-id="39549-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="39549-108">Puede utilizar este procedimiento en los datos para la empresa de demostración USMF o en sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="39549-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="39549-109">Conceder permiso para especificar solicitudes de compra en nombre de otro trabajador</span><span class="sxs-lookup"><span data-stu-id="39549-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="39549-110">Vaya a Adquisición y abastecimiento > Configuración > Directivas > Permisos de solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="39549-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="39549-111">Asegúrese de que el campo Vista actual está establecido en Por preparador.</span><span class="sxs-lookup"><span data-stu-id="39549-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="39549-112">La lista del panel izquierdo muestra a la gente a quien se le puede conceder permiso para preparar solicitudes en nombre de otras personas.</span><span class="sxs-lookup"><span data-stu-id="39549-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="39549-113">Seleccione la persona a la que le concederá el permiso (el preparador).</span><span class="sxs-lookup"><span data-stu-id="39549-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="39549-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39549-114">Click Add.</span></span>
4. <span data-ttu-id="39549-115">Encuentre y seleccione la persona para agregarla como solicitante.</span><span class="sxs-lookup"><span data-stu-id="39549-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="39549-116">El solicitante es la persona en nombre de la cual el preparador puede crear solicitudes.</span><span class="sxs-lookup"><span data-stu-id="39549-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="39549-117">En el campo Autorización, seleccione Específico si el preparador debe poder crear solicitudes de compra en nombre del trabajador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39549-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="39549-118">Seleccione Notificación si el preparador debe poder crear solicitudes de compra en nombre de todos los trabajadores que informen a ese trabajador.</span><span class="sxs-lookup"><span data-stu-id="39549-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="39549-119">En el campo Vigente, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="39549-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="39549-120">En el campo Caducidad, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="39549-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="39549-121">Ver preparadores que tienen permiso para crear solicitudes de compra para un trabajador seleccionado</span><span class="sxs-lookup"><span data-stu-id="39549-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="39549-122">En el campo Vista actual, seleccione “Por solicitante”.</span><span class="sxs-lookup"><span data-stu-id="39549-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="39549-123">Esta lista muestra una lista de preparadores a los que se le han concedido permiso para crear solicitudes de compra en nombre de un trabajador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39549-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="39549-124">Utilice el Filtro rápido para encontrar el trabajador que acaba de agregar como solicitante.</span><span class="sxs-lookup"><span data-stu-id="39549-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="39549-125">Seleccione el solicitante.</span><span class="sxs-lookup"><span data-stu-id="39549-125">Select the requester.</span></span>
    * <span data-ttu-id="39549-126">La lista Preparador muestra las personas con permiso para pedir artículos en nombre del solicitante seleccionado en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="39549-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="39549-127">Puede agregar preparadores adicionales aquí.</span><span class="sxs-lookup"><span data-stu-id="39549-127">You can add additional preparers here.</span></span>   <span data-ttu-id="39549-128">Esta vista también le permite conceder el permiso de solicitante para crear solicitudes en entidades jurídicas y unidades operativas que no son la entidad jurídica principal o unidad operativa de esa persona.</span><span class="sxs-lookup"><span data-stu-id="39549-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  

