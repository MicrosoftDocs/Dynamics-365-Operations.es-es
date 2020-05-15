---
title: Crear modelos de previsión para presupuestos de proyectos
description: Este tema describe cómo crear un modelo de previsión para los presupuestos restantes.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321788"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="10348-103">Crear modelos de previsión para presupuestos de proyectos</span><span class="sxs-lookup"><span data-stu-id="10348-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10348-104">Este tema describe cómo crear un modelo de previsión para los presupuestos restantes.</span><span class="sxs-lookup"><span data-stu-id="10348-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="10348-105">Un proyecto sujeto a control presupuestario usa dos tipos de presupuesto: original y restante.</span><span class="sxs-lookup"><span data-stu-id="10348-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="10348-106">Al crear un presupuesto de proyecto, debe especificar los modelos de previsión del presupuesto original y restante que se crearon en la página **Modelos de previsión**.</span><span class="sxs-lookup"><span data-stu-id="10348-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="10348-107">Los presupuestos de proyecto basados en los modelos especificados se crean al comprometer el presupuesto de proyecto.</span><span class="sxs-lookup"><span data-stu-id="10348-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="10348-108">Un modelo de previsión que se use para el control presupuestario no puede tener un submodelo ni usarse como tal.</span><span class="sxs-lookup"><span data-stu-id="10348-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="10348-109">Seleccione **Gestión de proyectos y contabilidad** > **Configurar** > **Previsiones**  > **Modelos de previsión**.</span><span class="sxs-lookup"><span data-stu-id="10348-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="10348-110">Seleccione **Nuevo** para crear un nuevo modelo de previsión y, a continuación, especifique un número de id. de modelo y un nombre para el nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="10348-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="10348-111">Seleccione la opción **Detenido** al valor **Sí** para evitar cualquier cambio en las líneas de previsión del modelo de previsión.</span><span class="sxs-lookup"><span data-stu-id="10348-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="10348-112">Si las líneas de previsión asociadas al modelo generaran previsiones de flujo de efectivo en la contabilidad general, establezca **Incluir en previsiones de flujo de efectivo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="10348-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="10348-113">Para usar la fecha del proyecto como la fecha de la factura, establezca **Fecha de factura prevista** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="10348-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="10348-114">En el campo **Tipo de presupuesto**, seleccione uno de los siguientes tipos de modelo:</span><span class="sxs-lookup"><span data-stu-id="10348-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="10348-115">**Presupuesto original**: use los importes de presupuesto original comprometidos al crear y aprobar el presupuesto inicial.</span><span class="sxs-lookup"><span data-stu-id="10348-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="10348-116">**Presupuesto restante**: use los importes de presupuesto restantes durante la vida del proyecto.</span><span class="sxs-lookup"><span data-stu-id="10348-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="10348-117">Los saldos de este modelo de previsión se reducen con las transacciones reales y aumentan o disminuyen con las revisiones presupuestarias.</span><span class="sxs-lookup"><span data-stu-id="10348-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="10348-118">**Transferir**: use los importes de presupuesto a transferir para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="10348-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="10348-119">La transferencia es un proceso opcional que se puede ejecutar para transferir importes de presupuesto sin usar de un ejercicio a otro.</span><span class="sxs-lookup"><span data-stu-id="10348-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="10348-120">Configure las siguientes opciones según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="10348-120">Set the following options as required:</span></span>

   - <span data-ttu-id="10348-121">Para usar la fecha del proyecto como la fecha de la factura, establezca **Fecha de factura prevista** en Sí.</span><span class="sxs-lookup"><span data-stu-id="10348-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="10348-122">Habilite **Previsión con WIP** para pronosticar en función del trabajo en curso (WIP) y luego seleccione el tipo de WIP.</span><span class="sxs-lookup"><span data-stu-id="10348-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="10348-123">Puede mantener el valor predeterminado **Tipo de presupuesto** como **Ninguno** o introducir un nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="10348-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="10348-124">El tipo de presupuesto no se puede cambiar después de cambiar un registro.</span><span class="sxs-lookup"><span data-stu-id="10348-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="10348-125">Si cambia el tipo de presupuesto predeterminado, todas las demás opciones no estarán disponibles para las actualizaciones y no podrá reutilizar este modelo de previsión.</span><span class="sxs-lookup"><span data-stu-id="10348-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

