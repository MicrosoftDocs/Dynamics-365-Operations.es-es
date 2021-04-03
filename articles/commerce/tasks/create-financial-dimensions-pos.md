---
title: Creación de dimensiones financieras para los registros de PDV y configuración de los valores de dimensión en los registros
description: Este procedimiento le muestra la creación de dimensiones financieras para registros del punto de venta (PDV) y muestra cómo configurar valores de dimensión financiera en los registros.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4042fb9da0fe38de50ad7e0c8e64b98925ea1188
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5265968"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="5b2a4-103">Creación de dimensiones financieras para los registros de PDV y configuración de los valores de dimensión en los registros</span><span class="sxs-lookup"><span data-stu-id="5b2a4-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b2a4-104">Este procedimiento le muestra la creación de dimensiones financieras para registros del punto de venta (PDV) y muestra cómo configurar valores de dimensión financiera en los registros.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="5b2a4-105">Este procedimiento no incluye otros pasos relacionados, como la creación de conjuntos de dimensiones y estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="5b2a4-106">Estas tareas se pueden encontrar en otros temas.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="5b2a4-107">Esta grabación usa la empresa de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="5b2a4-108">Vaya a Contabilidad general > Plan contable > Dimensiones > Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="5b2a4-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-109">Click New.</span></span>
3. <span data-ttu-id="5b2a4-110">En el campo Usar valores de, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="5b2a4-111">En el campo Nombre de dimensión, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="5b2a4-112">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-112">Click Activate.</span></span>
6. <span data-ttu-id="5b2a4-113">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-113">Click Close.</span></span>
7. <span data-ttu-id="5b2a4-114">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-114">Click Activate.</span></span>
8. <span data-ttu-id="5b2a4-115">Haga clic en Valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-115">Click Dimension values.</span></span>
9. <span data-ttu-id="5b2a4-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-116">Close the page.</span></span>
10. <span data-ttu-id="5b2a4-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-117">Click Save.</span></span>
11. <span data-ttu-id="5b2a4-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-118">Close the page.</span></span>
12. <span data-ttu-id="5b2a4-119">Vaya a Retail y Commerce > Configuración de canal > Configuración de PDV > PDV > Cajas registradoras.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="5b2a4-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5b2a4-121">Expanda la sección Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="5b2a4-122">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-122">Click Edit.</span></span>
16. <span data-ttu-id="5b2a4-123">En el campo Terminal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="5b2a4-124">En la lista, busque y seleccione el valor de dimensión para el registro que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="5b2a4-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]