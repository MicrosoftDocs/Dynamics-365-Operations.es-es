---
title: Ajuste de valores de coste de inventario disponible
description: Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2417a278e58f4309873ab4d33b0d1f1686081951
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "335172"
---
# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="aa0b8-103">Ajuste de valores de coste de inventario disponible</span><span class="sxs-lookup"><span data-stu-id="aa0b8-103">Adjust on-hand inventory cost values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa0b8-104">Use la página Ajuste del inventario disponible para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="aa0b8-105">Puede usar la página **Ajuste del inventario disponible** para ajustar el valor de coste de las cantidades de inventario disponible después de efectuar un cierre de inventario.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="aa0b8-106">**Nota**: para abrir la página **Ajuste del inventario disponible**, en la página **Cierre y ajuste**, seleccione el registro de un proceso de cierre de inventario finalizado y haga clic en **Ajuste** &gt; **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="aa0b8-107">**Ejemplo:** Tiene las siguientes transacciones en febrero:</span><span class="sxs-lookup"><span data-stu-id="aa0b8-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="aa0b8-108">1 de febrero: recepción financiera de inventario para una cantidad de 2 a un coste de 10,00 USD</span><span class="sxs-lookup"><span data-stu-id="aa0b8-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="aa0b8-109">5 de febrero: una recepción financiera de inventario para una cantidad de 1 a un coste de 13,00 USD</span><span class="sxs-lookup"><span data-stu-id="aa0b8-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="aa0b8-110">19 de febrero: una emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 11,00</span><span class="sxs-lookup"><span data-stu-id="aa0b8-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="aa0b8-111">Este artículo se ha configurado con el modelo de inventario FIFO, y el cierre de inventario se ha efectuado con fecha de 28 de febrero.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="aa0b8-112">La transacción de emisión financiera de 11,00 USD se liquidará con la recepción financiera del 1 de febrero, y se efectuará un ajuste de 1,00 USD.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="aa0b8-113">Las siguientes recepciones de inventario contendrán cantidades de inventario abiertas:</span><span class="sxs-lookup"><span data-stu-id="aa0b8-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="aa0b8-114">1 de febrero: una cantidad de 1 a un coste de 10,00 dólares</span><span class="sxs-lookup"><span data-stu-id="aa0b8-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="aa0b8-115">5 de febrero: una cantidad de 1 a un coste de 13,00 dólares</span><span class="sxs-lookup"><span data-stu-id="aa0b8-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="aa0b8-116">Para definir el coste de estos dos artículos en 15,00 USD, utilice la opción de ajuste disponible para ajustar las cantidades abiertas disponibles como del último período de cierre del inventario.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="aa0b8-117">**Nota**: la fecha de contabilización de la transacción de ajuste disponible será la fecha del último cierre de inventario.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="aa0b8-118">Este valor de fecha no se podrá modificar.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-118">This date can't be modified.</span></span>
