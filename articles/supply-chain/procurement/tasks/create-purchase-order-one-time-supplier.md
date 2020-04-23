---
title: Crear un pedido de compra para un proveedor plantilla
description: Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76915772809d736cac9e8a9439d9e693a4490eec
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204916"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="ca110-103">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="ca110-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca110-104">Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.</span><span class="sxs-lookup"><span data-stu-id="ca110-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="ca110-105">El proveedor se crea automáticamente con el pedido de compra, en lugar de tener que crear la cuenta de proveedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="ca110-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="ca110-106">Los pedidos de compra normalmente se crean por un agente de compras.</span><span class="sxs-lookup"><span data-stu-id="ca110-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="ca110-107">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="ca110-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="ca110-108">Es un requisito previo que se haya configurado una cuenta de proveedor plantilla en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="ca110-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="ca110-109">Crear un pedido de compra para un proveedor plantilla</span><span class="sxs-lookup"><span data-stu-id="ca110-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="ca110-110">Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="ca110-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ca110-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ca110-111">Click New.</span></span>
3. <span data-ttu-id="ca110-112">Seleccione Sí en el campo Proveedor de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="ca110-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="ca110-113">Una cuenta de proveedor se crea automáticamente y se asigna al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ca110-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="ca110-114">La cuenta de proveedor se crea basándose en la plantilla que se especifica en la pestaña General de la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="ca110-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="ca110-115">En el campo Nombre, escriba un nombre único para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="ca110-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="ca110-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ca110-116">Click OK.</span></span>
    * <span data-ttu-id="ca110-117">El pedido de compra se puede completar ahora y procesarse como cualquier otro pedido.</span><span class="sxs-lookup"><span data-stu-id="ca110-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="ca110-118">No hay características especiales relacionadas con cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="ca110-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="ca110-119">La factura considerará una transacción vencida en la cuenta del proveedor que se creó con el pedido y el pago se procesará entonces.</span><span class="sxs-lookup"><span data-stu-id="ca110-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>

