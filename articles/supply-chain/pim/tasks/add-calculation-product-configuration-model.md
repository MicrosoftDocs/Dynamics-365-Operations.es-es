---
title: Agregar un cálculo a un modelo de configuración de producto
description: Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812692"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="16d00-103">Agregar un cálculo a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="16d00-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="16d00-104">Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="16d00-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="16d00-105">Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios.</span><span class="sxs-lookup"><span data-stu-id="16d00-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="16d00-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="16d00-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="16d00-107">Agregar un cálculo</span><span class="sxs-lookup"><span data-stu-id="16d00-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="16d00-108">Crear expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="16d00-108">Create calculation expression</span></span>
1. <span data-ttu-id="16d00-109">Haga clic en Editar expresión.</span><span class="sxs-lookup"><span data-stu-id="16d00-109">Click Edit expression.</span></span>
2. <span data-ttu-id="16d00-110">En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".</span><span class="sxs-lookup"><span data-stu-id="16d00-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="16d00-111">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="16d00-111">Click Validate.</span></span>
4. <span data-ttu-id="16d00-112">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="16d00-112">Click Close.</span></span>
5. <span data-ttu-id="16d00-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="16d00-113">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]