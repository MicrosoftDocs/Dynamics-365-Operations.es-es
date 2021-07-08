---
title: El pedido de producción planificado se debe programar para poder ser firmado
description: Cuando intenta reafirmar un pedido planificado, recibe un mensaje de error que indica que el pedido debe programarse antes de que pueda reafirmarse.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294177"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="844b8-103">El pedido de producción planificado se debe programar para poder ser firmado</span><span class="sxs-lookup"><span data-stu-id="844b8-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="844b8-104">Código de error: SYS309802</span><span class="sxs-lookup"><span data-stu-id="844b8-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="844b8-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="844b8-105">Symptoms</span></span>

<span data-ttu-id="844b8-106">Cuando intenta confirmar un pedido planificado, recibe el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="844b8-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="844b8-107">El pedido de producción planificado se debe programar para poder ser firmado.</span><span class="sxs-lookup"><span data-stu-id="844b8-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="844b8-108">Causa</span><span class="sxs-lookup"><span data-stu-id="844b8-108">Cause</span></span>

<span data-ttu-id="844b8-109">Las fechas de inicio y finalización programadas no pueden estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="844b8-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="844b8-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="844b8-110">Resolution</span></span>

<span data-ttu-id="844b8-111">Para especificar las fechas de inicio y finalización de la orden planificada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="844b8-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="844b8-112">Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="844b8-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="844b8-113">Abra el pedido planificado pertinente.</span><span class="sxs-lookup"><span data-stu-id="844b8-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="844b8-114">Sobre la ficha desplegable **General**, en la sección **Programado**, especifique las fechas en los campos **Fecha de inicio** y **Fecha final**.</span><span class="sxs-lookup"><span data-stu-id="844b8-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
