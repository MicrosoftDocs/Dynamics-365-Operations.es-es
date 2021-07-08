---
title: Preguntas frecuentes sobre informes financieros
description: En este tema se proporcionan respuestas a algunas de las preguntas más frecuentes sobre los informes financieros.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266642"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="dcd39-103">Preguntas frecuentes sobre informes financieros</span><span class="sxs-lookup"><span data-stu-id="dcd39-103">Financial reporting FAQ</span></span>

<span data-ttu-id="dcd39-104">En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los informes financieros.</span><span class="sxs-lookup"><span data-stu-id="dcd39-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="dcd39-105">¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?</span><span class="sxs-lookup"><span data-stu-id="dcd39-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="dcd39-106">En el siguiente ejemplo se muestra cómo restringir el acceso a un informe mediante seguridad de árbol.</span><span class="sxs-lookup"><span data-stu-id="dcd39-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="dcd39-107">La empresa de demostración USMF tiene un informe de **balance de situación** al que no todos los usuarios de informes financieros deberían tener acceso.</span><span class="sxs-lookup"><span data-stu-id="dcd39-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="dcd39-108">Solución: puede utilizar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo usuarios específicos puedan acceder a él.</span><span class="sxs-lookup"><span data-stu-id="dcd39-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="dcd39-109">Iniciar sesión en Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="dcd39-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="dcd39-110">Seleccione **Archivo \> Nuevo \> Definición de árbol** para crear una nueva definición de árbol.</span><span class="sxs-lookup"><span data-stu-id="dcd39-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="dcd39-111">Toque dos veces (o haga doble clic) en la línea **Resumen** de la columna **Seguridad de la unidad**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="dcd39-112">Seleccione **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="dcd39-113">Seleccione los usuarios o grupos a los que debe conceder acceso al informe.</span><span class="sxs-lookup"><span data-stu-id="dcd39-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="dcd39-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-114">Select **Save**.</span></span>
7. <span data-ttu-id="dcd39-115">En la definición del informe, agregue su nueva definición de árbol.</span><span class="sxs-lookup"><span data-stu-id="dcd39-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="dcd39-116">En la definición del árbol, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="dcd39-117">Luego, en **Selección de unidad de informes**, seleccione **Incluir todas las unidades**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="dcd39-118">¿Cómo identifico qué cuentas no coinciden con mis saldos?</span><span class="sxs-lookup"><span data-stu-id="dcd39-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="dcd39-119">Si cuenta con un informe que no tiene saldos coincidentes, use los siguientes procedimientos para identificar cada cuenta y desviación.</span><span class="sxs-lookup"><span data-stu-id="dcd39-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="dcd39-120">En Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="dcd39-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="dcd39-121">Cree una nueva definición de fila.</span><span class="sxs-lookup"><span data-stu-id="dcd39-121">Create a new row definition.</span></span>
2. <span data-ttu-id="dcd39-122">Seleccione **Editar \> Insertar filas desde Dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="dcd39-123">Seleccione **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="dcd39-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-124">Select **OK**.</span></span>
5. <span data-ttu-id="dcd39-125">Guarde la definición de fila.</span><span class="sxs-lookup"><span data-stu-id="dcd39-125">Save the row definition.</span></span>
6. <span data-ttu-id="dcd39-126">Cree una nueva definición de columna.</span><span class="sxs-lookup"><span data-stu-id="dcd39-126">Create a new column definition.</span></span>
7. <span data-ttu-id="dcd39-127">Cree una nueva definición de informe.</span><span class="sxs-lookup"><span data-stu-id="dcd39-127">Create a new report definition.</span></span>
8. <span data-ttu-id="dcd39-128">Seleccione **Ajustes** y desmarque esta opción.</span><span class="sxs-lookup"><span data-stu-id="dcd39-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="dcd39-129">Genere el informe.</span><span class="sxs-lookup"><span data-stu-id="dcd39-129">Generate the report.</span></span> 
10. <span data-ttu-id="dcd39-130">Exporte el informe a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="dcd39-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="dcd39-131">En Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="dcd39-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="dcd39-132">Vaya a **Contabilidad general \> Consultas e informes \> Saldo de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="dcd39-133">Establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcd39-133">Set the following fields:</span></span>

    - <span data-ttu-id="dcd39-134">**Fecha inicial**: introduzca la fecha de inicio del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="dcd39-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="dcd39-135">**Fecha final**: introduzca la fecha para la que está generando el informe.</span><span class="sxs-lookup"><span data-stu-id="dcd39-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="dcd39-136">**Dimensión financiera**: establezca este campo en **Conjunto de cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="dcd39-137">Seleccione **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="dcd39-138">Exportar el informe a Excel.</span><span class="sxs-lookup"><span data-stu-id="dcd39-138">Export the report to Excel.</span></span>

<span data-ttu-id="dcd39-139">Ahora debería poder copiar los datos desde el informe de Excel de Financial Reporter al informe **Saldo de comprobación**, de modo que puede comparar las columnas **Saldo de cierre**.</span><span class="sxs-lookup"><span data-stu-id="dcd39-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="dcd39-140">Cuando diseño un informe en Report Designer o cuando genero un informe financiero, recibo el siguiente mensaje: "La operación no se pudo completar debido a un problema en el marco del proveedor de datos".</span><span class="sxs-lookup"><span data-stu-id="dcd39-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="dcd39-141">¿Cómo debo responder?</span><span class="sxs-lookup"><span data-stu-id="dcd39-141">How should I respond?</span></span>

<span data-ttu-id="dcd39-142">El mensaje indica que se produjo un problema cuando el sistema intentó recuperar metadatos financieros del data mart mientras usaba Financial Reporting.</span><span class="sxs-lookup"><span data-stu-id="dcd39-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="dcd39-143">Hay dos formas de responder a este problema:</span><span class="sxs-lookup"><span data-stu-id="dcd39-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="dcd39-144">Revise el estado de integración de los datos yendo a **Herramientas \> Estado de integración** en Report Designer.</span><span class="sxs-lookup"><span data-stu-id="dcd39-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="dcd39-145">Si la integración está incompleta, espere a que se complete.</span><span class="sxs-lookup"><span data-stu-id="dcd39-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="dcd39-146">Luego, vuelva a intentar lo que estaba haciendo cuando recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dcd39-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="dcd39-147">Póngase en contacto con el servicio de asistencia para identificar y solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="dcd39-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="dcd39-148">Puede haber datos incoherentes en el sistema.</span><span class="sxs-lookup"><span data-stu-id="dcd39-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="dcd39-149">Los ingenieros de soporte pueden ayudarle a identificar ese problema en el servidor y encontrar datos específicos que pueden requerir una actualización.</span><span class="sxs-lookup"><span data-stu-id="dcd39-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
