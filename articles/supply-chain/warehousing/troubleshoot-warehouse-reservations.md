---
title: Solución de problemas de reservas en gestión de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828115"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="c6297-103">Solución de problemas de reservas en gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="c6297-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6297-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c6297-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c6297-105">Para temas relacionados con los registros de lotes y números de serie, consulte [Solucionar problemas de jerarquías de reserva en serie y por lotes del almacén](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="c6297-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="c6297-106">Aparece el mensaje de error: "No se pueden quitar las reservas porque se ha creado un trabajo que depende de ellas".</span><span class="sxs-lookup"><span data-stu-id="c6297-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c6297-107">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-107">Issue description</span></span>

<span data-ttu-id="c6297-108">No se puede anular la reserva de inventario en una línea de ventas, porque hay trabajo abierto contra la línea.</span><span class="sxs-lookup"><span data-stu-id="c6297-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c6297-109">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-109">Issue resolution</span></span>

<span data-ttu-id="c6297-110">Investigar si existe trabajo de grupo de empaque abierto para llevar el artículo de una estación de empaque a otra ubicación (como *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="c6297-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="c6297-111">Revise los registros en las páginas **Registro del historial de creación de trabajos** y **Detalles del trabajo** para determinar qué está reservando físicamente el inventario, y luego completar o eliminar el trabajo para liberar la reserva.</span><span class="sxs-lookup"><span data-stu-id="c6297-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="c6297-112">Recibo el siguiente mensaje de error: "Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2...."</span><span class="sxs-lookup"><span data-stu-id="c6297-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c6297-113">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-113">Issue description</span></span>

<span data-ttu-id="c6297-114">Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6297-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="c6297-115">A continuación se muestra el texto completo del mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="c6297-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="c6297-116">Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2 con dimensiones Tamaño=%3, Color=%4, Adiciones=%5, Sitio=%6, Almacén=%7, Ubicación=%8, Estado de inventario=Disponible, Matrícula=%9, Número de lote=%10 para ID de referencia %11 en ID de lote %12.</span><span class="sxs-lookup"><span data-stu-id="c6297-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c6297-117">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-117">Issue resolution</span></span>

<span data-ttu-id="c6297-118">Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad.</span><span class="sxs-lookup"><span data-stu-id="c6297-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="c6297-119">Por ejemplo, estas transacciones pueden abrir pedidos de calidad, registros de bloqueo de inventario o pedidos de salida.</span><span class="sxs-lookup"><span data-stu-id="c6297-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="c6297-120">Recibo el siguiente mensaje de error: "Físico disponible ... no se puede reservar porque solo 0.00 están disponibles en el inventario".</span><span class="sxs-lookup"><span data-stu-id="c6297-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c6297-121">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-121">Issue description</span></span>

<span data-ttu-id="c6297-122">Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6297-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="c6297-123">A continuación se muestra el texto completo del mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="c6297-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="c6297-124">Sitio físico disponible=%1, Almacén=%2, Estado de inventario=Disponible, Número de lote=%3, Propietario=%4: %5 no se puede reservar porque solo 0.00 están disponibles en el inventario.</span><span class="sxs-lookup"><span data-stu-id="c6297-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c6297-125">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c6297-125">Issue resolution</span></span>

<span data-ttu-id="c6297-126">Este problema probablemente se deba al trabajo abierto.</span><span class="sxs-lookup"><span data-stu-id="c6297-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="c6297-127">Completar el trabajo o recibir sin creación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6297-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="c6297-128">Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad.</span><span class="sxs-lookup"><span data-stu-id="c6297-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="c6297-129">Por ejemplo, estas transacciones pueden ser pedidos de calidad, registros de bloqueo de inventario o pedidos de salida abiertos.</span><span class="sxs-lookup"><span data-stu-id="c6297-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
