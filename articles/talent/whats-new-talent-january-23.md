---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (23 de enero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3c7a389ef4a651135836ce682d7cda95c536011a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550214"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a><span data-ttu-id="20e24-103">Novedades y cambios en Dynamics 365 Talent - Core HR (23 de enero de 2019)</span><span class="sxs-lookup"><span data-stu-id="20e24-103">What's new or changed in Dynamics 365 Talent - Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="20e24-104">**Compilación 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="20e24-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="20e24-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="20e24-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="20e24-106">Cambios</span><span class="sxs-lookup"><span data-stu-id="20e24-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="20e24-107">Importación de compensación fija del empleado que no funciona al crear nuevos registros de compensación fija</span><span class="sxs-lookup"><span data-stu-id="20e24-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="20e24-108">Un cambio se ha realizado a la entidad de la compensación fija del empleado para recuperar el nivel de compensación al realizar la importación.</span><span class="sxs-lookup"><span data-stu-id="20e24-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="20e24-109">Antes de esta versión, un mensaje se visualizaba indicando que se requería el nivel.</span><span class="sxs-lookup"><span data-stu-id="20e24-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="20e24-110">Eliminación del campo de saldo mínimo desde el cuadro de diálogo de solicitud de licencia</span><span class="sxs-lookup"><span data-stu-id="20e24-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="20e24-111">El campo de **saldo mínimo** se ha eliminado del cuadro de diálogo **solicitud de licencia**.</span><span class="sxs-lookup"><span data-stu-id="20e24-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="20e24-112">Este cambio afecta a todas las áreas en las que el tiempo libre puede ser solicitado.</span><span class="sxs-lookup"><span data-stu-id="20e24-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="20e24-113">Actualización de datos para niveles de compensación que no actualizan en todas las situaciones</span><span class="sxs-lookup"><span data-stu-id="20e24-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="20e24-114">Un cambio se ha realizado para actualizar el nivel de compensación en planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="20e24-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="20e24-115">Este cambio rellenará el nivel de compensación de los planes fijos para el trabajo asignado al empleado.</span><span class="sxs-lookup"><span data-stu-id="20e24-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="20e24-116">La información de nómina en la página de administración de cambios sólo está disponible si está abierta sesión como administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="20e24-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="20e24-117">Este cambio permite a empleados con el rol de administrador acceder a la información de nómina en la página **Línea de tiempo de cambios > administrar cambios** para el puesto.</span><span class="sxs-lookup"><span data-stu-id="20e24-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="20e24-118">Los campos de trabajo toman puestos como valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="20e24-118">Job fields default to positions</span></span>
<span data-ttu-id="20e24-119">Al cambiar el trabajo en un puesto, los campos de trabajo establecerán como valor predeterminado el puesto.</span><span class="sxs-lookup"><span data-stu-id="20e24-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="20e24-120">Un mensaje de alerta aparecerá y dará la opción de aceptar los valores predeterminados o conservar los valores existentes de dichos campos.</span><span class="sxs-lookup"><span data-stu-id="20e24-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="20e24-121">El período y el calendario de período de prueba no se muestran para los empleados contratados en el futuro.</span><span class="sxs-lookup"><span data-stu-id="20e24-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="20e24-122">Con este cambio, los campos **Período de prueba** y **Calendario** se han agregado a la página **Gestionar los cambios** para permitir la entrada de datos para empleados del futuro y pasados.</span><span class="sxs-lookup"><span data-stu-id="20e24-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23-for-finance-and-operations"></a><span data-ttu-id="20e24-123">Platform update 23 para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="20e24-123">Platform update 23 for Finance and Operations</span></span>
<span data-ttu-id="20e24-124">Se han incluido correcciones de errores de menor importancia como parte de la Platform update 23 para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20e24-124">Minor bug fixes have been included as part of Platform update 23 for Finance and Operations.</span></span> <span data-ttu-id="20e24-125">Para obtener más información, consulte [Novedades y cambios en la actualización 23 de la plataforma Dynamics 365 Finance and Operations (enero de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="20e24-125">For more information, see [What's new or changed in Dynamics 365 Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
