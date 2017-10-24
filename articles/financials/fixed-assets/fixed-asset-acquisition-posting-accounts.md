---
title: "Cuentas de registro de adquisición de activos fijos"
description: "En este artículo se explica cómo configurar cuentas de registro de contabilidad general para adquirir activos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 887616463856875e2382a00b1d56520391ead844
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="dacd9-103">Cuentas de registro de adquisición de activos fijos</span><span class="sxs-lookup"><span data-stu-id="dacd9-103">Fixed asset acquisition posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dacd9-104">En este artículo se explica cómo configurar cuentas de registro de contabilidad general para adquirir activos.</span><span class="sxs-lookup"><span data-stu-id="dacd9-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="dacd9-105">Las cuentas usadas para registrar adquisiciones de activos fijos pueden variar en función del método usado para adquirir el activo.</span><span class="sxs-lookup"><span data-stu-id="dacd9-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="dacd9-106">En la página Perfiles de contabilización de activos fijos, en la pestaña Cuentas contables, seleccione Adquisición y Ajuste de adquisición para configurar cuentas de activos fijos para registrarlas en la contabilidad.</span><span class="sxs-lookup"><span data-stu-id="dacd9-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="dacd9-107">En los diarios y en los pedidos de compra, Cuenta contable es normalmente la cuenta de balance de situación, donde se adeuda el valor de adquisición del activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="dacd9-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="dacd9-108">Esta cuenta no se puede ver en el diario ni sustituir en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="dacd9-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="dacd9-109">Cuenta de contrapartida también es una cuenta de balance de situación.</span><span class="sxs-lookup"><span data-stu-id="dacd9-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="dacd9-110">En el diario general y en diario de activos fijos, esta cuenta suele ser la cuenta bancaria utilizada para pagar la adquisición del activo.</span><span class="sxs-lookup"><span data-stu-id="dacd9-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="dacd9-111">La cuenta de contrapartida es una cuenta predeterminada sugerida en los diarios.</span><span class="sxs-lookup"><span data-stu-id="dacd9-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="dacd9-112">Es posible cambiarla en el diario a una cuenta del plan contable o a una cuenta del proveedor, si un proveedor ha comprado el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="dacd9-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="dacd9-113">Cuando se utiliza Diario de facturas o Pedidos de compra en Proveedores para las adquisiciones de activos fijos, la cuenta de contrapartida de la transacción de activos fijos se sustituye por la cuenta de proveedor seleccionada para la transacción.</span><span class="sxs-lookup"><span data-stu-id="dacd9-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="dacd9-114">En las adquisiciones registradas con el diario Inventario a activos fijos en la contabilidad general, el activo fijo no se compra por fuentes externas, sino que se transfiere del propio inventario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="dacd9-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="dacd9-115">Por lo tanto, la cuenta de contrapartida es una cuenta de emisión de inventario del artículo de inventario de Gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="dacd9-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="dacd9-116">Para obtener más información, consulte [Adquisición de activos mediante compra](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="dacd9-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>




