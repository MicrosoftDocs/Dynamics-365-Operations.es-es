---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)'
description: Este tema describe cómo configurar un modelo de informes electrónicos (ER) para usar dimensiones financieras como origen de datos para informes ER. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1fe332de84339d3369ba495ca13f50c4901f366
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092284"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="75d6f-104">ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)</span><span class="sxs-lookup"><span data-stu-id="75d6f-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="75d6f-105">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="75d6f-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="75d6f-106">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="75d6f-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="75d6f-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)".</span><span class="sxs-lookup"><span data-stu-id="75d6f-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="75d6f-108">También debe configurar tipos de documento predeterminados en la página Parámetros de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="75d6f-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="75d6f-109">Los tipos de documento predeterminados también se especifican al descarga e importar cualquier configuración del ER.</span><span class="sxs-lookup"><span data-stu-id="75d6f-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="75d6f-110">Ejecutar informe</span><span class="sxs-lookup"><span data-stu-id="75d6f-110">Run report</span></span>
1. <span data-ttu-id="75d6f-111">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="75d6f-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="75d6f-112">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="75d6f-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="75d6f-113">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras\Informe del diario contable".</span><span class="sxs-lookup"><span data-stu-id="75d6f-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="75d6f-114">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="75d6f-114">Click Run.</span></span>
<span data-ttu-id="75d6f-115">![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="75d6f-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="75d6f-116">En el campo nombre de Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="75d6f-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="75d6f-117">Para seleccionar todas las dimensiones de la empresa actual, introduzca la siguiente información: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="75d6f-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="75d6f-119">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="75d6f-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="75d6f-120">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="75d6f-120">Click Filter.</span></span>
8. <span data-ttu-id="75d6f-121">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="75d6f-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="75d6f-122">En el campo Criterios, escriba "00057".</span><span class="sxs-lookup"><span data-stu-id="75d6f-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="75d6f-123">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="75d6f-123">Click OK.</span></span>
11. <span data-ttu-id="75d6f-124">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="75d6f-124">Click OK.</span></span>
<span data-ttu-id="75d6f-125">![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="75d6f-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="75d6f-126">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="75d6f-126">Review the generated output.</span></span> <span data-ttu-id="75d6f-127">Para cada transacción del lote seleccionado, se presentan las dimensiones financieras del conjunto de dimensiones correspondiente.</span><span class="sxs-lookup"><span data-stu-id="75d6f-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="75d6f-128">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="75d6f-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run4.png)
