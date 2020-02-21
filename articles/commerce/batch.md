---
title: Control mejorado de artículos con seguimiento por lotes
description: En este tema se describen las mejoras que se han realizado al control de los lotes para los artículos con seguimiento por lotes durante el proceso de registro de extracto.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: ecff18f0a34d22ef359f473fa6aaaff16c811bb6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004214"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="36b66-103">Control mejorado de artículos con seguimiento por lotes</span><span class="sxs-lookup"><span data-stu-id="36b66-103">Improved handling of batch-tracked items</span></span>


[!include [banner](includes/banner.md)]


<span data-ttu-id="36b66-104">En el punto de venta (PDV), no se pueden obtener los números de lotes para los artículos con seguimiento por lotes en el momento de la venta.</span><span class="sxs-lookup"><span data-stu-id="36b66-104">In Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="36b66-105">Sin embargo, para las configuraciones específicas, cuando se registran las ventas en las sedes a través del registro de extractos o pedidos de clientes, el sistema de Microsoft Dynamics espera que existan números de lotes válidos para artículos con seguimiento por lotes y que se usarán durante el proceso de facturación.</span><span class="sxs-lookup"><span data-stu-id="36b66-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="36b66-106">Si hay números de lotes válidos disponibles para los productos, el proceso de facturación de pedidos de clientes y el proceso de facturación de pedidos de ventas del registro de extractos los usan.</span><span class="sxs-lookup"><span data-stu-id="36b66-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="36b66-107">De lo contrario, el proceso de facturación de pedidos de clientes no puede registrar y el usuario del PDV recibe un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="36b66-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="36b66-108">El registro de extractos entra a continuación en un estado de error.</span><span class="sxs-lookup"><span data-stu-id="36b66-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="36b66-109">Este estado de error se produce cuando se ha activado inventario negativo para los productos.</span><span class="sxs-lookup"><span data-stu-id="36b66-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="36b66-110">Las mejoras que se han realizado en Retail versión 10.0.4 y posteriores ayudan a garantizar que, cuando se activa inventario negativo para artículos con seguimiento por lotes, no se bloquean la facturación de pedidos de clientes ni la facturación de pedidos de ventas a través del registro de extractos para esos artículos si el inventario es 0 (cero) o un número de lote no está disponible.</span><span class="sxs-lookup"><span data-stu-id="36b66-110">Improvements that have been made in Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="36b66-111">La nueva funcionalidad usa un id. de lote predeterminado para las líneas de ventas cuando los números de lotes no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="36b66-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="36b66-112">Para definir el id. de lote predeterminado que se usa para pedidos de cliente, en la página **Parámetros de Commerce**, en la pestaña **Pedidos de cliente**, en la ficha desplegable **Pedido**, establezca el campo de **Id. de lote predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="36b66-112">To define the default batch ID that is used for customer orders, on the **Commerce parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="36b66-113">Para definir el id. de lote predeterminado que se usa para facturación de pedidos de ventas a través del registro de extractos, en la página **Parámetros de Commerce**, en la pestaña **Registro**, en la ficha desplegable **Actualización del inventario**, establezca el campo de **id. de lote predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="36b66-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Commerce parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="36b66-114">Esta funcionalidad solo está disponible cuando el almacenamiento avanzado está activado para los artículos y el almacén de la tienda específicos.</span><span class="sxs-lookup"><span data-stu-id="36b66-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="36b66-115">En una versión posterior, la funcionalidad también se admitirá para escenarios donde no se use la gestión avanzada de almacenes.</span><span class="sxs-lookup"><span data-stu-id="36b66-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="36b66-116">La compatibilidad para el control mejorado de los artículos con seguimiento por lotes durante el registro de extractos para los escenarios no avanzados de gestión de almacenes se introdujo en Retail versión 10.0.5.</span><span class="sxs-lookup"><span data-stu-id="36b66-116">Support for improved handling of batch-tracked items during statement posting for non-advanced warehouse management scenarios was introduced in Retail version 10.0.5.</span></span>
