---
title: Trabajadores responsables de aprobar disconformidades
description: Este tema describe cómo configurar trabajadores que son responsables de aprobar disconformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5979cb33146a00c3ea49ada9577140b24c07928f
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956822"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="5fd7f-103">Trabajadores responsables de aprobar disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5fd7f-104">Este tema describe cómo configurar trabajadores que son responsables de aprobar disconformidades.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="5fd7f-105">Las disconformidades deben aprobarse antes de que los usuarios puedan comenzar a introducir detalles como correcciones u operaciones.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="5fd7f-106">Antes de que los usuarios puedan aprobar o rechazar las disconformidades, su id. de usuario (registro de usuario) debe estar vinculado a un registro de trabajador.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="5fd7f-107">Opcionalmente, puede configurar trabajadores que son responsables de la calidad y luego permitir que un trabajador apruebe el trabajo en nombre de otro trabajador.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="5fd7f-108">Habilitar a un usuario para el procesamiento de disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="5fd7f-109">Antes de que un usuario pueda aprobar o rechazar las disconformidades, se debe vincular su id. de usuario a un registro de trabajador.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="5fd7f-110">Los campos de aprobación se pueden configurar automáticamente, y el usuario actual se puede completar automáticamente para la hoja de tiempos.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="5fd7f-111">Para que el usuario pueda utilizar las notas de documento, es necesario activar el manejo de documentos en sus opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="5fd7f-112">Vaya a **Administración del sistema \> Usuarios \> Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="5fd7f-113">Busque y abra el usuario que debería poder aprobar o rechazar las disconformidades.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="5fd7f-114">Establezca el campo **Persona** con el nombre del trabajador que está relacionado con el registro de usuario actual.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="5fd7f-115">En el panel de acciones, seleccione **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="5fd7f-116">En la página **Opciones** del registro de usuario actual, en la pestaña **Preferencias**, establezca la opción **Habilitar el manejo de documentos** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="5fd7f-117">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="5fd7f-118">Definir trabajadores responsables de la calidad</span><span class="sxs-lookup"><span data-stu-id="5fd7f-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="5fd7f-119">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Trabajadores responsables de la calidad**.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="5fd7f-120">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="5fd7f-121">En el campo **Trabajador**, seleccione el trabajador que introduce los datos de calidad.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="5fd7f-122">En el campo **Trabajador responsable**, seleccione el trabajador en nombre del cual el trabajador seleccionado introduce el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="5fd7f-123">Cuando se crean y actualizan disconformidades, este trabajador se introducirá de orma predeterminada en los campos **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="5fd7f-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5fd7f-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5fd7f-124">Additional resources</span></span>

- [<span data-ttu-id="5fd7f-125">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="5fd7f-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="5fd7f-126">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="5fd7f-127">Gastos de calidad</span><span class="sxs-lookup"><span data-stu-id="5fd7f-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="5fd7f-128">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="5fd7f-129">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="5fd7f-130">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="5fd7f-131">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="5fd7f-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="5fd7f-132">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="5fd7f-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
