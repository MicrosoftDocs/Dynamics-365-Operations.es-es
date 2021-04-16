---
title: Aprobar proveedores para categorías de compras específicas
description: Este tema explica cómo aprobar proveedores para las categorías de compras específicas en Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 887905c35c684f2f60c3ce17eb652532831193cc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812455"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="a5e73-103">Aprobar proveedores para categorías de compras específicas</span><span class="sxs-lookup"><span data-stu-id="a5e73-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5e73-104">Este tema explica cómo aprobar proveedores para las categorías de compras específicas en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a5e73-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a5e73-105">Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras.</span><span class="sxs-lookup"><span data-stu-id="a5e73-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="a5e73-106">Este procedimiento le muestra cómo especificar que un proveedor está aprobado o preferido para una categoría de compras específica.</span><span class="sxs-lookup"><span data-stu-id="a5e73-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="a5e73-107">Esta tarea la lleva a cabo normalmente un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="a5e73-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="a5e73-108">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a5e73-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="a5e73-109">En el panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Proveedores > Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="a5e73-110">Seleccione el proveedor que desea establecer como proveedor aprobado o preferido para una categoría.</span><span class="sxs-lookup"><span data-stu-id="a5e73-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="a5e73-111">En el panel de acciones, seleccione **Gneral**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="a5e73-112">Seleccione **Categorías**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-112">Select **Categories**.</span></span>
5. <span data-ttu-id="a5e73-113">Seleccione **Agregar categoría**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-113">Select **Add category**.</span></span>
6. <span data-ttu-id="a5e73-114">En el campo **Categoría**, seleccione **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="a5e73-115">En el campo **Estado de categoría del proveedor**, seleccione **Preferido**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="a5e73-116">Es posible especificar más de un proveedor preferido para una categoría.</span><span class="sxs-lookup"><span data-stu-id="a5e73-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="a5e73-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-117">Select **Save**.</span></span>
9. <span data-ttu-id="a5e73-118">En el Panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Categorías de compras**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="a5e73-119">En el árbol, seleccione **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="a5e73-120">Expanda la sección **Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="a5e73-121">Compruebe si el proveedor que ha seleccionado aparece como proveedor preferido para la categoría de accesorios de la oficina y escritorio.</span><span class="sxs-lookup"><span data-stu-id="a5e73-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="a5e73-122">Si está ejecutando este procedimiento como guía de tareas, es posible que tenga que hacer seleccionar en el botón **Desbloquear** para poder desplazarse hacia abajo en la lista de proveedores.</span><span class="sxs-lookup"><span data-stu-id="a5e73-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="a5e73-123">También es posible agregar proveedores preferidos y aprobados en esta página.</span><span class="sxs-lookup"><span data-stu-id="a5e73-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="a5e73-124">En el árbol, expanda **OFFICE AND DESK ACCESSORIES** y seleccione **Tijeras**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="a5e73-125">Seleccione **No** en el campo **Heredar proveedores de la categoría principal:**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="a5e73-126">Seleccione **Sí** en el campo **Heredar proveedores de la categoría principal:**.</span><span class="sxs-lookup"><span data-stu-id="a5e73-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]