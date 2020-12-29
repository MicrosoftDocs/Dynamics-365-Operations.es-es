---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)'
description: En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
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
ms.openlocfilehash: fb7f49310aa25ff7c17ab4bcd50e1842be84fe2d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684748"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="092fc-103">ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)</span><span class="sxs-lookup"><span data-stu-id="092fc-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="092fc-104">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="092fc-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="092fc-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="092fc-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="092fc-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)".</span><span class="sxs-lookup"><span data-stu-id="092fc-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="092fc-107">También debe configurar tipos de documento predeterminados en la página Parámetros de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="092fc-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="092fc-108">Los tipos de documento predeterminados también se especifican al descarga e importar cualquier configuración del ER.</span><span class="sxs-lookup"><span data-stu-id="092fc-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="092fc-109">Ejecutar informe</span><span class="sxs-lookup"><span data-stu-id="092fc-109">Run report</span></span>
1. <span data-ttu-id="092fc-110">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="092fc-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="092fc-111">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="092fc-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="092fc-112">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras\Informe del diario contable".</span><span class="sxs-lookup"><span data-stu-id="092fc-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="092fc-113">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="092fc-113">Click Run.</span></span>
<span data-ttu-id="092fc-114">![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="092fc-114">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="092fc-115">En el campo nombre de Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="092fc-115">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="092fc-116">Para seleccionar todas las dimensiones de la empresa actual, introduzca la siguiente información: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="092fc-116">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="092fc-118">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="092fc-118">Expand the Records to include section.</span></span>
7. <span data-ttu-id="092fc-119">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="092fc-119">Click Filter.</span></span>
8. <span data-ttu-id="092fc-120">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="092fc-120">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="092fc-121">En el campo Criterios, escriba "00057".</span><span class="sxs-lookup"><span data-stu-id="092fc-121">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="092fc-122">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="092fc-122">Click OK.</span></span>
11. <span data-ttu-id="092fc-123">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="092fc-123">Click OK.</span></span>
<span data-ttu-id="092fc-124">![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="092fc-124">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="092fc-125">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="092fc-125">Review the generated output.</span></span> <span data-ttu-id="092fc-126">Para cada transacción del lote seleccionado, se presentan las dimensiones financieras del conjunto de dimensiones correspondiente.</span><span class="sxs-lookup"><span data-stu-id="092fc-126">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="092fc-127">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="092fc-127">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Página de configuraciones de ER](../media/er-financial-dimensions-guides-run4.png)
