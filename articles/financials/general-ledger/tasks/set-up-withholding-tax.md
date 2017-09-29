--- 
title: "Configurar retención de impuestos"
description: "La retención de impuestos es un impuesto sobre los proveedores que no crea transacciones de impuestos."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dc4c0745235052cb4145bc7083fef1a88c8bb5c9
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="f0e5c-103">Configurar retención de impuestos</span><span class="sxs-lookup"><span data-stu-id="f0e5c-103">Set up withholding tax</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0e5c-104">La retención de impuestos es un impuesto sobre los proveedores que no crea transacciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="f0e5c-105">La retención de impuestos calculada sobre los pagos de proveedor es un pasivo.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="f0e5c-106">Por lo tanto, tan solo las cuentas de balance de situación o las cuentas de pasivos son cuentas validas para el registro de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="f0e5c-107">Esta guía de la tarea demuestra cómo configurar la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="f0e5c-108">Vaya a Impuestos > Impuestos indirectos > Retención de impuestos > Códigos de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="f0e5c-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-109">Click New.</span></span>
3. <span data-ttu-id="f0e5c-110">En el campo de código de retenciones de impuestos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="f0e5c-111">En el campo Nombre de la retención de impuestos, especifique el nombre del código de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="f0e5c-112">En el campo Cuenta principal, seleccione la cuenta principal para registrar el pasivo de la retención de deuda tributaria.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="f0e5c-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-113">Click Save.</span></span>
7. <span data-ttu-id="f0e5c-114">Haga clic en Valores.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-114">Click Values.</span></span>
8. <span data-ttu-id="f0e5c-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="f0e5c-116">En el campo Valor, especifique un porcentaje usado para el cálculo de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="f0e5c-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-117">Click Save.</span></span>
11. <span data-ttu-id="f0e5c-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-118">Close the page.</span></span>
12. <span data-ttu-id="f0e5c-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-119">Click Save.</span></span>
13. <span data-ttu-id="f0e5c-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-120">Close the page.</span></span>
14. <span data-ttu-id="f0e5c-121">Vaya a Impuestos > Impuestos indirectos > Retención de impuestos > Grupos de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="f0e5c-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-122">Click New.</span></span>
16. <span data-ttu-id="f0e5c-123">En el campo Grupo de retenciones de impuestos, especifique el identificador del grupo de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="f0e5c-124">En el campo Descripción, especifique el nombre del grupo de retenciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="f0e5c-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="f0e5c-126">En el campo Código de retención de impuestos, seleccione el código de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="f0e5c-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="f0e5c-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f0e5c-128">Click Save.</span></span>


