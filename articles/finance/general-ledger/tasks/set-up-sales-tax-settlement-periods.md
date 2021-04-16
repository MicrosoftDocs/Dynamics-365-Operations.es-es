---
title: Configurar períodos de liquidación de impuestos
description: Este tema explica cómo configurar períodos de liquidación de impuestos en Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd11068a31b5324d87416e7c00f75a59743f695a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813516"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="36040-103">Configurar períodos de liquidación de impuestos</span><span class="sxs-lookup"><span data-stu-id="36040-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="36040-104">Este tema explica cómo configurar períodos de liquidación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="36040-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="36040-105">Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos.</span><span class="sxs-lookup"><span data-stu-id="36040-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="36040-106">Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto.</span><span class="sxs-lookup"><span data-stu-id="36040-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="36040-107">Todos los códigos de impuestos asociados con el período de liquidación se liquidarán.</span><span class="sxs-lookup"><span data-stu-id="36040-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="36040-108">Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="36040-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="36040-109">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="36040-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="36040-110">En el panel de navegación, vaya a **Módulos > Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="36040-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="36040-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36040-111">Select **New**.</span></span>
3. <span data-ttu-id="36040-112">En el campo **Período de liquidación**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="36040-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="36040-113">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="36040-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="36040-114">En el campo **Autoridad**, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="36040-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="36040-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="36040-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="36040-116">En el campo **Condiciones de pago**, seleccione en el menú desplegable el registro que desee.</span><span class="sxs-lookup"><span data-stu-id="36040-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="36040-117">La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="36040-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="36040-118">Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="36040-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="36040-119">Seleccione un tipo para los intervalos del período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="36040-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="36040-120">Especifique el número de unidades del intervalo de períodos por período.</span><span class="sxs-lookup"><span data-stu-id="36040-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="36040-121">Por ejemplo, un trimestre tiene 3 meses.</span><span class="sxs-lookup"><span data-stu-id="36040-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="36040-122">Active o desactive la casilla **Usar procesamiento por lotes para la liquidación de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="36040-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="36040-123">El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="36040-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="36040-124">Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="36040-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="36040-125">No se admite actualmente en España, Japón y Países Bajos.</span><span class="sxs-lookup"><span data-stu-id="36040-125">Currently this is not supported in Spain, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="36040-126">Seleccione o borre la casilla **Evitar generar transacciones de impuestos de contrapartida**.</span><span class="sxs-lookup"><span data-stu-id="36040-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="36040-127">De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="36040-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="36040-128">Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="36040-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="36040-129">Expanda la pestaña **Intervalos de período**.</span><span class="sxs-lookup"><span data-stu-id="36040-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="36040-130">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36040-130">Select **Add**.</span></span>
14. <span data-ttu-id="36040-131">En el campo **Fecha inicial** en la nueva fila, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="36040-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="36040-132">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="36040-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="36040-133">Seleccione **Intervalo de período nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36040-133">Select **New period interval**.</span></span> <span data-ttu-id="36040-134">Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente.</span><span class="sxs-lookup"><span data-stu-id="36040-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="36040-135">Puede volverse y agregar nuevos intervalos de períodos en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="36040-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="36040-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="36040-136">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]