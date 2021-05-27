---
title: API de detalle del trabajo
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de detalle del trabajo en Dynamics 365 Human Resources.
author: jcart
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
ms.openlocfilehash: c92b0636fbd68c6ee7eded90a8cb5bcd0cda7ca3
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018371"
---
# <a name="job-detail-api"></a><span data-ttu-id="597d1-103">API de detalle del trabajo</span><span class="sxs-lookup"><span data-stu-id="597d1-103">Job detail API</span></span>

<span data-ttu-id="597d1-104">Este tema proporciona detalles y una consulta de ejemplo para la entidad de detalle del trabajo en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="597d1-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="597d1-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="597d1-105">Properties</span></span>

| <span data-ttu-id="597d1-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="597d1-106">Property</span></span><br><span data-ttu-id="597d1-107">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="597d1-107">**Physical name**</span></span><br><span data-ttu-id="597d1-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="597d1-108">**_Type_**</span></span> | <span data-ttu-id="597d1-109">Utilizar</span><span class="sxs-lookup"><span data-stu-id="597d1-109">Use</span></span> | <span data-ttu-id="597d1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="597d1-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="597d1-111">**Id. de trabajo**</span><span class="sxs-lookup"><span data-stu-id="597d1-111">**Job ID**</span></span><br><span data-ttu-id="597d1-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="597d1-112">mshr_jobid</span></span><br><span data-ttu-id="597d1-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="597d1-113">*String*</span></span> | <span data-ttu-id="597d1-114">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="597d1-114">Read-only</span></span><br><span data-ttu-id="597d1-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="597d1-115">Required</span></span> | <span data-ttu-id="597d1-116">Identificación única para un trabajo.</span><span class="sxs-lookup"><span data-stu-id="597d1-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="597d1-117">**Umbral bajo del precio de mercado**</span><span class="sxs-lookup"><span data-stu-id="597d1-117">**Market price low threshold**</span></span><br><span data-ttu-id="597d1-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="597d1-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="597d1-119">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="597d1-119">*Decimal*</span></span> | | <span data-ttu-id="597d1-120">Valor GUID generado por el sistema para identificar el puesto de forma única.</span><span class="sxs-lookup"><span data-stu-id="597d1-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
