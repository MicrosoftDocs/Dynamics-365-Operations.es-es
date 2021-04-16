---
title: Crear un código de interés con un intervalo
description: Los códigos de interés se pueden configurar para calcular diferentes importes de interés basados en un intervalo de valores.
author: ShivamPandey-msft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c18269d277f64433da35e7dc1675cd3afda8e070
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835037"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="6009e-103">Crear un código de interés con un intervalo</span><span class="sxs-lookup"><span data-stu-id="6009e-103">Create an interest code with a range</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="6009e-104">Los códigos de interés se pueden configurar para calcular diferentes importes de interés basados en un intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="6009e-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="6009e-105">Este procedimiento le mostrará cómo agregar un código de interés y agregarle un intervalo.</span><span class="sxs-lookup"><span data-stu-id="6009e-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="6009e-106">Vaya a Crédito y cobros > Interés > Configurar códigos de interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="6009e-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6009e-107">Click New.</span></span>
3. <span data-ttu-id="6009e-108">En el campo Código del interés, especifique el nombre del código de interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="6009e-109">En el campo Descripción, especifique una descripción para el código de interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="6009e-110">Seleccione Mes.</span><span class="sxs-lookup"><span data-stu-id="6009e-110">Select Month.</span></span>
6. <span data-ttu-id="6009e-111">Expanda la sección Ganancias.</span><span class="sxs-lookup"><span data-stu-id="6009e-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="6009e-112">Expanda las ganancias por sección de divisa.</span><span class="sxs-lookup"><span data-stu-id="6009e-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="6009e-113">En el campo Cuenta de registro de libro mayor, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="6009e-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="6009e-114">En campo Interés por intervalo, seleccione "Meses".</span><span class="sxs-lookup"><span data-stu-id="6009e-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="6009e-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6009e-115">Click Add.</span></span>
11. <span data-ttu-id="6009e-116">En el campo Descripción, especifique una descripción para esta divisa e intervalo.</span><span class="sxs-lookup"><span data-stu-id="6009e-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="6009e-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6009e-117">Click Save.</span></span>
13. <span data-ttu-id="6009e-118">Haga clic en Intervalos.</span><span class="sxs-lookup"><span data-stu-id="6009e-118">Click Ranges.</span></span>
14. <span data-ttu-id="6009e-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6009e-119">Click New.</span></span>
15. <span data-ttu-id="6009e-120">Especifique el Valor inicial como 0 y especifique el porcentaje de interés al mes que se usará para calcular el interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="6009e-121">Para nuestro ejemplo, es 1,5.</span><span class="sxs-lookup"><span data-stu-id="6009e-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="6009e-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6009e-122">Click New.</span></span>
17. <span data-ttu-id="6009e-123">Especifique el siguiente Valor inicial como 4, que es el primer mes en que calculará un nuevo importe de interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="6009e-124">Especifique el porcentaje de interés al mes que se usará para calcular el interés que empieza el mes 4.</span><span class="sxs-lookup"><span data-stu-id="6009e-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="6009e-125">Para este ejemplo, es 2.0.</span><span class="sxs-lookup"><span data-stu-id="6009e-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="6009e-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6009e-126">Click New.</span></span>
20. <span data-ttu-id="6009e-127">Especifique el siguiente Valor inicial como 7, que es el siguiente mes en que calculará un nuevo importe de interés.</span><span class="sxs-lookup"><span data-stu-id="6009e-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="6009e-128">Especifique el porcentaje de interés al mes que se usará para calcular el interés que empieza el mes 7.</span><span class="sxs-lookup"><span data-stu-id="6009e-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="6009e-129">Para este ejemplo, es 2.5.</span><span class="sxs-lookup"><span data-stu-id="6009e-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="6009e-130">Haga clic en Cerrar para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="6009e-130">Click Close to complete the setup.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]