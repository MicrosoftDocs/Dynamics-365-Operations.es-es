---
title: Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección
description: Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026865"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="914a8-103">Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección</span><span class="sxs-lookup"><span data-stu-id="914a8-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="914a8-104">Número de KB: 4613106</span><span class="sxs-lookup"><span data-stu-id="914a8-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="914a8-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="914a8-105">Symptoms</span></span>

<span data-ttu-id="914a8-106">Este problema ocurre cuando su sistema está configurado para reservar automáticamente pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="914a8-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="914a8-107">Si intenta seleccionar la ubicación para una línea de registro de la lista de selección, recibirá el siguiente mensaje de error cuando utilice los procesos de reserva de gestión de almacenes (WMS):</span><span class="sxs-lookup"><span data-stu-id="914a8-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="914a8-108">No se puede actualizar la cantidad con nuevas dimensiones</span><span class="sxs-lookup"><span data-stu-id="914a8-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="914a8-109">Este problema puede ocurrir porque no tiene suficiente inventario disponible en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="914a8-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="914a8-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="914a8-110">Resolution</span></span>

<span data-ttu-id="914a8-111">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="914a8-111">The system is behaving as designed.</span></span>

<span data-ttu-id="914a8-112">En situaciones en las que usa el proceso de reserva a nivel de almacén, si el inventario disponible no se reserva en todos los niveles de dimensión de inventario y no tiene suficiente inventario disponible en una ubicación específica, le recomendamos que utilice el proceso de reserva manual desde la línea de selección.</span><span class="sxs-lookup"><span data-stu-id="914a8-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="914a8-113">A continuación, puede utilizar la función *Reservar lote* para distribuir las reservas más bajas, como la ubicación, para todas las cantidades disponibles.</span><span class="sxs-lookup"><span data-stu-id="914a8-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
