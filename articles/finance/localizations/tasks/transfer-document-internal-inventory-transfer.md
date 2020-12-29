---
title: Generar un documento de transferencia para una transferencia de inventario interna
description: Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cb0d3d51bf30717f05a4daf1a098565d5d48621
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447629"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="57854-103">Generar un documento de transferencia para una transferencia de inventario interna</span><span class="sxs-lookup"><span data-stu-id="57854-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57854-104">Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="57854-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="57854-105">Este procedimiento sólo está disponible para entidades jurídicas con dirección principal en Lituania.</span><span class="sxs-lookup"><span data-stu-id="57854-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="57854-106">Este procedimiento se ha creado con los datos de demostración de la empresa DEMF, con una dirección principal en Lituania.</span><span class="sxs-lookup"><span data-stu-id="57854-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="57854-107">Antes de completar este procedimiento, deberá completar el procedimiento de “Configuración de los documentos de transferencia de mercancías dentro de una empresa”.</span><span class="sxs-lookup"><span data-stu-id="57854-107">Before you can complete this procedure, you must complete the "Set up transfer documents for goods movement inside a company" procedure.</span></span> <span data-ttu-id="57854-108">Este procedimiento está dirigido a contables de inventario.</span><span class="sxs-lookup"><span data-stu-id="57854-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="57854-109">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="57854-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="57854-110">Creación de un pedido de transferencia</span><span class="sxs-lookup"><span data-stu-id="57854-110">Create a transfer order</span></span>
1. <span data-ttu-id="57854-111">Vaya a Gestión del inventario > Pedidos de entrada > Orden de transferencia.</span><span class="sxs-lookup"><span data-stu-id="57854-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="57854-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57854-112">Click New.</span></span>
3. <span data-ttu-id="57854-113">En el campo Desde almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="57854-114">En el campo Hasta almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="57854-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="57854-115">Click Add.</span></span>
6. <span data-ttu-id="57854-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57854-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="57854-117">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="57854-118">Especificar los detalles de transporte para el pedido de transferencia</span><span class="sxs-lookup"><span data-stu-id="57854-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="57854-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="57854-119">Click Save.</span></span>
2. <span data-ttu-id="57854-120">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="57854-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="57854-121">Haga clic en Detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="57854-121">Click Transportation details.</span></span>
4. <span data-ttu-id="57854-122">Seleccione Sí en el campo Imprimir detalles de transporte.</span><span class="sxs-lookup"><span data-stu-id="57854-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="57854-123">En el campo Mercancías emitidas por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="57854-124">En el campo Paquete, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="57854-125">En el campo Nivel de riesgo de la carga, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="57854-126">En el campo Transportista, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="57854-127">En el campo Modelo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="57854-128">En el campo Número de registro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="57854-129">En el campo Número de registro del tráiler, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="57854-130">En el campo Conductor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="57854-131">En el campo Nombre de conductor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="57854-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="57854-132">Click Save.</span></span>
15. <span data-ttu-id="57854-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57854-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="57854-134">Ver el albarán para el pedido de transferencia sin registrar</span><span class="sxs-lookup"><span data-stu-id="57854-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="57854-135">Haga clic en Albarán.</span><span class="sxs-lookup"><span data-stu-id="57854-135">Click Packing slip.</span></span>
2. <span data-ttu-id="57854-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57854-136">Click OK.</span></span>
3. <span data-ttu-id="57854-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57854-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="57854-138">Ver el albarán para el pedido de transferencia registrado</span><span class="sxs-lookup"><span data-stu-id="57854-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="57854-139">En el panel de acciones, haga clic Transferir pedido.</span><span class="sxs-lookup"><span data-stu-id="57854-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="57854-140">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="57854-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="57854-141">Haga clic en Enviar pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="57854-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="57854-142">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="57854-142">Click the General tab.</span></span>
5. <span data-ttu-id="57854-143">En el campo Actualizar, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="57854-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="57854-144">Haga clic en la ficha Visión general.</span><span class="sxs-lookup"><span data-stu-id="57854-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="57854-145">En el campo Albarán, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57854-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="57854-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57854-146">Click OK.</span></span>
9. <span data-ttu-id="57854-147">En el panel de acciones, haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="57854-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="57854-148">Haga clic en Albarán.</span><span class="sxs-lookup"><span data-stu-id="57854-148">Click Packing slip.</span></span>
11. <span data-ttu-id="57854-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57854-149">Click OK.</span></span>

