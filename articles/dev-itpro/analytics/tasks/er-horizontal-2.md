--- 
title: "Ejecutar formatos para agregar dinámicamente columnas a los informes de Excel como intervalos horizontalmente ensanchables"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: c7d563da9a02c91cce17cfa1d4a6915dd768ac3d
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="run-formats-to-dynamically-add-columns-to-excel-reports-as-horizontally-expandable-ranges"></a><span data-ttu-id="98981-103">Ejecutar formatos para agregar dinámicamente columnas a los informes de Excel como intervalos horizontalmente ensanchables</span><span class="sxs-lookup"><span data-stu-id="98981-103">Run formats to dynamically add columns to Excel reports as horizontally expandable ranges</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98981-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables.</span><span class="sxs-lookup"><span data-stu-id="98981-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="98981-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="98981-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="98981-106">Para completar estos pasos, primero debe completar los pasos en el “ER Uso de los intervalos horizontalmente ensanchables para agregar columnas de manera dinámica en informes de Excel (Parte 1: Diseño de formato)”.</span><span class="sxs-lookup"><span data-stu-id="98981-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="98981-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="98981-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="98981-108">Busque el formato creado</span><span class="sxs-lookup"><span data-stu-id="98981-108">Find created format</span></span>
1. <span data-ttu-id="98981-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="98981-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="98981-110">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="98981-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="98981-111">En el árbol, seleccione "Modelo de ejemplo de dimensiones financieras\Ejemplo de muestra con intervalos horizontalmente ensanchables".</span><span class="sxs-lookup"><span data-stu-id="98981-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="98981-112">Ejecute el formato para crear un resultado en formato Excel</span><span class="sxs-lookup"><span data-stu-id="98981-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="98981-113">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="98981-113">Click Run.</span></span>
2. <span data-ttu-id="98981-114">En el campo Nombre de dimensión, introduzca “BusinessUnit;CostCenter;Departament”.</span><span class="sxs-lookup"><span data-stu-id="98981-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="98981-115">En el campo nombre de Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="98981-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="98981-116">Para seleccionar todas las dimensiones para la empresa actual, especifique lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="98981-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="98981-117">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="98981-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="98981-118">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="98981-118">Click Filter.</span></span>
5. <span data-ttu-id="98981-119">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="98981-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="98981-120">En campo Criterios, introduzca '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="98981-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="98981-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="98981-121">00057..00058</span></span>  
7. <span data-ttu-id="98981-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="98981-122">Click OK.</span></span>
8. <span data-ttu-id="98981-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="98981-123">Click OK.</span></span>
    * <span data-ttu-id="98981-124">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="98981-124">Review the generated output.</span></span> <span data-ttu-id="98981-125">Tenga en cuenta que el archivo de Excel recién creado contiene el mismo número de columnas que han sido seleccionadas para las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="98981-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="98981-126">El encabezado del informe en las columnas representa los nombres de las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="98981-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="98981-127">Las líneas de transacciones en las columnas representan las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="98981-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="98981-128">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionadas o el número de dimensiones configuradas para esta instancia de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="98981-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations instance.</span></span>  


