---
title: Visión general del desarrollo
description: Esta Guía de desarrolladores proporciona una API y una referencia de campos personalizados. También proporciona información sobre la integración con otras aplicaciones.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 94652ba35879c043121cc5e74b4230b5a250e4bf
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054052"
---
# <a name="development-overview"></a><span data-ttu-id="922df-104">Visión general del desarrollo</span><span class="sxs-lookup"><span data-stu-id="922df-104">Development overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="922df-105">Esta Guía de desarrolladores proporciona una API y una referencia de campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="922df-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="922df-106">También proporciona información sobre la integración con otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="922df-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="922df-107">Información general</span><span class="sxs-lookup"><span data-stu-id="922df-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="922df-108">Ampliar con Power Apps y Power Automate</span><span class="sxs-lookup"><span data-stu-id="922df-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="922df-109">Entidades de Recursos Humanos en Dataverse</span><span class="sxs-lookup"><span data-stu-id="922df-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="922df-110">Campos personalizados</span><span class="sxs-lookup"><span data-stu-id="922df-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="922df-111">Configurar integración de datos</span><span class="sxs-lookup"><span data-stu-id="922df-111">Set up data integration</span></span>
  - [<span data-ttu-id="922df-112">Elegir una tecnología de integración de datos</span><span class="sxs-lookup"><span data-stu-id="922df-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="922df-113">Configurar la integración de Dataverse</span><span class="sxs-lookup"><span data-stu-id="922df-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="922df-114">Configurar la integración con Finance</span><span class="sxs-lookup"><span data-stu-id="922df-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="922df-115">Configurar la integración con Dayforce</span><span class="sxs-lookup"><span data-stu-id="922df-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="922df-116">Crear una aplicación de exportación de datos periódica</span><span class="sxs-lookup"><span data-stu-id="922df-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="922df-117">Integrar con Office</span><span class="sxs-lookup"><span data-stu-id="922df-117">Integrate with Office</span></span>
    - [<span data-ttu-id="922df-118">Tutorial de integración con Office</span><span class="sxs-lookup"><span data-stu-id="922df-118">Office integration tutorial</span></span>](../fin-ops-core/dev-itpro/office-integration/office-integration-tutorial.md?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)
    - [<span data-ttu-id="922df-119">Actualizar los datos de la entidad en Excel</span><span class="sxs-lookup"><span data-stu-id="922df-119">Update entity data in Excel</span></span>](../fin-ops-core/dev-itpro/office-integration/use-excel-add-in.md?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)
    - [<span data-ttu-id="922df-120">Crear experiencias de tipo Abrir en Excel</span><span class="sxs-lookup"><span data-stu-id="922df-120">Create Open in Excel experiences</span></span>](../fin-ops-core/dev-itpro/office-integration/office-integration-edit-excel.md?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)
    - [<span data-ttu-id="922df-121">Solución de problemas de la integración con Office</span><span class="sxs-lookup"><span data-stu-id="922df-121">Troubleshoot Office integration</span></span>](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)

- <span data-ttu-id="922df-122">Referencia de API de entidad</span><span class="sxs-lookup"><span data-stu-id="922df-122">Entity API reference</span></span>
  - [<span data-ttu-id="922df-123">Autenticación</span><span class="sxs-lookup"><span data-stu-id="922df-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="922df-124">Entidades</span><span class="sxs-lookup"><span data-stu-id="922df-124">Entities</span></span>
    - [<span data-ttu-id="922df-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="922df-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="922df-126">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="922df-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="922df-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="922df-127">See also</span></span>

- [<span data-ttu-id="922df-128">Novedades y cambios en Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="922df-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="922df-129">Guía del administrador</span><span class="sxs-lookup"><span data-stu-id="922df-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="922df-130">Manual del usuario</span><span class="sxs-lookup"><span data-stu-id="922df-130">User Guide</span></span>](hr-hrpro-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]