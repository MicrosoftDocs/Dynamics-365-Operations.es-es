---
title: Solucionar problemas de operaciones de almacén de entrada
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970264"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="b76b7-103">Solucionar problemas de operaciones de almacén de entrada</span><span class="sxs-lookup"><span data-stu-id="b76b7-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b76b7-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b76b7-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="b76b7-105">Recibo el siguiente mensaje de error: "Pedido de calidad %1 ha sido generado.</span><span class="sxs-lookup"><span data-stu-id="b76b7-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="b76b7-106">No se encuentra el perfil de clúster. Compruebe la configuración".</span><span class="sxs-lookup"><span data-stu-id="b76b7-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b76b7-107">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-107">Issue description</span></span>

<span data-ttu-id="b76b7-108">Este mensaje de error está relacionado con un proceso de recepción donde la gestión de la calidad (QMS) está activada.</span><span class="sxs-lookup"><span data-stu-id="b76b7-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="b76b7-109">Según las configuraciones de su entorno, los detalles adicionales sobre la transacción que genera el mensaje de error pueden ayudar a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="b76b7-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b76b7-110">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-110">Issue resolution</span></span>

<span data-ttu-id="b76b7-111">Primero, revise la configuración de la [selección de clúster](set-up-cluster-picking.md) y asegúrese de que los perfiles de clúster estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="b76b7-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="b76b7-112">No puede utilizar un elemento del menú de un dispositivo móvil para la selección de grupos a menos que se configuren perfiles de grupos.</span><span class="sxs-lookup"><span data-stu-id="b76b7-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="b76b7-113">Dependiendo de su entorno, es posible que también deba revisar otras configuraciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b76b7-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="b76b7-114">La recepción de matrículas mixtas no funciona para ningún código de disposición, excepto Crédito.</span><span class="sxs-lookup"><span data-stu-id="b76b7-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b76b7-115">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-115">Issue description</span></span>

<span data-ttu-id="b76b7-116">Cuando el campo **Acción** para un código de disposición se establece en *Crédito* o *Chatarra*, puede usar solo el elemento de menú [Recepción de matrículas mixtas](mixed-license-plate-receiving.md) para procesar elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="b76b7-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b76b7-117">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-117">Issue resolution</span></span>

<span data-ttu-id="b76b7-118">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="b76b7-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="b76b7-119">Actualmente, solo se admiten [códigos de disposición](../service-management/set-up-disposition-codes.md) donde el campo **Acción** está configurado en *Crédito* o *Chatarra* para la recepción de matrículas mixtas.</span><span class="sxs-lookup"><span data-stu-id="b76b7-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="b76b7-120">Cuando ejecuto la tarea periódica Actualizar recibos de productos, se confirman los pedidos de compra no confirmados.</span><span class="sxs-lookup"><span data-stu-id="b76b7-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b76b7-121">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-121">Issue description</span></span>

<span data-ttu-id="b76b7-122">Después de ejecutar la tarea periódica *Actualizar recibos de productos*, el sistema confirma automáticamente las órdenes de compra no confirmadas que tienen un estado de transacción de inventario de *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="b76b7-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b76b7-123">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="b76b7-123">Issue resolution</span></span>

<span data-ttu-id="b76b7-124">Una nueva función de manipulación de carga entrante, *Sobre recepción de cantidades de carga*, soluciona este problema.</span><span class="sxs-lookup"><span data-stu-id="b76b7-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="b76b7-125">Para activar esta característica, vaya a [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las siguientes características (en el mismo orden):</span><span class="sxs-lookup"><span data-stu-id="b76b7-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="b76b7-126">Asociar transacciones de inventario de pedido de compra a carga</span><span class="sxs-lookup"><span data-stu-id="b76b7-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="b76b7-127">Recepción en exceso de cantidades de carga</span><span class="sxs-lookup"><span data-stu-id="b76b7-127">Over receipt of load quantities</span></span>

<span data-ttu-id="b76b7-128">Para más información, vea [Contabilice las cantidades de producto registradas contra las órdenes de compra](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="b76b7-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
