---
title: Configuración de firmas electrónicas
description: Sírvase de este procedimiento para configurar firmas electrónicas.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eb6bf529b1e94d598e219482f182140402f2928a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "318589"
---
# <a name="set-up-electronic-signatures"></a><span data-ttu-id="73c42-103">Configuración de firmas electrónicas</span><span class="sxs-lookup"><span data-stu-id="73c42-103">Set up electronic signatures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73c42-104">Sírvase de este procedimiento para configurar firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="73c42-104">Use this procedure to set up electronic signatures.</span></span> <span data-ttu-id="73c42-105">Una firma electrónica confirma la identidad de una persona que va a comenzar o aprobar un proceso informático.</span><span class="sxs-lookup"><span data-stu-id="73c42-105">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="73c42-106">La empresa de datos de demostración utilizada para crear este procedimiento es DAT.</span><span class="sxs-lookup"><span data-stu-id="73c42-106">The demo data company used to create this procedure is DAT.</span></span>


## <a name="enable-the-electronic-signature-configuration-key"></a><span data-ttu-id="73c42-107">Activación de la clave de configuración de firma electrónica</span><span class="sxs-lookup"><span data-stu-id="73c42-107">Enable the Electronic signature configuration key</span></span>
1. <span data-ttu-id="73c42-108">Vaya a Administración del sistema > Configuración > Configuración de licencias.</span><span class="sxs-lookup"><span data-stu-id="73c42-108">Go to System administration > Setup > License configuration.</span></span>
2. <span data-ttu-id="73c42-109">En el árbol, expanda Administración.</span><span class="sxs-lookup"><span data-stu-id="73c42-109">In the tree, expand 'Administration'.</span></span>
    * <span data-ttu-id="73c42-110">Compruebe que se haya seleccionado la casilla Firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="73c42-110">Verify that the Electronic signature check box is selected.</span></span>  
    * <span data-ttu-id="73c42-111">Si la casilla Firma electrónica no está activada, debe activar el modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="73c42-111">If the Electronic signature check box is not selected, you must enable maintenance mode.</span></span> <span data-ttu-id="73c42-112">Para habilitar el modo de mantenimiento en este entorno, ejecute el trabajo de mantenimiento desde Lifecycle Services o use la herramienta Deployment.Setup de manera local.</span><span class="sxs-lookup"><span data-stu-id="73c42-112">Maintenance mode can be enabled in this environment by running a maintenance job from Lifecycle Services, or by using the Deployment.Setup tool locally.</span></span>  
3. <span data-ttu-id="73c42-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="73c42-113">Close the page.</span></span>

## <a name="set-up-electronic-signature-parameters"></a><span data-ttu-id="73c42-114">Configuración de parámetros de firma electrónica</span><span class="sxs-lookup"><span data-stu-id="73c42-114">Set up electronic signature parameters</span></span>
1. <span data-ttu-id="73c42-115">Vaya a Administración de la organización > Configuración > Firma electrónica > Parámetros de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="73c42-115">Go to Organization administration > Setup > Electronic signature > Electronic signature parameters.</span></span>
2. <span data-ttu-id="73c42-116">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="73c42-116">Click Edit.</span></span>
3. <span data-ttu-id="73c42-117">En el campo Aviso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73c42-117">In the Notice field, type a value.</span></span>
    * <span data-ttu-id="73c42-118">Escriba el aviso que recibirán los firmantes cuando se requiera una firma.</span><span class="sxs-lookup"><span data-stu-id="73c42-118">Enter the notice that signers will receive when a signature is requested.</span></span> <span data-ttu-id="73c42-119">Puede escribir el texto que desee.</span><span class="sxs-lookup"><span data-stu-id="73c42-119">You can enter any text.</span></span> <span data-ttu-id="73c42-120">Normalmente, este texto le explica al usuario lo que quiere decir firmar un documento electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="73c42-120">Typically, this text tells the user what it means to sign a document electronically.</span></span>  
    * <span data-ttu-id="73c42-121">Si desea escribir el texto del aviso en otros idiomas, haga clic en el botón Traducciones.</span><span class="sxs-lookup"><span data-stu-id="73c42-121">If you want to enter the Notice text in additional languages, click the Translations button.</span></span>  
4. <span data-ttu-id="73c42-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="73c42-122">Click Save.</span></span>
5. <span data-ttu-id="73c42-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="73c42-123">Close the page.</span></span>

## <a name="set-up-reason-codes-for-electronic-signatures"></a><span data-ttu-id="73c42-124">Configuración de códigos de motivo para firmas electrónicas</span><span class="sxs-lookup"><span data-stu-id="73c42-124">Set up reason codes for electronic signatures</span></span>
1. <span data-ttu-id="73c42-125">Vaya a Administración de la organización > Configuración > Firma electrónica > Códigos de motivo de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="73c42-125">Go to Organization administration > Setup > Electronic signature > Electronic signature reason codes.</span></span>
2. <span data-ttu-id="73c42-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="73c42-126">Click New.</span></span>
    * <span data-ttu-id="73c42-127">Debe configurar códigos de motivo antes de usar las firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="73c42-127">You must set up reason codes before using electronic signatures.</span></span> <span data-ttu-id="73c42-128">Se requerirá un código de motivo válido cuando se firme un documento.</span><span class="sxs-lookup"><span data-stu-id="73c42-128">A valid reason code is required when signing a document.</span></span>     <span data-ttu-id="73c42-129">Un firmante selecciona un código de motivo para indicar el propósito de una firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="73c42-129">A signer selects a reason code to indicate the purpose of an electronic signature.</span></span> <span data-ttu-id="73c42-130">Por ejemplo, un código de motivo se podría usar para indicar la aprobación legal.</span><span class="sxs-lookup"><span data-stu-id="73c42-130">For example, a reason code could be used to indicate legal approval.</span></span>  
