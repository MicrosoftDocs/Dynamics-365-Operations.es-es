---
title: Proponer adquisiciones de activos fijos
description: Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b35b13dc266fd5bccde437526400832d394b9aa
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839914"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="1f6bd-103">Proponer adquisiciones de activos fijos</span><span class="sxs-lookup"><span data-stu-id="1f6bd-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f6bd-104">Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="1f6bd-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="1f6bd-106">En el panel de navegación, vaya a **Módulos > Activos fijos > Entradas del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="1f6bd-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-107">Select **New**.</span></span>
3. <span data-ttu-id="1f6bd-108">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="1f6bd-109">En el panel de acciones, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="1f6bd-110">Seleccione **Propuestas**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="1f6bd-111">Seleccione **Propuesta de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="1f6bd-112">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-112">Select **Filter**.</span></span> <span data-ttu-id="1f6bd-113">Seleccione **Restablecer** para borrar los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="1f6bd-114">Seleccione la fila **Número de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="1f6bd-115">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="1f6bd-116">Establezca los criterios restantes para los activos fijos que desea adquirir con esta propuesta.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="1f6bd-117">Seleccione **Aceptar** dos veces para salir fuera del panel.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="1f6bd-118">Compruebe las líneas de transacción creadas.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="1f6bd-119">Solo los activos fijos con la fecha de adquisición y el precio de adquisición establecidos en el libro se incluirán en la propuesta de adquisición.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="1f6bd-120">En la página, seleccione la ficha **Libros**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="1f6bd-121">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="1f6bd-121">Select **Post**.</span></span>

