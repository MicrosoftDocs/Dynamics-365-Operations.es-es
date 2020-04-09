---
title: 'Informe electrónico Usar intervalos expandibles horizontalmente para agregar columnas dinámicamente en los informes de Excel (Parte 2: Ejecución de formato)'
description: En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66c2a97a068ed83f93699f14e827bdc2fb580d93
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141842"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a><span data-ttu-id="bd5d9-103">Informe electrónico Usar intervalos expandibles horizontalmente para agregar columnas dinámicamente en los informes de Excel (Parte 2: Ejecución de formato)</span><span class="sxs-lookup"><span data-stu-id="bd5d9-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd5d9-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="bd5d9-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="bd5d9-106">Para completar estos pasos, primero debe completar los pasos en el “ER Uso de los intervalos horizontalmente ensanchables para agregar columnas de manera dinámica en informes de Excel (Parte 1: Diseño de formato)”.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-106">To complete these steps, you must first complete the steps in the "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)" procedure.</span></span>

<span data-ttu-id="bd5d9-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="bd5d9-108">Busque el formato creado</span><span class="sxs-lookup"><span data-stu-id="bd5d9-108">Find created format</span></span>
1. <span data-ttu-id="bd5d9-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="bd5d9-110">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="bd5d9-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="bd5d9-111">En el árbol, seleccione "Modelo de ejemplo de dimensiones financieras\Ejemplo de muestra con intervalos horizontalmente ensanchables".</span><span class="sxs-lookup"><span data-stu-id="bd5d9-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="bd5d9-112">Ejecute el formato para crear un resultado en formato Excel</span><span class="sxs-lookup"><span data-stu-id="bd5d9-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="bd5d9-113">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-113">Click Run.</span></span>
2. <span data-ttu-id="bd5d9-114">En el campo Nombre de dimensión, introduzca “BusinessUnit;CostCenter;Departament”.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="bd5d9-115">En el campo nombre de Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="bd5d9-116">Para seleccionar todas las dimensiones para la empresa actual, especifique lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="bd5d9-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="bd5d9-117">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="bd5d9-118">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-118">Click Filter.</span></span>
5. <span data-ttu-id="bd5d9-119">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="bd5d9-120">En campo Criterios, introduzca '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="bd5d9-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="bd5d9-121">00057..00058</span></span>  
7. <span data-ttu-id="bd5d9-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bd5d9-122">Click OK.</span></span>
8. <span data-ttu-id="bd5d9-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bd5d9-123">Click OK.</span></span>
    * <span data-ttu-id="bd5d9-124">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-124">Review the generated output.</span></span> <span data-ttu-id="bd5d9-125">Tenga en cuenta que el archivo de Excel recién creado contiene el mismo número de columnas que han sido seleccionadas para las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="bd5d9-126">El encabezado del informe en las columnas representa los nombres de las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-126">The report header in those columns represents financial dimensions' names.</span></span> <span data-ttu-id="bd5d9-127">Las líneas de transacciones en las columnas representan las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-127">The transactions' lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="bd5d9-128">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="bd5d9-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

