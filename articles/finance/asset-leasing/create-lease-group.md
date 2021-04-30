---
title: Crear un grupo de arrendamientos
description: En este tema se explica cómo configurar grupos de arrendamientos. Se requieren grupos de arrendamientos para crear nuevos arrendamientos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88a49e4db868078fd05875df33ca5727363aaa18
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881237"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="f0ea4-104">Crear un grupo de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="f0ea4-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0ea4-105">En este tema se explica cómo configurar grupos de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="f0ea4-106">Se requieren grupos de arrendamientos para crear nuevos arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="f0ea4-107">Los libros de arrendamiento están asociados con cada grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="f0ea4-108">Los libros de arrendamiento determinan los libros predeterminados que se deben crear para cada arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="f0ea4-109">Puede asignar cuentas específicas a un grupo de arrendamientos en la página **Parámetros de publicación de arrendamientos**.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="f0ea4-110">Crear un libro de arrendamiento y agregar un grupo de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="f0ea4-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="f0ea4-111">Vaya a **Arrendamiento de activos \> Configuración \> Grupos de arrendamientos**.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="f0ea4-112">En el Panel de acciones, seleccione **Nuevo** para agregar un grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="f0ea4-113">Se agrega una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="f0ea4-114">En la nueva línea, en el campo **Grupo de arrendamientos**, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="f0ea4-115">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="f0ea4-116">La información que acaba de introducir se agrega al campo **Grupo de arrendamientos** en la página **Agregar arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="f0ea4-117">Asociar un libro a un grupo de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="f0ea4-117">Associate a book with a lease group</span></span>

<span data-ttu-id="f0ea4-118">Después de crear grupos de arrendamientos, puede asignar libros a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="f0ea4-119">Cuando crea un arrendamiento y lo asigna a un grupo de arrendamientos, el sistema crea un conjunto de programaciones para cada libro que está asociado con ese grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ea4-120">Los libros deben configurarse antes de que puedan asignarse a un grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="f0ea4-121">Vaya a **Arrendamiento de activos \> Configuración \> Grupo de arrendamientos**.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="f0ea4-122">Seleccione un grupo de arrendamientos y luego seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="f0ea4-123">Seleccione **Nuevo** y luego, en el campo **Tipo de libro**, seleccione el libro para asignar al grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="f0ea4-124">Puede asignar varios libros a un grupo de arrendamientos si un arrendamiento debe contabilizarse de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
