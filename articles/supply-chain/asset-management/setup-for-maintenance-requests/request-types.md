---
title: Tipos de solicitudes de mantenimiento
description: En este tema se explica cómo configurar tipos de solicitudes de mantenimiento en Administración de activos.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ff80b2f3e23f46467b8a2fe7a2abd805e5e3a20
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808505"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="ae47a-103">Tipos de solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="ae47a-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ae47a-104">Los tipos de solicitudes de mantenimiento se usan para clasificar las solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="ae47a-105">Por ejemplo, puede que tenga tipos de solicitudes de mantenimiento relacionados con el mantenimiento preventivo y el mantenimiento correctivo.</span><span class="sxs-lookup"><span data-stu-id="ae47a-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="ae47a-106">O bien puede tener un tipo de solicitud de mantenimiento especial que se use para administrar la reparación de los activos (reparación interna).</span><span class="sxs-lookup"><span data-stu-id="ae47a-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="ae47a-107">Un tipo de solicitud de mantenimiento define la afiliación con un grupo de estados de ciclo de vida de solicitud de mantenimiento (modelo de ciclo de vida de mantenimiento).</span><span class="sxs-lookup"><span data-stu-id="ae47a-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="ae47a-108">Los modelos de ciclo de vida de solicitud de mantenimiento definen los estados de ciclo de vida que se pueden establecer para una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="ae47a-109">(Ejemplos de estados de ciclo de vida de solicitud de mantenimiento son **Creada**, **Activa** y **Finalizada**).</span><span class="sxs-lookup"><span data-stu-id="ae47a-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="ae47a-110">Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Tipos de solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="ae47a-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="ae47a-111">Seleccione **Nuevo** para crear un tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="ae47a-112">En el campo **Tipo de solicitud de mantenimiento** , especifique un identificador para el tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="ae47a-113">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="ae47a-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="ae47a-114">En el FastTab **General**, en el campo **Modelo de ciclo de vida de solicitud de mantenimiento**, seleccione un modelo de ciclo de vida de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="ae47a-115">En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ae47a-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="ae47a-116">Cuando una solicitud de mantenimiento se convierte en una orden de trabajo, la orden de trabajo obtiene automáticamente el tipo de orden de trabajo relacionado con el tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ae47a-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="ae47a-117">La ilustración siguiente muestra un ejemplo de la página **Tipos de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="ae47a-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Página de tipos de solicitudes de mantenimiento](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]