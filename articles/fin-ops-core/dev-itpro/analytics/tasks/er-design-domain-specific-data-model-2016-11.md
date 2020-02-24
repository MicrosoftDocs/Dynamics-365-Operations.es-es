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
ms.openlocfilehash: 3fe08b30977b8515ffd8d0acc1fd8f4b3085de93
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026095"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="db61f-103">CE Diseñar el modelo de datos específico de dominio</span><span class="sxs-lookup"><span data-stu-id="db61f-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db61f-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="db61f-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="db61f-105">Este modelo de datos se usará posteriormente como origen de datos al crear el formato de los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="db61f-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="db61f-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="db61f-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="db61f-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="db61f-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="db61f-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="db61f-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="db61f-109">Seleccione el proveedor de configuración de la empresa de ejemplo, "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="db61f-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="db61f-110">Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="db61f-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="db61f-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="db61f-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="db61f-112">Creará una configuración que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="db61f-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="db61f-113">Este modelo de datos se usará posteriormente como origen de datos cuando cree el formato para los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="db61f-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="db61f-114">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="db61f-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="db61f-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="db61f-116">En el campo Nombre, escriba Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="db61f-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="db61f-117">Pagos (modelo simplificado)</span><span class="sxs-lookup"><span data-stu-id="db61f-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="db61f-118">En el campo Descripción, escriba Configuración del modelo de pago.</span><span class="sxs-lookup"><span data-stu-id="db61f-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="db61f-119">Configuración del modelo de pago</span><span class="sxs-lookup"><span data-stu-id="db61f-119">Payment model configuration</span></span>  
    * <span data-ttu-id="db61f-120">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="db61f-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="db61f-121">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="db61f-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="db61f-122">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="db61f-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="db61f-123">Haga clic en el botón Crear configuración para completar la tarea de creación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="db61f-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="db61f-124">Creación de un modelo de datos</span><span class="sxs-lookup"><span data-stu-id="db61f-124">Create a data model</span></span>
