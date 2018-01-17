---
title: "Mantener tipos de códigos de barras"
description: "Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: bc863ce86c4dc3cbdd3a1df881eb7a6efeea1656
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---
# <a name="maintain-bar-code-types"></a><span data-ttu-id="5d993-103">Mantener tipos de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="5d993-103">Maintain bar code types</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d993-104">Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección.</span><span class="sxs-lookup"><span data-stu-id="5d993-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="5d993-105">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="5d993-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5d993-106">Si está usando USMF, puede utilizar los valores del ejemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="5d993-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="5d993-107">Estas tareas las realizará normalmente el director del almacén.</span><span class="sxs-lookup"><span data-stu-id="5d993-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="5d993-108">Vaya a Códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="5d993-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="5d993-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d993-109">Click New.</span></span>
3. <span data-ttu-id="5d993-110">En el campo Configuración de código de barras, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5d993-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="5d993-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5d993-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5d993-112">En el campo Tipo de código de barra, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="5d993-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="5d993-113">Si está usando USMF, puede seleccionar "Código 39".</span><span class="sxs-lookup"><span data-stu-id="5d993-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="5d993-114">En el campo Tamaño, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="5d993-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="5d993-115">Escriba un número en el campo Longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="5d993-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="5d993-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5d993-116">Click Save.</span></span>
9. <span data-ttu-id="5d993-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5d993-117">Close the page.</span></span>
10. <span data-ttu-id="5d993-118">Vaya a Parámetros de gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="5d993-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="5d993-119">En el campo Configuración de código de barras, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5d993-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="5d993-120">Seleccione la configuración del código de barras que ha creado antes, pero tenga en cuenta que el formato del código de barras debe coincidir con el formato del identificador único del tipo de registro usado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d993-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="5d993-121">Por ejemplo, para las rutas de picking, el formato del código de barras debe coincidir con el formato de la referencia de la ruta de picking, que suele ser una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="5d993-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="5d993-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5d993-122">Click Save.</span></span>
13. <span data-ttu-id="5d993-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5d993-123">Close the page.</span></span>

