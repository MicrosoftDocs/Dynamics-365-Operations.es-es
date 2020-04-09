---
title: Recibir artículos de un pedido de compra a partir de un artículo requerido
description: En este tema se explica cómo recibir artículos en un pedido de compra desde un artículo requerido.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f288a47f952a30d98a4a5b96409dc53f880d41d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139073"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="0261c-103">Recibir artículos de un pedido de compra a partir de un artículo requerido</span><span class="sxs-lookup"><span data-stu-id="0261c-103">Receive items on purchase order from item requirement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0261c-104">En este tema se explica cómo recibir artículos en un pedido de compra desde un artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="0261c-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="0261c-105">Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.</span><span class="sxs-lookup"><span data-stu-id="0261c-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="0261c-106">Esta tarea usa el conjunto de datos USSI.</span><span class="sxs-lookup"><span data-stu-id="0261c-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="0261c-107">En el panel de navegación, vaya a **Módulos > Gestión y contabilidad de proyectos > Proyectos > Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="0261c-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="0261c-108">En la lista, seleccione el vínculo de la fila deseada.</span><span class="sxs-lookup"><span data-stu-id="0261c-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="0261c-109">En el panel de acciones, haga clic en **Plan**.</span><span class="sxs-lookup"><span data-stu-id="0261c-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="0261c-110">Seleccione **Requisitos de artículos**.</span><span class="sxs-lookup"><span data-stu-id="0261c-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="0261c-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0261c-111">Select **New**.</span></span>
6. <span data-ttu-id="0261c-112">En la nueva fila, introduzca o seleccione un valor en el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="0261c-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="0261c-113">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0261c-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="0261c-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0261c-114">Select **Save**.</span></span>
9. <span data-ttu-id="0261c-115">En el panel de acciones, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="0261c-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="0261c-116">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="0261c-116">Select **Functions**.</span></span>
11. <span data-ttu-id="0261c-117">Seleccione **Crear pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="0261c-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="0261c-118">Seleccione la casilla **Incluir todos**.</span><span class="sxs-lookup"><span data-stu-id="0261c-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="0261c-119">En el campo **Cuenta de proveedor**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0261c-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="0261c-120">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0261c-120">Select **OK**.</span></span>
15. <span data-ttu-id="0261c-121">En el panel de navegación, vaya a **Módulos > Proveedores > Pedidos de compra > Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="0261c-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="0261c-122">En la lista, seleccione el vínculo de la fila deseada.</span><span class="sxs-lookup"><span data-stu-id="0261c-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="0261c-123">En el panel de acciones, selecione **Compra.**</span><span class="sxs-lookup"><span data-stu-id="0261c-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="0261c-124">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0261c-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="0261c-125">En el panel de acciones, seleccione **Recibir**.</span><span class="sxs-lookup"><span data-stu-id="0261c-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="0261c-126">Seleccione **Recepción de producto**.</span><span class="sxs-lookup"><span data-stu-id="0261c-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="0261c-127">En el campo **Recepción de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0261c-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="0261c-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0261c-128">Select **OK**.</span></span>

