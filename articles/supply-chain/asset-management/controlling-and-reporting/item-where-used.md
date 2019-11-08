---
title: Dónde se usó el artículo
description: En este tema se explica cómo obtener una visión general de dónde se usa un artículo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 511108e689c10e27a42253d95b02e5394f9eb713
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652365"
---
# <a name="item-where-used"></a><span data-ttu-id="1826a-103">Dónde se usó el artículo</span><span class="sxs-lookup"><span data-stu-id="1826a-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1826a-104">Puede realizar un cálculo para que un artículo específico para obtener una visión general de dónde se ha utilizado el artículo en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="1826a-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="1826a-105">Los resultados muestran el contexto en el que el artículo se ha utilizado durante su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="1826a-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="1826a-106">La página **Dónde se usó el artículo** se puede abrir desde el menú principal de Administración de activos y también puede tener acceso a la misma desde las siguientes páginas:</span><span class="sxs-lookup"><span data-stu-id="1826a-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="1826a-107">L. MAT. de activos</span><span class="sxs-lookup"><span data-stu-id="1826a-107">Asset BOM</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="1826a-108">Recambios en los valores predeterminados de tipos de activo</span><span class="sxs-lookup"><span data-stu-id="1826a-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md)

- [<span data-ttu-id="1826a-109">Previsión de artículos en la previsión de valores predeterminados de tipos de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="1826a-109">Item forecast on Maintenance job type defaults forecast</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="1826a-110">Previsión de mantenimiento de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="1826a-110">Work order maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="1826a-111">Solicitud de compra de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="1826a-111">Work order purchase requisition</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="1826a-112">Compra de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="1826a-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="1826a-113">Realizar un cálculo de dónde se usó un artículo</span><span class="sxs-lookup"><span data-stu-id="1826a-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="1826a-114">Haga clic en **Administración de activos** > **Consultas** > **Dónde se usó el artículo** o seleccione el botón **Dónde se uso el artículo** en una de las páginas anteriormente mencionadas.</span><span class="sxs-lookup"><span data-stu-id="1826a-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="1826a-115">En el cuadro de diálogo **Dónde se usó el artículo**, seleccione el artículo para el que desea realizar el cálculo en el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="1826a-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="1826a-116">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de artículo con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="1826a-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="1826a-117">Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de varios niveles de la ubicación técnica, todas las líneas de artículo para una ubicación técnica se mostrará en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1826a-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="1826a-118">Por lo tanto, la relación o la cantidad en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="1826a-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="1826a-119">Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de artículo en todos los niveles de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="1826a-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="1826a-120">En la sección **Incluir**, seleccione "Sí" en los botones de alternar que desea incluir en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="1826a-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="1826a-121">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="1826a-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="1826a-122">En la pestaña **Dónde se usó el artículo** seleccione los botones **Agrupar por** para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="1826a-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="1826a-123">Se resaltarán los botones **Agrupar por** seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1826a-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="1826a-124">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="1826a-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="1826a-125">Si desea mostrar las dimensiones relacionadas con el artículo, haga clic en **Dimensiones de la pantalla** y seleccione las dimensiones que se mostrarán.</span><span class="sxs-lookup"><span data-stu-id="1826a-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="1826a-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1826a-126">Example</span></span>

<span data-ttu-id="1826a-127">En la siguiente imagen, verá un ejemplo de un cálculo de dónde se usó el artículo para el número "1000".</span><span class="sxs-lookup"><span data-stu-id="1826a-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Ejemplo de artículo dónde se usó el cálculo](media/12-controlling-and-reporting.png)

