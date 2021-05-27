---
title: Generar y revisar entidades de nómina
description: Este tema describe cómo generar y revisar entidades de nómina.
author: andreabichsel
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4adab0225190b4dea5213dccf297eaab33efc863
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021329"
---
# <a name="generate-payroll-entities"></a><span data-ttu-id="0dae4-103">Generar entidades de nómina</span><span class="sxs-lookup"><span data-stu-id="0dae4-103">Generate payroll entities</span></span>

<span data-ttu-id="0dae4-104">Utilice esta función de OData para generar las entidades necesarias para la integración de la nómina.</span><span class="sxs-lookup"><span data-stu-id="0dae4-104">Use this OData function to generate the entities needed for payroll integration.</span></span> <span data-ttu-id="0dae4-105">Si se realizan cambios en estas entidades en Recursos humanos, como agregar campos personalizados, esta función se puede volver a llamar para actualizar los metadatos de cada entidad.</span><span class="sxs-lookup"><span data-stu-id="0dae4-105">If any changes are made to these entities in Human Resources, such as adding custom fields, this function can be called again to refresh the metadata of each entity.</span></span> <span data-ttu-id="0dae4-106">La respuesta contiene un ID de operación que puede supervisar para saber cuándo se ha completado el proceso de generación.</span><span class="sxs-lookup"><span data-stu-id="0dae4-106">The response contains an operation ID that you can monitor so you know when the generation process has completed.</span></span>

<span data-ttu-id="0dae4-107">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0dae4-107">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/RefreshHumanResourcesVirtualEntities
```

<span data-ttu-id="0dae4-108">**cuerpo**</span><span class="sxs-lookup"><span data-stu-id="0dae4-108">**body**</span></span>

```json
{
    "PhysicalNames" : ["PayrollEmployeeEntity", "HcmWorkerBaseEntity", "PayrollPositionEntity", "PayrollPositionJobEntity", "PayrollWorkerAddressEntity", "HcmJobDetailEntity", "HcmCompFixedPlanTableEntity", "PayrollFixedCompensationPlanEntity", "HcmEmploymentDetailEntity"]
}
```

<span data-ttu-id="0dae4-109">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="0dae4-109">**Response**</span></span>

```json
{
    "AsyncOperationId": "8b98d338-f939-4c86-9a91-80b76b6ab2ea"
}
```

## <a name="review-payroll-entities"></a><span data-ttu-id="0dae4-110">Revisar entidades de nómina</span><span class="sxs-lookup"><span data-stu-id="0dae4-110">Review payroll entities</span></span>

<span data-ttu-id="0dae4-111">Utilice esta API para recuperar una lista de las entidades que se han generado correctamente y están listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="0dae4-111">Use this API to retrieve a list of the entities that have been successfully generated and are ready for use.</span></span>

<span data-ttu-id="0dae4-112">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0dae4-112">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hrvirtualentitycatalogs?$filter=mshr_hasbeengenerated eq true
```

<span data-ttu-id="0dae4-113">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="0dae4-113">**Response**</span></span>

```json
{
      "value": [
        {
            "mshr_physicalname": "PayrollWorkerAddressEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-1c00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmJobDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6400-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmCompFixedPlanTableEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6b00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollEmployeeEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6d00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmEmploymentDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-7e00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollFixedCompensationPlanEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-9300-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmWorkerBaseEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-c000-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollPositionJobEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-e700-005001000000",
            "mshr_refresh": null
        }
    ]
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]