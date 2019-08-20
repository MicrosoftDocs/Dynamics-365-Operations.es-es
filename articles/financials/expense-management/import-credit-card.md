---
title: Importar y mantener transacciones de tarjeta de crédito
description: En este tema se explica cómo importar y mantener transacciones de tarjeta de crédito relacionadas con los gastos. Puede configurar estas transacciones para importarlas automáticamente en una programación recurrente o bien, puede importar manualmente las transacciones cada vez si fuera necesario.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4484ea6fa446c73b8854e7822237bb3c6b9f9023
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840946"
---
# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="7077b-104">Importar y mantener transacciones de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="7077b-104">Import and maintain credit card transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7077b-105">Puede configurar las transacciones de la tarjeta de crédito relacionadas con gastos para que se importen de forma automática en una programación recurrente.</span><span class="sxs-lookup"><span data-stu-id="7077b-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="7077b-106">Como alternativa, puede importar las transacciones de forma manual si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="7077b-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="7077b-107">Las transacciones de tarjeta de crédito se importan a través de la entidad de datos de transacciones de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="7077b-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="7077b-108">Para obtener más información acerca de las entidades de datos, consulte [Entidades de datos](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="7077b-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="7077b-109">Importar transacciones de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="7077b-109">Import credit card transactions</span></span>

1. <span data-ttu-id="7077b-110">En la página **Transacciones de tarjeta de crédito**, seleccione **Importar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="7077b-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="7077b-111">Si es la primera vez que abre la opción de gestión de datos, el sistema actualizará la lista de entidades de datos antes de que pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="7077b-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="7077b-112">En el campo **Nombre**, escriba una descripción única del trabajo de importación.</span><span class="sxs-lookup"><span data-stu-id="7077b-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="7077b-113">En el campo **Formato de datos de origen**, seleccione el formato del archivo que contiene las transacciones de la tarjeta de crédito que se importarán.</span><span class="sxs-lookup"><span data-stu-id="7077b-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="7077b-114">Seleccione **Cargar** y, a continuación, busque y seleccione el archivo que quiera importar.</span><span class="sxs-lookup"><span data-stu-id="7077b-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="7077b-115">Una vez cargado el archivo, valide la asignación del archivo de transacción de la tarjeta de crédito y las columnas de la entidad de datos de las transacciones de la tarjeta de crédito; para ello, seleccione el vínculo **Ver asignación** en el icono.</span><span class="sxs-lookup"><span data-stu-id="7077b-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="7077b-116">Si hay errores de asignación o si tiene que cambiar la asignación, realice los cambios de asignación desde la pestaña **Visualización de asignación** o **Detalles de la asignación**.</span><span class="sxs-lookup"><span data-stu-id="7077b-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="7077b-117">Para automatizar las transacciones de la tarjeta de crédito, seleccione **Crear un trabajo de datos recurrente**.</span><span class="sxs-lookup"><span data-stu-id="7077b-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="7077b-118">Es entonces cuando puede establecer la recurrencia que definirá con qué frecuencia se importarán las transacciones de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="7077b-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="7077b-119">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7077b-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="7077b-120">Para importar el archivo seleccionado, seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7077b-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="7077b-121">Si se produce algún error durante la importación, puede consultar el registro de ejecución o los datos provisionales para ver qué errores debe corregir para garantizar una importación correcta.</span><span class="sxs-lookup"><span data-stu-id="7077b-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="7077b-122">Si debe importar más de un formato de archivo, debe crear trabajos de importación separados para cada tipo de formato.</span><span class="sxs-lookup"><span data-stu-id="7077b-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="7077b-123">Reasignar transacciones de la tarjeta de crédito de empleados despedidos</span><span class="sxs-lookup"><span data-stu-id="7077b-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="7077b-124">Una vez finaliza un registro de empleado, la cuenta Active Directory Domain Services de ese empleado se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="7077b-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="7077b-125">Sin embargo, es posible que haya transacciones de tarjeta de crédito que todavía deban ser calculadas y reembolsadas.</span><span class="sxs-lookup"><span data-stu-id="7077b-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="7077b-126">Desde la página **Transacciones de tarjeta de crédito** puede reasignar el empleado de cualquier transacción de tarjeta de crédito cuyo empleado asociado haya sido despedido.</span><span class="sxs-lookup"><span data-stu-id="7077b-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="7077b-127">Seleccione una o más transacciones de tarjeta de crédito y, a continuación, seleccione **Volver a asignar las transacciones**.</span><span class="sxs-lookup"><span data-stu-id="7077b-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="7077b-128">A continuación puede seleccionar otro empleado para asignarle esas transacciones de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="7077b-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="7077b-129">Tras reasignar las transacciones de tarjeta de crédito, se pueden seleccionar para un informe de gastos y podrá pagarlas mediante el proceso habitual para el reembolso del informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="7077b-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>
