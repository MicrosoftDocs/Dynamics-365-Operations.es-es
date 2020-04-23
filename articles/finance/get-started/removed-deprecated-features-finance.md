---
title: Características quitadas u obsoletas de Dynamics 365 Finance
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175117"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="30d05-103">Características quitadas u obsoletas de Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="30d05-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30d05-104">En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="30d05-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="30d05-105">Una función *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="30d05-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="30d05-106">Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="30d05-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="30d05-107">Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="30d05-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="30d05-108">La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="30d05-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="30d05-109">Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30d05-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="30d05-110">Características quitadas o en desuso en la versión Finance 10.0.12</span><span class="sxs-lookup"><span data-stu-id="30d05-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="30d05-111">Informes de SSRS polacos: registro de IVA diferido, registro de IVA soportado, registro de resumen de IVA de la UE - Referencia de características PL-00014</span><span class="sxs-lookup"><span data-stu-id="30d05-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="30d05-112">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="30d05-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="30d05-113">Legalmente no requerido.</span><span class="sxs-lookup"><span data-stu-id="30d05-113">Not legally required.</span></span>  |
| <span data-ttu-id="30d05-114">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="30d05-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="30d05-115">Sí (formato Excel para el archivo de auditoría estándar con declaración de IVA - JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="30d05-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="30d05-116">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="30d05-116">**Product areas affected**</span></span>         | <span data-ttu-id="30d05-117">Solicitud</span><span class="sxs-lookup"><span data-stu-id="30d05-117">Application</span></span> |
| <span data-ttu-id="30d05-118">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="30d05-118">**Deployment option**</span></span>              | <span data-ttu-id="30d05-119">Todos</span><span class="sxs-lookup"><span data-stu-id="30d05-119">All</span></span> |
| <span data-ttu-id="30d05-120">**Estado**</span><span class="sxs-lookup"><span data-stu-id="30d05-120">**Status**</span></span>                         | <span data-ttu-id="30d05-121">En desuso: está previsto que el 1 de julio de 2021 se retiren los informes de SSRS: **Registro de IVA diferido, Registro de IVA soportado, Registro de resumen de IVA de la UE - Referencia de características PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="30d05-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="30d05-122">En su lugar se incluirá el ejemplo con formato Excel del archivo de auditoría estándar con declaración de IVA (JPK_VDEK).</span><span class="sxs-lookup"><span data-stu-id="30d05-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a><span data-ttu-id="30d05-123">Características quitadas o en desuso en la versión Finance 10.0.11</span><span class="sxs-lookup"><span data-stu-id="30d05-123">Features removed or deprecated in the Finance 10.0.11 release</span></span>

### <a name="norwegian-standard-main-accounts"></a><span data-ttu-id="30d05-124">Cuentas principales noruegas estándar</span><span class="sxs-lookup"><span data-stu-id="30d05-124">Norwegian Standard main accounts</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="30d05-125">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="30d05-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="30d05-126">Rediseño</span><span class="sxs-lookup"><span data-stu-id="30d05-126">Redesign</span></span>  |
| <span data-ttu-id="30d05-127">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="30d05-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="30d05-128">Sí (reemplazado con parámetros específicos de la aplicación en formato ER)</span><span class="sxs-lookup"><span data-stu-id="30d05-128">Yes (Replaced with ER format application-specific parameters)</span></span> |
| <span data-ttu-id="30d05-129">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="30d05-129">**Product areas affected**</span></span>         | <span data-ttu-id="30d05-130">Solicitud</span><span class="sxs-lookup"><span data-stu-id="30d05-130">Application</span></span> |
| <span data-ttu-id="30d05-131">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="30d05-131">**Deployment option**</span></span>              | <span data-ttu-id="30d05-132">Todos</span><span class="sxs-lookup"><span data-stu-id="30d05-132">All</span></span> |
| <span data-ttu-id="30d05-133">**Estado**</span><span class="sxs-lookup"><span data-stu-id="30d05-133">**Status**</span></span>                         | <span data-ttu-id="30d05-134">En desuso: para el 1 de abril de 2021, planeamos dejar de admitir la funcionalidad relacionada con las cuentas principales estándar: campo de referencia, tabla relacionada, entidad de datos.</span><span class="sxs-lookup"><span data-stu-id="30d05-134">Deprecated: By April 1, 2021, we plan to no longer support functionality related to Standard main accounts: Reference field, related table, data entity.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="30d05-135">Características quitadas o en desuso en la versión Finance 10.0.7</span><span class="sxs-lookup"><span data-stu-id="30d05-135">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="30d05-136">El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario</span><span class="sxs-lookup"><span data-stu-id="30d05-136">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="30d05-137">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="30d05-137">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="30d05-138">Cambiado a la característica con la selección de grupos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="30d05-138">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="30d05-139">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="30d05-139">**Replaced by another feature?**</span></span>   | <span data-ttu-id="30d05-140">Sí</span><span class="sxs-lookup"><span data-stu-id="30d05-140">Yes</span></span> |
| <span data-ttu-id="30d05-141">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="30d05-141">**Product areas affected**</span></span>         | <span data-ttu-id="30d05-142">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="30d05-142">Workflow</span></span> |
| <span data-ttu-id="30d05-143">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="30d05-143">**Deployment option**</span></span>              | <span data-ttu-id="30d05-144">Todos</span><span class="sxs-lookup"><span data-stu-id="30d05-144">All</span></span> |
| <span data-ttu-id="30d05-145">**Estado**</span><span class="sxs-lookup"><span data-stu-id="30d05-145">**Status**</span></span>                         | <span data-ttu-id="30d05-146">En desuso: El 1 de diciembre de 2020, planeamos dejar de admitir la configuración de tipos de asiento para China sin selección de grupos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="30d05-146">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="30d05-147">Para obtener más detalles sobre el nuevo diseño, consulte [Novedades en 10.0.7](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="30d05-147">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="30d05-148">Anuncios anteriores sobre funciones quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="30d05-148">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="30d05-149">Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="30d05-149">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
