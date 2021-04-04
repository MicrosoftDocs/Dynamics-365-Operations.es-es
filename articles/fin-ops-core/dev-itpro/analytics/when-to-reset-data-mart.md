---
title: Cuando restablecer un data mart
description: En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart y las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71324d4aa2d20dd6ae4729412a017d130ab0144f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563748"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="4b53f-103">Cuando restablecer un data mart</span><span class="sxs-lookup"><span data-stu-id="4b53f-103">When to reset a data mart</span></span>

<span data-ttu-id="4b53f-104">El restablecimiento de un data mart puede llevar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="4b53f-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="4b53f-105">Dependiendo de las circunstancias, es posible que esta acción no sea la solución necesaria.</span><span class="sxs-lookup"><span data-stu-id="4b53f-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="4b53f-106">En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart, así como las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.</span><span class="sxs-lookup"><span data-stu-id="4b53f-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="4b53f-107">¿Cuándo necesita hacer restablecer un data mart?</span><span class="sxs-lookup"><span data-stu-id="4b53f-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="4b53f-108">Tenga en cuenta las siguientes preguntas antes de restablecer un data mart.</span><span class="sxs-lookup"><span data-stu-id="4b53f-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="4b53f-109">Responder afirmativamente a una o más preguntas podría indicar que su organización puede beneficiarse al restablecer el data mart.</span><span class="sxs-lookup"><span data-stu-id="4b53f-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="4b53f-110">La base de datos de aplicaciones se restauró, pero la base de datos de data mart no se restauró.</span><span class="sxs-lookup"><span data-stu-id="4b53f-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="4b53f-111">Ve datos incorrectos para un período contable, que no es el resultado de un problema con el diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="4b53f-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="4b53f-112">Ve datos incorrectos para un período contable y los registros se enumeran en Intentos de integración en la página **Estado de integración** en el Diseñador de informes (inicie el Diseñador de informes y seleccione **Herramientas> Estado de integración**).</span><span class="sxs-lookup"><span data-stu-id="4b53f-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="4b53f-113">Ha abierto un incidente de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="4b53f-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="4b53f-114">¿Cuándo no es apropiado restablecer un data mart?</span><span class="sxs-lookup"><span data-stu-id="4b53f-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="4b53f-115">Hay algunas circunstancias en las que no recomendamos restablecer un data mart.</span><span class="sxs-lookup"><span data-stu-id="4b53f-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="4b53f-116">Entre estas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b53f-116">These include the following.</span></span> 

- <span data-ttu-id="4b53f-117">Siempre que el motivo no se mencione en este tema.</span><span class="sxs-lookup"><span data-stu-id="4b53f-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="4b53f-118">Tiene problemas de rendimiento asociados a una sincronización de datos. En esta circunstancia, el restablecimiento del data mart probablemente no ayudará.</span><span class="sxs-lookup"><span data-stu-id="4b53f-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="4b53f-119">Si tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="4b53f-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="4b53f-120">**Datos perdidos**: primero, elimine los problemas de diseño de informes y los problemas de tiempo de sincronización de datos; por ejemplo, observe que el mapa de hechos no se ha ejecutado desde que se publicaron los datos que faltan.</span><span class="sxs-lookup"><span data-stu-id="4b53f-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="4b53f-121">**Estado de integración atascado**: si la integración es lenta o parece bloqueada, es poco probable que el restablecimiento del data mart resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="4b53f-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="4b53f-122">**Los intentos de restablecimiento no han tenido éxito**: si se han realizado varios intentos de completar un restablecimiento y no han tenido éxito debido a que faltan datos, recomendamos abrir un incidente de soporte y trabajar con un ingeniero de soporte para analizar su situación antes de intentar restablecer el data mart nuevamente.</span><span class="sxs-lookup"><span data-stu-id="4b53f-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="4b53f-123">**Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart.</span><span class="sxs-lookup"><span data-stu-id="4b53f-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="4b53f-124">Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.</span><span class="sxs-lookup"><span data-stu-id="4b53f-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="4b53f-125">Lo que no hace un restablecimiento de data mart</span><span class="sxs-lookup"><span data-stu-id="4b53f-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="4b53f-126">Un restablecimiento solo comenzará cuando se completen las tareas existentes.</span><span class="sxs-lookup"><span data-stu-id="4b53f-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="4b53f-127">Esto garantizan que no se inserten datos antiguos.</span><span class="sxs-lookup"><span data-stu-id="4b53f-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="4b53f-128">En este punto, es posible que vea un mensaje como, "El restablecimiento del data mart no se pudo procesar debido a una tarea activa.</span><span class="sxs-lookup"><span data-stu-id="4b53f-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="4b53f-129">Vuelva a intentarlo más tarde".</span><span class="sxs-lookup"><span data-stu-id="4b53f-129">Please try again later.”</span></span>
- <span data-ttu-id="4b53f-130">El restablecimiento deshabilitará las tareas de integración y eliminará todos los datos del data mart.</span><span class="sxs-lookup"><span data-stu-id="4b53f-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="4b53f-131">Se vuelve a habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="4b53f-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="4b53f-132">Los siguientes puntos especifican dos cosas que el restablecimiento de un data mart *no* hará.</span><span class="sxs-lookup"><span data-stu-id="4b53f-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="4b53f-133">Los restablecimientos no borran los diseños de informes.</span><span class="sxs-lookup"><span data-stu-id="4b53f-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="4b53f-134">Los restablecimientos no borran los datos de la empresa o los datos del usuario a menos que se seleccionen.</span><span class="sxs-lookup"><span data-stu-id="4b53f-134">Resets do not clear company data or user data unless selected.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]