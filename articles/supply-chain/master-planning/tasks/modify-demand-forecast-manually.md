---
title: Modificar manualmente una previsión de demanda
description: Este tema describe cómo modificar la previsión de un artículo
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889033"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="a11d5-103">Modificar manualmente una previsión de demanda</span><span class="sxs-lookup"><span data-stu-id="a11d5-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a11d5-104">Este procedimiento muestra cómo modificar la previsión de un artículo.</span><span class="sxs-lookup"><span data-stu-id="a11d5-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="a11d5-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a11d5-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a11d5-106">Este procedimiento se va a utilizar para el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="a11d5-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="a11d5-107">Modificación de la previsión para un artículo seleccionado</span><span class="sxs-lookup"><span data-stu-id="a11d5-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="a11d5-108">Para modificar la previsión para un artículo seleccionado:</span><span class="sxs-lookup"><span data-stu-id="a11d5-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="a11d5-109">Vaya a **Módulos \> Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="a11d5-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="a11d5-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a11d5-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="a11d5-111">Seleccione el artículo para el que desee modificar la previsión.</span><span class="sxs-lookup"><span data-stu-id="a11d5-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="a11d5-112">En el panel de acciones, abra la pestaña **Plan** y seleccione **Previsión de demanda**.</span><span class="sxs-lookup"><span data-stu-id="a11d5-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="a11d5-113">En la lista, seleccione una fila.</span><span class="sxs-lookup"><span data-stu-id="a11d5-113">In the list, select a row.</span></span> <span data-ttu-id="a11d5-114">Si no hay líneas de previsión, cree una nueva seleccionando **Nuevo** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="a11d5-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="a11d5-115">En el campo **Cantidad de ventas**, introduzca un número positivo.</span><span class="sxs-lookup"><span data-stu-id="a11d5-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="a11d5-116">Este número representa la cantidad prevista para el artículo.</span><span class="sxs-lookup"><span data-stu-id="a11d5-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="a11d5-117">Se mostrará un error si ingresa un número negativo.</span><span class="sxs-lookup"><span data-stu-id="a11d5-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="a11d5-118">Rellene los demás campos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a11d5-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="a11d5-119">Seleccione **Guardar** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="a11d5-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="a11d5-120">Modificar la previsión de uno o más elementos en Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a11d5-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="a11d5-121">Para modificar la previsión de uno o más elementos en Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="a11d5-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="a11d5-122">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a11d5-122">Do one of the following:</span></span>
    - <span data-ttu-id="a11d5-123">Abra la página **Previsión de demanda** para cualquier elemento (no importa cuál) como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a11d5-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="a11d5-124">Vaya a **Planificación maestra \> Previsión \> Previsión de demanda \> Previsión de la demanda ajustada**.</span><span class="sxs-lookup"><span data-stu-id="a11d5-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="a11d5-125">En el panel de acciones, seleccione **Abrir en Microsoft Office \> Entradas de previsión de demanda**.</span><span class="sxs-lookup"><span data-stu-id="a11d5-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="a11d5-126">Seleccione una ubicación de descarga, guarde y luego abra el archivo descargado en Excel.</span><span class="sxs-lookup"><span data-stu-id="a11d5-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="a11d5-127">Si ve una advertencia, elija **Permitir la edición**.</span><span class="sxs-lookup"><span data-stu-id="a11d5-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="a11d5-128">En Excel, inicie sesión en Supply Chain Management utilizando el panel de tareas de Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="a11d5-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="a11d5-129">Debes iniciar sesión con la opción **Mantenme conectado** habilitada y debe confiar en la aplicación de conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="a11d5-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="a11d5-130">La hoja de cálculo de Excel ahora muestra todas las líneas de pronóstico de demanda actuales para su empresa.</span><span class="sxs-lookup"><span data-stu-id="a11d5-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="a11d5-131">Puede agregar, eliminar y editar líneas de previsión de demanda según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a11d5-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="a11d5-132">Seleccione **Publicar** en el panel de tareas de Microsoft Dynamics para volver a cargar los cambios en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a11d5-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
