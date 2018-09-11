--- 
title: "Configuración de secuencias numéricas mediante asistente"
description: "Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan."
author: sericks007
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 1aaea94678e9ddfa771c21063f53aefa172b5e97
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="02408-103">Configuración de secuencias numéricas mediante asistente</span><span class="sxs-lookup"><span data-stu-id="02408-103">Set up number sequences by using a wizard</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02408-104">Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan.</span><span class="sxs-lookup"><span data-stu-id="02408-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="02408-105">El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia.</span><span class="sxs-lookup"><span data-stu-id="02408-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="02408-106">Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia.</span><span class="sxs-lookup"><span data-stu-id="02408-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="02408-107">Este procedimiento explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.</span><span class="sxs-lookup"><span data-stu-id="02408-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="02408-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="02408-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="02408-109">Vaya a Administración de la organización > Secuencias numéricas > Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="02408-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="02408-110">Haga clic en Generar.</span><span class="sxs-lookup"><span data-stu-id="02408-110">Click Generate.</span></span>
3. <span data-ttu-id="02408-111">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="02408-111">Click Next.</span></span>
    * <span data-ttu-id="02408-112">En esta página, puede modificar el código de identificación, el valor más bajo y el valor más alto.</span><span class="sxs-lookup"><span data-stu-id="02408-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="02408-113">Además, puede indicar si la secuencia numérica debe ser continua.</span><span class="sxs-lookup"><span data-stu-id="02408-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="02408-114">No seleccione la opción Continuo si debe preasignar números para la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="02408-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="02408-115">Para agregar un segmento de ámbito al formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, haga clic en Incluir ámbito en el formato.</span><span class="sxs-lookup"><span data-stu-id="02408-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="02408-116">Para quitar un segmento de ámbito del formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, haga clic en Quitar ámbito del formato.</span><span class="sxs-lookup"><span data-stu-id="02408-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="02408-117">Para excluir una secuencia numérica de la generación automática, seleccione la secuencia numérica en la lista y, a continuación, haga clic en Eliminar.</span><span class="sxs-lookup"><span data-stu-id="02408-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="02408-118">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="02408-118">Click Next.</span></span>
5. <span data-ttu-id="02408-119">Haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="02408-119">Click Finish.</span></span>


