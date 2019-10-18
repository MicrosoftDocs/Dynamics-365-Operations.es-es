---
title: Configuración de clientes y cuentas bancarias de cliente para domiciliaciones bancarias ISO20022
description: Esta tarea le guía por el procedimiento de configuración de una cuenta bancaria de cliente y una orden de domiciliación bancaria de cliente, necesarias para generar el archivo de pago de cliente como la domiciliación bancaria ISO20022.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a8a3eff1f882d0d9b3d4943e352a8f3d1a6ae4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185736"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="c9dd4-103">Configuración de clientes y cuentas bancarias de cliente para domiciliaciones bancarias ISO20022</span><span class="sxs-lookup"><span data-stu-id="c9dd4-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9dd4-104">Esta tarea le guía por el procedimiento de configuración de una cuenta bancaria de cliente y una orden de domiciliación bancaria de cliente, necesarias para generar el archivo de pago de cliente como la domiciliación bancaria ISO20022.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="c9dd4-105">En función de los formatos de pago del cliente configurados, la información adicional, que no se cubren en este procedimiento, puede ser necesaria para un cliente o una cuenta bancaria de cliente.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="c9dd4-106">Esta tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal de entidad jurídica en Alemania.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="c9dd4-107">Este es el cuarto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="c9dd4-108">Configuración de una cuenta bancaria de cliente</span><span class="sxs-lookup"><span data-stu-id="c9dd4-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="c9dd4-109">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="c9dd4-110">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c9dd4-111">Por ejemplo, filtre por el campo Cuenta, por el valor "DE-010".</span><span class="sxs-lookup"><span data-stu-id="c9dd4-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="c9dd4-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c9dd4-113">En el panel de acciones, haga clic en Clientes.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="c9dd4-114">Haga clic en Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="c9dd4-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-115">Click New.</span></span>
7. <span data-ttu-id="c9dd4-116">En el campo Cuenta bancaria, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="c9dd4-117">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c9dd4-118">Por ejemplo, especifique "Banco EUR".</span><span class="sxs-lookup"><span data-stu-id="c9dd4-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="c9dd4-119">En el campo Grupos de bancos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="c9dd4-120">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="c9dd4-121">Por ejemplo, escriba "DE36200400000628808808".</span><span class="sxs-lookup"><span data-stu-id="c9dd4-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="c9dd4-122">En el campo Código SWIFT, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="c9dd4-123">Por ejemplo, especifique "COBADEFFXXX".</span><span class="sxs-lookup"><span data-stu-id="c9dd4-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="c9dd4-124">Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="c9dd4-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-125">Click Save.</span></span>
13. <span data-ttu-id="c9dd4-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-126">Close the page.</span></span>
14. <span data-ttu-id="c9dd4-127">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-127">Click Edit.</span></span>
15. <span data-ttu-id="c9dd4-128">Expanda la sección Valores predeterminados de pago.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="c9dd4-129">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="c9dd4-130">Adición de una orden de domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="c9dd4-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="c9dd4-131">Expanda la sección Órdenes de domiciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="c9dd4-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-132">Click Add.</span></span>
3. <span data-ttu-id="c9dd4-133">En el campo Cuenta bancaria de acreedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="c9dd4-134">Por ejemplo, seleccione DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="c9dd4-135">En el campo Fecha de firma, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="c9dd4-136">Haga clic en Sí para confirmar la actualización de la fecha.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="c9dd4-137">En el campo Ubicación de firma, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="c9dd4-138">En el campo Número esperado de pagos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="c9dd4-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c9dd4-139">Click OK.</span></span>
9. <span data-ttu-id="c9dd4-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-140">Click Save.</span></span>

