---
title: CE Diseñar el modelo de datos específico de dominio
description: En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7882a7a17f5736d9d5a11cd91ac963fa89ff12f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042905"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="d5179-103">CE Diseñar el modelo de datos específico de dominio</span><span class="sxs-lookup"><span data-stu-id="d5179-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5179-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="d5179-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="d5179-105">Este modelo de datos se usará posteriormente como origen de datos al crear el formato de los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="d5179-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="d5179-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="d5179-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="d5179-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="d5179-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="d5179-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="d5179-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="d5179-109">Seleccione el proveedor de configuración de la empresa de ejemplo, "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="d5179-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="d5179-110">Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="d5179-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
    
2. <span data-ttu-id="d5179-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="d5179-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="d5179-112">Creará una configuración que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="d5179-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="d5179-113">Este modelo de datos se usará posteriormente como origen de datos cuando cree el formato para los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="d5179-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="d5179-114">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="d5179-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="d5179-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="d5179-116">En el campo Nombre, escriba Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="d5179-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="d5179-117">En el campo Descripción, escriba Configuración del modelo de pago.</span><span class="sxs-lookup"><span data-stu-id="d5179-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="d5179-118">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="d5179-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="d5179-119">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="d5179-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="d5179-120">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="d5179-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="d5179-121">Haga clic en el botón Crear configuración para completar la tarea de creación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="d5179-121">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="d5179-122">Creación de un modelo de datos</span><span class="sxs-lookup"><span data-stu-id="d5179-122">Create a data model</span></span>
<span data-ttu-id="d5179-123">Usted está creando un nuevo modelo de datos para la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d5179-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="d5179-124">Esta versión de la configuración tendrá un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="d5179-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="d5179-125">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="d5179-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="d5179-126">Definición de la estructura de una parte que participa en un proceso de pago</span><span class="sxs-lookup"><span data-stu-id="d5179-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="d5179-127">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5179-128">Escriba "Parte" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="d5179-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="d5179-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-129">Click Add.</span></span>
4. <span data-ttu-id="d5179-130">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="d5179-131">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="d5179-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="d5179-132">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="d5179-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="d5179-133">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-133">Click Add.</span></span>
8. <span data-ttu-id="d5179-134">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="d5179-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="d5179-135">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="d5179-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="d5179-136">Definición de la estructura bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="d5179-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="d5179-137">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5179-138">En el campo Nombre, escriba "Agente".</span><span class="sxs-lookup"><span data-stu-id="d5179-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="d5179-139">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="d5179-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="d5179-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-140">Click Add.</span></span>
5. <span data-ttu-id="d5179-141">En el campo Descripción, escriba "Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedeor).</span><span class="sxs-lookup"><span data-stu-id="d5179-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="d5179-142">Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedor).</span><span class="sxs-lookup"><span data-stu-id="d5179-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="d5179-143">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="d5179-144">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="d5179-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="d5179-145">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="d5179-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="d5179-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-146">Click Add.</span></span>
10. <span data-ttu-id="d5179-147">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="d5179-148">En el campo Nombre, escriba "SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="d5179-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="d5179-149">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-149">Click Add.</span></span>
13. <span data-ttu-id="d5179-150">En el campo Descripción, escriba un "código de identificación del Banco".</span><span class="sxs-lookup"><span data-stu-id="d5179-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="d5179-151">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="d5179-152">En el campo Nombre, especifique "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="d5179-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="d5179-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-153">Click Add.</span></span>
17. <span data-ttu-id="d5179-154">En el campo Descripción, especifique un "Número de ruta".</span><span class="sxs-lookup"><span data-stu-id="d5179-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="d5179-155">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="d5179-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="d5179-156">Definición de la cuenta bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="d5179-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="d5179-157">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5179-158">En el campo Nombre, escriba "Cuenta".</span><span class="sxs-lookup"><span data-stu-id="d5179-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="d5179-159">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="d5179-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="d5179-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-160">Click Add.</span></span>
5. <span data-ttu-id="d5179-161">En el campo Descripción, escriba "Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco)".</span><span class="sxs-lookup"><span data-stu-id="d5179-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="d5179-162">Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco).</span><span class="sxs-lookup"><span data-stu-id="d5179-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="d5179-163">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="d5179-164">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="d5179-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="d5179-165">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="d5179-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="d5179-166">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-166">Click Add.</span></span>
10. <span data-ttu-id="d5179-167">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="d5179-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="d5179-168">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="d5179-169">En el campo Nombre, escriba "Número".</span><span class="sxs-lookup"><span data-stu-id="d5179-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="d5179-170">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-170">Click Add.</span></span>
14. <span data-ttu-id="d5179-171">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="d5179-172">En el campo Nombre, escriba "IBAN".</span><span class="sxs-lookup"><span data-stu-id="d5179-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="d5179-173">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-173">Click Add.</span></span>
17. <span data-ttu-id="d5179-174">En el campo descripción, escriba "Número de cuenta bancaria internacional".</span><span class="sxs-lookup"><span data-stu-id="d5179-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="d5179-175">Definición de la estructura del mensaje de pago para el tipo de pago de transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="d5179-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="d5179-176">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5179-177">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="d5179-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="d5179-178">En el campo Nombre, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="d5179-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="d5179-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-179">Click Add.</span></span>
5. <span data-ttu-id="d5179-180">En el campo Buscar, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="d5179-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="d5179-181">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="d5179-181">Click Find previous.</span></span>
7. <span data-ttu-id="d5179-182">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="d5179-183">En el campo Nombre, escriba "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="d5179-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="d5179-184">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-184">Click Add.</span></span>
10. <span data-ttu-id="d5179-185">En el campo Descripción, escriba "La referencia punto a punto asignada por la parte ordenante (y enviada a la siguiente parte) para identificar un mensaje".</span><span class="sxs-lookup"><span data-stu-id="d5179-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="d5179-186">La referencia punto a punto asignada por la parte ordenante (y que se envía a la siguiente parte) para identificar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d5179-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="d5179-187">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="d5179-188">En el campo Nombre, escriba "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="d5179-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="d5179-189">En el campo Tipo de artículo, seleccione DateTime.</span><span class="sxs-lookup"><span data-stu-id="d5179-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="d5179-190">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-190">Click Add.</span></span>
15. <span data-ttu-id="d5179-191">En el campo Descripción, escriba "Fecha y hora de creación del mensaje de pago".</span><span class="sxs-lookup"><span data-stu-id="d5179-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="d5179-192">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="d5179-193">Definición de la estructura de transacción de pago para este modelo.</span><span class="sxs-lookup"><span data-stu-id="d5179-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="d5179-194">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="d5179-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="d5179-195">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="d5179-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="d5179-196">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-196">Click Add.</span></span>
20. <span data-ttu-id="d5179-197">En el campo Descripción, especifique Líneas de pago del mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="d5179-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="d5179-198">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="d5179-199">En el campo Nombre, escriba "Acreedor".</span><span class="sxs-lookup"><span data-stu-id="d5179-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="d5179-200">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="d5179-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="d5179-201">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-201">Click Add.</span></span>
25. <span data-ttu-id="d5179-202">En el campo Descripción, escriba "Parte a la que se debe una suma de dinero".</span><span class="sxs-lookup"><span data-stu-id="d5179-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="d5179-203">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="d5179-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="d5179-204">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="d5179-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="d5179-205">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5179-205">Click Find next.</span></span>
29. <span data-ttu-id="d5179-206">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d5179-206">Click OK.</span></span>
30. <span data-ttu-id="d5179-207">En el campo Buscar, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="d5179-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="d5179-208">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5179-208">Click Find next.</span></span>
32. <span data-ttu-id="d5179-209">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="d5179-210">En el campo Nombre, escriba "Deudor".</span><span class="sxs-lookup"><span data-stu-id="d5179-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="d5179-211">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-211">Click Add.</span></span>
35. <span data-ttu-id="d5179-212">En el campo Descripción, escriba "Parte que adeuda una suma de dinero al (último) acreedor".</span><span class="sxs-lookup"><span data-stu-id="d5179-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="d5179-213">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="d5179-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="d5179-214">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="d5179-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="d5179-215">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5179-215">Click Find next.</span></span>
39. <span data-ttu-id="d5179-216">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d5179-216">Click OK.</span></span>
40. <span data-ttu-id="d5179-217">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5179-217">Click Find next.</span></span>
41. <span data-ttu-id="d5179-218">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="d5179-219">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="d5179-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="d5179-220">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="d5179-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="d5179-221">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-221">Click Add.</span></span>
45. <span data-ttu-id="d5179-222">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="d5179-223">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="d5179-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="d5179-224">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-224">Click Add.</span></span>
48. <span data-ttu-id="d5179-225">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="d5179-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="d5179-226">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="d5179-227">En el campo Nombre, escriba "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="d5179-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="d5179-228">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="d5179-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="d5179-229">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-229">Click Add.</span></span>
53. <span data-ttu-id="d5179-230">En el campo Descripción, escriba una "Fecha de transacción".</span><span class="sxs-lookup"><span data-stu-id="d5179-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="d5179-231">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="d5179-232">En el campo Nombre, escriba "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="d5179-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="d5179-233">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="d5179-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="d5179-234">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-234">Click Add.</span></span>
58. <span data-ttu-id="d5179-235">En el campo Descripción, escriba "La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos".</span><span class="sxs-lookup"><span data-stu-id="d5179-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="d5179-236">El importe se debe expresar en la divisa solicitada por la parte iniciadora."</span><span class="sxs-lookup"><span data-stu-id="d5179-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="d5179-237">La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos.</span><span class="sxs-lookup"><span data-stu-id="d5179-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="d5179-238">El importe se debe expresar en la divisa solicitada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="d5179-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="d5179-239">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5179-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="d5179-240">En el campo Nombre, escriba "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="d5179-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="d5179-241">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="d5179-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="d5179-242">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d5179-242">Click Add.</span></span>
63. <span data-ttu-id="d5179-243">En el campo Descripción, escriba "La identificación única asignada por la parte iniciadora".</span><span class="sxs-lookup"><span data-stu-id="d5179-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="d5179-244">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo".</span><span class="sxs-lookup"><span data-stu-id="d5179-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="d5179-245">En el campo Nombre, especifique "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="d5179-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="d5179-246">El nombre del modelo de pago se alinea con las interfaces predefinidas de los formularios de pago.</span><span class="sxs-lookup"><span data-stu-id="d5179-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="d5179-247">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d5179-247">Click Save.</span></span>
66. <span data-ttu-id="d5179-248">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d5179-248">Close the page.</span></span>

