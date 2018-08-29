--- 
title: "Ejecutar informes que usen dimensiones financieras como orígenes de datos"
description: "En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: 6569f9b97d5d15bf74b8b3882bf4bab50970dd0f
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="run-reports-that-use-financial-dimensions-as-data-sources"></a><span data-ttu-id="2197b-103">Ejecutar informes que usen dimensiones financieras como orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="2197b-103">Run reports that use financial dimensions as data sources</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2197b-104">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="2197b-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="2197b-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="2197b-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="2197b-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)".</span><span class="sxs-lookup"><span data-stu-id="2197b-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="2197b-107">También debe configurar tipos de documento predeterminados en la página Parámetros de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2197b-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="2197b-108">Los tipos de documento predeterminados también se especifican al descarga e importar cualquier configuración del ER.</span><span class="sxs-lookup"><span data-stu-id="2197b-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="2197b-109">Ejecutar informe</span><span class="sxs-lookup"><span data-stu-id="2197b-109">Run report</span></span>
1. <span data-ttu-id="2197b-110">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="2197b-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="2197b-111">En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="2197b-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="2197b-112">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras\Informe del diario contable".</span><span class="sxs-lookup"><span data-stu-id="2197b-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="2197b-113">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="2197b-113">Click Run.</span></span>
5. <span data-ttu-id="2197b-114">En el campo Nombre de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="2197b-114">In the Dimension name field, In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="2197b-115">Para seleccionar todas las dimensiones de la empresa actual, introduzca lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="2197b-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="2197b-116">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="2197b-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="2197b-117">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="2197b-117">Click Filter.</span></span>
8. <span data-ttu-id="2197b-118">Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.</span><span class="sxs-lookup"><span data-stu-id="2197b-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="2197b-119">En el campo Criterios, escriba "00057".</span><span class="sxs-lookup"><span data-stu-id="2197b-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="2197b-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2197b-120">Click OK.</span></span>
11. <span data-ttu-id="2197b-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2197b-121">Click OK.</span></span>
    * <span data-ttu-id="2197b-122">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="2197b-122">Review the generated output.</span></span> <span data-ttu-id="2197b-123">Tenga en cuenta que para cada transacción del lote seleccionado, se incluyen las dimensiones financieras del conjunto de dimensiones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2197b-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="2197b-124">Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionadas o el número de dimensiones configuradas para esta instancia de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2197b-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations instance.</span></span>  


