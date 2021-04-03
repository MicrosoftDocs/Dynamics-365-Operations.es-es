---
title: ER Generar documentos electrónicos para pagos con una configuración de formato
description: Este tema describe cómo usar una nueva configuración de formato de informes electrónicos (ER) para generar documentos electrónicos para el procesamiento de pagos.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6dd39b3faba90b38b837cd5167b216f9faa31d82
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570225"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a><span data-ttu-id="3a3ed-103">ER Generar documentos electrónicos para pagos con una configuración de formato</span><span class="sxs-lookup"><span data-stu-id="3a3ed-103">ER Generate electronic documents for payments using a format configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a3ed-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede usar una nueva configuración de formato de informes electrónicos para generar documentos electrónicos para procesar pagos.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="3a3ed-105">Estos pasos se pueden llevar a cabo en la empresa de muestra de GBSI.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="3a3ed-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación de una configuración con formato de documento de pago".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-106">To complete these steps, you must first complete the steps in the "Create a configuration with format of payment document" procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="3a3ed-107">Cambiar la configuración del método de pago electrónico</span><span class="sxs-lookup"><span data-stu-id="3a3ed-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="3a3ed-108">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="3a3ed-109">Alterne la sección de Formato de archivo para ampliarla, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="3a3ed-110">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3a3ed-111">Por ejemplo, filtre por el campo Forma de pago, por el valor "Electrónico".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="3a3ed-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-112">Click Edit.</span></span>
5. <span data-ttu-id="3a3ed-113">Establezca el campo de informes electrónicos generales en Sí.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="3a3ed-114">Seleccione Sí para usar el modelo de informes electrónicos generales para la generación de archivos de pago.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="3a3ed-115">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="3a3ed-116">Seleccione la configuración de formato BACS (ficticio Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="3a3ed-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="3a3ed-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-117">Click Save.</span></span>
9. <span data-ttu-id="3a3ed-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="3a3ed-119">Probar el formato de archivos de pago generados</span><span class="sxs-lookup"><span data-stu-id="3a3ed-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="3a3ed-120">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="3a3ed-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-121">Click New.</span></span>
3. <span data-ttu-id="3a3ed-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3a3ed-123">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="3a3ed-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3a3ed-125">Seleccione VendPay.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-125">Select VendPay.</span></span>  
6. <span data-ttu-id="3a3ed-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-126">Click Save.</span></span>
7. <span data-ttu-id="3a3ed-127">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-127">Click Lines.</span></span>
8. <span data-ttu-id="3a3ed-128">En el campo Empresa, escriba "DEMF".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="3a3ed-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="3a3ed-129">DEMF</span></span>  
9. <span data-ttu-id="3a3ed-130">En el campo Cuenta, especifique los valores "DE-01001".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="3a3ed-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="3a3ed-131">DE-01001</span></span>  
10. <span data-ttu-id="3a3ed-132">En el campo Descripción, escriba "Pago".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="3a3ed-133">Pago</span><span class="sxs-lookup"><span data-stu-id="3a3ed-133">Payment</span></span>  
11. <span data-ttu-id="3a3ed-134">En el campo Débito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="3a3ed-135">1000</span><span class="sxs-lookup"><span data-stu-id="3a3ed-135">1000</span></span>  
12. <span data-ttu-id="3a3ed-136">Haga clic en la ficha Pago.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="3a3ed-137">En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="3a3ed-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3a3ed-139">Seleccione el valor electrónico.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="3a3ed-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="3a3ed-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-141">Click Save.</span></span>
17. <span data-ttu-id="3a3ed-142">Haga clic en Generar pagos.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-142">Click Generate payments.</span></span>
18. <span data-ttu-id="3a3ed-143">En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="3a3ed-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3a3ed-145">Seleccione el valor electrónico.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="3a3ed-146">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3a3ed-147">Seleccione el valor electrónico.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="3a3ed-148">En el campo Nombre de archivo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="3a3ed-149">Por ejemplo, escriba "pagos".</span><span class="sxs-lookup"><span data-stu-id="3a3ed-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="3a3ed-150">En el campo Cuenta bancaria, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="3a3ed-151">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3a3ed-152">Seleccione el valor GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="3a3ed-153">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3a3ed-153">Click OK.</span></span>
25. <span data-ttu-id="3a3ed-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3a3ed-154">Click OK.</span></span>
    * <span data-ttu-id="3a3ed-155">Analice el archivo de pago creado en formato XML.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="3a3ed-156">Compárelo con el diseño de documento y los atributos de transacción de pago definidos.</span><span class="sxs-lookup"><span data-stu-id="3a3ed-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]