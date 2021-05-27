---
title: Cuando restablecer un data mart
description: En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart y las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "5989001"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="91529-103">Cuando restablecer un data mart</span><span class="sxs-lookup"><span data-stu-id="91529-103">When to reset a data mart</span></span>

<span data-ttu-id="91529-104">El restablecimiento de un data mart puede llevar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="91529-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="91529-105">Dependiendo de las circunstancias, es posible que esta acción no sea la solución necesaria.</span><span class="sxs-lookup"><span data-stu-id="91529-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="91529-106">En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart, así como las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.</span><span class="sxs-lookup"><span data-stu-id="91529-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="91529-107">¿Cuándo necesito hacer un restablecimiento de data mart?</span><span class="sxs-lookup"><span data-stu-id="91529-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="91529-108">Tenga en cuenta las siguientes preguntas antes de restablecer un data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="91529-109">Responder afirmativamente a una o más preguntas podría indicar que su organización puede beneficiarse al restablecer el data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="91529-110">¿Se restableció la base de datos de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="91529-110">Was the application database restored?</span></span>
- <span data-ttu-id="91529-111">¿Ha abierto un incidente de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas?</span><span class="sxs-lookup"><span data-stu-id="91529-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="91529-112">¿Cuándo no es apropiado restablecer un data mart?</span><span class="sxs-lookup"><span data-stu-id="91529-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="91529-113">Hay algunas circunstancias en las que no recomendamos restablecer un data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="91529-114">Entre estas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="91529-114">These include the following.</span></span> 

- <span data-ttu-id="91529-115">Tiene problemas de rendimiento asociados con una sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="91529-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="91529-116">Si tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="91529-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="91529-117">**Datos perdidos**</span><span class="sxs-lookup"><span data-stu-id="91529-117">**Missing data**</span></span> 
  - <span data-ttu-id="91529-118">**Estado de integración atascado**</span><span class="sxs-lookup"><span data-stu-id="91529-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="91529-119">**Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="91529-120">Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.</span><span class="sxs-lookup"><span data-stu-id="91529-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="91529-121">¿Qué es un restablecimiento de data mart?</span><span class="sxs-lookup"><span data-stu-id="91529-121">What is a data mart reset?</span></span>
- <span data-ttu-id="91529-122">Un restablecimiento solo comenzará cuando se completen las tareas existentes.</span><span class="sxs-lookup"><span data-stu-id="91529-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="91529-123">Esto garantizan que no se inserten datos antiguos.</span><span class="sxs-lookup"><span data-stu-id="91529-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="91529-124">En este punto, es posible que vea un mensaje como, "El restablecimiento del data mart no se pudo procesar debido a una tarea activa.</span><span class="sxs-lookup"><span data-stu-id="91529-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="91529-125">Vuelva a intentarlo más tarde".</span><span class="sxs-lookup"><span data-stu-id="91529-125">Please try again later.”</span></span>
- <span data-ttu-id="91529-126">El restablecimiento deshabilitará las tareas de integración y eliminará todos los datos del data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="91529-127">Se vuelve a habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="91529-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="91529-128">Si restablezco el data mart, ¿perderé los informes que ya diseñé?</span><span class="sxs-lookup"><span data-stu-id="91529-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="91529-129">No, sus informes se almacenan en tablas SQL que no se ven afectadas por un restablecimiento de data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="91529-130">Si le preocupa perder los informes que ha diseñado, puede hacer una copia de seguridad de los diseños que no desea perder.</span><span class="sxs-lookup"><span data-stu-id="91529-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="91529-131">Para hacer una copia de seguridad, abra el diseñador de informes y vaya a **Empresa > Empresas > Bloques de creación > Exportar**.</span><span class="sxs-lookup"><span data-stu-id="91529-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="91529-132">¿Es necesario que todos los usuarios salgan del sistema para restablecer el data mart?</span><span class="sxs-lookup"><span data-stu-id="91529-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="91529-133">No, los usuarios pueden seguir trabajando en el sistema al restablecer el data mart.</span><span class="sxs-lookup"><span data-stu-id="91529-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="91529-134">Sin embargo, no podrán acceder a los informes que se crearon con Financial Reporter hasta que finalice el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="91529-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
