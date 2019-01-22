---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (15 de noviembre de 2018)
description: "Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 3cc19a8e5f726495e698a3a2f4ccce7460a61657
ms.openlocfilehash: 0e9de5e36e67941ab09c773a63b0e7045105a07e
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="e40c4-103">Novedades y cambios en Dynamics 365 for Talent Core HR (15 de noviembre de 2018)</span><span class="sxs-lookup"><span data-stu-id="e40c4-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e40c4-104">**Compilación 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="e40c4-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="e40c4-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="e40c4-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="e40c4-106">Otros cambios/correcciones</span><span class="sxs-lookup"><span data-stu-id="e40c4-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="e40c4-107">Incapaz de cambiar el puesto actual del empleado por una vacante futura</span><span class="sxs-lookup"><span data-stu-id="e40c4-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="e40c4-108">Un cambio se ha realizado para habilitar las transferencias de puesto cuando el puesto sólo está disponible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e40c4-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="e40c4-109">El puesto no muestra al crear un nuevo empleado</span><span class="sxs-lookup"><span data-stu-id="e40c4-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="e40c4-110">Un cambio se ha realizado para mostrar todas las vacantes que están disponibles para su asignación cuando se contratan nuevos empleados en Talent.</span><span class="sxs-lookup"><span data-stu-id="e40c4-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="e40c4-111">Esto incluye puestos históricos o si los puestos se han fechado en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e40c4-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="e40c4-112">Los puestos ahora aparecerán correctamente según la fecha de inicio del empleo.</span><span class="sxs-lookup"><span data-stu-id="e40c4-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="e40c4-113">La fecha final se muestra en función de la configuración del usuario</span><span class="sxs-lookup"><span data-stu-id="e40c4-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="e40c4-114">Un cambio se ha realizado en la última lista de los empleados del pasado para explicar cualquier desplazamiento horario de la zona horaria preferida de los empleados cuando se visualiza la fecha final.</span><span class="sxs-lookup"><span data-stu-id="e40c4-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="e40c4-115">Los enlaces de elementos de trabajo que se me asignan no contienen la información correcta</span><span class="sxs-lookup"><span data-stu-id="e40c4-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="e40c4-116">Con este cambio, la navegación a los detalles de los elementos de trabajo individuales en la lista mostrarán la información correcta para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e40c4-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="e40c4-117">Este problema solo se producía con opciones de seguridad avanzadas.</span><span class="sxs-lookup"><span data-stu-id="e40c4-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="e40c4-118">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="e40c4-118">Known issue</span></span>

- <span data-ttu-id="e40c4-119">**Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan.</span><span class="sxs-lookup"><span data-stu-id="e40c4-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="e40c4-120">**Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados.</span><span class="sxs-lookup"><span data-stu-id="e40c4-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="e40c4-121">Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan.</span><span class="sxs-lookup"><span data-stu-id="e40c4-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="e40c4-122">(Este problema se corregirá en la siguiente actualización de la plataforma).</span><span class="sxs-lookup"><span data-stu-id="e40c4-122">(This issue will be fixed in the next platform update.)</span></span>
