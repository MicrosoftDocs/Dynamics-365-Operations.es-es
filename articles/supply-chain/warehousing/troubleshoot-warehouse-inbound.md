---
title: Solucionar problemas de operaciones de almacén de entrada
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920996"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="248a4-103">Solucionar problemas de operaciones de almacén de entrada</span><span class="sxs-lookup"><span data-stu-id="248a4-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="248a4-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="248a4-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="248a4-105">Recibo el siguiente mensaje de error: "Pedido de calidad %1 ha sido generado.</span><span class="sxs-lookup"><span data-stu-id="248a4-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="248a4-106">No se encuentra el perfil de clúster. Compruebe la configuración".</span><span class="sxs-lookup"><span data-stu-id="248a4-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="248a4-107">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-107">Issue description</span></span>

<span data-ttu-id="248a4-108">Este mensaje de error está relacionado con un proceso de recepción donde la gestión de la calidad (QMS) está activada.</span><span class="sxs-lookup"><span data-stu-id="248a4-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="248a4-109">Según las configuraciones de su entorno, los detalles adicionales sobre la transacción que genera el mensaje de error pueden ayudar a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="248a4-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="248a4-110">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-110">Issue resolution</span></span>

<span data-ttu-id="248a4-111">Primero, revise la configuración de la [selección de clúster](set-up-cluster-picking.md) y asegúrese de que los perfiles de clúster estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="248a4-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="248a4-112">No puede utilizar un elemento del menú de un dispositivo móvil para la selección de grupos a menos que se configuren perfiles de grupos.</span><span class="sxs-lookup"><span data-stu-id="248a4-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="248a4-113">Dependiendo de su entorno, es posible que también deba revisar otras configuraciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="248a4-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="248a4-114">La recepción de matrículas mixtas no funciona para ningún código de disposición, excepto Crédito.</span><span class="sxs-lookup"><span data-stu-id="248a4-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="248a4-115">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-115">Issue description</span></span>

<span data-ttu-id="248a4-116">Cuando el campo **Acción** para un código de disposición se establece en *Crédito* o *Chatarra*, puede usar solo el elemento de menú [Recepción de matrículas mixtas](mixed-license-plate-receiving.md) para procesar elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="248a4-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="248a4-117">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-117">Issue resolution</span></span>

<span data-ttu-id="248a4-118">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="248a4-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="248a4-119">Actualmente, solo se admiten [códigos de disposición](../service-management/set-up-disposition-codes.md) donde el campo **Acción** está configurado en *Crédito* o *Chatarra* para la recepción de matrículas mixtas.</span><span class="sxs-lookup"><span data-stu-id="248a4-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="248a4-120">Cuando ejecuto la tarea periódica Actualizar recibos de productos, se confirman los pedidos de compra no confirmados.</span><span class="sxs-lookup"><span data-stu-id="248a4-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="248a4-121">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-121">Issue description</span></span>

<span data-ttu-id="248a4-122">Después de ejecutar la tarea periódica *Actualizar recibos de productos*, el sistema confirma automáticamente las órdenes de compra no confirmadas que tienen un estado de transacción de inventario de *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="248a4-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="248a4-123">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-123">Issue resolution</span></span>

<span data-ttu-id="248a4-124">Una nueva función de manipulación de carga entrante, *Sobre recepción de cantidades de carga*, soluciona este problema.</span><span class="sxs-lookup"><span data-stu-id="248a4-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="248a4-125">Para activar esta característica, vaya al espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las siguientes características (en el mismo ordenen que se enumeran):</span><span class="sxs-lookup"><span data-stu-id="248a4-125">To turn on this feature, go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="248a4-126">Asociar transacciones de inventario de pedido de compra a carga</span><span class="sxs-lookup"><span data-stu-id="248a4-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="248a4-127">Recepción en exceso de cantidades de carga</span><span class="sxs-lookup"><span data-stu-id="248a4-127">Over receipt of load quantities</span></span>

<span data-ttu-id="248a4-128">Para más información, vea [Contabilice las cantidades de producto registradas contra las órdenes de compra](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="248a4-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="248a4-129">Cuando registro pedidos entrantes, recibo el siguiente mensaje de error: "La cantidad no es válida".</span><span class="sxs-lookup"><span data-stu-id="248a4-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="248a4-130">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-130">Issue description</span></span>

<span data-ttu-id="248a4-131">Si el campo **Directiva de agrupación de matrículas** está configurado en *Definido por el usuario* para un elemento de menú de dispositivo móvil que se utiliza para registrar pedidos entrantes, recibe un mensaje de error ("La cantidad no es válida") y no puede completar el registro.</span><span class="sxs-lookup"><span data-stu-id="248a4-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="248a4-132">Causa del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-132">Issue cause</span></span>

<span data-ttu-id="248a4-133">Cuándo *Definido por el usuario* se utiliza como una directiva de agrupación de matrículas, el sistema divide el inventario entrante en matrículas separadas, como lo indica el grupo de secuencia de unidades.</span><span class="sxs-lookup"><span data-stu-id="248a4-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="248a4-134">Si se utilizan números de lote o de serie para rastrear el artículo que se está recibiendo, las cantidades de cada lote o serie deben especificarse por matrícula registrada.</span><span class="sxs-lookup"><span data-stu-id="248a4-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="248a4-135">Si la cantidad que se especifica para una matrícula excede la cantidad que aún debe recibirse para las dimensiones actuales, recibirá el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="248a4-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="248a4-136">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="248a4-136">Issue resolution</span></span>

<span data-ttu-id="248a4-137">Cuando registra un elemento utilizando un elemento de menú de dispositivo móvil donde el campo **Directiva de agrupación de matrículas** el campo está configurado en *Definido por el usuario*, es posible que el sistema requiera que confirme o ingrese números de matrícula, números de lote o números de serie.</span><span class="sxs-lookup"><span data-stu-id="248a4-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="248a4-138">En la página de confirmación de la matrícula, el sistema mostrará la cantidad asignada para la matrícula actual.</span><span class="sxs-lookup"><span data-stu-id="248a4-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="248a4-139">En las páginas de confirmación del lote o de la serie, el sistema mostrará la cantidad que aún debe recibirse en la matrícula actual.</span><span class="sxs-lookup"><span data-stu-id="248a4-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="248a4-140">También incluirá un campo donde puede ingresar la cantidad a registrar para esa combinación de placa y lote o número de serie.</span><span class="sxs-lookup"><span data-stu-id="248a4-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="248a4-141">En este caso, asegúrese de que la cantidad que se está registrando para la matrícula no exceda la cantidad que aún debe recibirse.</span><span class="sxs-lookup"><span data-stu-id="248a4-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="248a4-142">Alternativamente, si se generan demasiadas matrículas en el registro de pedidos entrantes, el valor del campo **Directiva de agrupación de matrículas** se puede cambiar a *Agrupación de matrículas*, se puede asignar un nuevo grupo de secuencia de unidades al artículo, o la opción **Agrupación de matrículas** para el grupo de secuencia de unidades se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="248a4-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
