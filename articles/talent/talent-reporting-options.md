---
title: Opciones de informes en Talent
description: Este tema explica cómo resolver el problema en que el cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306162"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="be599-103">Opciones de informes en Talent</span><span class="sxs-lookup"><span data-stu-id="be599-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="be599-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="be599-104">**Environment details**</span></span>

<span data-ttu-id="be599-105">Este problema se aplica a todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="be599-105">This issue applies to all environments.</span></span>

<span data-ttu-id="be599-106">**Síntoma**</span><span class="sxs-lookup"><span data-stu-id="be599-106">**Symptom**</span></span>

<span data-ttu-id="be599-107">El cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes.</span><span class="sxs-lookup"><span data-stu-id="be599-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="be599-108">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="be599-108">**Issue**</span></span>

<span data-ttu-id="be599-109">El usuario no puede personalizar los informes incrustados de Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="be599-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="be599-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="be599-110">**Solution**</span></span>

- <span data-ttu-id="be599-111">Los datos de Core HR que fluyen a Common Data Service for Apps se pueden notificar mediante el conector de PowerApps CDS a Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="be599-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="be599-112">Tenga en cuenta que Common Data Service for Apps contiene un subconjunto de datos de Core HR.</span><span class="sxs-lookup"><span data-stu-id="be599-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="be599-113">Para obtener más información sobre Power BI y los paneles, consulte [Crear informes y paneles de Power BI con PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="be599-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="be599-114">Los informes electrónicos (ER) están disponibles para algunos informes en Talent.</span><span class="sxs-lookup"><span data-stu-id="be599-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="be599-115">Las personalizaciones adaptadas a las necesidades del cliente se pueden realizar a través de las opciones de configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="be599-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="be599-116">Los datos se pueden exportar a Microsoft Excel o a Microsoft Word mediante diversas entidades de datos que Talent proporciona mediante la integración de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="be599-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="be599-117">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="be599-117">**Long-term solution**</span></span>

<span data-ttu-id="be599-118">Las opciones adicionales de Power BI estarán disponibles, y más entidades y datos formarán parte de Common Data Service for Apps.</span><span class="sxs-lookup"><span data-stu-id="be599-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>
