---
title: Configurar y generar información de vencimiento de clientes
description: Esta guía le ayudará a configurar una definición de período de vencimiento, vencer saldos de cliente y ver los saldos en la lista Saldos vencidos para mostrar la página Cobros.
author: mikefalkner
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68d2e4a440ba99e52d715b9e5e3cfd77bb61814f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816181"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="990bd-103">Configurar y generar información de vencimiento de clientes</span><span class="sxs-lookup"><span data-stu-id="990bd-103">Set up and generate accounts receivable aging information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="990bd-104">Esta guía le ayudará a configurar una definición de período de vencimiento, vencer saldos de cliente y ver los saldos en la lista Saldos vencidos para mostrar la página Cobros.</span><span class="sxs-lookup"><span data-stu-id="990bd-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="990bd-105">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="990bd-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="990bd-106">Crear una definición de período de vencimiento</span><span class="sxs-lookup"><span data-stu-id="990bd-106">Create an aging period definition</span></span>
1. <span data-ttu-id="990bd-107">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Definiciones de período de vencimiento**.</span><span class="sxs-lookup"><span data-stu-id="990bd-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="990bd-108">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="990bd-108">Click **New**.</span></span>
3. <span data-ttu-id="990bd-109">En el campo **Definición de período de vencimiento**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990bd-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="990bd-110">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990bd-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="990bd-111">Haga clic en **Agregar abajo** para insertar un nuevo período de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="990bd-112">En el campo **Período**, escriba la descripción para mostrar en los informes de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="990bd-113">En el campo **Unidad**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="990bd-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="990bd-114">En el campo **Intervalo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="990bd-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="990bd-115">El período contable coincide con el período del calendario contable.</span><span class="sxs-lookup"><span data-stu-id="990bd-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="990bd-116">Los valores de día, semana, mes, trimestre y años definen el tamaño del intervalo del tipo de fecha.</span><span class="sxs-lookup"><span data-stu-id="990bd-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="990bd-117">Ilimitado selecciona todas las transacciones antes o después del período anterior en función de si es el primer período o el último.</span><span class="sxs-lookup"><span data-stu-id="990bd-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="990bd-118">En el campo **Vencimiento**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="990bd-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="990bd-119">Seleccione el período en la parte superior de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="990bd-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="990bd-120">Actualice la descripción para describir el período más antiguo en la definición de período de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="990bd-121">En el campo **Período**, escriba la nueva descripción del período de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="990bd-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="990bd-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="990bd-123">Calcular el vencimiento de los saldos</span><span class="sxs-lookup"><span data-stu-id="990bd-123">Age the balances</span></span>
1. <span data-ttu-id="990bd-124">Vaya a **Crédito y cobros > Tareas periódicas > Calcular vencimientos de saldos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="990bd-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="990bd-125">En el campo **Definición de período de vencimiento**, seleccione la definición de período de vencimiento que ha creado.</span><span class="sxs-lookup"><span data-stu-id="990bd-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="990bd-126">Puede tener una instantánea activa para cada definición de período de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="990bd-127">Se procesan todos los clientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="990bd-127">All customers are processed by default.</span></span> <span data-ttu-id="990bd-128">Puede usar esta selección para calcular una sola sección de cobros de clientes.</span><span class="sxs-lookup"><span data-stu-id="990bd-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="990bd-129">Seleccione la fecha de la transacción que usará para el vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="990bd-130">Seleccione la fecha “a partir de” para el vencimiento.</span><span class="sxs-lookup"><span data-stu-id="990bd-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="990bd-131">El valor predeterminado es la fecha actual pero, si cambia este campo a la fecha seleccionada, podrá seleccionar la fecha que desee.</span><span class="sxs-lookup"><span data-stu-id="990bd-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="990bd-132">Para el procesamiento por lotes, use la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="990bd-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="990bd-133">Expanda el intervalo **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="990bd-133">Expand the **Company** range.</span></span> <span data-ttu-id="990bd-134">Puede seleccionar las empresas que se incluirán en la instantánea.</span><span class="sxs-lookup"><span data-stu-id="990bd-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="990bd-135">La empresa actual está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="990bd-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="990bd-136">Haga clic en **Aceptar** para procesar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="990bd-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="990bd-137">Llevará algún tiempo, así que espere a que desaparezca el control deslizante y compruebe el centro de mensajes para ver si hay algún mensaje.</span><span class="sxs-lookup"><span data-stu-id="990bd-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="990bd-138">Ver los saldos en la lista de saldos vencidos y en la página de cobros</span><span class="sxs-lookup"><span data-stu-id="990bd-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="990bd-139">Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.</span><span class="sxs-lookup"><span data-stu-id="990bd-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="990bd-140">La página de lista muestra el saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="990bd-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="990bd-141">El icono de vencimiento muestra el período de vencimiento de la transacción más antigua.</span><span class="sxs-lookup"><span data-stu-id="990bd-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="990bd-142">Seleccione un cliente con saldo.</span><span class="sxs-lookup"><span data-stu-id="990bd-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="990bd-143">Expanda el área del cuadro informativo **Vencimiento** para ver los saldos vencidos.</span><span class="sxs-lookup"><span data-stu-id="990bd-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="990bd-144">La definición de período de vencimiento para el cuadro informativo se toma de la definición de período de vencimiento predeterminada que se haya especificado en los parámetros.</span><span class="sxs-lookup"><span data-stu-id="990bd-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="990bd-145">Puede cambiarse mediante el menú Cobrar.</span><span class="sxs-lookup"><span data-stu-id="990bd-145">You can change it using the Collect menu.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]