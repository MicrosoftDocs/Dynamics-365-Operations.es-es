---
title: Agregar dimensiones financieras al espacio de trabajo del CFO
description: "Este tema explica cómo agregar dimensiones financieras al área de trabajo de CFO, para que se puedan usar en el libro mayor y los informes presupuestarios."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5faefe5da8c3a64987a38ebef92eb87049ebe874
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="c56e2-103">Agregar dimensiones financieras al espacio de trabajo del CFO</span><span class="sxs-lookup"><span data-stu-id="c56e2-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c56e2-104">Este tema explica cómo agregar dimensiones financieras al área de trabajo de CFO (Director financiero), para que se puedan usar en el libro mayor y los informes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="c56e2-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="c56e2-105">El área de trabajo del director financiero tiene una pestaña **Visión general** y una pestaña **Datos financieros**. Los informes de estas dos pestañas se basan en dos medidas: LedgerActivityMeasure y BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="c56e2-105">The CFO workspace has an **Overview** tab and a **Financial** tab. The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="c56e2-106">En Microsoft Dynamics 365 for Finance and Operations,Enterprise Edition (julio de 2017), existe una relación entre las dos medidas y la entidad de DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="c56e2-106">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="c56e2-107">Por lo tanto, puede seleccionar las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="c56e2-107">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="c56e2-108">En Finance and Operations, en la página **Almacén de la entidad** , actualice las medidas **MedidasActividadContable** y **MedidasActividadPresupuestaria** .</span><span class="sxs-lookup"><span data-stu-id="c56e2-108">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="c56e2-109">En Microsoft Visual Studio, abra el Explorador de la aplicación, y busque **ContabilidadCFO**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-109">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="c56e2-110">En **Recursos**, abra **ContabilidadCFOEspacioDeTrabajoPBIX**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-110">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="c56e2-111">Cuando el recurso se abre en el escritorio de Power BI de Microsoft, seleccione **Recopilar datos**, seleccione **Base de datos de SQL Server**, y después seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-111">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="c56e2-112">Especifique el nombre del servidor y seleccione **AxDW** como la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c56e2-112">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="c56e2-113">Haga clic en **DirectQuery** y, a continuación, en  **OK**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-113">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="c56e2-114">Busque y seleccione **MedidasDeActividadContable\_DimensiónCombinación**, y después seleccione **carga**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-114">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c56e2-115">En el lista **Campos** , cambie el nombre de la tabla **Dimensiones financieras**, de modo que sea fácil identificar.</span><span class="sxs-lookup"><span data-stu-id="c56e2-115">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="c56e2-116">Seleccione **Gestionar las relaciones**, y después seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-116">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="c56e2-117">En el primer campo, seleccione **Actividades de la contabilidad general**, y después seleccione **DimensiónContable**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-117">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="c56e2-118">En el segundo campo, seleccione **LedgerActivityMeasure\_DimensionCombination** (o **Dimensiones financieras** si se retituló la tabla).</span><span class="sxs-lookup"><span data-stu-id="c56e2-118">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="c56e2-119">Seleccione el encabezado **DimensiónCombinaciónRECID** .</span><span class="sxs-lookup"><span data-stu-id="c56e2-119">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="c56e2-120">En el campo **Cardinalidad** , seleccione **Muchos a uno**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-120">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="c56e2-121">Cambie el valor de **Dirección del filtro cruzado** a **Individual**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-121">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="c56e2-122">Seleccione **Hacer esta relación activa** y **Asumir la integridad referencial**, seleccione **Aceptar** y, a continuación seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-122">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="c56e2-123">[![Crear una relación](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="c56e2-123">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="c56e2-124">En el lista **Campos** , debe ver la tabla y las dimensiones financieras disponibles.</span><span class="sxs-lookup"><span data-stu-id="c56e2-124">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="c56e2-125">Arrastre las dimensiones financieras que desea a los filtros de informes nivel.</span><span class="sxs-lookup"><span data-stu-id="c56e2-125">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="c56e2-126">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="c56e2-126">Save your changes.</span></span>
15. <span data-ttu-id="c56e2-127">En el Árbol de objetos de aplicaciones (AOT), haga clic con el botón derecho en el proyecto y, a continuación seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="c56e2-127">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="c56e2-128">Compile el proyecto, y después abra la aplicación para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="c56e2-128">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="c56e2-129">[![Espacio de trabajo completado](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="c56e2-129">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

