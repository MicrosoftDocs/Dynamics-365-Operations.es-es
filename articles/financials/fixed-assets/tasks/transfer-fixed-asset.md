--- 
title: Transferir un activo fijo
description: "Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: bb8a5b94d9a0bb510daa2a698524e0c380597991
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="1cfbc-103">Transferir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="1cfbc-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1cfbc-104">Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="1cfbc-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="1cfbc-106">Vaya a Activos fijos > Activos fijos > Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="1cfbc-107">En la lista, busque y seleccione el activo fijo para transferir.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="1cfbc-108">En el panel de acciones, haga clic en Activo fijo.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="1cfbc-109">Haga clic en Transferir activos fijos.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="1cfbc-110">En el campo Fecha de transferencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="1cfbc-111">Escriba comentarios para describir la transferencia.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="1cfbc-112">Esta lista muestra todos los libros para el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="1cfbc-113">Marque los libros que desea transferir a un nuevo conjunto de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="1cfbc-114">Esta lista muestra los valores de dimensión financiera existentes para el libro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="1cfbc-115">seleccione la dimensión financiera que desee actualizar para el libro de activo fijo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="1cfbc-116">En el campo Dimensión financiera, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="1cfbc-117">Defina otros valores de la dimensión financiera si procede.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="1cfbc-118">Todos los valores de la dimensión financiera cambiarán cuando se produzca una transferencia, tanto si se ha especificado un valor como si se ha dejado en blanco.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="1cfbc-119">Por ejemplo, si se ha especificado un valor para BusinessUnit y se han dejado en blanco las dimensiones financieras CostCenter y Departamento.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="1cfbc-120">Si la estructura de cuentas permite valores en blanco para CostCenter y Departamento, la transferencia haría que cada modelo de valor tenga el nuevo valor para BusinessUnit y un valor en blanco para CostCenter y Departamento.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="1cfbc-121">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-121">Click Update.</span></span>
    * <span data-ttu-id="1cfbc-122">Tiene la oportunidad de ver los cambios de requisito previo antes de finalizar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="1cfbc-123">Revise los resultados antes de transferir los libros de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="1cfbc-124">Haga clic en Transferir.</span><span class="sxs-lookup"><span data-stu-id="1cfbc-124">Click Transfer.</span></span>


