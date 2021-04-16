---
title: Proponer adquisiciones de activos fijos
description: Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817181"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="ab15c-103">Proponer adquisiciones de activos fijos</span><span class="sxs-lookup"><span data-stu-id="ab15c-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ab15c-104">Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="ab15c-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="ab15c-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="ab15c-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="ab15c-106">Para adquirir un activo fijo a través de un diario de propuestas de activos fijos, primero debe crear el registro de activos fijos y luego definir el precio de adquisición en el libro de activos.</span><span class="sxs-lookup"><span data-stu-id="ab15c-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="ab15c-107">Crear una propuesta de adquisición de activos</span><span class="sxs-lookup"><span data-stu-id="ab15c-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="ab15c-108">Complete los siguientes pasos para crear una propuesta de adquisición de activos.</span><span class="sxs-lookup"><span data-stu-id="ab15c-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="ab15c-109">En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="ab15c-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-110">Select **New**.</span></span>
3. <span data-ttu-id="ab15c-111">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab15c-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="ab15c-112">En el panel de acciones, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="ab15c-113">Seleccione **Propuestas**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="ab15c-114">Seleccione **Propuesta de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="ab15c-115">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-115">Select **Filter**.</span></span> <span data-ttu-id="ab15c-116">Seleccione **Restablecer** para borrar los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="ab15c-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="ab15c-117">Seleccione la fila **Número de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="ab15c-118">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab15c-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="ab15c-119">Establezca los criterios restantes para los activos fijos que desea adquirir con esta propuesta.</span><span class="sxs-lookup"><span data-stu-id="ab15c-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="ab15c-120">Seleccione **Aceptar** dos veces para salir fuera del panel.</span><span class="sxs-lookup"><span data-stu-id="ab15c-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="ab15c-121">Compruebe que se creen las líneas de transacción.</span><span class="sxs-lookup"><span data-stu-id="ab15c-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="ab15c-122">Solo los activos fijos con la fecha de adquisición y el precio de adquisición establecidos en el libro se incluirán en la propuesta de adquisición.</span><span class="sxs-lookup"><span data-stu-id="ab15c-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="ab15c-123">En la página, seleccione la ficha **Libros**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="ab15c-124">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="ab15c-125">Incluir dimensiones financieras predeterminadas en una propuesta de adquisición</span><span class="sxs-lookup"><span data-stu-id="ab15c-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="ab15c-126">La transacción de adquisición se puede crear utilizando complementos de Excel, yendo a **Activos fijos > Asientos de diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="ab15c-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="ab15c-127">Cree un nuevo diario, vaya a la sección **Líneas** de la página, seleccione el icono de Excel, y luego elija una línea de diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="ab15c-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="ab15c-128">El sistema creará y abrirá una plantilla de Excel que representa las líneas del diario.</span><span class="sxs-lookup"><span data-stu-id="ab15c-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="ab15c-129">Puede agregar datos para las líneas de diario que esté agregando a la plantilla y luego publicar esa información otra vez en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ab15c-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="ab15c-130">Si se han configurado dimensiones predeterminadas para el libro de activos seleccionado y los activos fijos correspondientes que se introdujeron en la plantilla de Excel, las dimensiones financieras predeterminadas se llamarán desde los datos maestros del libro de activos cuando el diario se publique desde Excel en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ab15c-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="ab15c-131">Para incluir dimensiones financieras en un libro de activos automáticamente mientras se publica el diario de activos fijos desde el complemento de Excel, las dimensiones predeterminadas deben configurarse de antemano.</span><span class="sxs-lookup"><span data-stu-id="ab15c-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
