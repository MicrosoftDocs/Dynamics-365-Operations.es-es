---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (24 de septiembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aeb75fe4c775b9003c6429de536498f495224098
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306117"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-24-2018"></a><span data-ttu-id="74f75-103">Novedades y cambios en Dynamics 365 for Talent Core HR (24 de septiembre de 2018)</span><span class="sxs-lookup"><span data-stu-id="74f75-103">What's new or changed in Dynamics 365 for Talent Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="74f75-104">**Compilación 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="74f75-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="74f75-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="74f75-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="74f75-106">Divisa agregada a prestaciones</span><span class="sxs-lookup"><span data-stu-id="74f75-106">Currency added to Benefits</span></span>

<span data-ttu-id="74f75-107">Se han actualizado los planes de prestaciones para incluir la divisa de la prestación.</span><span class="sxs-lookup"><span data-stu-id="74f75-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="74f75-108">Este nuevo campo también está disponible en las prestaciones de los trabajadores inscritos.</span><span class="sxs-lookup"><span data-stu-id="74f75-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="74f75-109">Este nuevo campo es parte del privilegio de seguridad Mantener beneficios y Ver una lista de beneficios.</span><span class="sxs-lookup"><span data-stu-id="74f75-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="74f75-110">Actualizar proceso de prorrateo - bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="74f75-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="74f75-111">Las organizaciones conceden tiempo libre de manera diferente basándose en cuándo los empleados se unen y dejan la empresa.</span><span class="sxs-lookup"><span data-stu-id="74f75-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="74f75-112">Para los empleados que salen de la organización, algunos tienen que finalizar la prima en la fecha final, mientras que otros se basan en el último día trabajado para detener el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="74f75-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="74f75-113">Estos cambios proporcionan a las organizaciones la capacidad para elegir cuándo finalizar la inscripción durante el proceso de finalización.</span><span class="sxs-lookup"><span data-stu-id="74f75-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="74f75-114">Estas nuevas opciones son parte de los privilegios para dar de baja a un trabajador y dar de baja a un trabajador del autoservicio de directores.</span><span class="sxs-lookup"><span data-stu-id="74f75-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="74f75-115">Otros cambios</span><span class="sxs-lookup"><span data-stu-id="74f75-115">Other changes</span></span>

<span data-ttu-id="74f75-116">Este lanzamiento incluye varias correcciones de errores adicionales.</span><span class="sxs-lookup"><span data-stu-id="74f75-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="74f75-117">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="74f75-117">Known Issue</span></span>

-   <span data-ttu-id="74f75-118">**Problema:** Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** se atenúan. **Solución alternativa**: Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos de la página **Trabajador** estén cerrados.</span><span class="sxs-lookup"><span data-stu-id="74f75-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="74f75-119">Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan.</span><span class="sxs-lookup"><span data-stu-id="74f75-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="74f75-120">(Este problema se corregirá en la siguiente actualización de la plataforma).</span><span class="sxs-lookup"><span data-stu-id="74f75-120">(This issue will be fixed in the next platform update.)</span></span>
