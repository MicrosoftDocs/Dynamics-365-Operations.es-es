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
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be50eba098b7b28594c8e18c721579f4bb2e879
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415587"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="cbe43-103">Creación de dimensiones financieras para los registros de PDV y configuración de los valores de dimensión en los registros</span><span class="sxs-lookup"><span data-stu-id="cbe43-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbe43-104">Este procedimiento le muestra la creación de dimensiones financieras para registros del punto de venta (PDV) y muestra cómo configurar valores de dimensión financiera en los registros.</span><span class="sxs-lookup"><span data-stu-id="cbe43-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="cbe43-105">Este procedimiento no incluye otros pasos relacionados, como la creación de conjuntos de dimensiones y estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="cbe43-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="cbe43-106">Estas tareas se pueden encontrar en otros temas.</span><span class="sxs-lookup"><span data-stu-id="cbe43-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="cbe43-107">Esta grabación usa la empresa de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="cbe43-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="cbe43-108">Vaya a Contabilidad general > Plan contable > Dimensiones > Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="cbe43-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="cbe43-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cbe43-109">Click New.</span></span>
3. <span data-ttu-id="cbe43-110">En el campo Usar valores de, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cbe43-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="cbe43-111">En el campo Nombre de dimensión, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cbe43-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="cbe43-112">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-112">Click Activate.</span></span>
6. <span data-ttu-id="cbe43-113">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-113">Click Close.</span></span>
7. <span data-ttu-id="cbe43-114">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-114">Click Activate.</span></span>
8. <span data-ttu-id="cbe43-115">Haga clic en Valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="cbe43-115">Click Dimension values.</span></span>
9. <span data-ttu-id="cbe43-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cbe43-116">Close the page.</span></span>
10. <span data-ttu-id="cbe43-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-117">Click Save.</span></span>
11. <span data-ttu-id="cbe43-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cbe43-118">Close the page.</span></span>
12. <span data-ttu-id="cbe43-119">Vaya a Retail y Commerce > Configuración de canal > Configuración de PDV > PDV > Cajas registradoras.</span><span class="sxs-lookup"><span data-stu-id="cbe43-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="cbe43-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cbe43-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="cbe43-121">Expanda la sección Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="cbe43-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="cbe43-122">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-122">Click Edit.</span></span>
16. <span data-ttu-id="cbe43-123">En el campo Terminal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cbe43-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="cbe43-124">En la lista, busque y seleccione el valor de dimensión para el registro que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="cbe43-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="cbe43-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="cbe43-125">Click Save.</span></span>

