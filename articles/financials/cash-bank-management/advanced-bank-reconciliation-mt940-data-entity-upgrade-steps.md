---
title: "Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos"
description: "Es necesario añadir un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a76558d220e98de85060d23d6e5d8df1c0cd1baf
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="d6e67-103">Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="d6e67-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d6e67-104">Es necesario añadir un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="d6e67-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="d6e67-105">Siga estos pasos para agregar la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="d6e67-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="d6e67-106">Recopilar y sincronizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6e67-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="d6e67-107">Entidad compuesta\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="d6e67-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="d6e67-108">Entidad\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="d6e67-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="d6e67-109">Entidad\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="d6e67-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="d6e67-110">Entidad\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="d6e67-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="d6e67-111">Entidad\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="d6e67-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="d6e67-112">Tablas\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="d6e67-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="d6e67-113">Gestión de datos\\proyectos de datos.</span><span class="sxs-lookup"><span data-stu-id="d6e67-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="d6e67-114">Cargar proyecto(s) de importación MT940</span><span class="sxs-lookup"><span data-stu-id="d6e67-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="d6e67-115">Cambiar XSLT.</span><span class="sxs-lookup"><span data-stu-id="d6e67-115">Change XSLT.</span></span>
            -   <span data-ttu-id="d6e67-116">Haga clic en **Ver mapa**.</span><span class="sxs-lookup"><span data-stu-id="d6e67-116">Click **View map**.</span></span>
            -   <span data-ttu-id="d6e67-117">Haga clic en **Ver mapa** en el documento del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="d6e67-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="d6e67-118">Haga clic en **Transformaciones**</span><span class="sxs-lookup"><span data-stu-id="d6e67-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="d6e67-119">Eliminar el archivo de BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="d6e67-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="d6e67-120">Añadir la nueva versión de BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="d6e67-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="d6e67-121">Exponer el **Número de secuencia** en el diseño de **Datos de origen**.</span><span class="sxs-lookup"><span data-stu-id="d6e67-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="d6e67-122">Formato de datos de origen = Elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d6e67-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="d6e67-123">Nombre de la entidad = Extractos bancarios.</span><span class="sxs-lookup"><span data-stu-id="d6e67-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="d6e67-124">Cargar archivo de datos = nueva versión SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="d6e67-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="d6e67-125">Haga clic en **Sí** para sobrescribir el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="d6e67-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="d6e67-126">Haga clic en **Sí** para generar una nueva asignación.</span><span class="sxs-lookup"><span data-stu-id="d6e67-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="d6e67-127">Comprobar que se ha asignado S**equenceNumber**.</span><span class="sxs-lookup"><span data-stu-id="d6e67-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="d6e67-128">Haga clic en **Ver mapa** en la entidad del extracto.</span><span class="sxs-lookup"><span data-stu-id="d6e67-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="d6e67-129">Comprobar que **SequenceNumber** se asigna desde Origen a Montaje.</span><span class="sxs-lookup"><span data-stu-id="d6e67-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="d6e67-130">Importar el extracto nuevo.</span><span class="sxs-lookup"><span data-stu-id="d6e67-130">Import the new statement.</span></span>





