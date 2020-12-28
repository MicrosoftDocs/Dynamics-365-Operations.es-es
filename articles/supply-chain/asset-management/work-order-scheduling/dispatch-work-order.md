---
title: Distribuir orden de trabajo
description: En este tema se explica cómo distribuir órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d46beb04923d06aa8ccec05355731aa1b3f27c5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436677"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="f9ba8-103">Distribuir orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="f9ba8-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f9ba8-104">Puede programar una orden de trabajo o varias para un trabajador mediante la funcionalidad **Distribuir** .</span><span class="sxs-lookup"><span data-stu-id="f9ba8-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="f9ba8-105">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f9ba8-106">Seleccione la orden de trabajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="f9ba8-107">En la ficha **General**, haga clic en **Distribuir**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="f9ba8-108">En el cuadro de diálogo **Programar orden de trabajo**, seleccione el trabajador en el campo **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="f9ba8-109">En el campo **Horas de la programación**, puede insertar las horas de trabajo esperadas en el caso de que las horas de trabajo esperadas difieran de las horas previstas.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="f9ba8-110">En el campo **Inicio programado**, puede editar la fecha y hora de inicio, si procede.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="f9ba8-111">Si el proceso de programación debe respetar las limitaciones de capacidad respecto a los recursos ya programados en otros trabajos, asegúrese de que los botones de alternar **Activo**, **Herramienta** y **Trabajador** están configurados en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="f9ba8-112">Si desea ver información detallada sobre los procesos de programación, seleccione **Sí** en el botón de alternar **Detallado**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="f9ba8-113">Esto significa que la información detallada sobre las puntuaciones calculadas en la orden de trabajo se mostrará en el registro de información.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="f9ba8-114">Seleccione **Sí** en el botón de alternar **Omitir programación** para omitir días cerrados en el calendario (se aplica a activo, trabajador y herramientas).</span><span class="sxs-lookup"><span data-stu-id="f9ba8-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="f9ba8-115">Seleccione **Sí** en el botón de alternar **Ignorar ejecución programada** para ignorar las limitaciones que puedan haberse seleccionado en la orden de trabajo en conexión con la programación.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="f9ba8-116">Para obtener información acerca de la configuración de la ejecución programada, consulte la sección [Ejecución programada](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="f9ba8-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="f9ba8-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-117">Click **OK**.</span></span> <span data-ttu-id="f9ba8-118">El estado de ciclo de vida de la orden de trabajo se actualiza automáticamente según el estado de ciclo de vida **Programado** especificado en **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Modelos del ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="f9ba8-119">La ilustración siguiente muestra un ejemplo de las selecciones de distribución en el cuadro de diálogo **Programar orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Figura 1](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="f9ba8-121">Si desea eliminar la programación en una orden de trabajo, seleccione la orden de trabajo en **Todas las órdenes de trabajo** y haga clic en **Eliminar programación** en la pestaña **General**. Recuerde actualizar manualmente el estado de ciclo de vida de la orden de trabajo si elimina la programación.</span><span class="sxs-lookup"><span data-stu-id="f9ba8-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>

