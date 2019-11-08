---
title: Calendario y programación de trabajador de mantenimiento
description: En este tema se explica el calendario del trabajador de mantenimiento en relación con la programación en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: aa2d50a976af7ee7dde5335f94336b995fdc2d11
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652066"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="915cb-103">Calendario y programación de trabajador de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="915cb-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="915cb-104">Cuando programe órdenes de trabajo, puede crear una programación para los trabajadores de mantenimiento, las herramientas y los activos.</span><span class="sxs-lookup"><span data-stu-id="915cb-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="915cb-105">Para programar los trabajadores de mantenimiento, debe configurarse un calendario para cada trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="915cb-105">In order to schedule maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="915cb-106">Los trabajadores de mantenimiento están relacionados con un recurso y los calendarios de tiempo de trabajo se configuran en recursos.</span><span class="sxs-lookup"><span data-stu-id="915cb-106">Maintenance workers are related to a resource, and working time calendars are set up for resources.</span></span> <span data-ttu-id="915cb-107">Puede configurar el recurso y el calendario en **Administración de activos** > **Configuración** > **Trabajadores** > **Trabajadores**, que se describe en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="915cb-107">You set up the resource and calendar in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="915cb-108">La captura de pantalla siguiente muestra un ejemplo de un trabajador de mantenimiento que se relaciona con un recurso que utiliza el calendario laboral "Producción".</span><span class="sxs-lookup"><span data-stu-id="915cb-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Figura 1](media/01-work-order-scheduling.png)

<span data-ttu-id="915cb-110">La configuración del calendario para herramientas y activos no es necesaria en relación con la programación de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="915cb-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="915cb-111">La suposición es que las herramientas y activos están disponibles 24 horas al día para el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="915cb-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

