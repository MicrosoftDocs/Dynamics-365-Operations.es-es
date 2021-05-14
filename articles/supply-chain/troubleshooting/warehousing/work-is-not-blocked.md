---
title: El trabajo no está bloqueado
description: El trabajo no está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924213"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="c4897-103">El trabajo no está bloqueado</span><span class="sxs-lookup"><span data-stu-id="c4897-103">Work isn't blocked</span></span>

<span data-ttu-id="c4897-104">Código de error: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="c4897-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="c4897-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="c4897-105">Symptoms</span></span>

<span data-ttu-id="c4897-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="c4897-106">The system shows the following error message:</span></span>

> <span data-ttu-id="c4897-107">El trabajo con id. %1 no está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c4897-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="c4897-108">Causa</span><span class="sxs-lookup"><span data-stu-id="c4897-108">Cause</span></span>

<span data-ttu-id="c4897-109">La opción **Lanzamiento bloqueado** del lanzamiento está configurada en *No*.</span><span class="sxs-lookup"><span data-stu-id="c4897-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="c4897-110">El trabajo no se puede desbloquear porque no está bloqueado actualmente.</span><span class="sxs-lookup"><span data-stu-id="c4897-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="c4897-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="c4897-111">Resolution</span></span>

 <span data-ttu-id="c4897-112">Trabaje solo cuando la opción **Lanzamiento bloqueado** está configurada en *Sí* y se puede desbloquear.</span><span class="sxs-lookup"><span data-stu-id="c4897-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
