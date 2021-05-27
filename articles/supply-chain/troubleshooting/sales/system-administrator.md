---
title: Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados
description: Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026898"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a><span data-ttu-id="9b0d9-103">Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados</span><span class="sxs-lookup"><span data-stu-id="9b0d9-103">System administrators can't clear order holds because they aren't authorized</span></span>

<span data-ttu-id="9b0d9-104">Número de KB: 4614642</span><span class="sxs-lookup"><span data-stu-id="9b0d9-104">KB number: 4614642</span></span>

## <a name="symptoms"></a><span data-ttu-id="9b0d9-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9b0d9-105">Symptoms</span></span>

<span data-ttu-id="9b0d9-106">Los administradores del sistema no pueden compensar las retenciones de pedidos de ventas a menos que tengan el rol específico que se les asigna en el código de retención de pedidos.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-106">System administrators can't clear sales order holds unless they have the specific role that is assigned in the order hold code.</span></span>

## <a name="resolution"></a><span data-ttu-id="9b0d9-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="9b0d9-107">Resolution</span></span>

<span data-ttu-id="9b0d9-108">El acceso a algunas operaciones, como la compensación de pedidos de ventas retenidos, se controla mediante la configuración de una política comercial.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-108">Access to some operations, such as clearing sales order holds, is driven by the setup of a business policy.</span></span> <span data-ttu-id="9b0d9-109">Por lo general, los administradores del sistema no pueden realizar operaciones de este tipo.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-109">System administrators aren't typically allowed to perform operations of this type.</span></span> 

<span data-ttu-id="9b0d9-110">Con mayor frecuencia, el acceso para realizar una tarea específica se rige por políticas comerciales y solo las personas específicas de una organización están autorizadas para realizar esa tarea.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-110">More often, access to perform a specific task is governed by business policies, and only specific persons in an organization are approved to perform that task.</span></span> <span data-ttu-id="9b0d9-111">Los ejemplos incluyen aprobaciones que son el resultado de aprobaciones de flujo de trabajo y tareas específicas que son el resultado de una configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-111">Examples include approvals that are the result of workflow approvals and specific tasks that are the result of a workflow configuration.</span></span>

<span data-ttu-id="9b0d9-112">Aunque ningún flujo de trabajo está asociado con las retenciones de pedidos, el principio es similar.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-112">Although no workflow is associated with order holds, the principle is similar.</span></span> <span data-ttu-id="9b0d9-113">Un rol relevante designa al grupo específico de personas en una organización que tienen derecho a compensar retenciones de pedidos.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-113">A relevant role designates the specific group of people in an organization who have the right to clear order holds.</span></span> <span data-ttu-id="9b0d9-114">Este derecho no debe otorgarse necesariamente a todos los administradores, porque ese enfoque infringe la política comercial definida.</span><span class="sxs-lookup"><span data-stu-id="9b0d9-114">This right should not necessarily be granted to all administrators, because that approach violates the defined business policy.</span></span>
