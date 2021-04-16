---
title: Configurar la visualización de lotes más antiguos del almacén en un dispositivo móvil
description: Este tema describe cómo configurar un dispositivo móvil para mostrar una lista de ubicaciones con lotes más antiguos que la ubicación actual de una línea de trabajo.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5156b17b9eddc2c3127b6d91fd8cd7d519d240e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838307"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="fedcc-103">Configurar la visualización de lotes más antiguos del almacén en un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="fedcc-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fedcc-104">La configuración **Visualización de lotes más antiguos del almacén** permite mostrar una lista de ubicaciones con lotes más antiguos que la ubicación actual de la línea del trabajo.</span><span class="sxs-lookup"><span data-stu-id="fedcc-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="fedcc-105">La lista de ubicaciones que aparece incluye información sobre los lotes más antiguos de la ubicación con la fecha de vencimiento y el inventario físico de cada lote.</span><span class="sxs-lookup"><span data-stu-id="fedcc-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="fedcc-106">Puede elegir seleccionar en una nueva ubicación o continuar seleccionando en la ubicación actual.</span><span class="sxs-lookup"><span data-stu-id="fedcc-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="fedcc-107">Selección en una nueva ubicación - si selecciona una nueva ubicación para elegir, la línea del trabajo actual se actualizará para usar la nueva ubicación y el trabajo continuará como de costumbre con la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="fedcc-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="fedcc-108">Para que la nueva ubicación sea válida, debe tener cantidad suficiente disponible para toda la línea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fedcc-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="fedcc-109">Si la cantidad requerida no está disponible, la línea del trabajo no se actualizará, y la lista se mostrará.</span><span class="sxs-lookup"><span data-stu-id="fedcc-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="fedcc-110">Continuar seleccionando en la ubicación actual - si continúa con la ubicación de la línea del trabajo actual, las cantidades de la línea de trabajo se continuarán seleccionando en la ubicación original.</span><span class="sxs-lookup"><span data-stu-id="fedcc-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="fedcc-111">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="fedcc-111">Where it applies</span></span>
<span data-ttu-id="fedcc-112">Visualizar lotes más antiguos del almacén se configura en elementos de menú del dispositivo móvil y afecta a la selección de artículos del lote siguiente.</span><span class="sxs-lookup"><span data-stu-id="fedcc-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="fedcc-113">Configuración de la visualización de lotes más antiguos del almacén</span><span class="sxs-lookup"><span data-stu-id="fedcc-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="fedcc-114">La configuración de **Visualización de lotes más antiguos del almacén** está disponible en elementos de menú del dispositivo móvil cuando la opción **Seleccionar lote más antiguo** se establece en **Advertir**.</span><span class="sxs-lookup"><span data-stu-id="fedcc-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="fedcc-115">En **Gestión de almacenes** > **Configuración** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**, establezca **Usar trabajo existente** en **Sí** para el elemento de menú, y seleccione **Advertir** en el campo **Seleccionar lote más antiguo**.</span><span class="sxs-lookup"><span data-stu-id="fedcc-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]