---
title: Proponer adquisiciones de activos fijos
description: Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 426a5e42c1fc26958ab37eddd915334f8b0e19cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205037"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="ea86c-103">Proponer adquisiciones de activos fijos</span><span class="sxs-lookup"><span data-stu-id="ea86c-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ea86c-104">Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="ea86c-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="ea86c-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="ea86c-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="ea86c-106">Para adquirir un activo fijo a través de un diario de propuestas de activos fijos, primero debe crear el registro de activos fijos y luego definir el precio de adquisición en el libro de activos.</span><span class="sxs-lookup"><span data-stu-id="ea86c-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="ea86c-107">En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="ea86c-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-108">Select **New**.</span></span>
3. <span data-ttu-id="ea86c-109">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ea86c-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="ea86c-110">En el panel de acciones, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="ea86c-111">Seleccione **Propuestas**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="ea86c-112">Seleccione **Propuesta de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="ea86c-113">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-113">Select **Filter**.</span></span> <span data-ttu-id="ea86c-114">Seleccione **Restablecer** para borrar los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="ea86c-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="ea86c-115">Seleccione la fila **Número de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="ea86c-116">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ea86c-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="ea86c-117">Establezca los criterios restantes para los activos fijos que desea adquirir con esta propuesta.</span><span class="sxs-lookup"><span data-stu-id="ea86c-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="ea86c-118">Seleccione **Aceptar** dos veces para salir fuera del panel.</span><span class="sxs-lookup"><span data-stu-id="ea86c-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="ea86c-119">Compruebe las líneas de transacción creadas.</span><span class="sxs-lookup"><span data-stu-id="ea86c-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="ea86c-120">Solo los activos fijos con la fecha de adquisición y el precio de adquisición establecidos en el libro se incluirán en la propuesta de adquisición.</span><span class="sxs-lookup"><span data-stu-id="ea86c-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="ea86c-121">En la página, seleccione la ficha **Libros**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="ea86c-122">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="ea86c-122">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]