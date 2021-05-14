---
title: El lanzamiento no es idónea para limpieza
description: El lanzamiento no es idónea para limpieza
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924336"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="9a2bd-103">El lanzamiento no es idónea para limpieza</span><span class="sxs-lookup"><span data-stu-id="9a2bd-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="9a2bd-104">Código de error: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="9a2bd-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="9a2bd-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9a2bd-105">Symptoms</span></span>

<span data-ttu-id="9a2bd-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="9a2bd-106">The system shows the following error message:</span></span>

> <span data-ttu-id="9a2bd-107">No es posible elegir el lanzamiento %1 para limpieza.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="9a2bd-108">Los datos del lanzamiento no se pueden limpiar.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="9a2bd-109">Causa</span><span class="sxs-lookup"><span data-stu-id="9a2bd-109">Cause</span></span>

<span data-ttu-id="9a2bd-110">El lanzamiento se está procesando actualmente, como lo indica una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="9a2bd-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="9a2bd-111">El campo **Estado de lanzamiento** está establecido en *Ejecución*.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="9a2bd-112">Cuando selecciona **Trabajo por lotes** en el grupo **Lanzamiento** de la pestaña **Lanzamiento** del panel de acciones, el campo **Estado** no está configurado en *Terminado*, *Error* ni *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="9a2bd-113">Por lo tanto, se está ejecutando un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="9a2bd-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="9a2bd-114">Resolution</span></span>

<span data-ttu-id="9a2bd-115">En el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Trabajo por lotes** y luego siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9a2bd-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="9a2bd-116">Si el campo **Estado** está configurado en *Ejecución*: en el panel de acciones, en la pestaña **Trabajo por lotes**, en el grupo **Trabajo por lotes**, seleccione **Ver tareas**.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="9a2bd-117">Puede seguir el progreso actualizando la página **Tareas por lotes**.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="9a2bd-118">Si el campo **Estado** no está configurado en *Ejecución*: en el panel de acciones, en la pestaña **Trabajo por lotes**, en el grupo **Funciones**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="9a2bd-119">En el campo **Seleccionar nuevo estado**, seleccione *Espera*.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="9a2bd-120">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a2bd-120">Then select **OK**.</span></span>
