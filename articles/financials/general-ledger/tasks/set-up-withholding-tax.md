---
title: Configurar retención de impuestos
description: Este tema explica cómo configurar la retención de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e7018c79e54841d0729636b08ad475a94d20d5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834743"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="fde19-103">Configurar retención de impuestos</span><span class="sxs-lookup"><span data-stu-id="fde19-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fde19-104">Este tema explica cómo configurar la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="fde19-105">La *retención de impuestos* es un impuesto sobre los proveedores que no crea transacciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="fde19-106">La retención de impuestos calculada sobre los pagos de proveedor es un pasivo.</span><span class="sxs-lookup"><span data-stu-id="fde19-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="fde19-107">Por lo tanto, tan solo las cuentas de balance de situación o las cuentas de pasivos son cuentas validas para el registro de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="fde19-108">Esta guía de la tarea demuestra cómo configurar la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="fde19-109">Vaya al **panel de navegación > Módulos > Impuestos > Impuestos indirectos > Retención de impuestos > Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="fde19-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="fde19-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fde19-110">Select **New**.</span></span>
3. <span data-ttu-id="fde19-111">En el campo **Código de retención de impuestos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fde19-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="fde19-112">En el campo **Nombre de la retención de impuestos**, especifique el nombre del código de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="fde19-113">En el campo **Cuenta principal**, seleccione la cuenta principal para registrar el pasivo de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="fde19-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fde19-114">Select **Save**.</span></span>
7. <span data-ttu-id="fde19-115">Seleccione **Valores** y marque el registro deseado en la lisat.</span><span class="sxs-lookup"><span data-stu-id="fde19-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="fde19-116">En el campo **Valor**, especifique un porcentaje usado para el cálculo de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="fde19-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fde19-117">Select **Save**.</span></span>
10. <span data-ttu-id="fde19-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fde19-118">Close the page.</span></span>
11. <span data-ttu-id="fde19-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fde19-119">Select **Save**.</span></span>
12. <span data-ttu-id="fde19-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fde19-120">Close the page.</span></span>
13. <span data-ttu-id="fde19-121">Vaya a **Panel de navegación > Módulos > Impuestos > Impuestos indirectos > Retención de impuestos > Grupos de retenciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="fde19-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="fde19-122">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fde19-122">Select **New**.</span></span>
15. <span data-ttu-id="fde19-123">En el campo **Grupo de retenciones de impuestos**, especifique el identificador del grupo de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="fde19-124">En el campo **Descripción**, especifique el nombre del grupo de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="fde19-125">En el campo **Código de retención de impuestos**, seleccione el código de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fde19-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="fde19-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fde19-126">Select **Save**.</span></span>
19. <span data-ttu-id="fde19-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fde19-127">Close the page.</span></span>

