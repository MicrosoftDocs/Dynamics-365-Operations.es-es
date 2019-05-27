---
title: Crear una secuencia de cartas de cobro
description: Use esta guía de tarea para crear una secuencia de cartas de cobro.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db5264f6d8d7723ff01d13e99728c2bfebcb4515
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567453"
---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="f5f30-103">Crear una secuencia de cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="f5f30-103">Create a collection letter sequence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5f30-104">Use esta guía de tarea para crear una secuencia de cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="f5f30-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="f5f30-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f5f30-106">Vaya a Crédito y cobros > Configuración > Configurar secuencia de cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="f5f30-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f5f30-107">Click New.</span></span>
3. <span data-ttu-id="f5f30-108">En el campo Secuencia de la carta de cobro, especifique un identificador de secuencia que represente la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="f5f30-109">Se usará cuando se configure un perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="f5f30-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="f5f30-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f5f30-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="f5f30-111">Las condiciones de pago son opcionales.</span><span class="sxs-lookup"><span data-stu-id="f5f30-111">The terms of payment is optional.</span></span> <span data-ttu-id="f5f30-112">Si especifica un valor aquí, la factura de la cuota de la carta de cobro usará estas condiciones de pago, en lugar de las condiciones de pago almacenadas con el cliente.</span><span class="sxs-lookup"><span data-stu-id="f5f30-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="f5f30-113">En el campo del código de carta de cobro, seleccione el código para la primera carta de cobro que desee enviar.</span><span class="sxs-lookup"><span data-stu-id="f5f30-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="f5f30-114">La primera carta de cobro se crea de acuerdo con la fecha de vencimiento que figura en la factura, el valor especificado para el período de gracia en el campo Días en esta línea y otra información indicada en esta línea.</span><span class="sxs-lookup"><span data-stu-id="f5f30-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="f5f30-115">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f5f30-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="f5f30-116">La divisa de la cuota se establecerá por defecto en la divisa del cliente.</span><span class="sxs-lookup"><span data-stu-id="f5f30-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="f5f30-117">Este código de divisa puede ser diferente de la divisa de la factura.</span><span class="sxs-lookup"><span data-stu-id="f5f30-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="f5f30-118">Haga clic en Agregar para agregar la siguiente carta de cobro que se enviará en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="f5f30-119">En muchos casos, la primera carta de cobro es solo una advertencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="f5f30-120">Puede agregar cuotas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f5f30-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="f5f30-121">En el campo del código de carta de cobro, seleccione la siguiente carta de cobro que se enviará en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="f5f30-122">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f5f30-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="f5f30-123">En el campo de la cuenta principal, seleccione la cuenta de ingresos que se usará para las cuotas.</span><span class="sxs-lookup"><span data-stu-id="f5f30-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="f5f30-124">Especifique la cuota que se cobrará cuando se registre esta carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="f5f30-125">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f5f30-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="f5f30-126">Seleccione un grupo de impuestos de artículo si se deben calcular impuestos en la cuota.</span><span class="sxs-lookup"><span data-stu-id="f5f30-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="f5f30-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f5f30-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="f5f30-128">Escriba el saldo vencido mínimo necesario antes de enviar una carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="f5f30-129">Escriba el número de días de gracia que se permitirán.</span><span class="sxs-lookup"><span data-stu-id="f5f30-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="f5f30-130">Este es el número de días después de la fecha de vencimiento en el que se puede generar una carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="f5f30-131">La fecha de vencimiento que se usa para el cálculo depende del puesto de la carta de cobro en la secuencia de cartas de cobro:  ⦁  El período de gracia para la carta de cobro 1 es relativo a la fecha de vencimiento de la factura.</span><span class="sxs-lookup"><span data-stu-id="f5f30-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="f5f30-132">⦁ El período de gracia para las cartas de cobro 2 y superiores depende de la fecha en que la carta de cobro anterior se haya registrado o impreso, en función de la selección en el campo Actualizar código de carta de cobro en la página Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="f5f30-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="f5f30-133">Haga clic en Agregar para agregar la última carta de cobro en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="f5f30-134">Puede agregar hasta cinco códigos de cartas de cobro para la secuencia de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="f5f30-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="f5f30-135">En el campo del código de carta de cobro, seleccione la siguiente carta de cobro que se enviará en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5f30-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="f5f30-136">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f5f30-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="f5f30-137">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="f5f30-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="f5f30-138">En el campo Cuota en divisa, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="f5f30-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="f5f30-139">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f5f30-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="f5f30-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f5f30-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="f5f30-141">Especifique un número en el campo Saldo vencido mínimo.</span><span class="sxs-lookup"><span data-stu-id="f5f30-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="f5f30-142">En el campo Días, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="f5f30-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="f5f30-143">Seleccione esta casilla de verificación para detener otras entregas y facturas adicionales por parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="f5f30-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="f5f30-144">Para desbloquear la cuenta, seleccione No en el campo Facturación y entrega en espera en la página Clientes.</span><span class="sxs-lookup"><span data-stu-id="f5f30-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="f5f30-145">Expanda la ficha desplegable Nota.</span><span class="sxs-lookup"><span data-stu-id="f5f30-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="f5f30-146">Especifique el texto tal como desea que aparezca en la carta de cobro para el código de carta de cobro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f5f30-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="f5f30-147">Puede traducir este texto a varios idiomas mediante el menú Traducciones encima del cuadro de nota.</span><span class="sxs-lookup"><span data-stu-id="f5f30-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  

