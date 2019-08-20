---
title: Agregar un cálculo a un modelo de configuración de producto
description: Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39450b5aef2fb7b57492a52011f4b0db9dc8ff2e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845057"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="c0089-103">Agregar un cálculo a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="c0089-103">Add a calculation to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c0089-104">Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="c0089-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="c0089-105">Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios.</span><span class="sxs-lookup"><span data-stu-id="c0089-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="c0089-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c0089-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="c0089-107">Agregar un cálculo</span><span class="sxs-lookup"><span data-stu-id="c0089-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="c0089-108">Crear expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="c0089-108">Create calculation expression</span></span>
1. <span data-ttu-id="c0089-109">Haga clic en Editar expresión.</span><span class="sxs-lookup"><span data-stu-id="c0089-109">Click Edit expression.</span></span>
2. <span data-ttu-id="c0089-110">En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".</span><span class="sxs-lookup"><span data-stu-id="c0089-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="c0089-111">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="c0089-111">Click Validate.</span></span>
4. <span data-ttu-id="c0089-112">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="c0089-112">Click Close.</span></span>
5. <span data-ttu-id="c0089-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c0089-113">Click OK.</span></span>

