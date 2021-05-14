---
title: Reclasificar activos fijos
description: Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944724"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="e3c32-103">Reclasificar activos fijos</span><span class="sxs-lookup"><span data-stu-id="e3c32-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e3c32-104">Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="e3c32-105">Cuando se reclasifica un activo fijo:</span><span class="sxs-lookup"><span data-stu-id="e3c32-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="e3c32-106">Todos los libros del activo fijo existente se crean para el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="e3c32-107">Cualquier información que se haya configurado para el activo fijo se copia en el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="e3c32-108">El estado de los libros para el activo fijo original es Cerrado.</span><span class="sxs-lookup"><span data-stu-id="e3c32-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="e3c32-109">Los libros nuevos para un nuevo activo fijo contienen la fecha de reclasificación en el campo **Fecha de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="e3c32-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="e3c32-110">La fecha del campo **Fecha de ejecución de la depreciación** se copia de la información del activo original.</span><span class="sxs-lookup"><span data-stu-id="e3c32-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="e3c32-111">Si ya se inició la depreciación, el campo **Fecha en la que se ejecutó la última depreciación** mostrará la fecha de reclasificación.</span><span class="sxs-lookup"><span data-stu-id="e3c32-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="e3c32-112">Las transacciones de activos fijos existentes para el activo fijo original se cancelan y se vuelven a generar para el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="e3c32-113">Cuando un activo que tiene una transacción de transferencia ha sido reclasificado, el sistema mostrará un mensaje en el **Centro de acciones** para indicar que una transacción de transferencia no se completó durante el proceso de reclasificación.</span><span class="sxs-lookup"><span data-stu-id="e3c32-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="e3c32-114">Es necesario completar una transacción de transferencia para mover las transacciones de reclasificación existentes a las dimensiones financieras adecuadas.</span><span class="sxs-lookup"><span data-stu-id="e3c32-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="e3c32-115">Durante el proceso de reclasificación, el sistema ejecuta las siguientes acciones para reclasificar el saldo de activo del activo original al activo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="e3c32-116">El proceso de reclasificación copia los datos del libro de activos fijos original al nuevo libro de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e3c32-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="e3c32-117">La transacción de reclasificación utiliza información de la adquisición contabilizada original que incluye información de la dimensión financiera que se incluye en la transacción de adquisición.</span><span class="sxs-lookup"><span data-stu-id="e3c32-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="e3c32-118">Al mismo tiempo, el proceso de reclasificación revierte la transacción original de adquisición y transferencia de activos.</span><span class="sxs-lookup"><span data-stu-id="e3c32-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="e3c32-119">El siguiente diagrama y procedimiento proporcionan un ejemplo del proceso de reclasificación.</span><span class="sxs-lookup"><span data-stu-id="e3c32-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="e3c32-120">[![Diagrama que muestra el proceso de reclasicificación](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="e3c32-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="e3c32-121">Siga estos pasos para reclasificar un activo fijo:</span><span class="sxs-lookup"><span data-stu-id="e3c32-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="e3c32-122">Vaya a **Activos fijos > Tareas periódicas > Reclasificación**.</span><span class="sxs-lookup"><span data-stu-id="e3c32-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="e3c32-123">En el campo **Grupo de activos fijos**, seleccione el grupo a reclasificar.</span><span class="sxs-lookup"><span data-stu-id="e3c32-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="e3c32-124">En el campo **Número de activo fijo**, seleccione el activo fijo a reclasificar.</span><span class="sxs-lookup"><span data-stu-id="e3c32-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="e3c32-125">En el campo **Nuevo grupo de activos fijos**, seleccione un grupo al que transferirle el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="e3c32-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="e3c32-126">Si el nuevo grupo de activos fijos está vinculado a una secuencia numérica, el campo **Nuevo número de activo fijo** se actualiza con el número de la nueva secuencia numérica del grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e3c32-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="e3c32-127">De no ser así, el campo **Nuevo número de activo fijo** se actualizará con el número de la secuencia numérica que esté configurada en la página de los **Parámetros de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="e3c32-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="e3c32-128">Si no hay configurada una secuencia numérica en la página de **Parámetros del Activo fijo**, introduzca un número en el campo **Nuevo número de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="e3c32-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="e3c32-129">En el campo **Fecha de reclasificación**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="e3c32-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="e3c32-130">En el campo **Series de asientos**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e3c32-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="e3c32-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e3c32-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
