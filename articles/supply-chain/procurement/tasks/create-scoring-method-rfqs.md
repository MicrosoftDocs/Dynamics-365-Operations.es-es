---
title: Crear un método de puntuación para solicitudes de presupuesto
description: Este procedimiento muestra cómo crear un método de puntuación.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b098975f5557e9b99e7a951c0f8035bbaea5210
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812095"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="646d3-103">Crear un método de puntuación para solicitudes de presupuesto</span><span class="sxs-lookup"><span data-stu-id="646d3-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="646d3-104">Este procedimiento muestra cómo crear un método de puntuación.</span><span class="sxs-lookup"><span data-stu-id="646d3-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="646d3-105">Un método de puntuación es un conjunto de criterios que se pueden utilizar para comparar ofertas que se envían en respuesta a una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="646d3-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="646d3-106">Por ejemplo, puede que desee evaluar el rendimiento de un proveedor anterior, o calificar si la empresa es respetuosa con el medio ambiente o un buen colaborador, o puede que desee comparar ofertas en función del precio.</span><span class="sxs-lookup"><span data-stu-id="646d3-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="646d3-107">El método de puntuación se puede asociar a un tipo de solicitud como el método de puntuación predeterminado para solicitudes de presupuesto de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="646d3-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="646d3-108">Estas tareas las realizará normalmente el director de compras.</span><span class="sxs-lookup"><span data-stu-id="646d3-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="646d3-109">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="646d3-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="646d3-110">Vaya a Adquisición y abastecimiento > Configuración > Solicitud de presupuesto > Método de puntuación.</span><span class="sxs-lookup"><span data-stu-id="646d3-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="646d3-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="646d3-111">Click New.</span></span>
3. <span data-ttu-id="646d3-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="646d3-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="646d3-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="646d3-114">Click Save.</span></span>
6. <span data-ttu-id="646d3-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="646d3-115">Click New.</span></span>
7. <span data-ttu-id="646d3-116">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="646d3-117">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="646d3-118">Esta descripción se muestra junto con el nombre del método de puntuación cuando hay un método de puntuación seleccionado para una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="646d3-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="646d3-119">En el campo Inicio de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="646d3-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="646d3-120">El rango limita qué puede introducir el profesional de compras como puntuación.</span><span class="sxs-lookup"><span data-stu-id="646d3-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="646d3-121">Cuando hay varios criterios de puntuación en una solicitud de presupuesto, las puntuaciones que se han introducido se agregan a cada uno y la suma se hace disponible para permitir la comparación de las ofertas.</span><span class="sxs-lookup"><span data-stu-id="646d3-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="646d3-122">En el campo Fin de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="646d3-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="646d3-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="646d3-123">Click New.</span></span>
12. <span data-ttu-id="646d3-124">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="646d3-125">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="646d3-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="646d3-126">En el campo Inicio de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="646d3-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="646d3-127">En el campo Fin de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="646d3-127">In the Range to field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]