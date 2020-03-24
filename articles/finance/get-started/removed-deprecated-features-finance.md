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
ms.openlocfilehash: ec13076e6a05c3402af566487f7921f6971da215
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127986"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="82434-103">Características quitadas u obsoletas de Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="82434-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82434-104">En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="82434-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="82434-105">Una función *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="82434-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="82434-106">Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="82434-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="82434-107">Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="82434-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="82434-108">La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="82434-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="82434-109">Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="82434-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="82434-110">Características quitadas o en desuso en la versión Finance 10.0.12</span><span class="sxs-lookup"><span data-stu-id="82434-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="82434-111">Informes de SSRS polacos: registro de IVA diferido, registro de IVA soportado, registro de resumen de IVA de la UE - Referencia de características PL-00014</span><span class="sxs-lookup"><span data-stu-id="82434-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="82434-112">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="82434-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="82434-113">Legalmente no requerido.</span><span class="sxs-lookup"><span data-stu-id="82434-113">Not legally required.</span></span>  |
| <span data-ttu-id="82434-114">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="82434-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="82434-115">Sí (formato Excel para el archivo de auditoría estándar con declaración de IVA - JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="82434-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="82434-116">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="82434-116">**Product areas affected**</span></span>         | <span data-ttu-id="82434-117">Solicitud</span><span class="sxs-lookup"><span data-stu-id="82434-117">Application</span></span> |
| <span data-ttu-id="82434-118">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="82434-118">**Deployment option**</span></span>              | <span data-ttu-id="82434-119">Todos</span><span class="sxs-lookup"><span data-stu-id="82434-119">All</span></span> |
| <span data-ttu-id="82434-120">**Estado**</span><span class="sxs-lookup"><span data-stu-id="82434-120">**Status**</span></span>                         | <span data-ttu-id="82434-121">En desuso: está previsto que el 1 de julio de 2021 se retiren los informes de SSRS: **Registro de IVA diferido, Registro de IVA soportado, Registro de resumen de IVA de la UE - Referencia de características PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="82434-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="82434-122">En su lugar se incluirá el ejemplo con formato Excel del archivo de auditoría estándar con declaración de IVA (JPK_VDEK).</span><span class="sxs-lookup"><span data-stu-id="82434-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="82434-123">Características quitadas o en desuso en la versión Finance 10.0.7</span><span class="sxs-lookup"><span data-stu-id="82434-123">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="82434-124">El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario</span><span class="sxs-lookup"><span data-stu-id="82434-124">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="82434-125">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="82434-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="82434-126">Cambiado a la característica con la selección de grupos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="82434-126">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="82434-127">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="82434-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="82434-128">Sí</span><span class="sxs-lookup"><span data-stu-id="82434-128">Yes</span></span> |
| <span data-ttu-id="82434-129">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="82434-129">**Product areas affected**</span></span>         | <span data-ttu-id="82434-130">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="82434-130">Workflow</span></span> |
| <span data-ttu-id="82434-131">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="82434-131">**Deployment option**</span></span>              | <span data-ttu-id="82434-132">Todos</span><span class="sxs-lookup"><span data-stu-id="82434-132">All</span></span> |
| <span data-ttu-id="82434-133">**Estado**</span><span class="sxs-lookup"><span data-stu-id="82434-133">**Status**</span></span>                         | <span data-ttu-id="82434-134">En desuso: El 1 de diciembre de 2020, planeamos dejar de admitir la configuración de tipos de asiento para China sin selección de grupos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="82434-134">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="82434-135">Para obtener más detalles sobre el nuevo diseño, consulte [Novedades en 10.0.7](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="82434-135">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="82434-136">Anuncios anteriores sobre funciones quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="82434-136">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="82434-137">Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="82434-137">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
