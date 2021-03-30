---
title: Habilitar el proceso de nómina para tiempo y asistencia
description: Este procedimiento muestra cómo habilitar el proceso de nóminas para tiempo y asistencia.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72b925feb8f784c257656dd93b48c9c0cc66da5e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214923"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="c47f1-103">Habilitar el proceso de nómina para tiempo y asistencia</span><span class="sxs-lookup"><span data-stu-id="c47f1-103">Enable the payroll process for time and attendance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c47f1-104">Este procedimiento muestra cómo habilitar el proceso de nóminas para tiempo y asistencia.</span><span class="sxs-lookup"><span data-stu-id="c47f1-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="c47f1-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="c47f1-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="c47f1-106">Crear un tipo de sueldo con un índice salarial relacionado</span><span class="sxs-lookup"><span data-stu-id="c47f1-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="c47f1-107">Tiempo y asistencia > Configurar > Nómina > Tipos de sueldo</span><span class="sxs-lookup"><span data-stu-id="c47f1-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="c47f1-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-108">Click New.</span></span>
3. <span data-ttu-id="c47f1-109">En el campo Tipo de sueldo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="c47f1-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c47f1-111">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c47f1-111">Click Save.</span></span>
6. <span data-ttu-id="c47f1-112">Haga clic en Tasas.</span><span class="sxs-lookup"><span data-stu-id="c47f1-112">Click Rates.</span></span>
    * <span data-ttu-id="c47f1-113">Los índices para los tipos de sueldo se configuran para intervalos de tiempo concretos, y se pueden especificar índices individuales para los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="c47f1-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="c47f1-114">No siempre es necesario crear índices para los tipos de tiempo y asistencia.</span><span class="sxs-lookup"><span data-stu-id="c47f1-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="c47f1-115">Esta información puede existir en el sistema de nómina utilizado para generar los salarios.</span><span class="sxs-lookup"><span data-stu-id="c47f1-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="c47f1-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-116">Click New.</span></span>
8. <span data-ttu-id="c47f1-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c47f1-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="c47f1-118">En el campo Tasa, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="c47f1-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="c47f1-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c47f1-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="c47f1-120">Crear un acuerdo de sueldo</span><span class="sxs-lookup"><span data-stu-id="c47f1-120">Create a pay agreement</span></span>
1. <span data-ttu-id="c47f1-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c47f1-121">Close the page.</span></span>
2. <span data-ttu-id="c47f1-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c47f1-122">Close the page.</span></span>
3. <span data-ttu-id="c47f1-123">Vaya a Acuerdos de sueldo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="c47f1-124">Tiempo y asistencia > Configurar > Acuerdos de sueldo</span><span class="sxs-lookup"><span data-stu-id="c47f1-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="c47f1-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-125">Click New.</span></span>
5. <span data-ttu-id="c47f1-126">En el campo Acuerdo de sueldo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="c47f1-127">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="c47f1-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c47f1-128">Click Save.</span></span>
8. <span data-ttu-id="c47f1-129">Haga clic en Líneas de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="c47f1-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-130">Click New.</span></span>
10. <span data-ttu-id="c47f1-131">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c47f1-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="c47f1-132">En el campo Tipo de perfil, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="c47f1-133">En el campo Tipo de sueldo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="c47f1-134">Configurar un acuerdo de sueldo para un trabajador de tiempo y registro</span><span class="sxs-lookup"><span data-stu-id="c47f1-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="c47f1-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c47f1-135">Close the page.</span></span>
2. <span data-ttu-id="c47f1-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c47f1-136">Close the page.</span></span>
3. <span data-ttu-id="c47f1-137">Vaya a Trabajadores con registro de horas.</span><span class="sxs-lookup"><span data-stu-id="c47f1-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="c47f1-138">Tiempo y asistencia > Configurar > Trabajadores con registro de horas</span><span class="sxs-lookup"><span data-stu-id="c47f1-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="c47f1-139">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c47f1-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c47f1-140">Haga clic en la ficha Empleo.</span><span class="sxs-lookup"><span data-stu-id="c47f1-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="c47f1-141">Expanda la sección Registro de horas.</span><span class="sxs-lookup"><span data-stu-id="c47f1-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="c47f1-142">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c47f1-142">Click Edit.</span></span>
8. <span data-ttu-id="c47f1-143">En el campo Acuerdo de sueldo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c47f1-143">In the Pay agreement field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]