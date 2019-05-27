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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9754c46010e7bbdb2edef0d6e68162f344bb1257
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570420"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="82218-103">Agregar un cálculo a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="82218-103">Add a calculation to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="82218-104">Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="82218-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="82218-105">Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios.</span><span class="sxs-lookup"><span data-stu-id="82218-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="82218-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="82218-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="82218-107">Agregar un cálculo</span><span class="sxs-lookup"><span data-stu-id="82218-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="82218-108">Crear expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="82218-108">Create calculation expression</span></span>
1. <span data-ttu-id="82218-109">Haga clic en Editar expresión.</span><span class="sxs-lookup"><span data-stu-id="82218-109">Click Edit expression.</span></span>
2. <span data-ttu-id="82218-110">En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".</span><span class="sxs-lookup"><span data-stu-id="82218-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="82218-111">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="82218-111">Click Validate.</span></span>
4. <span data-ttu-id="82218-112">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="82218-112">Click Close.</span></span>
5. <span data-ttu-id="82218-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="82218-113">Click OK.</span></span>