<span data-ttu-id="db61f-125">Usted está creando un nuevo modelo de datos para la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="db61f-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="db61f-126">Esta versión de la configuración tendrá un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="db61f-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="db61f-127">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="db61f-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="db61f-128">Definición de la estructura de una parte que participa en un proceso de pago</span><span class="sxs-lookup"><span data-stu-id="db61f-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="db61f-129">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="db61f-130">Escriba "Parte" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="db61f-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="db61f-131">Parte</span><span class="sxs-lookup"><span data-stu-id="db61f-131">Party</span></span>  
3. <span data-ttu-id="db61f-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-132">Click Add.</span></span>
4. <span data-ttu-id="db61f-133">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="db61f-134">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="db61f-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="db61f-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="db61f-135">Name</span></span>  
6. <span data-ttu-id="db61f-136">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="db61f-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="db61f-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-137">Click Add.</span></span>
8. <span data-ttu-id="db61f-138">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="db61f-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="db61f-139">Parte</span><span class="sxs-lookup"><span data-stu-id="db61f-139">Party</span></span>  
9. <span data-ttu-id="db61f-140">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="db61f-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="db61f-141">Definición de la estructura bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="db61f-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="db61f-142">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="db61f-143">En el campo Nombre, escriba "Agente".</span><span class="sxs-lookup"><span data-stu-id="db61f-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="db61f-144">Agente</span><span class="sxs-lookup"><span data-stu-id="db61f-144">Agent</span></span>  
3. <span data-ttu-id="db61f-145">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="db61f-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="db61f-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-146">Click Add.</span></span>
5. <span data-ttu-id="db61f-147">En el campo Descripción, escriba "Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedeor).</span><span class="sxs-lookup"><span data-stu-id="db61f-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="db61f-148">Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedor).</span><span class="sxs-lookup"><span data-stu-id="db61f-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="db61f-149">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="db61f-150">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="db61f-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="db61f-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="db61f-151">Name</span></span>  
8. <span data-ttu-id="db61f-152">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="db61f-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="db61f-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-153">Click Add.</span></span>
10. <span data-ttu-id="db61f-154">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="db61f-155">En el campo Nombre, escriba "SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="db61f-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="db61f-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="db61f-156">SWIFT</span></span>  
12. <span data-ttu-id="db61f-157">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-157">Click Add.</span></span>
13. <span data-ttu-id="db61f-158">En el campo Descripción, escriba un "código de identificación del Banco".</span><span class="sxs-lookup"><span data-stu-id="db61f-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="db61f-159">Código de identificación del banco</span><span class="sxs-lookup"><span data-stu-id="db61f-159">Bank identification code</span></span>  
14. <span data-ttu-id="db61f-160">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="db61f-161">En el campo Nombre, especifique "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="db61f-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="db61f-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="db61f-162">RoutingNumber</span></span>  
16. <span data-ttu-id="db61f-163">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-163">Click Add.</span></span>
17. <span data-ttu-id="db61f-164">En el campo Descripción, especifique un "Número de ruta".</span><span class="sxs-lookup"><span data-stu-id="db61f-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="db61f-165">Número de ruta</span><span class="sxs-lookup"><span data-stu-id="db61f-165">Routing number</span></span>  
18. <span data-ttu-id="db61f-166">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="db61f-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="db61f-167">Definición de la cuenta bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="db61f-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="db61f-168">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="db61f-169">En el campo Nombre, escriba "Cuenta".</span><span class="sxs-lookup"><span data-stu-id="db61f-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="db61f-170">Cuenta</span><span class="sxs-lookup"><span data-stu-id="db61f-170">Account</span></span>  
3. <span data-ttu-id="db61f-171">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="db61f-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="db61f-172">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-172">Click Add.</span></span>
5. <span data-ttu-id="db61f-173">En el campo Descripción, escriba "Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco)".</span><span class="sxs-lookup"><span data-stu-id="db61f-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="db61f-174">Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco).</span><span class="sxs-lookup"><span data-stu-id="db61f-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="db61f-175">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="db61f-176">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="db61f-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="db61f-177">Divisa</span><span class="sxs-lookup"><span data-stu-id="db61f-177">Currency</span></span>  
8. <span data-ttu-id="db61f-178">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="db61f-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="db61f-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-179">Click Add.</span></span>
10. <span data-ttu-id="db61f-180">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="db61f-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="db61f-181">Código de divisa</span><span class="sxs-lookup"><span data-stu-id="db61f-181">Currency code</span></span>  
11. <span data-ttu-id="db61f-182">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="db61f-183">En el campo Nombre, escriba "Número".</span><span class="sxs-lookup"><span data-stu-id="db61f-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="db61f-184">Número</span><span class="sxs-lookup"><span data-stu-id="db61f-184">Number</span></span>  
13. <span data-ttu-id="db61f-185">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-185">Click Add.</span></span>
14. <span data-ttu-id="db61f-186">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="db61f-187">En el campo Nombre, escriba "IBAN".</span><span class="sxs-lookup"><span data-stu-id="db61f-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="db61f-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="db61f-188">IBAN</span></span>  
16. <span data-ttu-id="db61f-189">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-189">Click Add.</span></span>
17. <span data-ttu-id="db61f-190">En el campo descripción, escriba "Número de cuenta bancaria internacional".</span><span class="sxs-lookup"><span data-stu-id="db61f-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="db61f-191">Número internacional de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="db61f-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="db61f-192">Definición de la estructura del mensaje de pago para el tipo de pago de transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="db61f-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="db61f-193">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="db61f-194">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="db61f-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="db61f-195">En el campo Nombre, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="db61f-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="db61f-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="db61f-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="db61f-197">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-197">Click Add.</span></span>
5. <span data-ttu-id="db61f-198">En el campo Buscar, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="db61f-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="db61f-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="db61f-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="db61f-200">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="db61f-200">Click Find previous.</span></span>
7. <span data-ttu-id="db61f-201">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="db61f-202">En el campo Nombre, escriba "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="db61f-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="db61f-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="db61f-203">MessageIdentification</span></span>  
9. <span data-ttu-id="db61f-204">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-204">Click Add.</span></span>
10. <span data-ttu-id="db61f-205">En el campo Descripción, escriba "La referencia punto a punto asignada por la parte ordenante (y enviada a la siguiente parte) para identificar un mensaje".</span><span class="sxs-lookup"><span data-stu-id="db61f-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="db61f-206">La referencia punto a punto asignada por la parte ordenante (y que se envía a la siguiente parte) para identificar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="db61f-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="db61f-207">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="db61f-208">En el campo Nombre, escriba "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="db61f-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="db61f-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="db61f-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="db61f-210">En el campo Tipo de artículo, seleccione DateTime.</span><span class="sxs-lookup"><span data-stu-id="db61f-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="db61f-211">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-211">Click Add.</span></span>
15. <span data-ttu-id="db61f-212">En el campo Descripción, escriba "Fecha y hora de creación del mensaje de pago".</span><span class="sxs-lookup"><span data-stu-id="db61f-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="db61f-213">Fecha y hora de creación del mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="db61f-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="db61f-214">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="db61f-215">Definición de la estructura de transacción de pago para este modelo.</span><span class="sxs-lookup"><span data-stu-id="db61f-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="db61f-216">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="db61f-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="db61f-217">Pagos</span><span class="sxs-lookup"><span data-stu-id="db61f-217">Payments</span></span>  
18. <span data-ttu-id="db61f-218">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="db61f-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="db61f-219">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-219">Click Add.</span></span>
20. <span data-ttu-id="db61f-220">En el campo Descripción, especifique Líneas de pago del mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="db61f-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="db61f-221">Líneas de pago del mensaje actual</span><span class="sxs-lookup"><span data-stu-id="db61f-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="db61f-222">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="db61f-223">En el campo Nombre, escriba "Acreedor".</span><span class="sxs-lookup"><span data-stu-id="db61f-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="db61f-224">Acreedor</span><span class="sxs-lookup"><span data-stu-id="db61f-224">Creditor</span></span>  
23. <span data-ttu-id="db61f-225">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="db61f-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="db61f-226">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-226">Click Add.</span></span>
25. <span data-ttu-id="db61f-227">En el campo Descripción, escriba "Parte a la que se debe una suma de dinero".</span><span class="sxs-lookup"><span data-stu-id="db61f-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="db61f-228">Parte a la que se debe una suma de dinero.</span><span class="sxs-lookup"><span data-stu-id="db61f-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="db61f-229">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="db61f-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="db61f-230">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="db61f-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="db61f-231">Parte</span><span class="sxs-lookup"><span data-stu-id="db61f-231">Party</span></span>  
28. <span data-ttu-id="db61f-232">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="db61f-232">Click Find next.</span></span>
29. <span data-ttu-id="db61f-233">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="db61f-233">Click OK.</span></span>
30. <span data-ttu-id="db61f-234">En el campo Buscar, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="db61f-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="db61f-235">Pagos</span><span class="sxs-lookup"><span data-stu-id="db61f-235">Payments</span></span>  
31. <span data-ttu-id="db61f-236">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="db61f-236">Click Find next.</span></span>
32. <span data-ttu-id="db61f-237">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="db61f-238">En el campo Nombre, escriba "Deudor".</span><span class="sxs-lookup"><span data-stu-id="db61f-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="db61f-239">Deudor</span><span class="sxs-lookup"><span data-stu-id="db61f-239">Debtor</span></span>  
34. <span data-ttu-id="db61f-240">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-240">Click Add.</span></span>
35. <span data-ttu-id="db61f-241">En el campo Descripción, escriba "Parte que adeuda una suma de dinero al (último) acreedor".</span><span class="sxs-lookup"><span data-stu-id="db61f-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="db61f-242">Parte que adeuda una suma de dinero al (último) acreedor.</span><span class="sxs-lookup"><span data-stu-id="db61f-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="db61f-243">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="db61f-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="db61f-244">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="db61f-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="db61f-245">Parte</span><span class="sxs-lookup"><span data-stu-id="db61f-245">Party</span></span>  
38. <span data-ttu-id="db61f-246">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="db61f-246">Click Find next.</span></span>
39. <span data-ttu-id="db61f-247">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="db61f-247">Click OK.</span></span>
40. <span data-ttu-id="db61f-248">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="db61f-248">Click Find next.</span></span>
41. <span data-ttu-id="db61f-249">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="db61f-250">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="db61f-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="db61f-251">Descripción</span><span class="sxs-lookup"><span data-stu-id="db61f-251">Description</span></span>  
43. <span data-ttu-id="db61f-252">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="db61f-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="db61f-253">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-253">Click Add.</span></span>
45. <span data-ttu-id="db61f-254">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="db61f-255">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="db61f-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="db61f-256">Divisa</span><span class="sxs-lookup"><span data-stu-id="db61f-256">Currency</span></span>  
47. <span data-ttu-id="db61f-257">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-257">Click Add.</span></span>
48. <span data-ttu-id="db61f-258">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="db61f-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="db61f-259">Código de divisa</span><span class="sxs-lookup"><span data-stu-id="db61f-259">Currency code</span></span>  
49. <span data-ttu-id="db61f-260">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="db61f-261">En el campo Nombre, escriba "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="db61f-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="db61f-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="db61f-262">TransactionDate</span></span>  
51. <span data-ttu-id="db61f-263">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="db61f-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="db61f-264">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-264">Click Add.</span></span>
53. <span data-ttu-id="db61f-265">En el campo Descripción, escriba una "Fecha de transacción".</span><span class="sxs-lookup"><span data-stu-id="db61f-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="db61f-266">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="db61f-266">Transaction date</span></span>  
54. <span data-ttu-id="db61f-267">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="db61f-268">En el campo Nombre, escriba "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="db61f-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="db61f-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="db61f-269">InstructedAmount</span></span>  
56. <span data-ttu-id="db61f-270">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="db61f-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="db61f-271">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-271">Click Add.</span></span>
58. <span data-ttu-id="db61f-272">En el campo Descripción, escriba "La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos".</span><span class="sxs-lookup"><span data-stu-id="db61f-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="db61f-273">El importe se debe expresar en la divisa solicitada por la parte iniciadora."</span><span class="sxs-lookup"><span data-stu-id="db61f-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="db61f-274">La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos.</span><span class="sxs-lookup"><span data-stu-id="db61f-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="db61f-275">El importe se debe expresar en la divisa solicitada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="db61f-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="db61f-276">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="db61f-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="db61f-277">En el campo Nombre, escriba "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="db61f-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="db61f-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="db61f-278">End2EndID</span></span>  
61. <span data-ttu-id="db61f-279">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="db61f-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="db61f-280">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="db61f-280">Click Add.</span></span>
63. <span data-ttu-id="db61f-281">En el campo Descripción, escriba "La identificación única asignada por la parte iniciadora".</span><span class="sxs-lookup"><span data-stu-id="db61f-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="db61f-282">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo".</span><span class="sxs-lookup"><span data-stu-id="db61f-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="db61f-283">La identificación única asignada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="db61f-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="db61f-284">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="db61f-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="db61f-285">En el campo Nombre, especifique "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="db61f-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="db61f-286">El nombre del modelo de pago se alinea con las interfaces predefinidas de los formularios de pago.</span><span class="sxs-lookup"><span data-stu-id="db61f-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="db61f-287">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="db61f-287">Click Save.</span></span>
66. <span data-ttu-id="db61f-288">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="db61f-288">Close the page.</span></span>

