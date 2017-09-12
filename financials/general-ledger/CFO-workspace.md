---
title: Agregar dimensiones financieras al espacio de trabajo del CFO
description: "Este tema explica cómo agregar dimensiones financieras al área de trabajo de CFO, para que se puedan usar en el libro mayor y los informes presupuestarios."
author: aolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.2.0
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 05fd7ce5293b3a300aabc073a6e492c5804d1897
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="f6910-103">Agregar dimensiones financieras al espacio de trabajo del CFO</span><span class="sxs-lookup"><span data-stu-id="f6910-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f6910-104">Este tema explica cómo agregar dimensiones financieras al área de trabajo de CFO (Director financiero), para que se puedan usar en el libro mayor y los informes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="f6910-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="f6910-105">El área de trabajo de CFO tiene una pestaña **Visión general** y una pestaña **Financiero** .</span><span class="sxs-lookup"><span data-stu-id="f6910-105">The CFO workspace has an **Overview** tab and a **Financial** tab.</span></span> <span data-ttu-id="f6910-106">Los informes en estas dos fichas están apoyados por dos medidas: MedidasActividadContable y MedidasActividadPresupuestaria.</span><span class="sxs-lookup"><span data-stu-id="f6910-106">The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="f6910-107">En Microsoft Dynamics 365 for Finance and Operations,Enterprise edition actualización de julio de 2017, existe una relación entre las dos medidas y la entidad de DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="f6910-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update, there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="f6910-108">Por lo tanto, puede seleccionar las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="f6910-108">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="f6910-109">En Finance and Operations, en la página **Almacén de la entidad** , actualice las medidas **MedidasActividadContable** y **MedidasActividadPresupuestaria** .</span><span class="sxs-lookup"><span data-stu-id="f6910-109">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="f6910-110">En Microsoft Visual Studio, abra el Explorador de la aplicación, y busque **ContabilidadCFO**.</span><span class="sxs-lookup"><span data-stu-id="f6910-110">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="f6910-111">En **Recursos**, abra **ContabilidadCFOEspacioDeTrabajoPBIX**.</span><span class="sxs-lookup"><span data-stu-id="f6910-111">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="f6910-112">Cuando el recurso se abre en el escritorio de Power BI de Microsoft, seleccione **Recopilar datos**, seleccione **Base de datos de SQL Server**, y después seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="f6910-112">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="f6910-113">Especifique el nombre del servidor y seleccione **AxDW** como la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f6910-113">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="f6910-114">Haga clic en **DirectQuery** y, a continuación, en  **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6910-114">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="f6910-115">Busque y seleccione **MedidasDeActividadContable\_DimensiónCombinación**, y después seleccione **carga**.</span><span class="sxs-lookup"><span data-stu-id="f6910-115">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f6910-116">En el lista **Campos** , cambie el nombre de la tabla **Dimensiones financieras**, de modo que sea fácil identificar.</span><span class="sxs-lookup"><span data-stu-id="f6910-116">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="f6910-117">Seleccione **Gestionar las relaciones**, y después seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f6910-117">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="f6910-118">En el primer campo, seleccione **Actividades de la contabilidad general**, y después seleccione **DimensiónContable**.</span><span class="sxs-lookup"><span data-stu-id="f6910-118">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="f6910-119">En el segundo campo, seleccione **LedgerActivityMeasure\_DimensionCombination** (o **Dimensiones financieras** si se retituló la tabla).</span><span class="sxs-lookup"><span data-stu-id="f6910-119">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="f6910-120">Seleccione el encabezado **DimensiónCombinaciónRECID** .</span><span class="sxs-lookup"><span data-stu-id="f6910-120">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="f6910-121">En el campo **Cardinalidad** , seleccione **Muchos a uno**.</span><span class="sxs-lookup"><span data-stu-id="f6910-121">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="f6910-122">Cambie el valor de **Dirección del filtro cruzado** a **Individual**.</span><span class="sxs-lookup"><span data-stu-id="f6910-122">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="f6910-123">Seleccione **Hacer esta relación activa** y **Asumir la integridad referencial**, seleccione **Aceptar** y, a continuación seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f6910-123">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="f6910-124">[![Crear una relación](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="f6910-124">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="f6910-125">En el lista **Campos** , debe ver la tabla y las dimensiones financieras disponibles.</span><span class="sxs-lookup"><span data-stu-id="f6910-125">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="f6910-126">Arrastre las dimensiones financieras que desea a los filtros de informes nivel.</span><span class="sxs-lookup"><span data-stu-id="f6910-126">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="f6910-127">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="f6910-127">Save your changes.</span></span>
15. <span data-ttu-id="f6910-128">En el Árbol de objetos de aplicaciones (AOT), haga clic con el botón derecho en el proyecto y, a continuación seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="f6910-128">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="f6910-129">Compile el proyecto, y después abra la aplicación para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="f6910-129">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="f6910-130">[![Espacio de trabajo completado](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="f6910-130">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

