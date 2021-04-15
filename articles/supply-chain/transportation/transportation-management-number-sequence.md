---
title: Secuencia numérica de administración de transporte
description: Este tema describe cómo configurar secuencias numéricas para la gestión del transporte.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3da757cbf47e0e1af781b720d17a673e19aeb3b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807689"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="83742-103">Secuencia numérica de administración de transporte</span><span class="sxs-lookup"><span data-stu-id="83742-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83742-104">Utilice la página **Secuencias numéricas** del módulo de gestión de transporte para configurar varios números profesionales.</span><span class="sxs-lookup"><span data-stu-id="83742-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="83742-105">Los transportistas utilizan los números profesionales para organizar y realizar un seguimiento del progreso de cada envío.</span><span class="sxs-lookup"><span data-stu-id="83742-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="83742-106">Crear una secuencia numérica para un número profesional</span><span class="sxs-lookup"><span data-stu-id="83742-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="83742-107">Para crear una secuencia numérica para un número profesional, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83742-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="83742-108">Vaya a **Administración de transporte \> Configuración \> Transportistas \> Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="83742-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="83742-109">Seleccione **Nuevo** para crear una nueva secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="83742-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="83742-110">Escriba un identificador único y un nombre descriptivo para la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="83742-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="83742-111">En el campo **Tipo de secuencia numérica**, *Número profesional* es la única opción.</span><span class="sxs-lookup"><span data-stu-id="83742-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="83742-112">En el campo **Comprobar dígito**, *Comprobar dígito* es la única opción y está configurada como motor genérico.</span><span class="sxs-lookup"><span data-stu-id="83742-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="83742-113">En la ficha desplegable **Secuencia**, proporciona información sobre la secuencia.</span><span class="sxs-lookup"><span data-stu-id="83742-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="83742-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="83742-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="83742-115">Vincular una secuencia numérica a un transportista</span><span class="sxs-lookup"><span data-stu-id="83742-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="83742-116">Para vincular una secuencia numérica a un operador, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83742-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="83742-117">Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.</span><span class="sxs-lookup"><span data-stu-id="83742-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="83742-118">Seleccione un transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="83742-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="83742-119">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="83742-119">Select **Edit**.</span></span>
1. <span data-ttu-id="83742-120">En la ficha desplegable **Visión de conjunto**, seleccione una opción en el campo **Secuencia de números profesional**.</span><span class="sxs-lookup"><span data-stu-id="83742-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="83742-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="83742-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]