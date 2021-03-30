---
title: Crear un método de puntuación para solicitudes de presupuesto
description: Este procedimiento muestra cómo crear un método de puntuación.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba3f0b2be16c02129616025c0ee6258996189c6a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211823"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="165f5-103">Crear un método de puntuación para solicitudes de presupuesto</span><span class="sxs-lookup"><span data-stu-id="165f5-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="165f5-104">Este procedimiento muestra cómo crear un método de puntuación.</span><span class="sxs-lookup"><span data-stu-id="165f5-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="165f5-105">Un método de puntuación es un conjunto de criterios que se pueden utilizar para comparar ofertas que se envían en respuesta a una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="165f5-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="165f5-106">Por ejemplo, puede que desee evaluar el rendimiento de un proveedor anterior, o calificar si la empresa es respetuosa con el medio ambiente o un buen colaborador, o puede que desee comparar ofertas en función del precio.</span><span class="sxs-lookup"><span data-stu-id="165f5-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="165f5-107">El método de puntuación se puede asociar a un tipo de solicitud como el método de puntuación predeterminado para solicitudes de presupuesto de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="165f5-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="165f5-108">Estas tareas las realizará normalmente el director de compras.</span><span class="sxs-lookup"><span data-stu-id="165f5-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="165f5-109">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="165f5-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="165f5-110">Vaya a Adquisición y abastecimiento > Configuración > Solicitud de presupuesto > Método de puntuación.</span><span class="sxs-lookup"><span data-stu-id="165f5-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="165f5-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="165f5-111">Click New.</span></span>
3. <span data-ttu-id="165f5-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="165f5-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="165f5-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="165f5-114">Click Save.</span></span>
6. <span data-ttu-id="165f5-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="165f5-115">Click New.</span></span>
7. <span data-ttu-id="165f5-116">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="165f5-117">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="165f5-118">Esta descripción se muestra junto con el nombre del método de puntuación cuando hay un método de puntuación seleccionado para una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="165f5-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="165f5-119">En el campo Inicio de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="165f5-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="165f5-120">El rango limita qué puede introducir el profesional de compras como puntuación.</span><span class="sxs-lookup"><span data-stu-id="165f5-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="165f5-121">Cuando hay varios criterios de puntuación en una solicitud de presupuesto, las puntuaciones que se han introducido se agregan a cada uno y la suma se hace disponible para permitir la comparación de las ofertas.</span><span class="sxs-lookup"><span data-stu-id="165f5-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="165f5-122">En el campo Fin de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="165f5-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="165f5-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="165f5-123">Click New.</span></span>
12. <span data-ttu-id="165f5-124">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="165f5-125">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="165f5-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="165f5-126">En el campo Inicio de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="165f5-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="165f5-127">En el campo Fin de intervalo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="165f5-127">In the Range to field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]