---
title: Crear y asignar estructuras de reglas avanzadas
description: En este tema se explica cómo crear y asignar una estructura de reglas avanzada a una estructura contable.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6a3f7d174c91e357dce8a19ab50a5cd42a85561
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968618"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="faddb-103">Crear y asignar estructuras de reglas avanzadas</span><span class="sxs-lookup"><span data-stu-id="faddb-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="faddb-104">En este tema se explica cómo crear y asignar una estructura de reglas avanzada a una estructura contable.</span><span class="sxs-lookup"><span data-stu-id="faddb-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="faddb-105">Esta guía usa la empresa de demostración de USMF.</span><span class="sxs-lookup"><span data-stu-id="faddb-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="faddb-106">Crear una estructura de reglas avanzada</span><span class="sxs-lookup"><span data-stu-id="faddb-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="faddb-107">Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Estructuras de reglas avanzada**.</span><span class="sxs-lookup"><span data-stu-id="faddb-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="faddb-108">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="faddb-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="faddb-109">En el campo de **Estructura de reglas avanzada**, escriba un nombre para describir la estructura de reglas.</span><span class="sxs-lookup"><span data-stu-id="faddb-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="faddb-110">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="faddb-110">Select **OK**.</span></span>
5. <span data-ttu-id="faddb-111">Seleccione **Agregar segmento**.</span><span class="sxs-lookup"><span data-stu-id="faddb-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="faddb-112">En la lista de segmentos, seleccione una dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="faddb-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="faddb-113">Por ejemplo, **Almacén**.</span><span class="sxs-lookup"><span data-stu-id="faddb-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="faddb-114">Seleccione **Agregar segmento**.</span><span class="sxs-lookup"><span data-stu-id="faddb-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="faddb-115">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="faddb-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="faddb-116">Aplicar una estructura de reglas avanzada a una estructura contable</span><span class="sxs-lookup"><span data-stu-id="faddb-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="faddb-117">Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Configurar estructuras contables**.</span><span class="sxs-lookup"><span data-stu-id="faddb-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="faddb-118">En la lista, busque y seleccione la estructura contable a la que desea aplicar la regla avanzada.</span><span class="sxs-lookup"><span data-stu-id="faddb-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="faddb-119">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="faddb-119">Select **Edit**.</span></span> <span data-ttu-id="faddb-120">También puede seleccionar **Reglas avanzadas** y se le pedirá que ponga la estructura contable en **modo de borrador**.</span><span class="sxs-lookup"><span data-stu-id="faddb-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="faddb-121">Seleccione **Reglas avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="faddb-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="faddb-122">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="faddb-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="faddb-123">En el campo **Regla avanzada**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="faddb-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="faddb-124">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="faddb-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="faddb-125">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="faddb-125">Select **Create**.</span></span>
9. <span data-ttu-id="faddb-126">Seleccione **Agregar nuevos criterios**.</span><span class="sxs-lookup"><span data-stu-id="faddb-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="faddb-127">En el campo **Lugar**, seleccione la cuenta principal o una dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="faddb-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="faddb-128">En el campo **Operador**, seleccione una opción, como **está entre** o **incluye**.</span><span class="sxs-lookup"><span data-stu-id="faddb-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="faddb-129">En el campo **Valor**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="faddb-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="faddb-130">En el campo **hasta**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="faddb-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="faddb-131">Seleccione **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="faddb-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="faddb-132">En la lista, busque la estructura de regla avanzada que desea usar cuando se cumplen los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="faddb-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="faddb-133">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="faddb-133">Select **Add**.</span></span>
17. <span data-ttu-id="faddb-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="faddb-134">Close the page.</span></span>
18. <span data-ttu-id="faddb-135">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="faddb-135">Select **Activate**.</span></span>

