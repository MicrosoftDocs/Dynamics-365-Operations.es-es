---
title: Configuración de la depreciación de bonificación
description: Este procedimiento muestra cómo crear un método de amortización por depreciación especial y asociarlo con un libro de activos fijos.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad1b7f584d2b2a63dba5f8519ada9d89d6265e7b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815629"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="d2297-103">Configuración de la depreciación de bonificación</span><span class="sxs-lookup"><span data-stu-id="d2297-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2297-104">Este procedimiento muestra cómo crear un método de amortización por depreciación especial y asociarlo con un libro de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="d2297-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="d2297-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="d2297-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="d2297-106">Crear un método de amortización por depreciación especial</span><span class="sxs-lookup"><span data-stu-id="d2297-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="d2297-107">Vaya a Activos fijos > Configuración > Método de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="d2297-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="d2297-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2297-108">Click New.</span></span>
3. <span data-ttu-id="d2297-109">En el campo Método de amortización por depreciación especial, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2297-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="d2297-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2297-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d2297-111">En el campo Porcentaje, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="d2297-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="d2297-112">Defina un importe si no se ha indicado ningún porcentaje.</span><span class="sxs-lookup"><span data-stu-id="d2297-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="d2297-113">Asociar un método de amortización por depreciación especial con un libro del grupo de activos fijos</span><span class="sxs-lookup"><span data-stu-id="d2297-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="d2297-114">Vaya a Activos fijos > Configuración > Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="d2297-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="d2297-115">En la lista, seleccione el grupo de activos fijos que se asociará con el método de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="d2297-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="d2297-116">Haga clic en Libros.</span><span class="sxs-lookup"><span data-stu-id="d2297-116">Click Books.</span></span>
4. <span data-ttu-id="d2297-117">En la lista, seleccione el libro asociado al método de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="d2297-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="d2297-118">Haga clic en Método de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="d2297-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="d2297-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2297-119">Click New.</span></span>
7. <span data-ttu-id="d2297-120">En el campo Método de amortización por depreciación especial, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d2297-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="d2297-121">El porcentaje o el importe predeterminado proviene de la configuración del método de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="d2297-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="d2297-122">En el campo Prioridad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="d2297-122">In the Priority field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]