--- 
title: "Agregar un cálculo a un modelo de configuración de producto"
description: "Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2db8fb922b085a7f118822ef4fd974ac338f4d99
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="3acb0-103">Agregar un cálculo a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="3acb0-103">Add a calculation to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3acb0-104">Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="3acb0-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="3acb0-105">Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios.</span><span class="sxs-lookup"><span data-stu-id="3acb0-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="3acb0-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="3acb0-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="3acb0-107">Agregar un cálculo</span><span class="sxs-lookup"><span data-stu-id="3acb0-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="3acb0-108">Crear expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="3acb0-108">Create calculation expression</span></span>
1. <span data-ttu-id="3acb0-109">Haga clic en Editar expresión.</span><span class="sxs-lookup"><span data-stu-id="3acb0-109">Click Edit expression.</span></span>
2. <span data-ttu-id="3acb0-110">En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".</span><span class="sxs-lookup"><span data-stu-id="3acb0-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="3acb0-111">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="3acb0-111">Click Validate.</span></span>
4. <span data-ttu-id="3acb0-112">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="3acb0-112">Click Close.</span></span>
5. <span data-ttu-id="3acb0-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3acb0-113">Click OK.</span></span>


