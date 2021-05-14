---
title: Preguntas frecuentes sobre informes financieros
description: Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923034"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="0b469-103">Preguntas frecuentes sobre informes financieros</span><span class="sxs-lookup"><span data-stu-id="0b469-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="0b469-104">En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los informes financieros.</span><span class="sxs-lookup"><span data-stu-id="0b469-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="0b469-105">¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?</span><span class="sxs-lookup"><span data-stu-id="0b469-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="0b469-106">En el siguiente ejemplo se muestra cómo restringir el acceso a un informe mediante seguridad de árbol.</span><span class="sxs-lookup"><span data-stu-id="0b469-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="0b469-107">La empresa de demostración USMF tiene un informe de balance de situación al que no todos los usuarios de informes financieros deberían tener acceso.</span><span class="sxs-lookup"><span data-stu-id="0b469-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="0b469-108">Para restringir el acceso, puede usar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo determinados usuarios puedan acceder al informe.</span><span class="sxs-lookup"><span data-stu-id="0b469-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="0b469-109">Siga estos pasos para restringir el acceso:</span><span class="sxs-lookup"><span data-stu-id="0b469-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="0b469-110">Inicie sesión en Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="0b469-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="0b469-111">Cree una nueva definición de árbol.</span><span class="sxs-lookup"><span data-stu-id="0b469-111">Create a new tree definition.</span></span> <span data-ttu-id="0b469-112">Vaya a **Archivo > Nuevo > Definición de árbol**.</span><span class="sxs-lookup"><span data-stu-id="0b469-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="0b469-113">Haga doble clic en la línea **Resumen** de la columna **Seguridad de la unidad**.</span><span class="sxs-lookup"><span data-stu-id="0b469-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="0b469-114">Seleccione **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="0b469-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="0b469-115">Seleccione los usuarios o grupos a los que debe conceder acceso a este informe.</span><span class="sxs-lookup"><span data-stu-id="0b469-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="0b469-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0b469-116">Select **Save**.</span></span>
7. <span data-ttu-id="0b469-117">En la definición del informe, agregue su nueva definición de árbol.</span><span class="sxs-lookup"><span data-stu-id="0b469-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="0b469-118">En la definición del árbol, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="0b469-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="0b469-119">En **Selección de unidad de informes**, seleccione **Incluir todas las unidades**.</span><span class="sxs-lookup"><span data-stu-id="0b469-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="0b469-120">¿Cómo identifico qué cuentas no coinciden con mis saldos?</span><span class="sxs-lookup"><span data-stu-id="0b469-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="0b469-121">Si cuenta con un informe que no tiene saldos coincidentes, aquí hay algunos pasos que puede seguir para identificar cada una de las cuentas y desviaciones.</span><span class="sxs-lookup"><span data-stu-id="0b469-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="0b469-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="0b469-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="0b469-123">En Financial Reporter Report Designer, cree una nueva definición de fila.</span><span class="sxs-lookup"><span data-stu-id="0b469-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="0b469-124">Seleccione **Editar > Insertar filas desde Dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="0b469-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="0b469-125">Seleccione **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="0b469-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="0b469-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b469-126">Select **OK**.</span></span>
5. <span data-ttu-id="0b469-127">Guarde la definición de fila.</span><span class="sxs-lookup"><span data-stu-id="0b469-127">Save the row definition.</span></span>
6. <span data-ttu-id="0b469-128">Cree una nueva definición de columna.</span><span class="sxs-lookup"><span data-stu-id="0b469-128">Create a new column definition</span></span>
7. <span data-ttu-id="0b469-129">Cree una nueva definición de informe.</span><span class="sxs-lookup"><span data-stu-id="0b469-129">Create a new report definition.</span></span>
8. <span data-ttu-id="0b469-130">Seleccione **Ajustes** y desmarque esta opción.</span><span class="sxs-lookup"><span data-stu-id="0b469-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="0b469-131">Genere el informe.</span><span class="sxs-lookup"><span data-stu-id="0b469-131">Generate the report.</span></span> 
10. <span data-ttu-id="0b469-132">Exporte el informe a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="0b469-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="0b469-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="0b469-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="0b469-134">En Dynamics 365 Finance, vaya a **Contabilidad general > Consultas e informes > Saldo de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="0b469-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="0b469-135">Configure los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="0b469-135">Set the following parameters:</span></span>
   - <span data-ttu-id="0b469-136">**Fecha inicial**: introduzca el inicio del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="0b469-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="0b469-137">**Fecha final**: introduzca la fecha para la que está generando el informe.</span><span class="sxs-lookup"><span data-stu-id="0b469-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="0b469-138">**Dimensión financiera**: establezca este campo en **Conjunto de cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="0b469-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="0b469-139">Seleccione **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="0b469-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="0b469-140">Exporte el informe a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="0b469-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="0b469-141">Ahora debería poder copiar los datos desde el informe de Excel de Financial Reporter al informe de saldo de comprobación, de modo que puede comparar las columnas **Saldo de cierre**.</span><span class="sxs-lookup"><span data-stu-id="0b469-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]