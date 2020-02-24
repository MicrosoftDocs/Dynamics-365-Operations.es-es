---
title: Configurar las opciones de idoneidad de contacto personal
description: Configurar opciones de idoneidad para contactos personales en Microsoft Dynamics 365 Human Resources. Los contactos personales pueden ser beneficiarios o dependientes.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a50c5e54d224a2f8607284eb105381ffb6ef7ad9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010489"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="846bc-104">Configurar las opciones de idoneidad de contacto personal</span><span class="sxs-lookup"><span data-stu-id="846bc-104">Configure personal contact eligibility options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="846bc-105">Este artículo le muestra cómo configurar tipos de contactos personales para usar en prestaciones de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="846bc-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="846bc-106">Los contactos personales pueden ser beneficiarios o dependientes.</span><span class="sxs-lookup"><span data-stu-id="846bc-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="846bc-107">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de idoneidad para contactos personales**.</span><span class="sxs-lookup"><span data-stu-id="846bc-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="846bc-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="846bc-108">Select **New**.</span></span>

3. <span data-ttu-id="846bc-109">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="846bc-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="846bc-110">Campo</span><span class="sxs-lookup"><span data-stu-id="846bc-110">Field</span></span> | <span data-ttu-id="846bc-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="846bc-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="846bc-112">**Opción de idoneidad**</span><span class="sxs-lookup"><span data-stu-id="846bc-112">**Eligibility option**</span></span> | <span data-ttu-id="846bc-113">Un nombre o código de opción de idoneidad único para identificar la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="846bc-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="846bc-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="846bc-114">**Description**</span></span> | <span data-ttu-id="846bc-115">Descripción breve de la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="846bc-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="846bc-116">**Código de idoneidad de contacto**</span><span class="sxs-lookup"><span data-stu-id="846bc-116">**Contact eligibility code**</span></span> | <span data-ttu-id="846bc-117">Código del sistema que mejor describe la opción de idoneidad personal.</span><span class="sxs-lookup"><span data-stu-id="846bc-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="846bc-118">Puede elegir entre:</span><span class="sxs-lookup"><span data-stu-id="846bc-118">You can choose from:</span></span> <ul><li><span data-ttu-id="846bc-119">Relación</span><span class="sxs-lookup"><span data-stu-id="846bc-119">Relationship</span></span></li><li><span data-ttu-id="846bc-120">Estudiante</span><span class="sxs-lookup"><span data-stu-id="846bc-120">Student</span></span></li><li><span data-ttu-id="846bc-121">Dependiente mayor de edad</span><span class="sxs-lookup"><span data-stu-id="846bc-121">Overage dependent</span></span></li><li><span data-ttu-id="846bc-122">Dependiente deshabilitado demasiado mayor</span><span class="sxs-lookup"><span data-stu-id="846bc-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="846bc-123">**Estado**</span><span class="sxs-lookup"><span data-stu-id="846bc-123">**Status**</span></span> | <span data-ttu-id="846bc-124">El estado de la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="846bc-124">The status of the eligibility option.</span></span> <span data-ttu-id="846bc-125">Si el estado de una opción de idoneidad está configurado como inactivo, no puede seleccionar esa opción de idoneidad de contacto personal para contactos personales.</span><span class="sxs-lookup"><span data-stu-id="846bc-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="846bc-126">**Relación**</span><span class="sxs-lookup"><span data-stu-id="846bc-126">**Relationship**</span></span> | <span data-ttu-id="846bc-127">Especifica la relación entre el contacto personal y el empleado.</span><span class="sxs-lookup"><span data-stu-id="846bc-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="846bc-128">Este campo solo está activo si el código de idoneidad de contacto está establecido en Relación.</span><span class="sxs-lookup"><span data-stu-id="846bc-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="846bc-129">**Vencimiento**</span><span class="sxs-lookup"><span data-stu-id="846bc-129">**Age**</span></span> | <span data-ttu-id="846bc-130">La edad máxima de un contacto personal idóneo para el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="846bc-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="846bc-131">Este campo solo está activo si selecciona una relación.</span><span class="sxs-lookup"><span data-stu-id="846bc-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="846bc-132">Esta edad se compara con la edad calculada del contacto personal.</span><span class="sxs-lookup"><span data-stu-id="846bc-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="846bc-133">La edad calculada es: (Fecha de cobertura - fecha de nacimiento del contacto personal / 365).</span><span class="sxs-lookup"><span data-stu-id="846bc-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="846bc-134">Este número siempre es un entero.</span><span class="sxs-lookup"><span data-stu-id="846bc-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="846bc-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="846bc-135">Select **Save**.</span></span> 
