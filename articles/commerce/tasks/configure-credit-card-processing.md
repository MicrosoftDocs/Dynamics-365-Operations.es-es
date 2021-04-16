---
title: Configurar el procesamiento de tarjeta de crédito
description: Este procedimiento muestra cómo ver la lista de proveedores de pago y cómo configurar una cuenta de pago para clientes.
author: jashanno
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13aa59ab1c6b0170ae9ab8972fb00bcf47e2b754
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789765"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="26645-103">Configurar el procesamiento de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="26645-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26645-104">Este procedimiento muestra cómo ver la lista de proveedores de pago y cómo configurar una cuenta de pago para clientes.</span><span class="sxs-lookup"><span data-stu-id="26645-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="26645-105">Este procedimiento usa la empresa USRT en datos de demostración y está pensado para administradores y profesionales de TI.</span><span class="sxs-lookup"><span data-stu-id="26645-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="26645-106">Ver una lista de proveedores de pago</span><span class="sxs-lookup"><span data-stu-id="26645-106">View a list of payment providers</span></span>
1. <span data-ttu-id="26645-107">Vaya a Clientes > Configuración de pagos > Servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="26645-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="26645-108">Haga clic en Ver proveedores disponibles.</span><span class="sxs-lookup"><span data-stu-id="26645-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="26645-109">Configurar cuenta de pago</span><span class="sxs-lookup"><span data-stu-id="26645-109">Configure payment account</span></span>
1. <span data-ttu-id="26645-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="26645-110">Click New.</span></span>
2. <span data-ttu-id="26645-111">En el campo Servicio de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="26645-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="26645-112">En el campo Conector de pago, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="26645-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="26645-113">Expanda la sección Cuenta de servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="26645-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="26645-114">En el campo Entorno:, escriba "PROD".</span><span class="sxs-lookup"><span data-stu-id="26645-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="26645-115">Haga clic en Tipos de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="26645-115">Click Credit card types.</span></span>
7. <span data-ttu-id="26645-116">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="26645-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="26645-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26645-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="26645-118">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="26645-118">Click Add.</span></span>
10. <span data-ttu-id="26645-119">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="26645-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="26645-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="26645-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="26645-121">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="26645-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="26645-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26645-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="26645-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="26645-123">Click Add.</span></span>
15. <span data-ttu-id="26645-124">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="26645-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="26645-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="26645-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="26645-126">Puede repetir estos pasos para tantos tipos de tarjeta como necesite.</span><span class="sxs-lookup"><span data-stu-id="26645-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="26645-127">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="26645-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="26645-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26645-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="26645-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="26645-129">Click Add.</span></span>
20. <span data-ttu-id="26645-130">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="26645-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="26645-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="26645-131">Click Save.</span></span>
22. <span data-ttu-id="26645-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="26645-132">Close the page.</span></span>
23. <span data-ttu-id="26645-133">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="26645-133">Click Validate.</span></span>
24. <span data-ttu-id="26645-134">Haga clic en la casilla Procesador predeterminado para tarjetas de crédito nuevas.</span><span class="sxs-lookup"><span data-stu-id="26645-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="26645-135">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="26645-135">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]