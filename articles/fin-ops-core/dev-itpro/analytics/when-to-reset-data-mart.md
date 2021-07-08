---
title: P+F de restablecimiento de data mart
description: En este tema se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart.
author: jinniew
ms.date: 06/09/2021
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
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266618"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="af992-103">P+F de restablecimiento de data mart</span><span class="sxs-lookup"><span data-stu-id="af992-103">Data mart resets FAQ</span></span>

<span data-ttu-id="af992-104">En este tema se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart.</span><span class="sxs-lookup"><span data-stu-id="af992-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="af992-105">El restablecimiento de la despensa de datos puede ser un proceso que requiere mucho tiempo y, según las circunstancias, puede que no sea la solución necesaria.</span><span class="sxs-lookup"><span data-stu-id="af992-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="af992-106">Por lo tanto, este tema incluye información sobre circunstancias en las que un restablecimiento de la despensa de datos podría ayudar y también circunstancias en las que es poco probable que ayude.</span><span class="sxs-lookup"><span data-stu-id="af992-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="af992-107">¿Qué es un restablecimiento de data mart?</span><span class="sxs-lookup"><span data-stu-id="af992-107">What is a data mart reset?</span></span>

<span data-ttu-id="af992-108">Un restablecimiento de la despensa de datos deshabilitará las tareas de integración, eliminará todos los datos de la despensa de datos y luego volverá a habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="af992-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="af992-109">Para asegurarse de que no se inserten datos antiguos, se puede iniciar un restablecimiento de la despensa de datos solo después de que se completen las tareas existentes.</span><span class="sxs-lookup"><span data-stu-id="af992-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="af992-110">Si intenta restablecer la despensa de datos antes de que se completen todas las tareas, es posible que reciba un mensaje como, "El restablecimiento de la despensa de datos no se pudo procesar debido a una tarea activa.</span><span class="sxs-lookup"><span data-stu-id="af992-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="af992-111">Vuelva a intentarlo más tarde".</span><span class="sxs-lookup"><span data-stu-id="af992-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="af992-112">¿Cuándo tengo que hacer un restablecimiento de data mart?</span><span class="sxs-lookup"><span data-stu-id="af992-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="af992-113">Si una o más de las siguientes afirmaciones se aplican a su situación, su organización puede beneficiarse de un restablecimiento de la despensa de datos:</span><span class="sxs-lookup"><span data-stu-id="af992-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="af992-114">La base de datos de la aplicación se restauró.</span><span class="sxs-lookup"><span data-stu-id="af992-114">The application database was restored.</span></span>
- <span data-ttu-id="af992-115">Ha abierto un vale de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="af992-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="af992-116">¿Cuando es apropiado restablecer un data mart?</span><span class="sxs-lookup"><span data-stu-id="af992-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="af992-117">Aquí tiene algunas de las circunstancias en las que no recomendamos restablecer un data mart:</span><span class="sxs-lookup"><span data-stu-id="af992-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="af992-118">Tiene problemas de rendimiento asociados con una sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="af992-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="af992-119">Tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="af992-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="af992-120">**Datos perdidos** - Si nota que faltan datos, abra un ticket de soporte con Microsoft para revisar el formato de su informe y los posibles problemas de sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="af992-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="af992-121">**Estado de integración atascado**</span><span class="sxs-lookup"><span data-stu-id="af992-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="af992-122">**Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart.</span><span class="sxs-lookup"><span data-stu-id="af992-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="af992-123">Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.</span><span class="sxs-lookup"><span data-stu-id="af992-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="af992-124">Si restablezco el data mart, ¿perderé los informes que ya diseñé?</span><span class="sxs-lookup"><span data-stu-id="af992-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="af992-125">No.</span><span class="sxs-lookup"><span data-stu-id="af992-125">No.</span></span> <span data-ttu-id="af992-126">Sus informes se almacenan en tablas SQL que no se ven afectadas por un restablecimiento de data mart.</span><span class="sxs-lookup"><span data-stu-id="af992-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="af992-127">Si le preocupa perder los informes que ha diseñado, puede hacer una copia de seguridad de los diseños que no desea perder.</span><span class="sxs-lookup"><span data-stu-id="af992-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="af992-128">Para hacer una copia de seguridad de los diseños, abra el diseñador de informes y vaya a **Empresa \> Empresas \> Bloques de creación \> Exportar**.</span><span class="sxs-lookup"><span data-stu-id="af992-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="af992-129">¿Todos los usuarios tienen que salir del sistema antes de que pueda restablecer la despensa de datos?</span><span class="sxs-lookup"><span data-stu-id="af992-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="af992-130">No.</span><span class="sxs-lookup"><span data-stu-id="af992-130">No.</span></span> <span data-ttu-id="af992-131">Los usuarios pueden seguir trabajando en el sistema durante un restablecimiento de data mart.</span><span class="sxs-lookup"><span data-stu-id="af992-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="af992-132">Sin embargo, no podrán acceder a los informes que se crearon con Financial Reporter hasta que finalice el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="af992-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
