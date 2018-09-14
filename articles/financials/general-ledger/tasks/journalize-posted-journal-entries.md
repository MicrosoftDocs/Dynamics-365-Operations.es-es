--- 
title: Registrar en el diario movimientos de diario
description: Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b50809cf9eb59475856f91d9f1ddfe28ecfd8de6
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="1fdac-103">Registrar en el diario movimientos de diario</span><span class="sxs-lookup"><span data-stu-id="1fdac-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1fdac-104">Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas.</span><span class="sxs-lookup"><span data-stu-id="1fdac-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="1fdac-105">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1fdac-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="1fdac-106">Validar la configuración para registrar en el diario bajo Contabilidad general > Configuración de contabilidad > Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="1fdac-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="1fdac-107">El campo Diario contable ampliado se puede establecer en Sí o No.</span><span class="sxs-lookup"><span data-stu-id="1fdac-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="1fdac-108">Si Sí, la salida de informes es diferente.</span><span class="sxs-lookup"><span data-stu-id="1fdac-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="1fdac-109">Seleccione si el período puede cerrarse si el proceso de registro en el diario no se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="1fdac-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="1fdac-110">Si esta opción se establece en Sí, no puede cerrarse el período hasta que el proceso de registro en el diario se haya completado para ese período.</span><span class="sxs-lookup"><span data-stu-id="1fdac-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="1fdac-111">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1fdac-111">Close the page.</span></span>
5. <span data-ttu-id="1fdac-112">Vaya a Contabilidad general > Tareas periódicas > Creación de diarios.</span><span class="sxs-lookup"><span data-stu-id="1fdac-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="1fdac-113">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="1fdac-113">Click Filter.</span></span>
7. <span data-ttu-id="1fdac-114">Resalte la fila con los criterios de filtro que desee definir.</span><span class="sxs-lookup"><span data-stu-id="1fdac-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="1fdac-115">En el campo Criterios, especifique o seleccione los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="1fdac-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="1fdac-116">Haga clic en Aceptar para cerrar la página de filtro.</span><span class="sxs-lookup"><span data-stu-id="1fdac-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="1fdac-117">Haga clic en Aceptar para iniciar el proceso de registro en el diario.</span><span class="sxs-lookup"><span data-stu-id="1fdac-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="1fdac-118">Se generará un informe después de que se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="1fdac-118">A report will be generated after the process is complete.</span></span>  


