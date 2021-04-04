---
title: Configuración del estado del viaje
description: Este tema describe cómo establecer los valores de estado que los usuarios pueden asignar a los viajes.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500895"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="2eb86-103">Configuración del estado del viaje</span><span class="sxs-lookup"><span data-stu-id="2eb86-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="2eb86-104">Sobre la página **Estados del viaje**, establece el conjunto de valores de estado que los usuarios pueden asignar a los viajes.</span><span class="sxs-lookup"><span data-stu-id="2eb86-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="2eb86-105">Los usuarios pueden asignar valores de estado de viaje a todos los niveles de un viaje: viaje, contenedor de envío, folio, orden de compra y artículo (líneas de compra y líneas de orden de transferencia).</span><span class="sxs-lookup"><span data-stu-id="2eb86-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="2eb86-106">Se utilizan para dos propósitos:</span><span class="sxs-lookup"><span data-stu-id="2eb86-106">They are used for two purposes:</span></span>

- <span data-ttu-id="2eb86-107">Informar al usuario sobre el estado del viaje, contenedor de envío, folio, orden de compra o artículo (líneas de compra y líneas de orden de transferencia).</span><span class="sxs-lookup"><span data-stu-id="2eb86-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="2eb86-108">Limite el uso del área de costos evitando modificaciones o eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="2eb86-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="2eb86-109">Para configurar los estados de su viaje, vaya a **Coste de aterrizaje \> Configuración \> Estados del viaje**.</span><span class="sxs-lookup"><span data-stu-id="2eb86-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="2eb86-110">Allí puede agregareliminar y editar estados usando los botones del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="2eb86-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="2eb86-111">Cada área de costo tiene su propio conjunto y jerarquía de estados de viaje.</span><span class="sxs-lookup"><span data-stu-id="2eb86-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="2eb86-112">Por lo tanto, en la página **Estados del viaje**, en el **Área de costo**, primero debe seleccionar el área de costo para la que desea ver o crear estados de viaje.</span><span class="sxs-lookup"><span data-stu-id="2eb86-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="2eb86-113">Luego, para cada estado de viaje, configure los campos que se describen en la siguiente tabla, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2eb86-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="2eb86-114">Tenga en cuenta que el estado de un viaje también se puede cambiar automáticamente por eventos del sistema, como las reglas que se han establecido mediante el uso del centro de control de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2eb86-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="2eb86-115">Campo</span><span class="sxs-lookup"><span data-stu-id="2eb86-115">Field</span></span> | <span data-ttu-id="2eb86-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2eb86-116">Description</span></span> |
|---|---|
| <span data-ttu-id="2eb86-117">Estado de viaje</span><span class="sxs-lookup"><span data-stu-id="2eb86-117">Voyage status</span></span> | <span data-ttu-id="2eb86-118">Especifique el nombre del estado del viaje.</span><span class="sxs-lookup"><span data-stu-id="2eb86-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="2eb86-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="2eb86-119">Description</span></span> | <span data-ttu-id="2eb86-120">Introduzca una descripción del estado del viaje.</span><span class="sxs-lookup"><span data-stu-id="2eb86-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="2eb86-121">Modificar</span><span class="sxs-lookup"><span data-stu-id="2eb86-121">Modify</span></span> | <span data-ttu-id="2eb86-122">Seleccione esta casilla de verificación si los usuarios pueden modificar los viajes que tienen este estado.</span><span class="sxs-lookup"><span data-stu-id="2eb86-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="2eb86-123">Borrar</span><span class="sxs-lookup"><span data-stu-id="2eb86-123">Delete</span></span> | <span data-ttu-id="2eb86-124">Seleccione esta casilla de verificación si los usuarios pueden eliminar los viajes que tienen este estado.</span><span class="sxs-lookup"><span data-stu-id="2eb86-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="2eb86-125">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="2eb86-125">Mandatory</span></span> | <span data-ttu-id="2eb86-126">Seleccione esta casilla de verificación para que el estado del viaje sea obligatorio, de modo que no se pueda omitir.</span><span class="sxs-lookup"><span data-stu-id="2eb86-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="2eb86-127">Principal</span><span class="sxs-lookup"><span data-stu-id="2eb86-127">Parent</span></span> | <span data-ttu-id="2eb86-128">Utilice este campo para establecer una jerarquía entre los valores de estado.</span><span class="sxs-lookup"><span data-stu-id="2eb86-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="2eb86-129">Los estados de la travesía se pueden cambiar (ya sea de forma manual o automática) solo hacia abajo en la jerarquía, de un estado principal a uno de sus estados secundarios.</span><span class="sxs-lookup"><span data-stu-id="2eb86-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="2eb86-130">Debe configurar solo los estados de viaje específicos que utiliza su organización.</span><span class="sxs-lookup"><span data-stu-id="2eb86-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="2eb86-131">Los estados de viaje típicos incluyen *Confirmado*, *Mercancías en tránsito*, *Recibido*, *Listo para calcular el costo* y *Estimado*.</span><span class="sxs-lookup"><span data-stu-id="2eb86-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="2eb86-132">Sin embargo, pueden estar presentes otros estados.</span><span class="sxs-lookup"><span data-stu-id="2eb86-132">However, other statuses might be present.</span></span>
