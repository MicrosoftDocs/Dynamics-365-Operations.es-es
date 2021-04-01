---
title: Mantener tipos de códigos de barras
description: Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 112438417e425b8b77dd56f25e0b6e6db21c5148
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244408"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="665f2-103">Mantener tipos de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="665f2-103">Maintain barcode types</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="665f2-104">Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección.</span><span class="sxs-lookup"><span data-stu-id="665f2-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="665f2-105">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="665f2-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="665f2-106">Si está usando USMF, puede utilizar los valores del ejemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="665f2-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="665f2-107">Estas tareas las realizará normalmente el director del almacén.</span><span class="sxs-lookup"><span data-stu-id="665f2-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="665f2-108">Vaya a Códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="665f2-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="665f2-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="665f2-109">Click New.</span></span>
3. <span data-ttu-id="665f2-110">En el campo Configuración de código de barras, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="665f2-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="665f2-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="665f2-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="665f2-112">En el campo Tipo de código de barra, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="665f2-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="665f2-113">Si está usando USMF, puede seleccionar "Código 39".</span><span class="sxs-lookup"><span data-stu-id="665f2-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="665f2-114">En el campo Tamaño, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="665f2-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="665f2-115">Escriba un número en el campo Longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="665f2-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="665f2-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="665f2-116">Click Save.</span></span>
9. <span data-ttu-id="665f2-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="665f2-117">Close the page.</span></span>
10. <span data-ttu-id="665f2-118">Vaya a Parámetros de gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="665f2-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="665f2-119">En el campo Configuración de código de barras, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="665f2-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="665f2-120">Seleccione la configuración del código de barras que ha creado antes, pero tenga en cuenta que el formato del código de barras debe coincidir con el formato del identificador único del tipo de registro usado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="665f2-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="665f2-121">Por ejemplo, para las rutas de picking, el formato del código de barras debe coincidir con el formato de la referencia de la ruta de picking, que suele ser una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="665f2-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="665f2-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="665f2-122">Click Save.</span></span>
13. <span data-ttu-id="665f2-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="665f2-123">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]