---
title: Crear un pedido de compra para un proveedor plantilla
description: Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beaf6bcbc870e11e74289375611c631306545633
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "312885"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="c2984-103">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="c2984-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2984-104">Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.</span><span class="sxs-lookup"><span data-stu-id="c2984-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="c2984-105">El proveedor se crea automáticamente con el pedido de compra, en lugar de tener que crear la cuenta de proveedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="c2984-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="c2984-106">Los pedidos de compra normalmente se crean por un agente de compras.</span><span class="sxs-lookup"><span data-stu-id="c2984-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="c2984-107">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c2984-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="c2984-108">Es un requisito previo que se haya configurado una cuenta de proveedor plantilla en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="c2984-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="c2984-109">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="c2984-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="c2984-110">Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="c2984-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="c2984-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c2984-111">Click New.</span></span>
3. <span data-ttu-id="c2984-112">Seleccione Sí en el campo Proveedor de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="c2984-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="c2984-113">Una cuenta de proveedor se crea automáticamente y se asigna al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="c2984-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="c2984-114">La cuenta de proveedor se crea basándose en la plantilla que se especifica en la pestaña General de la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="c2984-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="c2984-115">En el campo Nombre, escriba un nombre único para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="c2984-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="c2984-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c2984-116">Click OK.</span></span>
    * <span data-ttu-id="c2984-117">El pedido de compra se puede completar ahora y procesarse como cualquier otro pedido.</span><span class="sxs-lookup"><span data-stu-id="c2984-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="c2984-118">No hay características especiales relacionadas con cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="c2984-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="c2984-119">La factura considerará una transacción vencida en la cuenta del proveedor que se creó con el pedido y el pago se procesará entonces.</span><span class="sxs-lookup"><span data-stu-id="c2984-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="c2984-120">Cuando esto se complete, se podrá eliminar la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c2984-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="c2984-121">Esto lo suele realizar el departamento de proveedores.</span><span class="sxs-lookup"><span data-stu-id="c2984-121">This is typically done by the accounts payable department.</span></span>  