3. <span data-ttu-id="73c42-131">En el campo Código de motivo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73c42-131">In the Reason code field, type a value.</span></span>
4. <span data-ttu-id="73c42-132">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="73c42-132">In the Description field, type a value.</span></span>
    * <span data-ttu-id="73c42-133">Especifique códigos de motivo adicionales, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="73c42-133">Enter additional reason codes, if needed.</span></span>  
5. <span data-ttu-id="73c42-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="73c42-134">Click Save.</span></span>
6. <span data-ttu-id="73c42-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="73c42-135">Close the page.</span></span>

## <a name="require-electronic-signatures-for-existing-processes"></a><span data-ttu-id="73c42-136">Obligación de usar firmas electrónicas para procesos existentes</span><span class="sxs-lookup"><span data-stu-id="73c42-136">Require electronic signatures for existing processes</span></span>
1. <span data-ttu-id="73c42-137">Vaya a Administración de la organización > Configuración > Firma electrónica > Requisitos de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="73c42-137">Go to Organization administration > Setup > Electronic signature > Electronic signature requirements.</span></span>
2. <span data-ttu-id="73c42-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="73c42-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="73c42-139">Seleccione un proceso que requiera firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="73c42-139">Select a process that requires electronic signatures.</span></span>  
3. <span data-ttu-id="73c42-140">Active o desactive la casilla de verificación Se requiere firma.</span><span class="sxs-lookup"><span data-stu-id="73c42-140">Select or clear the Signature required check box.</span></span>
    * <span data-ttu-id="73c42-141">Repita estos pasos para cada proceso que requiera firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="73c42-141">Repeat these steps for each process that requires electronic signatures.</span></span>  
4. <span data-ttu-id="73c42-142">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="73c42-142">Click Save.</span></span>

## <a name="create-a-custom-requirement-for-electronic-signatures"></a><span data-ttu-id="73c42-143">Creación de un requisito personalizado para firmas electrónicas</span><span class="sxs-lookup"><span data-stu-id="73c42-143">Create a custom requirement for electronic signatures</span></span>
1. <span data-ttu-id="73c42-144">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="73c42-144">Click New.</span></span>
2. <span data-ttu-id="73c42-145">Active o desactive la casilla de verificación Se requiere firma.</span><span class="sxs-lookup"><span data-stu-id="73c42-145">Select or clear the Signature required check box.</span></span>
3. <span data-ttu-id="73c42-146">En el campo Nombre, especifique un nombre para el proceso que requiera firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="73c42-146">In the Name field, enter a name for the process that requires electronic signatures.</span></span>
4. <span data-ttu-id="73c42-147">En el campo Nombre de tabla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="73c42-147">In the Table name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="73c42-148">En la lista, localice y seleccione la tabla donde se almacenan los datos que deben firmarse.</span><span class="sxs-lookup"><span data-stu-id="73c42-148">In the list, find and select the table where the data that must be signed is stored.</span></span>
6. <span data-ttu-id="73c42-149">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="73c42-149">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="73c42-150">En el campo Nombre de campo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="73c42-150">In the Field name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="73c42-151">En la lista, localice y seleccione el campo de la tabla que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="73c42-151">In the list, find and select the field in the table that you want to monitor.</span></span>
9. <span data-ttu-id="73c42-152">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="73c42-152">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="73c42-153">Indique cuando se requiere una firma.</span><span class="sxs-lookup"><span data-stu-id="73c42-153">Specify when a signature is required.</span></span>     <span data-ttu-id="73c42-154">Seleccione Siempre si se requiere una firma cada vez que se modifican los datos en el campo.</span><span class="sxs-lookup"><span data-stu-id="73c42-154">Select Always if a signature is required when the data in the field changes.</span></span>     <span data-ttu-id="73c42-155">Seleccione Sólo si solo se requiere una firma en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="73c42-155">Select Only if a signature is required only under certain conditions.</span></span> <span data-ttu-id="73c42-156">Si selecciona Sólo, también debe seleccionar una de las siguientes opciones: Al insertar un registro, Al actualizar un registro o Al eliminar un registro.</span><span class="sxs-lookup"><span data-stu-id="73c42-156">If you select Only, you must also select one of the following options: When a record is inserted, When a record is updated, or When a record is deleted.</span></span>  
10. <span data-ttu-id="73c42-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="73c42-157">Click Save.</span></span>
11. <span data-ttu-id="73c42-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="73c42-158">Close the page.</span></span>

