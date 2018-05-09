--- 
title: Generar un documento de transferencia para una transferencia de inventario interna
description: "Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 699f7562f3b3a91f6544f85b892a55d371f4137f
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="d29a5-103">Generar un documento de transferencia para una transferencia de inventario interna</span><span class="sxs-lookup"><span data-stu-id="d29a5-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d29a5-104">Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="d29a5-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="d29a5-105">Este procedimiento sólo está disponible para entidades jurídicas con dirección principal en Lituania.</span><span class="sxs-lookup"><span data-stu-id="d29a5-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="d29a5-106">Este procedimiento se ha creado con los datos de demostración de la empresa DEMF, con una dirección principal en Lituania.</span><span class="sxs-lookup"><span data-stu-id="d29a5-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="d29a5-107">Antes de completar este procedimiento, deberá completar el procedimiento de “Configuración de los documentos de transferencia de mercancías dentro de una empresa”.</span><span class="sxs-lookup"><span data-stu-id="d29a5-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="d29a5-108">Este procedimiento está dirigido a contables de inventario.</span><span class="sxs-lookup"><span data-stu-id="d29a5-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="d29a5-109">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d29a5-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="d29a5-110">Creación de un pedido de transferencia</span><span class="sxs-lookup"><span data-stu-id="d29a5-110">Create a transfer order</span></span>
1. <span data-ttu-id="d29a5-111">Vaya a Gestión del inventario > Pedidos de entrada > Orden de transferencia.</span><span class="sxs-lookup"><span data-stu-id="d29a5-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="d29a5-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d29a5-112">Click New.</span></span>
3. <span data-ttu-id="d29a5-113">En el campo Desde almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="d29a5-114">En el campo Hasta almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="d29a5-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-115">Click Add.</span></span>
6. <span data-ttu-id="d29a5-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d29a5-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="d29a5-117">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="d29a5-118">Especificar los detalles de transporte para el pedido de transferencia</span><span class="sxs-lookup"><span data-stu-id="d29a5-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="d29a5-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-119">Click Save.</span></span>
2. <span data-ttu-id="d29a5-120">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="d29a5-121">Haga clic en Detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="d29a5-121">Click Transportation details.</span></span>
4. <span data-ttu-id="d29a5-122">Seleccione Sí en el campo Imprimir detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="d29a5-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="d29a5-123">En el campo Mercancías emitidas por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="d29a5-124">En el campo Paquete, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="d29a5-125">En el campo Nivel de riesgo de la carga, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="d29a5-126">En el campo Transportista, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="d29a5-127">En el campo Modelo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="d29a5-128">En el campo Número de registro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="d29a5-129">En el campo Número de registro del tráiler, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="d29a5-130">En el campo Conductor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="d29a5-131">En el campo Nombre de conductor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="d29a5-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-132">Click Save.</span></span>
15. <span data-ttu-id="d29a5-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d29a5-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="d29a5-134">Ver el albarán para el pedido de transferencia sin registrar</span><span class="sxs-lookup"><span data-stu-id="d29a5-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="d29a5-135">Haga clic en Albarán.</span><span class="sxs-lookup"><span data-stu-id="d29a5-135">Click Packing slip.</span></span>
2. <span data-ttu-id="d29a5-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d29a5-136">Click OK.</span></span>
3. <span data-ttu-id="d29a5-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d29a5-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="d29a5-138">Ver el albarán para el pedido de transferencia registrado</span><span class="sxs-lookup"><span data-stu-id="d29a5-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="d29a5-139">En el panel de acciones, haga clic Transferir pedido.</span><span class="sxs-lookup"><span data-stu-id="d29a5-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="d29a5-140">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="d29a5-141">Haga clic en Enviar pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="d29a5-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="d29a5-142">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="d29a5-142">Click the General tab.</span></span>
5. <span data-ttu-id="d29a5-143">En el campo Actualizar, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d29a5-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="d29a5-144">Haga clic en la ficha Visión general.</span><span class="sxs-lookup"><span data-stu-id="d29a5-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="d29a5-145">En el campo Albarán, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d29a5-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="d29a5-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d29a5-146">Click OK.</span></span>
9. <span data-ttu-id="d29a5-147">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="d29a5-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="d29a5-148">Haga clic en Albarán.</span><span class="sxs-lookup"><span data-stu-id="d29a5-148">Click Packing slip.</span></span>
11. <span data-ttu-id="d29a5-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d29a5-149">Click OK.</span></span>


