---
title: Novedades y cambios en Dynamics 365 Talent (14 de febrero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
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
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9f3fa269217bc03a15fde6ee0fc9d0c502c17b3e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009131"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a><span data-ttu-id="1d040-103">Novedades y cambios en Dynamics 365 Talent (14 de febrero de 2019)</span><span class="sxs-lookup"><span data-stu-id="1d040-103">What's new or changed in Dynamics 365 Talent (February 14, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d040-104">Este tema describe las características que son nuevas o que se han cambiado en Talent.</span><span class="sxs-lookup"><span data-stu-id="1d040-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="1d040-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="1d040-105">Changes in Attract</span></span>
<span data-ttu-id="1d040-106">En esta versión se incluyen correcciones de errores menores.</span><span class="sxs-lookup"><span data-stu-id="1d040-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="1d040-107">Cambios en Onboarding</span><span class="sxs-lookup"><span data-stu-id="1d040-107">Changes in Onboarding</span></span>
<span data-ttu-id="1d040-108">En esta versión se incluyen correcciones de errores menores.</span><span class="sxs-lookup"><span data-stu-id="1d040-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="1d040-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="1d040-109">Changes in Core HR</span></span> 
<span data-ttu-id="1d040-110">**Compilación 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="1d040-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="1d040-111">La entidad de compensación fija del empleado no exporta todos los registros</span><span class="sxs-lookup"><span data-stu-id="1d040-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="1d040-112">Con este cambio, la entidad **Compensación fija del empleado** ahora exportará todos los registros.</span><span class="sxs-lookup"><span data-stu-id="1d040-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="1d040-113">La entidad puede ser utilizada para crear y actualizar registros existentes de compensación fija para los empleados.</span><span class="sxs-lookup"><span data-stu-id="1d040-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="1d040-114">La fecha de finalización del empleo no cumple los valores preferidos de zona horaria del empleado</span><span class="sxs-lookup"><span data-stu-id="1d040-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="1d040-115">Las fechas de finalización del empleo ahora cumplen la zona horaria preferida del usuario al crear o finalizar el empleo en una empresa.</span><span class="sxs-lookup"><span data-stu-id="1d040-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="1d040-116">Las direcciones del Reino Unido se muestran en Analytics como direcciones del este de Suiza</span><span class="sxs-lookup"><span data-stu-id="1d040-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="1d040-117">En esta versión, un cambio se ha realizado para corregir la desalineación en las direcciones del informe "Recuento de personal por ubicación" de la **Dirección de personal**.</span><span class="sxs-lookup"><span data-stu-id="1d040-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="1d040-118">El código de finalización no se rellena en el registro de asignación de puesto del trabajador al finalizar el puesto</span><span class="sxs-lookup"><span data-stu-id="1d040-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="1d040-119">Un cambio se ha realizado para establecer el código de “motivo de la finalización” en el valor predeterminado al finalizar la asignación de puesto de los empleados.</span><span class="sxs-lookup"><span data-stu-id="1d040-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="1d040-120">Creada una nueva entidad para los niveles de compensación de trabajo</span><span class="sxs-lookup"><span data-stu-id="1d040-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="1d040-121">Se ha creado una nueva entidad de marco de gestión de datos (DMF).</span><span class="sxs-lookup"><span data-stu-id="1d040-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="1d040-122">La entidad se encarga de la creación y la actualización de los niveles de compensación, los valores de mercado, y la información de encuesta para cada trabajo definido en el sistema.</span><span class="sxs-lookup"><span data-stu-id="1d040-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
