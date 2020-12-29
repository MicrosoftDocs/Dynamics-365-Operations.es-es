---
title: Crear reglas avanzadas para diarios
description: Este procedimiento le guía por la creación de reglas avanzadas para los diarios.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: ea6ca24d27bb5b00bbe31060ce2f7e40bf2fb335
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447681"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="87bc4-103">Crear reglas avanzadas para diarios</span><span class="sxs-lookup"><span data-stu-id="87bc4-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="87bc4-104">Este procedimiento le guía por la creación de reglas avanzadas para los diarios.</span><span class="sxs-lookup"><span data-stu-id="87bc4-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="87bc4-105">Esto incluye la configuración de restricciones de registro de usuario y de control de diarios.</span><span class="sxs-lookup"><span data-stu-id="87bc4-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="87bc4-106">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="87bc4-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="87bc4-107">Configurar el control del diario</span><span class="sxs-lookup"><span data-stu-id="87bc4-107">Set up journal control</span></span>
1. <span data-ttu-id="87bc4-108">En el **Panel de exploración**, vaya a **Módulos > Contabilidad general > Configuración del diario > Nombres del diario**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="87bc4-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87bc4-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="87bc4-110">En el **panel de acciones**, haga clic en **Control del diario**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="87bc4-111">En la ficha desplegable, **¿Qué tipos de cuentas se pueden registrar?**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="87bc4-112">En el campo **Cuentas de la empresa**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87bc4-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="87bc4-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87bc4-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="87bc4-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87bc4-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="87bc4-115">En la ficha desplegable **¿Qué valores del segmento son válidos para este diario?**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="87bc4-116">En el campo **Estructura contable**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87bc4-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="87bc4-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87bc4-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="87bc4-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87bc4-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="87bc4-119">En el campo **Segmento**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87bc4-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="87bc4-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87bc4-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="87bc4-121">En el campo **Valor inicial**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87bc4-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="87bc4-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87bc4-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="87bc4-123">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87bc4-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="87bc4-124">En el campo **Valor final**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87bc4-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="87bc4-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87bc4-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="87bc4-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87bc4-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="87bc4-127">Configuración de restricciones de registro</span><span class="sxs-lookup"><span data-stu-id="87bc4-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="87bc4-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="87bc4-128">Close the page.</span></span>
2. <span data-ttu-id="87bc4-129">Haga clic en **Restricciones de registro**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="87bc4-130">En **¿Cómo desea configurar las restricciones de registro?**, seleccione "Por grupo de usuarios".</span><span class="sxs-lookup"><span data-stu-id="87bc4-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="87bc4-131">En el árbol, active "el grupo al que desea permitir el registro para este nombre de diario”.</span><span class="sxs-lookup"><span data-stu-id="87bc4-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="87bc4-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87bc4-132">Click **OK**.</span></span>

