--- 
title: "Configurar la conciliación automática de flete"
description: "Este procedimiento muestra cómo configurar los datos para la conciliación automática de flete."
author: ShylaThompson
manager: AnnBe
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d990efd7c929b15d57d64e850bc3308349abb978
ms.openlocfilehash: b7772ad779495b36941a3dc86cc456d80a964467
ms.contentlocale: es-es
ms.lasthandoff: 10/17/2018

---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="4ad49-103">Configurar la conciliación automática de flete</span><span class="sxs-lookup"><span data-stu-id="4ad49-103">Set up automatic freight reconciliation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ad49-104">Este procedimiento muestra cómo configurar los datos para la conciliación automática de flete.</span><span class="sxs-lookup"><span data-stu-id="4ad49-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="4ad49-105">Este proceso normalmente lo realiza el director del almacén.</span><span class="sxs-lookup"><span data-stu-id="4ad49-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="4ad49-106">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="4ad49-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="4ad49-107">Configurar el tipo de albarán de flete</span><span class="sxs-lookup"><span data-stu-id="4ad49-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="4ad49-108">Ir a Administración de transporte > Configuración > Conciliación de transporte > Tipo de albarán de transporte.</span><span class="sxs-lookup"><span data-stu-id="4ad49-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="4ad49-109">El tipo de albarán de flete define cómo deben conciliarse las cuentas de flete y las facturas del transportista.</span><span class="sxs-lookup"><span data-stu-id="4ad49-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="4ad49-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-110">Click New.</span></span>
3. <span data-ttu-id="4ad49-111">En el campo Tipo de alabarán de flete, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="4ad49-112">En el campo Ensamblado de motores, escriba "Microsoft.Dynamics.Ax.Tms.dll".</span><span class="sxs-lookup"><span data-stu-id="4ad49-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="4ad49-113">Esta es la biblioteca de códigos estándar del motor que coincide con la gestión de transporte.</span><span class="sxs-lookup"><span data-stu-id="4ad49-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="4ad49-114">En el campo Tipo de motor, escriba "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer".</span><span class="sxs-lookup"><span data-stu-id="4ad49-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="4ad49-115">Esta es la clase del motor estándar que coincide con la gestión de transporte.</span><span class="sxs-lookup"><span data-stu-id="4ad49-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="4ad49-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-116">Click New.</span></span>
7. <span data-ttu-id="4ad49-117">En el campo Descripción, elija el valor que se debe coincidir con el albarán de flete y la factura de transportista.</span><span class="sxs-lookup"><span data-stu-id="4ad49-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="4ad49-118">Seleccione Sí en el campo Correspondencia requerida.</span><span class="sxs-lookup"><span data-stu-id="4ad49-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="4ad49-119">Si configura este campo en Sí esto significa que el valor seleccionado en el campo Descripción debe coincidir con el albarán de flete y la factura de transportista.</span><span class="sxs-lookup"><span data-stu-id="4ad49-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="4ad49-120">Si configura en No, el campo puede quedar en blanco en uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="4ad49-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="4ad49-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ad49-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="4ad49-122">Configurar la asignación de tipo de albarán de flete</span><span class="sxs-lookup"><span data-stu-id="4ad49-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="4ad49-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ad49-123">Close the page.</span></span>
2. <span data-ttu-id="4ad49-124">Ir a Administración de transporte > Configuración > Conciliación de transporte > Asignación de tipos de albarán de transporte.</span><span class="sxs-lookup"><span data-stu-id="4ad49-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="4ad49-125">La asignación del tipo de albarán de flete se utiliza para especificar el tipo de albarán de flete que se usa para un transportista determinado.</span><span class="sxs-lookup"><span data-stu-id="4ad49-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="4ad49-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-126">Click New.</span></span>
4. <span data-ttu-id="4ad49-127">En el campo Modo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="4ad49-128">En el campo Transportista de envío, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="4ad49-129">En el campo Tipo de albarán de flete, seleccione el tipo de albarán de flete que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4ad49-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="4ad49-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ad49-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="4ad49-131">Configurar el maestro de auditoría</span><span class="sxs-lookup"><span data-stu-id="4ad49-131">Set up the audit master</span></span>
1. <span data-ttu-id="4ad49-132">Ir a Administración de transporte > Configuración > Conciliación de transporte > Director de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4ad49-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="4ad49-133">El maestro de auditoría define los límites de tolerancia para la conciliación automática de flete.</span><span class="sxs-lookup"><span data-stu-id="4ad49-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="4ad49-134">Especifica en cuánto pueden variar los importes monetarios en el albarán de flete y la factura de transportista y que se permita la conciliación.</span><span class="sxs-lookup"><span data-stu-id="4ad49-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="4ad49-135">También define cómo gestionar discrepancias.</span><span class="sxs-lookup"><span data-stu-id="4ad49-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="4ad49-136">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-136">Click New.</span></span>
3. <span data-ttu-id="4ad49-137">En el campo Id. de maestro de auditoría, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="4ad49-138">En el campo Transportista de envío, seleccione el mismo transportista de envío que seleccionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4ad49-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="4ad49-139">En el campo Tipo de albarán de flete, seleccione el tipo de albarán de flete que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4ad49-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="4ad49-140">Expanda la sección Tolerancia.</span><span class="sxs-lookup"><span data-stu-id="4ad49-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="4ad49-141">Especifique un número en el campo Nivel de tolerancia mínimo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="4ad49-142">Especifique un número en el campo Nivel de tolerancia máximo.</span><span class="sxs-lookup"><span data-stu-id="4ad49-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="4ad49-143">Expanda la sección Resultado.</span><span class="sxs-lookup"><span data-stu-id="4ad49-143">Expand the Result section.</span></span>
10. <span data-ttu-id="4ad49-144">En el campo Código de motivo de sobrepago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="4ad49-145">Si los importes monetarios difieren en el albarán de flete y la factura de transportista, los códigos de motivo de sobrepago y de pago insuficiente especifican las cuentas donde debe registrarse la diferencia, siempre que la diferencia se encuentre dentro de los niveles de tolerancia.</span><span class="sxs-lookup"><span data-stu-id="4ad49-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="4ad49-146">En el campo Código de motivo de pago insuficiente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4ad49-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="4ad49-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ad49-147">Close the page.</span></span>


