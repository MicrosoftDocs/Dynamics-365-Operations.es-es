---
title: Modificación manual de una previsión de demanda
description: Este procedimiento muestra cómo modificar la previsión de un artículo.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca6b881bc094b68d1bbf8c7c20b65418e42b28e3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835888"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="7f37c-103">Modificación manual de una previsión de demanda</span><span class="sxs-lookup"><span data-stu-id="7f37c-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7f37c-104">Este procedimiento muestra cómo modificar la previsión de un artículo.</span><span class="sxs-lookup"><span data-stu-id="7f37c-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="7f37c-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="7f37c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7f37c-106">Esta grabación va destinada al planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="7f37c-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="7f37c-107">Modificación de la previsión para un artículo</span><span class="sxs-lookup"><span data-stu-id="7f37c-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="7f37c-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="7f37c-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="7f37c-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7f37c-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7f37c-110">Seleccione el artículo para el que desee modificar la previsión.</span><span class="sxs-lookup"><span data-stu-id="7f37c-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="7f37c-111">Por ejemplo, puede seleccionar el artículo D0001.</span><span class="sxs-lookup"><span data-stu-id="7f37c-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="7f37c-112">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="7f37c-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="7f37c-113">Haga clic en Previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="7f37c-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="7f37c-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7f37c-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7f37c-115">Si no hay líneas de previsión, cree una nueva línea  .</span><span class="sxs-lookup"><span data-stu-id="7f37c-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="7f37c-116">haciendo clic en Nuevo en la barra de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f37c-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="7f37c-117">En el campo Cantidad de ventas, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="7f37c-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="7f37c-118">Este número representa la cantidad prevista para el artículo.</span><span class="sxs-lookup"><span data-stu-id="7f37c-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="7f37c-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7f37c-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="7f37c-120">Modificación de la previsión en Excel</span><span class="sxs-lookup"><span data-stu-id="7f37c-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="7f37c-121">Haga clic en Abrir en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7f37c-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="7f37c-122">Haga clic en Editar previsión de demanda en Excel.</span><span class="sxs-lookup"><span data-stu-id="7f37c-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="7f37c-123">En Excel, puede agregar, eliminar y editar líneas de previsión de demanda.</span><span class="sxs-lookup"><span data-stu-id="7f37c-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="7f37c-124">Si no puede ver los datos en Excel, necesita iniciar sesión en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con la opción Mantener la sesión iniciada habilitada, así como es preciso que confíe en la aplicación de conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="7f37c-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

