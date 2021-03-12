---
title: Configurar el procesamiento de tarjeta de crédito
description: Este procedimiento muestra cómo ver la lista de proveedores de pago y cómo configurar una cuenta de pago para clientes.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 611cc49d2373247da141d2fafc149d05f3bd13b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006119"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="965dc-103">Configurar el procesamiento de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="965dc-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="965dc-104">Este procedimiento muestra cómo ver la lista de proveedores de pago y cómo configurar una cuenta de pago para clientes.</span><span class="sxs-lookup"><span data-stu-id="965dc-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="965dc-105">Este procedimiento usa la empresa USRT en datos de demostración y está pensado para administradores y profesionales de TI.</span><span class="sxs-lookup"><span data-stu-id="965dc-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="965dc-106">Ver una lista de proveedores de pago</span><span class="sxs-lookup"><span data-stu-id="965dc-106">View a list of payment providers</span></span>
1. <span data-ttu-id="965dc-107">Vaya a Clientes > Configuración de pagos > Servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="965dc-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="965dc-108">Haga clic en Ver proveedores disponibles.</span><span class="sxs-lookup"><span data-stu-id="965dc-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="965dc-109">Configurar cuenta de pago</span><span class="sxs-lookup"><span data-stu-id="965dc-109">Configure payment account</span></span>
1. <span data-ttu-id="965dc-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="965dc-110">Click New.</span></span>
2. <span data-ttu-id="965dc-111">En el campo Servicio de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="965dc-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="965dc-112">En el campo Conector de pago, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="965dc-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="965dc-113">Expanda la sección Cuenta de servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="965dc-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="965dc-114">En el campo Entorno:, escriba "PROD".</span><span class="sxs-lookup"><span data-stu-id="965dc-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="965dc-115">Haga clic en Tipos de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="965dc-115">Click Credit card types.</span></span>
7. <span data-ttu-id="965dc-116">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="965dc-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="965dc-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="965dc-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="965dc-118">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="965dc-118">Click Add.</span></span>
10. <span data-ttu-id="965dc-119">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="965dc-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="965dc-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="965dc-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="965dc-121">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="965dc-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="965dc-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="965dc-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="965dc-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="965dc-123">Click Add.</span></span>
15. <span data-ttu-id="965dc-124">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="965dc-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="965dc-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="965dc-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="965dc-126">Puede repetir estos pasos para tantos tipos de tarjeta como necesite.</span><span class="sxs-lookup"><span data-stu-id="965dc-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="965dc-127">En el campo Diario de pagos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="965dc-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="965dc-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="965dc-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="965dc-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="965dc-129">Click Add.</span></span>
20. <span data-ttu-id="965dc-130">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="965dc-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="965dc-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="965dc-131">Click Save.</span></span>
22. <span data-ttu-id="965dc-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="965dc-132">Close the page.</span></span>
23. <span data-ttu-id="965dc-133">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="965dc-133">Click Validate.</span></span>
24. <span data-ttu-id="965dc-134">Haga clic en la casilla Procesador predeterminado para tarjetas de crédito nuevas.</span><span class="sxs-lookup"><span data-stu-id="965dc-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="965dc-135">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="965dc-135">Click Save.</span></span>

