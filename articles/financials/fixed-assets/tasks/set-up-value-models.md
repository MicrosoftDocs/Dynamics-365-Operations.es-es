--- 
title: Configurar libros
description: "Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b440c105e3b48eb3d0deb287f90b22c2817da41e
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-books"></a><span data-ttu-id="944a4-103">Configurar libros</span><span class="sxs-lookup"><span data-stu-id="944a4-103">Set up books</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="944a4-104">Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="944a4-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="944a4-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="944a4-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="944a4-106">Crear un libro</span><span class="sxs-lookup"><span data-stu-id="944a4-106">Create a book</span></span>
1. <span data-ttu-id="944a4-107">Vaya a Activos fijos > Configuración > Libros.</span><span class="sxs-lookup"><span data-stu-id="944a4-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="944a4-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="944a4-108">Click New.</span></span>
3. <span data-ttu-id="944a4-109">En el campo Libro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="944a4-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="944a4-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="944a4-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="944a4-111">Si se selecciona Calcular depreciación, el libro de activos asociado se incluirán en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="944a4-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="944a4-112">Si no se selecciona, el libro de activos no se depreciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="944a4-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="944a4-113">Seleccione Sí en el campo Calcular depreciación.</span><span class="sxs-lookup"><span data-stu-id="944a4-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="944a4-114">En el campo Método de depreciación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="944a4-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="944a4-115">Un método de depreciación alternativo también se conoce como método de cambio de depreciación.</span><span class="sxs-lookup"><span data-stu-id="944a4-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="944a4-116">La propuesta de depreciación cambiará a este perfil cuando el perfil alternativo calcule un importe de depreciación que sea mayor o igual que el perfil de depreciación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="944a4-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="944a4-117">El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales.</span><span class="sxs-lookup"><span data-stu-id="944a4-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="944a4-118">Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.</span><span class="sxs-lookup"><span data-stu-id="944a4-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="944a4-119">Si está activado Crear ajustes de depreciación con ajustes de base, los ajustes de depreciación se crearán automáticamente cuando se actualice el valor del activo.</span><span class="sxs-lookup"><span data-stu-id="944a4-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="944a4-120">Si no se selecciona, el valor del activo actualizado solo afectará a los cálculos de depreciación a partir de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="944a4-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="944a4-121">Seleccione Sí en el campo Crear ajustes de depreciación con ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="944a4-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="944a4-122">De forma predeterminada, las transacciones del libro de activos fijos se registran en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="944a4-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="944a4-123">Puede deshabilitar el registro en la contabilidad general para el libro configurando el registro en el campo de contabilidad general en No.</span><span class="sxs-lookup"><span data-stu-id="944a4-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="944a4-124">Los libros que no se registran en la contabilidad general normalmente se utilizan para fines de informes de impuestos.</span><span class="sxs-lookup"><span data-stu-id="944a4-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="944a4-125">Esto le da flexibilidad adicional para eliminar las transacciones históricas para el libro de activos ya que no se han confiado a la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="944a4-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="944a4-126">La capa de registro recibe los valores por defecto la capa Actual si el libro se registra en la contabilidad general y Ninguna si no se registra en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="944a4-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="944a4-127">Actualice la capa de registro si necesita que las transacciones de este libro se registren en otra capa.</span><span class="sxs-lookup"><span data-stu-id="944a4-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="944a4-128">En el campo Calendario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="944a4-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="944a4-129">Los libros derivados registran las transacciones en distintos libros al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="944a4-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="944a4-130">Puede crear transacciones con el libro principal y durante el registro, una copia precisa de la transacción se registra en el libro derivado.</span><span class="sxs-lookup"><span data-stu-id="944a4-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="944a4-131">No hay cálculo con transacciones del libro derivadas, por lo que no se va a utilizar para las transacciones de depreciación.</span><span class="sxs-lookup"><span data-stu-id="944a4-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="944a4-132">Asociar el libro con un grupo de activos fijos</span><span class="sxs-lookup"><span data-stu-id="944a4-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="944a4-133">Haga clic en Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="944a4-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="944a4-134">En el campo Grupo de activos fijos, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="944a4-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="944a4-135">En el campo Tiempo de vida, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="944a4-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="944a4-136">Tenga en cuenta que los Períodos de depreciación se calculan después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="944a4-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="944a4-137">Puede establecer la convención de depreciación según sea necesario para fines de impuestos.</span><span class="sxs-lookup"><span data-stu-id="944a4-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  


