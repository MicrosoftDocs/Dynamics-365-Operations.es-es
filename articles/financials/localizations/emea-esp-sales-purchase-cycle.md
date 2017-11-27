---
title: "Ventas y ciclos de compra para España"
description: "Este tema describe cómo configurar los ciclos de pedido de ventas o de compra para un proveedor o un cliente para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 263444
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 69467d0379c2fda239a8695749e52607de0def6f
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="sales-and-purchase-cycles-for-spain"></a><span data-ttu-id="d7bdc-103">Ventas y ciclos de compra para España</span><span class="sxs-lookup"><span data-stu-id="d7bdc-103">Sales and purchase cycles for Spain</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d7bdc-104">Este tema describe cómo configurar los ciclos de pedido de ventas o de compra para un proveedor o un cliente para las entidades jurídicas en España.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-104">This topic describes how to set up sales order or purchase order cycles for a vendor or customer for legal entities in Spain.</span></span>  

<span data-ttu-id="d7bdc-105">Según los requisitos de los clientes y proveedores, algunas empresas españolas no actualizan todos los documentos que se incluyen en el ciclo de ventas o de compras.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-105">Depending on the requirements of their customers and vendors, some Spanish companies don't update all documents that are included in the sales or purchase cycle.</span></span> <span data-ttu-id="d7bdc-106">A continuación se muestran algunos ejemplos de documentos de ventas o compras que no se actualizan:</span><span class="sxs-lookup"><span data-stu-id="d7bdc-106">Here are some examples of sales or purchase documents that aren't updated:</span></span>

-   <span data-ttu-id="d7bdc-107">Ofertas</span><span class="sxs-lookup"><span data-stu-id="d7bdc-107">Quotes</span></span>
-   <span data-ttu-id="d7bdc-108">Confirmaciones</span><span class="sxs-lookup"><span data-stu-id="d7bdc-108">Confirmations</span></span>
-   <span data-ttu-id="d7bdc-109">Albaranes</span><span class="sxs-lookup"><span data-stu-id="d7bdc-109">Packing slips</span></span>
-   <span data-ttu-id="d7bdc-110">Facturas</span><span class="sxs-lookup"><span data-stu-id="d7bdc-110">Invoices</span></span>

<span data-ttu-id="d7bdc-111">Para las entidades jurídicas que tengan su dirección principal en España, puede especificar qué documentos deben estar disponibles en pedidos de ventas o de compras.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-111">For legal entities that have their primary address in Spain, you can specify which documents should be available on sales orders or purchase orders.</span></span> <span data-ttu-id="d7bdc-112">También puede especificar qué documentos deben estar disponibles para clientes o proveedores.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-112">You can also specify which documents should be available for customers or vendors.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7bdc-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d7bdc-113">Prerequisites</span></span>
<span data-ttu-id="d7bdc-114">Antes de poder configurar los documentos predeterminados para los ciclos de ventas y de compra, debe configurar los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d7bdc-114">Before you can set up default documents for the sales and purchase cycles, you must set up the following parameters:</span></span>

-   <span data-ttu-id="d7bdc-115">**Ciclo de ventas**: seleccione esta opción en la página **Parámetros de clientes** para configurar un ciclo de documentos de venta predeterminado para los clientes.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-115">**Sales cycle** – Select this option on the **Accounts receivable parameters** page to set up a default sales document cycle for customers.</span></span> <span data-ttu-id="d7bdc-116">También puede seleccionar los tipos de documento que estarán disponibles en pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-116">You can also select the document types that will be available on sales orders.</span></span>
-   <span data-ttu-id="d7bdc-117">**Ciclo de compra**: seleccione esta opción en la página **Parámetros de adquisición y abastecimiento** para configurar un ciclo de documentos de compra predeterminado para proveedores.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-117">**Purchase cycle** – Select this option on the **Procurement and sourcing parameters** page to set up a default purchase document cycle for vendors.</span></span> <span data-ttu-id="d7bdc-118">También puede seleccionar los tipos de documento que estarán disponibles en pedidos de compras.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-118">You can also select the document types that will be available on purchase orders.</span></span>

## <a name="set-up-a-document-cycle-for-each-customer-or-vendor"></a><span data-ttu-id="d7bdc-119">Configurar un ciclo de documentos para cada cliente o proveedor</span><span class="sxs-lookup"><span data-stu-id="d7bdc-119">Set up a document cycle for each customer or vendor</span></span>
<span data-ttu-id="d7bdc-120">Puede especificar qué documentos estarán activos para un cliente o un proveedor específico.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-120">You can specify which documents are active for a specific customer or vendor.</span></span>

-   <span data-ttu-id="d7bdc-121">Para configurar un ciclo de documentos de ventas específico para un cliente, en la página **Todos los clientes**, seleccione un cliente.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-121">To set up a specific sales document cycle for a customer, on the **All customers** page, select a customer.</span></span> <span data-ttu-id="d7bdc-122">A continuación, haga clic en **Vender** &gt; **Configuración** &gt; **Ciclo de ventas** &gt; **Edición**.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-122">Then click **Sell** &gt; **Set up** &gt; **Sales cycle** &gt; **Edit**.</span></span>
-   <span data-ttu-id="d7bdc-123">Para configurar un ciclo de documentos de compra específico para un proveedor, en la página **Todos los proveedores**, seleccione un **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-123">To set up a specific purchase document cycle for a vendor, on the **All vendors** page, select a **Vendor**.</span></span> <span data-ttu-id="d7bdc-124">A continuación, haga clic en **Adquisición** &gt; **Configuración** &gt; **Ciclo de compra** &gt; **Edición**.</span><span class="sxs-lookup"><span data-stu-id="d7bdc-124">Then click **Procurement** &gt; **Set up** &gt; **Purchase cycle** &gt; **Edit**.</span></span>





