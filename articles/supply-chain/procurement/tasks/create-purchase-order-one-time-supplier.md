--- 
title: Crear un pedido de compra para un proveedor plantilla
description: "Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla."
author: FrankDahl
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
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 59582e33a3a012d6f9e3f506d1f8303c07fb06a9
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0bf15-103">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="0bf15-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0bf15-104">Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.</span><span class="sxs-lookup"><span data-stu-id="0bf15-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="0bf15-105">El proveedor se crea automáticamente con el pedido de compra, en lugar de tener que crear la cuenta de proveedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="0bf15-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="0bf15-106">Los pedidos de compra normalmente se crean por un agente de compras.</span><span class="sxs-lookup"><span data-stu-id="0bf15-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="0bf15-107">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="0bf15-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="0bf15-108">Es un requisito previo que se haya configurado una cuenta de proveedor plantilla en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="0bf15-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0bf15-109">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="0bf15-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="0bf15-110">Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="0bf15-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0bf15-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0bf15-111">Click New.</span></span>
3. <span data-ttu-id="0bf15-112">Seleccione Sí en el campo Proveedor de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="0bf15-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="0bf15-113">Una cuenta de proveedor se crea automáticamente y se asigna al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="0bf15-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="0bf15-114">La cuenta de proveedor se crea basándose en la plantilla que se especifica en la pestaña General de la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="0bf15-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="0bf15-115">En el campo Nombre, escriba un nombre único para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="0bf15-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="0bf15-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0bf15-116">Click OK.</span></span>
    * <span data-ttu-id="0bf15-117">El pedido de compra se puede completar ahora y procesarse como cualquier otro pedido.</span><span class="sxs-lookup"><span data-stu-id="0bf15-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="0bf15-118">No hay características especiales relacionadas con cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="0bf15-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="0bf15-119">La factura considerará una transacción vencida en la cuenta del proveedor que se creó con el pedido y el pago se procesará entonces.</span><span class="sxs-lookup"><span data-stu-id="0bf15-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="0bf15-120">Cuando esto se complete, se podrá eliminar la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="0bf15-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="0bf15-121">Esto lo suele realizar el departamento de proveedores.</span><span class="sxs-lookup"><span data-stu-id="0bf15-121">This is typically done by the accounts payable department.</span></span>  


