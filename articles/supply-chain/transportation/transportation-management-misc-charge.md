---
title: Gastos varios de gestión de transporte
description: Este tema explica cómo los cargos generados por el transporte deben asociarse con un código de cargo.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "4437323"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="19b27-103">Gastos varios de gestión de transporte</span><span class="sxs-lookup"><span data-stu-id="19b27-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19b27-104">Como sucede con los cargos varios, los cargos generados por el transporte deben asociarse con un código de cargo.</span><span class="sxs-lookup"><span data-stu-id="19b27-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="19b27-105">De lo contrario, no se volverán a agregar al pedido como un cargo diverso.</span><span class="sxs-lookup"><span data-stu-id="19b27-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="19b27-106">El **Código de cargos** determina cómo se contabiliza el cargo en relación con el pedido y la línea de pedido donde se agrega.</span><span class="sxs-lookup"><span data-stu-id="19b27-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="19b27-107">Vaya a **Gestión de transporte > Configuración > Clasificación > Cargos varios** para definir los criterios de calificación que determinan cuándo un **Código de cargos** se aplica a un cargo.</span><span class="sxs-lookup"><span data-stu-id="19b27-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="19b27-108">Debe tener al menos una configuración para cada ajuste correspondiente de **Módulo de cargas** (*Cliente* y *Vendedor*) donde **Tipo de cargos varios** se establece en *Ninguno*.</span><span class="sxs-lookup"><span data-stu-id="19b27-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="19b27-109">Si falta, los cargos varios *no* se agregan al pedido.</span><span class="sxs-lookup"><span data-stu-id="19b27-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>
