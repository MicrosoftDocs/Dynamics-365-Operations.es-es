---
title: Crear reglas avanzadas para diarios
description: Este procedimiento le guía por la creación de reglas avanzadas para los diarios.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ec0db1bc5018649acaca05c71a510880b415777
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846688"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="6ef0e-103">Crear reglas avanzadas para diarios</span><span class="sxs-lookup"><span data-stu-id="6ef0e-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6ef0e-104">Este procedimiento le guía por la creación de reglas avanzadas para los diarios.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="6ef0e-105">Esto incluye la configuración de restricciones de registro de usuario y de control de diarios.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="6ef0e-106">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="6ef0e-107">Configurar el control del diario</span><span class="sxs-lookup"><span data-stu-id="6ef0e-107">Set up journal control</span></span>
1. <span data-ttu-id="6ef0e-108">Vaya a Contabilidad general > Configuración de diario > Nombres de diarios.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="6ef0e-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6ef0e-110">Haga clic en Control del diario.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-110">Click Journal control.</span></span>
4. <span data-ttu-id="6ef0e-111">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-111">Click Add.</span></span>
5. <span data-ttu-id="6ef0e-112">En el campo Cuentas de la empresa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6ef0e-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6ef0e-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="6ef0e-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-115">Click Add.</span></span>
9. <span data-ttu-id="6ef0e-116">En el campo Estructura contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="6ef0e-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6ef0e-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="6ef0e-119">En el campo Segmento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="6ef0e-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="6ef0e-121">En el campo Valor inicial, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="6ef0e-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="6ef0e-123">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="6ef0e-124">En el campo Valor final, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="6ef0e-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="6ef0e-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="6ef0e-127">Configuración de restricciones de registro</span><span class="sxs-lookup"><span data-stu-id="6ef0e-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="6ef0e-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-128">Close the page.</span></span>
2. <span data-ttu-id="6ef0e-129">Haga clic en Restricciones de registro.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="6ef0e-130">En ¿Cómo desea configurar las restricciones de registro?, seleccione Por grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="6ef0e-131">En el árbol, active "el grupo al que desea permitir el registro para este nombre de diario”.</span><span class="sxs-lookup"><span data-stu-id="6ef0e-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="6ef0e-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6ef0e-132">Click OK.</span></span>

