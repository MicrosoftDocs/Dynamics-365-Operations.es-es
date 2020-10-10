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
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 65970cdac114b72363d2fbbc08766c99ace00b88
ms.sourcegitcommit: 74b10104338222a945684d841d60ab4b8e570168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "3899382"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="7be4a-103">Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="7be4a-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7be4a-104">Es necesario agregar un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="7be4a-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="7be4a-105">Siga estos pasos para agregar la entidad de importación del extracto bancario para admitir el formato MT940.</span><span class="sxs-lookup"><span data-stu-id="7be4a-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="7be4a-106">Recopilar y sincronizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7be4a-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="7be4a-107">Entidad compuesta\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="7be4a-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="7be4a-108">Entidad\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="7be4a-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="7be4a-109">Entidad\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="7be4a-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="7be4a-110">Entidad\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="7be4a-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="7be4a-111">Entidad\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="7be4a-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="7be4a-112">Tablas\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="7be4a-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="7be4a-113">Gestión de datos\\proyectos de datos.</span><span class="sxs-lookup"><span data-stu-id="7be4a-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="7be4a-114">Cargar proyecto(s) de importación MT940</span><span class="sxs-lookup"><span data-stu-id="7be4a-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="7be4a-115">Cambiar XSLT.</span><span class="sxs-lookup"><span data-stu-id="7be4a-115">Change XSLT.</span></span>
            -   <span data-ttu-id="7be4a-116">Haga clic en **Ver mapa**.</span><span class="sxs-lookup"><span data-stu-id="7be4a-116">Click **View map**.</span></span>
            -   <span data-ttu-id="7be4a-117">Haga clic en **Ver mapa** en el documento del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="7be4a-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="7be4a-118">Haga clic en **Transformaciones**</span><span class="sxs-lookup"><span data-stu-id="7be4a-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="7be4a-119">Eliminar el archivo de BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="7be4a-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="7be4a-120">Agregar la nueva versión de BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="7be4a-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="7be4a-121">Exponer el **Número de secuencia** en el diseño de **Datos de origen**.</span><span class="sxs-lookup"><span data-stu-id="7be4a-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="7be4a-122">Formato de datos de origen = Elemento XML.</span><span class="sxs-lookup"><span data-stu-id="7be4a-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="7be4a-123">Nombre de la entidad = Extractos bancarios.</span><span class="sxs-lookup"><span data-stu-id="7be4a-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="7be4a-124">Cargar archivo de datos = nueva versión SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="7be4a-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="7be4a-125">Haga clic en **Sí** para sobrescribir el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="7be4a-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="7be4a-126">Haga clic en **Sí** para generar una nueva asignación.</span><span class="sxs-lookup"><span data-stu-id="7be4a-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="7be4a-127">Comprobar que se ha asignado S**equenceNumber**.</span><span class="sxs-lookup"><span data-stu-id="7be4a-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="7be4a-128">Haga clic en **Ver mapa** en la entidad del extracto.</span><span class="sxs-lookup"><span data-stu-id="7be4a-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="7be4a-129">Comprobar que **SequenceNumber** se asigna desde Origen a Montaje.</span><span class="sxs-lookup"><span data-stu-id="7be4a-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="7be4a-130">Importar el extracto nuevo.</span><span class="sxs-lookup"><span data-stu-id="7be4a-130">Import the new statement.</span></span>




