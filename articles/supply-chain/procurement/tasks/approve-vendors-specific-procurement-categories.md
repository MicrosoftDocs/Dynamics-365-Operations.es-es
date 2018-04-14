--- 
title: "Aprobar proveedores para categorías de compras específicas"
description: "Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3ee04497653b21600cd42fa9c90e7876e613acee
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="f4aa5-103">Aprobar proveedores para categorías de compras específicas</span><span class="sxs-lookup"><span data-stu-id="f4aa5-103">Approve vendors for specific procurement categories</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4aa5-104">Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="f4aa5-105">Este procedimiento le muestra cómo especificar que un proveedor está aprobado o preferido para una categoría de compras específica.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="f4aa5-106">Esta tarea la lleva a cabo normalmente un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="f4aa5-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="f4aa5-108">Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="f4aa5-109">Seleccione el proveedor que desea establecer como proveedor aprobado o preferido para una categoría.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="f4aa5-110">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="f4aa5-111">Haga clic Categorías.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-111">Click Categories.</span></span>
5. <span data-ttu-id="f4aa5-112">Haga clic en Agregar categoría.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-112">Click Add category.</span></span>
6. <span data-ttu-id="f4aa5-113">En el campo Categoría, seleccione OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span><span class="sxs-lookup"><span data-stu-id="f4aa5-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="f4aa5-114">En el campo Estado de categoría del proveedor, seleccione "Preferido".</span><span class="sxs-lookup"><span data-stu-id="f4aa5-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="f4aa5-115">Es posible especificar más de un proveedor preferido para una categoría.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="f4aa5-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-116">Click Save.</span></span>
9. <span data-ttu-id="f4aa5-117">Vaya a Adquisición y abastecimiento > Categorías de compras.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="f4aa5-118">En el árbol, seleccione "CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES".</span><span class="sxs-lookup"><span data-stu-id="f4aa5-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="f4aa5-119">Expanda la sección Proveedores.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="f4aa5-120">Compruebe si el proveedor que ha seleccionado aparece como proveedor preferido para la categoría de accesorios de la oficina y escritorio.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="f4aa5-121">Si está ejecutando este procedimiento como guía de tareas, es posible que tenga que hacer clic en el botón Desbloquear para poder desplazarse hacia abajo en la lista de proveedores.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="f4aa5-122">También es posible agregar proveedores preferidos y aprobados en esta página.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="f4aa5-123">En el árbol, expanda "OFFICE AND DESK ACCESSORIES".</span><span class="sxs-lookup"><span data-stu-id="f4aa5-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="f4aa5-124">En el árbol, seleccione "Tijeras".</span><span class="sxs-lookup"><span data-stu-id="f4aa5-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="f4aa5-125">Seleccione No en el campo Heredar proveedores de la categoría principal:.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="f4aa5-126">Seleccione Sí en el campo Heredar proveedores de la categoría principal:.</span><span class="sxs-lookup"><span data-stu-id="f4aa5-126">Select Yes in the Inherit vendors from parent category: field.</span></span>


