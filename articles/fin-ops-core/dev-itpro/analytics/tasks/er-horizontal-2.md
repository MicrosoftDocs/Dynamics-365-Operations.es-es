---
title: 'Informe electrónico Usar intervalos expandibles horizontalmente para agregar columnas dinámicamente en los informes de Excel (Parte 2: Ejecución de formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para generar informes como archivos de hojas de cálculo OPENXML (Excel). (Parte 2)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c13179f424d570b23615fe81ca5ddfb7afed582d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093485"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a><span data-ttu-id="da2ae-104">Informe electrónico Usar intervalos expandibles horizontalmente para agregar columnas dinámicamente en los informes de Excel (Parte 2: Ejecución de formato)</span><span class="sxs-lookup"><span data-stu-id="da2ae-104">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="da2ae-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables.</span><span class="sxs-lookup"><span data-stu-id="da2ae-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="da2ae-106">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="da2ae-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="da2ae-107">Para completar estos pasos, primero debe completar los pasos en el “ER Uso de los intervalos horizontalmente ensanchables para agregar columnas de manera dinámica en informes de Excel (Parte 1: Diseño de formato)”.</span><span class="sxs-lookup"><span data-stu-id="da2ae-107">To complete these steps, you must first complete the steps in the "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)" procedure.</span></span>

<span data-ttu-id="da2ae-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="da2ae-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="da2ae-109">Busque el formato creado</span><span class="sxs-lookup"><span data-stu-id="da2ae-109">Find created format</span></span>
1. <span data-ttu-id="da2ae-110">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="da2ae-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="da2ae-111">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="da2ae-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="da2ae-112">En el árbol, seleccione "Modelo de ejemplo de dimensiones financieras\Ejemplo de muestra con intervalos horizontalmente ensanchables".</span><span class="sxs-lookup"><span data-stu-id="da2ae-112">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="da2ae-113">Ejecute el formato para crear un resultado en formato Excel</span><span class="sxs-lookup"><span data-stu-id="da2ae-113">Execute format to create Excel output</span></span>
1. <span data-ttu-id="da2ae-114">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="da2ae-114">Click Run.</span></span>
2. <span data-ttu-id="da2ae-115">En el campo Nombre de dimensión, introduzca “BusinessUnit;CostCenter;Departament”.</span><span class="sxs-lookup"><span data-stu-id="da2ae-115">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="da2ae-116">En el campo nombre de Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="da2ae-116">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="da2ae-117">Para seleccionar todas las dimensiones para la empresa actual, especifique lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="da2ae-117">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="da2ae-118">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="da2ae-118">Expand the Records to include section.</span></span>
4. <span data-ttu-id="da2ae-119">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="da2ae-119">Click Filter.</span></span>
5. <span data-ttu-id="da2ae-120">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="da2ae-120">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="da2ae-121">En campo Criterios, introduzca '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="da2ae-121">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="da2ae-122">00057..00058</span><span class="sxs-lookup"><span data-stu-id="da2ae-122">00057..00058</span></span>  
7. <span data-ttu-id="da2ae-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="da2ae-123">Click OK.</span></span>
8. <span data-ttu-id="da2ae-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="da2ae-124">Click OK.</span></span>
    * <span data-ttu-id="da2ae-125">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="da2ae-125">Review the generated output.</span></span> <span data-ttu-id="da2ae-126">Tenga en cuenta que el archivo de Excel recién creado contiene el mismo número de columnas que han sido seleccionadas para las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="da2ae-126">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="da2ae-127">El encabezado del informe en las columnas representa los nombres de las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="da2ae-127">The report header in those columns represents financial dimensions' names.</span></span> <span data-ttu-id="da2ae-128">Las líneas de transacciones en las columnas representan las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="da2ae-128">The transactions' lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="da2ae-129">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="da2ae-129">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

