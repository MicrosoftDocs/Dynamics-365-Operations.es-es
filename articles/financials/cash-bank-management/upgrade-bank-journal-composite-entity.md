---
title: "Actualización de la entidad compuesta del diario del banco"
description: Es necesario seguir los pasos siguiientes para poder agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 18b2b228f287a946eb18536b1ea93b0d6af6900c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="3ad38-103">Actualización de la entidad compuesta del diario del banco</span><span class="sxs-lookup"><span data-stu-id="3ad38-103">Update the bank journal composite entity</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3ad38-104">Es necesario seguir los pasos siguiientes para poder agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.</span><span class="sxs-lookup"><span data-stu-id="3ad38-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="3ad38-105">Siga estos pasos para agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.</span><span class="sxs-lookup"><span data-stu-id="3ad38-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="3ad38-106">Recopilar y sincronizar las entidades compuestas del siguiente diario del banco, las partes y las tablas de montaje:</span><span class="sxs-lookup"><span data-stu-id="3ad38-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="3ad38-107">Entidad compuesta\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="3ad38-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="3ad38-108">Entidad\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="3ad38-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="3ad38-109">Entidad\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="3ad38-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="3ad38-110">Tabla\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="3ad38-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="3ad38-111">Tabla\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="3ad38-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="3ad38-112">Gestión de datos\\proyectos de datos</span><span class="sxs-lookup"><span data-stu-id="3ad38-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="3ad38-113">Exponga el tipo de **Transacción bancaria**en el diseño de **Datos de origen**.</span><span class="sxs-lookup"><span data-stu-id="3ad38-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="3ad38-114">Formato de datos de origen = Elemento XML</span><span class="sxs-lookup"><span data-stu-id="3ad38-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="3ad38-115">Nombre de la entidad = Diario del banco</span><span class="sxs-lookup"><span data-stu-id="3ad38-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="3ad38-116">Cargar archivo de datos = nueva versión SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="3ad38-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="3ad38-117">Haga clic en **Sí** para sobrescribir el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="3ad38-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="3ad38-118">Haga clic en **Sí** para generar la asignación desde cero.</span><span class="sxs-lookup"><span data-stu-id="3ad38-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="3ad38-119">Compruebe que se asigna el Tipo de transacción bancaria.</span><span class="sxs-lookup"><span data-stu-id="3ad38-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="3ad38-120">Haga clic en **Ver mapa** en la Entidad de la línea.</span><span class="sxs-lookup"><span data-stu-id="3ad38-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="3ad38-121">Compruebe que se asigna el Tipo de transacción bancaria del Origen a Montaje</span><span class="sxs-lookup"><span data-stu-id="3ad38-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="3ad38-122">Importar el extracto nuevo.</span><span class="sxs-lookup"><span data-stu-id="3ad38-122">Import the new statement.</span></span>





