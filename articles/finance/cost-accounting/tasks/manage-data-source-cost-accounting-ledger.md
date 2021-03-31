---
title: Gestionar un origen de datos para el libro mayor de contabilidad de costes
description: Use este procedimiento para gestionar el origen de datos de la contabilidad general para un libro mayor de contabilidad de costes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48fef42f1866b0995182ac6fd022045f7dd31906
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218920"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="69975-103">Gestionar un origen de datos para el libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="69975-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69975-104">Use este procedimiento para gestionar el origen de datos de la contabilidad general para un libro mayor de contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="69975-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="69975-105">Para completar esta tarea, asegúrese de que reproduce las guías de tareas “Crear un libro mayor de contabilidad de costes“ y “Definir unidades de control de costes".</span><span class="sxs-lookup"><span data-stu-id="69975-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="69975-106">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="69975-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="69975-107">Vaya a Contabilidad de costes > Configuración de libro mayor > Libros mayores de contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="69975-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="69975-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="69975-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="69975-109">Haga clic en Versiones reales.</span><span class="sxs-lookup"><span data-stu-id="69975-109">Click Actual versions.</span></span>
4. <span data-ttu-id="69975-110">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="69975-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="69975-111">Haga clic en Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="69975-111">Click General ledger.</span></span>
6. <span data-ttu-id="69975-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="69975-112">Click New.</span></span>
7. <span data-ttu-id="69975-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="69975-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="69975-114">En el campo Proveedor de datos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="69975-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="69975-115">Para este ejemplo, seleccione Dynamics 365 Finance - Entradas de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="69975-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="69975-116">En el campo Dimensión de elemento de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="69975-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="69975-117">Para este ejemplo, seleccione Elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="69975-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="69975-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="69975-118">Click Save.</span></span>
11. <span data-ttu-id="69975-119">Haga clic en Configurar proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="69975-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="69975-120">En el campo Entidad jurídica, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="69975-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="69975-121">Para este ejemplo, seleccione USP2.</span><span class="sxs-lookup"><span data-stu-id="69975-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="69975-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="69975-122">Click New.</span></span>
14. <span data-ttu-id="69975-123">En el campo Capa de registro, seleccione Actual.</span><span class="sxs-lookup"><span data-stu-id="69975-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="69975-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="69975-124">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]