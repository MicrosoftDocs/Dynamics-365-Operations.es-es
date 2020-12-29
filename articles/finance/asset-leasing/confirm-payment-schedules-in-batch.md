---
title: Confirmar programaciones de pago de arrendamiento de activos en un lote
description: Este tema explica cómo confirmar varias programaciones de pago en un lote.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447807"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="4e86f-103">Confirmar programaciones de pago de arrendamiento de activos en un lote</span><span class="sxs-lookup"><span data-stu-id="4e86f-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e86f-104">Este tema explica cómo confirmar varias programaciones de pago en un lote.</span><span class="sxs-lookup"><span data-stu-id="4e86f-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="4e86f-105">Los programas de pago se confirman en forma de arrendamiento a arrendamiento o mediante el proceso de confirmación por lotes.</span><span class="sxs-lookup"><span data-stu-id="4e86f-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="4e86f-106">Un movimiento de diario solo se puede registrar frente a un arrendamiento que tenga una programación de pagos confirmada.</span><span class="sxs-lookup"><span data-stu-id="4e86f-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="4e86f-107">La confirmación de la programación de pagos sirve como aprobación final de la información financiera para el arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="4e86f-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="4e86f-108">Todos los cambios futuros en la información financiera del arrendamiento, como los pagos y el plazo del arrendamiento, constituyen un ajuste del arrendamiento y deben procesarse de esa manera.</span><span class="sxs-lookup"><span data-stu-id="4e86f-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="4e86f-109">Para confirmar varias programaciones de pago, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4e86f-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="4e86f-110">Vaya a **Arrendamiento de activos \> Periódico \> Lote de confirmación**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="4e86f-111">En la página **Lote de confirmación**, seleccione **Lote de confirmación**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="4e86f-112">En el cuadro de diálogo que aparece, filtre según los libros que desea confirmar.</span><span class="sxs-lookup"><span data-stu-id="4e86f-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="4e86f-113">Para confirmar todos los libros en un grupo de arrendamiento específico, seleccione el grupo en el campo **Grupo de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="4e86f-114">Para confirmar libros específicos, seleccione los libros en el campo **Id. del libro**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="4e86f-115">Para confirmar todos los libros, active el parámetro **Para todos los libros**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="4e86f-116">La información de los libros recién confirmados se muestra en la página **Libros confirmados**.</span><span class="sxs-lookup"><span data-stu-id="4e86f-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="4e86f-117">Una vez confirmadas las programaciones de pago, los asientos de diario de reconocimiento inicial se pueden contabilizar frente a los arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="4e86f-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
