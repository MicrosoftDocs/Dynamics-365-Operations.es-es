---
title: Definiciones de contabilización
description: Este artículo proporciona información acerca de las definiciones de contabilización, y acerca de cómo definirlas y vincularlas. Para los tipos de contabilización y documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables.
author: ShylaThompson
manager: AnnBe
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76bae24a975c922ea49ee2584e87cf43ccca61c7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179729"
---
# <a name="posting-definitions"></a><span data-ttu-id="8a786-104">Definiciones de contabilización</span><span class="sxs-lookup"><span data-stu-id="8a786-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a786-105">Este artículo proporciona información acerca de las definiciones de contabilización, y acerca de cómo definirlas y vincularlas.</span><span class="sxs-lookup"><span data-stu-id="8a786-105">This article provides information about posting definitions, and how to define and link them.</span></span>
<span data-ttu-id="8a786-106">Para los tipos de contabilización y documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables.</span><span class="sxs-lookup"><span data-stu-id="8a786-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="8a786-107">Puede ver los documentos y los tipos de registro que admite la página **Definiciones de contabilización de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="8a786-107">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="8a786-108">Para empezar a usar definiciones de contabilización, seleccione**Usar definiciones de contabilización** en la página **Parámetros de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="8a786-108">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="8a786-109">Incluso al usar definiciones de contabilización, deberá definir los perfiles de contabilización para las entradas de origen y los documentos y los tipos de contabilización no admitidos.</span><span class="sxs-lookup"><span data-stu-id="8a786-109">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="8a786-110">Debe usar definiciones de contabilización para habilitar contabilidad de reserva de gasto para solicitudes de compra y contabilidad de pre-reserva de gasto para solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="8a786-110">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="8a786-111">Establecimiento de definiciones de contabilización</span><span class="sxs-lookup"><span data-stu-id="8a786-111">Defining posting definitions</span></span>
<span data-ttu-id="8a786-112">Use la página**Definiciones de contabilización** para especificar los criterios de coincidencia y para definir las entradas que se deben generar cuando se produce una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="8a786-112">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="8a786-113">Los criterios de coincidencia se evalúan para las entradas que se originan como distribuciones contables.</span><span class="sxs-lookup"><span data-stu-id="8a786-113">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="8a786-114">En la página **Definiciones de contabilización** puede también asignar números de prioridad a líneas de entradas para controlar el orden en el que se evalúan las líneas.</span><span class="sxs-lookup"><span data-stu-id="8a786-114">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="8a786-115">Las líneas con el número de prioridad más baja se evalúan primero.</span><span class="sxs-lookup"><span data-stu-id="8a786-115">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="8a786-116">Por ejemplo, se evalúan todas las líneas con una prioridad de 1, a continuación las líneas con una prioridad de 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="8a786-116">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="8a786-117">Cuando se encuentra una coincidencia, se omiten los demás criterios de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="8a786-117">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="8a786-118">Además, solo los criterios del grupo que coincidan con la transacción de origen crearán entradas generadas.</span><span class="sxs-lookup"><span data-stu-id="8a786-118">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="8a786-119">Puede validar las definiciones de contabilización mediante el **asistente para definición de contabilización de prueba**.</span><span class="sxs-lookup"><span data-stu-id="8a786-119">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="8a786-120">Tras definir una entrada de origen de muestra para una definición de contabilización, verá las entradas generadas.</span><span class="sxs-lookup"><span data-stu-id="8a786-120">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="8a786-121">Puede usar versiones de definición de contabilización junto con fechas de vigencia.</span><span class="sxs-lookup"><span data-stu-id="8a786-121">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="8a786-122">Por ejemplo, puede crear una versión futura de una definición de contabilización para registrar en una cuenta contable diferente en un nuevo ejercicio.</span><span class="sxs-lookup"><span data-stu-id="8a786-122">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="8a786-123">Use la página **Definiciones de contabilización de transacciones** para asignar definiciones de contabilización a los tipos transacciones.</span><span class="sxs-lookup"><span data-stu-id="8a786-123">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="8a786-124">Vinculación de definiciones de contabilización</span><span class="sxs-lookup"><span data-stu-id="8a786-124">Linking posting definitions</span></span>
<span data-ttu-id="8a786-125">Al crear definiciones de contabilización, puede crear un vínculo de una definición de contabilización a otra.</span><span class="sxs-lookup"><span data-stu-id="8a786-125">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="8a786-126">Los criterios de la definición a los que ha creado el vínculo se consideran además de los criterios de la definición de contabilización actual.</span><span class="sxs-lookup"><span data-stu-id="8a786-126">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="8a786-127">Esta función contribuye a ahorrar tiempo, ya que no tiene que volver a especificar criterios en la ficha desplegable **Entradas** de la página **Definiciones de contabilización** para la definición de contabilización actual si ya se han especificado esas líneas en otra definición.</span><span class="sxs-lookup"><span data-stu-id="8a786-127">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="8a786-128">En los diagramas o tablas, incluya los vínculos que pueda usar.</span><span class="sxs-lookup"><span data-stu-id="8a786-128">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="8a786-129">Para evitar conflictos con la definición de contabilización actual, asegúrese de que las líneas de las definiciones de contabilización a las que está creando vínculos sean únicas.</span><span class="sxs-lookup"><span data-stu-id="8a786-129">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="8a786-130">Al crear vínculos en definiciones de contabilización, se aplicarán las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="8a786-130">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="8a786-131">Cualquier definición de contabilización puede vincular a otra definición de contabilización o puede ser vinculada desde otra definición de contabilización, pero no las dos cosas.</span><span class="sxs-lookup"><span data-stu-id="8a786-131">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="8a786-132">No obstante, una definición de contabilización puede usarse como vínculo a varias definiciones de contabilización.</span><span class="sxs-lookup"><span data-stu-id="8a786-132">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="8a786-133">Puede configurar vínculos sólo entre definiciones de contabilización que se encuentren en el mismo módulo.</span><span class="sxs-lookup"><span data-stu-id="8a786-133">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="8a786-134">Puede asignar una definición de contabilización a cualquier tipo de transacción, pero el tipo de transacción debe estar en el mismo módulo que la definición de contabilización.</span><span class="sxs-lookup"><span data-stu-id="8a786-134">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="8a786-135">Use la página **Definiciones de contabilización de transacciones** para ver en qué módulo se encuentra un tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="8a786-135">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="8a786-136">Para obtener más información, consulte [Ejemplos de definiciones de contabilización](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="8a786-136">For more information, see [Posting definitions examples](example-posting-definitions.md).</span></span> 

