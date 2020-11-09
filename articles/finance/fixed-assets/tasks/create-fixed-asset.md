---
title: Crear un activo fijo
description: En este tema se explica cómo crear un nuevo registro de activo fijo desde la página de lista de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b7d65a047251fa036242fb456725bc8cba957b9
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000252"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="8aded-103">Crear un activo fijo</span><span class="sxs-lookup"><span data-stu-id="8aded-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8aded-104">En este tema se explica cómo crear un nuevo registro de activo fijo desde la página de lista **Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="8aded-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="8aded-105">El sistema asigna el número de activo, basado la secuencia numérica que se asigna al grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="8aded-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="8aded-106">Si utiliza la plantilla de activos fijos para importar activos a través del complemento de Microsoft Excel, o si utiliza otro trabajo de importación, el sistema creará automáticamente registros de activos fijos e incrementará el número de activo.</span><span class="sxs-lookup"><span data-stu-id="8aded-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="8aded-107">Para crear manualmente un registro de activo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8aded-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="8aded-108">Vaya a **Panel de navegación \> Módulos \> Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="8aded-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="8aded-109">En el **Panel de acciones** , seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8aded-109">On the **Action pane** , select **New**.</span></span>
3. <span data-ttu-id="8aded-110">En el campo **Grupo de activos fijos** , escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8aded-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="8aded-111">Se usará el valor predeterminado para **Número** si ha habilitado la funcionalidad **Enumerar automáticamente los activos** fijos en los **parámetros de activos fijos** y en el **grupo de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="8aded-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="8aded-112">Si no lo ha hecho, debe escribir un número único para identificar el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="8aded-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="8aded-113">En el campo **Nombre** , escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8aded-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="8aded-114">Especifique la información adicional que su empresa necesite para este activo.</span><span class="sxs-lookup"><span data-stu-id="8aded-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="8aded-115">En el **Panel de acciones** , seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="8aded-115">On the **Action pane** , select **Books**.</span></span>
6. <span data-ttu-id="8aded-116">En el campo **Fecha de adquisición** , escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="8aded-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="8aded-117">En el campo **Precio de adquisición** , escriba un número.</span><span class="sxs-lookup"><span data-stu-id="8aded-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="8aded-118">Introduzca la la información adicional que su empresa necesite para este libro.</span><span class="sxs-lookup"><span data-stu-id="8aded-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="8aded-119">Introduzca la información adicional que necesite su empresa para los libros restantes.</span><span class="sxs-lookup"><span data-stu-id="8aded-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="8aded-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8aded-120">Close the page.</span></span>

<span data-ttu-id="8aded-121">También puede importar activos fijos a través del complemento de Excel o ejecutando un trabajo de importación desde el espacio de trabajo **Administración de datos**.</span><span class="sxs-lookup"><span data-stu-id="8aded-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="8aded-122">Antes de ejecutar la importación, especifique los valores de los campos obligatorios en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8aded-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="8aded-123">Si no definió el número de activo fijo en la plantilla del complemento de Excel o en Administración de datos, el sistema crea un número de activo fijo para cada activo importado e incrementa automáticamente la secuencia numérica para cada uno.</span><span class="sxs-lookup"><span data-stu-id="8aded-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="8aded-124">Sin embargo, si importa activos y define números de activos en la plantilla, el sistema **no** incrementa automáticamente la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="8aded-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="8aded-125">En este caso, es posible que un administrador tenga actualizar manualmente la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="8aded-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="8aded-126">Si definió el número de activo fijo en la plantilla del complemento de Excel, el sistema utiliza el número de activo fijo definido e incrementa la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="8aded-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>
