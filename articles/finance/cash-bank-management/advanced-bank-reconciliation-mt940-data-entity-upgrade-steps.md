---
title: Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos
description: Es necesario agregar un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940.
author: panolte
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4d3bd54f0f2329c8c0602171a7f3c1ca444672b3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985420"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="8bc48-103">Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="8bc48-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bc48-104">Es necesario agregar un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="8bc48-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="8bc48-105">Siga estos pasos para agregar la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="8bc48-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="8bc48-106">Recopilar y sincronizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bc48-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="8bc48-107">Entidad compuesta\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="8bc48-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="8bc48-108">Entidad\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="8bc48-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="8bc48-109">Entidad\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="8bc48-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="8bc48-110">Entidad\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="8bc48-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="8bc48-111">Entidad\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="8bc48-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="8bc48-112">Tablas\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="8bc48-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="8bc48-113">Gestión de datos\\proyectos de datos.</span><span class="sxs-lookup"><span data-stu-id="8bc48-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="8bc48-114">Cargar proyecto(s) de importación MT940</span><span class="sxs-lookup"><span data-stu-id="8bc48-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="8bc48-115">Cambiar XSLT.</span><span class="sxs-lookup"><span data-stu-id="8bc48-115">Change XSLT.</span></span>
            -   <span data-ttu-id="8bc48-116">Haga clic en **Ver mapa**.</span><span class="sxs-lookup"><span data-stu-id="8bc48-116">Click **View map**.</span></span>
            -   <span data-ttu-id="8bc48-117">Haga clic en **Ver mapa** en el documento del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="8bc48-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="8bc48-118">Haga clic en **Transformaciones**</span><span class="sxs-lookup"><span data-stu-id="8bc48-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="8bc48-119">Eliminar el archivo de BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="8bc48-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="8bc48-120">Agregar la nueva versión de BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="8bc48-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="8bc48-121">Exponer el **Número de secuencia** en el diseño de **Datos de origen**.</span><span class="sxs-lookup"><span data-stu-id="8bc48-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="8bc48-122">Formato de datos de origen = Elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8bc48-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="8bc48-123">Nombre de la entidad = Extractos bancarios.</span><span class="sxs-lookup"><span data-stu-id="8bc48-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="8bc48-124">Cargar archivo de datos = nueva versión SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="8bc48-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="8bc48-125">Haga clic en **Sí** para sobrescribir el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="8bc48-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="8bc48-126">Haga clic en **Sí** para generar una nueva asignación.</span><span class="sxs-lookup"><span data-stu-id="8bc48-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="8bc48-127">Comprobar que se ha asignado S **equenceNumber**.</span><span class="sxs-lookup"><span data-stu-id="8bc48-127">Verify that S **equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="8bc48-128">Haga clic en **Ver mapa** en la entidad del extracto.</span><span class="sxs-lookup"><span data-stu-id="8bc48-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="8bc48-129">Comprobar que **SequenceNumber** se asigna desde Origen a Montaje.</span><span class="sxs-lookup"><span data-stu-id="8bc48-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="8bc48-130">Importar el extracto nuevo.</span><span class="sxs-lookup"><span data-stu-id="8bc48-130">Import the new statement.</span></span>




