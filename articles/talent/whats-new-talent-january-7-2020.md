---
title: Novedades y cambios en Dynamics 365 Talent (7 de enero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462478"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="fcb6a-103">Novedades y cambios en Dynamics 365 Talent (7 de enero de 2020)</span><span class="sxs-lookup"><span data-stu-id="fcb6a-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="fcb6a-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="fcb6a-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="fcb6a-105">Changes in Attract</span></span>

<span data-ttu-id="fcb6a-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="fcb6a-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="fcb6a-107">Changes in Onboard</span></span>

<span data-ttu-id="fcb6a-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="fcb6a-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="fcb6a-109">Changes in Core HR</span></span>

<span data-ttu-id="fcb6a-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="fcb6a-111">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fcb6a-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="fcb6a-112">No se pueden eliminar los trabajadores que no tienen registros de empleo - (386157)</span><span class="sxs-lookup"><span data-stu-id="fcb6a-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="fcb6a-113">Este cambio agrega una opción de eliminación en el formulario **Trabajadores sin empleo**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="fcb6a-114">Los trabajadores aparecen en este formulario cuando no existen empleos futuros, activos o históricos para el trabajador.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="fcb6a-115">En esta versión, la eliminación solo está habilitada para los administradores del sistema.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="fcb6a-116">Sin embargo, en la versión de la próxima semana, la seguridad se actualizará para permitir que todos los usuarios con el rol de asistente de Recursos Humanos eliminen a los empleados sin empleo.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="fcb6a-117">También puede realizar estos cambios manualmente siguiendo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="fcb6a-118">Vaya a **Configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="fcb6a-119">En la pestaña **Privilegios**, filtre la lista **Privilegios** para **Mantener trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="fcb6a-120">En la columna **Referencias**, seleccione **Elementos del menú de visualización**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="fcb6a-121">En **Elementos del menú de visualización**, seleccione **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="fcb6a-122">Selecciona el permiso **Eliminar** para Conceder.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="fcb6a-123">Seleccione la pestaña **Objetos sin publicar**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="fcb6a-124">Seleccione **Publicar todo**.</span><span class="sxs-lookup"><span data-stu-id="fcb6a-124">Select **Publish all**.</span></span>
