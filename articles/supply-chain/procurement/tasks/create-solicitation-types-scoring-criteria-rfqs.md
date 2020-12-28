---
title: Crear tipos de solicitud y criterios de puntuación para solicitudes de presupuesto
description: Esta guía le muestra cómo crear un tipo de solicitud y asociar esto a un método de puntuación.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b3876238a191cbbacc4e8c435bb798232e6fd6f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436958"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="7bd2f-103">Crear tipos de solicitud y criterios de puntuación para solicitudes de presupuesto</span><span class="sxs-lookup"><span data-stu-id="7bd2f-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7bd2f-104">Esta guía le muestra cómo crear un tipo de solicitud y asociar esto a un método de puntuación.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="7bd2f-105">También muestra cómo utilizar el tipo de solicitud en una solicitud de presupuesto que después establece el método de puntuación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="7bd2f-106">Estas tareas las realizará normalmente el director de compras.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="7bd2f-107">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="7bd2f-108">Necesita tener un método de puntuación disponible antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="7bd2f-109">Crear un tipo de solicitud</span><span class="sxs-lookup"><span data-stu-id="7bd2f-109">Create a solicitation type</span></span>
1. <span data-ttu-id="7bd2f-110">Vaya a Adquisición y abastecimiento > Configuración > Solicitud de presupuesto > Tipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="7bd2f-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-111">Click New.</span></span>
3. <span data-ttu-id="7bd2f-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7bd2f-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7bd2f-114">En el campo Método de puntuación, seleccione el método de puntuación que desea usar para este tipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="7bd2f-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-115">Click Save.</span></span>
7. <span data-ttu-id="7bd2f-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="7bd2f-117">Use el tipo de solicitud</span><span class="sxs-lookup"><span data-stu-id="7bd2f-117">Use the solicitation type</span></span>
1. <span data-ttu-id="7bd2f-118">Vaya a Adquisición y abastecimiento > Solicitudes de presupuestos > Todas las solicitudes de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="7bd2f-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-119">Click New.</span></span>
3. <span data-ttu-id="7bd2f-120">En el campo Tipo de solicitud, seleccione el tipo de la solicitación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="7bd2f-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7bd2f-121">Click OK.</span></span>
5. <span data-ttu-id="7bd2f-122">Haga clic en Criterios de puntuación.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="7bd2f-123">Los criterios de puntuación que se muestran son los del método de puntuación que asoció al tipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="7bd2f-124">Puede elegir agregar o eliminar criterios en esta página.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="7bd2f-125">También es posible agregar nuevos criterios copiándolos de otros métodos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="7bd2f-126">Haga clic en Copiar criterios.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="7bd2f-127">En el campo Método de puntuación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="7bd2f-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7bd2f-128">Click OK.</span></span>
9. <span data-ttu-id="7bd2f-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7bd2f-129">Close the page.</span></span>

