--- 
title: Crear una cuenta bancaria de proveedor
description: "Este procedimiento le muestra cómo crear una cuenta bancaria para un proveedor."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="73f2a-103">Crear una cuenta bancaria de proveedor</span><span class="sxs-lookup"><span data-stu-id="73f2a-103">Create a vendor bank account</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73f2a-104">Este procedimiento le muestra cómo crear una cuenta bancaria para un proveedor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="73f2a-105">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="73f2a-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="73f2a-106">Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="73f2a-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="73f2a-107">Seleccione el proveedor para el que desea crear una cuenta bancaria y, a continuación, haga clic en el vínculo del id. de la cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="73f2a-108">En el panel de acciones, haga clic en Proveedor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="73f2a-109">Haga clic en Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="73f2a-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="73f2a-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="73f2a-110">Click New.</span></span>
6. <span data-ttu-id="73f2a-111">En el campo Cuenta bancaria, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="73f2a-112">Este id. se utilizará para identificar la cuenta bancaria en el registro del proveedor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="73f2a-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="73f2a-114">En el campo Grupos de bancos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="73f2a-115">En el campo Tipo de número de ruta, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="73f2a-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="73f2a-116">Este es el tipo de número de ruta que se utiliza para los pagos internacionales.</span><span class="sxs-lookup"><span data-stu-id="73f2a-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="73f2a-117">En el campo Número de cuenta bancaria, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="73f2a-118">En el campo Código SWIFT, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="73f2a-119">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="73f2a-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="73f2a-120">El número IBAN debe estar en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="73f2a-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="73f2a-121">Por ejemplo, podría utilizar DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="73f2a-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="73f2a-122">El estado de la cuenta bancaria es Activo si se ha alcanzado la fecha activa y no se ha superado la Fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="73f2a-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="73f2a-123">También está activo si los campos Fecha de activación y Fecha de vencimiento están en blanco.</span><span class="sxs-lookup"><span data-stu-id="73f2a-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="73f2a-124">Si las fechas tanto del campo Fecha de activación como del campo Fecha de vencimiento son posteriores, los pagos electrónicos no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="73f2a-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="73f2a-125">Otros tipos de pago estarán disponibles y la cuenta bancaria estará activa.</span><span class="sxs-lookup"><span data-stu-id="73f2a-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="73f2a-126">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="73f2a-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="73f2a-127">En el campo Código de texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="73f2a-128">Este campo especifica un código que aparecerá en el extracto de cuenta del destinatario.</span><span class="sxs-lookup"><span data-stu-id="73f2a-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="73f2a-129">En el campo Mensaje para el banco, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="73f2a-130">En el campo Referencia de cambio, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="73f2a-131">Este es el número de referencia para cualquier tipo de cambio futuro o a plazo fijo.</span><span class="sxs-lookup"><span data-stu-id="73f2a-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="73f2a-132">En el campo Divisa, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="73f2a-133">Cuando se publican las validaciones de cuentas, esta sección proporciona una visión general de su estado (pendiente o aprobado).</span><span class="sxs-lookup"><span data-stu-id="73f2a-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="73f2a-134">Expanda la sección Dirección.</span><span class="sxs-lookup"><span data-stu-id="73f2a-134">Expand the Address section.</span></span>
19. <span data-ttu-id="73f2a-135">Expanda la sección Validaciones de cuentas.</span><span class="sxs-lookup"><span data-stu-id="73f2a-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="73f2a-136">Expanda la sección Información de contacto.</span><span class="sxs-lookup"><span data-stu-id="73f2a-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="73f2a-137">En el campo Teléfono, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73f2a-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="73f2a-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="73f2a-138">Close the page.</span></span>
23. <span data-ttu-id="73f2a-139">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="73f2a-139">Click Edit.</span></span>
24. <span data-ttu-id="73f2a-140">Expanda la sección Pago.</span><span class="sxs-lookup"><span data-stu-id="73f2a-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="73f2a-141">En el campo Cuenta bancaria, seleccione la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="73f2a-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="73f2a-142">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="73f2a-142">Click Save.</span></span>
    * <span data-ttu-id="73f2a-143">La dirección se puede heredar del grupo bancario, si se especifica uno, o se puede agregar aquí.</span><span class="sxs-lookup"><span data-stu-id="73f2a-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  


