---
title: Configurar las opciones de idoneidad de contacto personal
description: Configurar opciones de idoneidad para contactos personales en Microsoft Dynamics 365 Human Resources. Los contactos personales pueden ser beneficiarios o dependientes.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 0275331e600770a9f38a33bc2c3170c4cf9be951
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229887"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="43834-104">Configurar las opciones de idoneidad de contacto personal</span><span class="sxs-lookup"><span data-stu-id="43834-104">Configure personal contact eligibility options</span></span>

<span data-ttu-id="43834-105">Este artículo le muestra cómo configurar tipos de contactos personales para usar en prestaciones de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="43834-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="43834-106">Los contactos personales pueden ser beneficiarios o dependientes.</span><span class="sxs-lookup"><span data-stu-id="43834-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="43834-107">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de idoneidad para contactos personales**.</span><span class="sxs-lookup"><span data-stu-id="43834-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="43834-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="43834-108">Select **New**.</span></span>

3. <span data-ttu-id="43834-109">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="43834-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="43834-110">Campo</span><span class="sxs-lookup"><span data-stu-id="43834-110">Field</span></span> | <span data-ttu-id="43834-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="43834-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="43834-112">**Opción de idoneidad**</span><span class="sxs-lookup"><span data-stu-id="43834-112">**Eligibility option**</span></span> | <span data-ttu-id="43834-113">Un nombre o código de opción de idoneidad único para identificar la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="43834-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="43834-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="43834-114">**Description**</span></span> | <span data-ttu-id="43834-115">Descripción breve de la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="43834-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="43834-116">**Código de idoneidad de contacto**</span><span class="sxs-lookup"><span data-stu-id="43834-116">**Contact eligibility code**</span></span> | <span data-ttu-id="43834-117">Código del sistema que mejor describe la opción de idoneidad personal.</span><span class="sxs-lookup"><span data-stu-id="43834-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="43834-118">Puede elegir entre:</span><span class="sxs-lookup"><span data-stu-id="43834-118">You can choose from:</span></span> <ul><li><span data-ttu-id="43834-119">Relación</span><span class="sxs-lookup"><span data-stu-id="43834-119">Relationship</span></span></li><li><span data-ttu-id="43834-120">Estudiante</span><span class="sxs-lookup"><span data-stu-id="43834-120">Student</span></span></li><li><span data-ttu-id="43834-121">Dependiente mayor de edad</span><span class="sxs-lookup"><span data-stu-id="43834-121">Overage dependent</span></span></li><li><span data-ttu-id="43834-122">Dependiente deshabilitado demasiado mayor</span><span class="sxs-lookup"><span data-stu-id="43834-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="43834-123">**Estado**</span><span class="sxs-lookup"><span data-stu-id="43834-123">**Status**</span></span> | <span data-ttu-id="43834-124">El estado de la opción de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="43834-124">The status of the eligibility option.</span></span> <span data-ttu-id="43834-125">Si el estado de una opción de idoneidad está configurado como inactivo, no puede seleccionar esa opción de idoneidad de contacto personal para contactos personales.</span><span class="sxs-lookup"><span data-stu-id="43834-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="43834-126">**Relación**</span><span class="sxs-lookup"><span data-stu-id="43834-126">**Relationship**</span></span> | <span data-ttu-id="43834-127">Especifica la relación entre el contacto personal y el empleado.</span><span class="sxs-lookup"><span data-stu-id="43834-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="43834-128">Este campo solo está activo si el código de idoneidad de contacto está establecido en Relación.</span><span class="sxs-lookup"><span data-stu-id="43834-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="43834-129">**Vencimiento**</span><span class="sxs-lookup"><span data-stu-id="43834-129">**Age**</span></span> | <span data-ttu-id="43834-130">La edad máxima de un contacto personal idóneo para el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="43834-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="43834-131">Este campo solo está activo si selecciona una relación.</span><span class="sxs-lookup"><span data-stu-id="43834-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="43834-132">Esta edad se compara con la edad calculada del contacto personal.</span><span class="sxs-lookup"><span data-stu-id="43834-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="43834-133">La edad calculada es: (Fecha de cobertura - fecha de nacimiento del contacto personal / 365).</span><span class="sxs-lookup"><span data-stu-id="43834-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="43834-134">Este número siempre es un entero.</span><span class="sxs-lookup"><span data-stu-id="43834-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="43834-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="43834-135">Select **Save**.</span></span> 
