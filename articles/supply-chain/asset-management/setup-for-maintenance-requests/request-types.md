---
title: Tipos de solicitudes de mantenimiento
description: En este tema se explica cómo configurar tipos de solicitudes de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e4f622cda62cad13a8146cbc26bc2e5f1a45222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261198"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="42d55-103">Tipos de solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="42d55-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="42d55-104">Los tipos de solicitudes de mantenimiento se usan para clasificar las solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="42d55-105">Por ejemplo, puede que tenga tipos de solicitudes de mantenimiento relacionados con el mantenimiento preventivo y el mantenimiento correctivo.</span><span class="sxs-lookup"><span data-stu-id="42d55-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="42d55-106">O bien puede tener un tipo de solicitud de mantenimiento especial que se use para administrar la reparación de los activos (reparación interna).</span><span class="sxs-lookup"><span data-stu-id="42d55-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="42d55-107">Un tipo de solicitud de mantenimiento define la afiliación con un grupo de estados de ciclo de vida de solicitud de mantenimiento (modelo de ciclo de vida de mantenimiento).</span><span class="sxs-lookup"><span data-stu-id="42d55-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="42d55-108">Los modelos de ciclo de vida de solicitud de mantenimiento definen los estados de ciclo de vida que se pueden establecer para una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="42d55-109">(Ejemplos de estados de ciclo de vida de solicitud de mantenimiento son **Creada**, **Activa** y **Finalizada**).</span><span class="sxs-lookup"><span data-stu-id="42d55-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="42d55-110">Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Tipos de solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="42d55-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="42d55-111">Seleccione **Nuevo** para crear un tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="42d55-112">En el campo **Tipo de solicitud de mantenimiento** , especifique un identificador para el tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="42d55-113">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="42d55-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="42d55-114">En el FastTab **General**, en el campo **Modelo de ciclo de vida de solicitud de mantenimiento**, seleccione un modelo de ciclo de vida de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="42d55-115">En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="42d55-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="42d55-116">Cuando una solicitud de mantenimiento se convierte en una orden de trabajo, la orden de trabajo obtiene automáticamente el tipo de orden de trabajo relacionado con el tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="42d55-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="42d55-117">La ilustración siguiente muestra un ejemplo de la página **Tipos de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="42d55-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Página de tipos de solicitudes de mantenimiento](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]