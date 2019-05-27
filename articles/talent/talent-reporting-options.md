---
title: Opciones de informes en Talent
description: Este tema explica cómo resolver el problema en que el cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7e00a6e4fc01f72e1ef2347e08754997135215ed
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519044"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="fc932-103">Opciones de informes en Talent</span><span class="sxs-lookup"><span data-stu-id="fc932-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fc932-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="fc932-104">**Environment details**</span></span>

<span data-ttu-id="fc932-105">Este problema se aplica a todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="fc932-105">This issue applies to all environments.</span></span>

<span data-ttu-id="fc932-106">**Síntoma**</span><span class="sxs-lookup"><span data-stu-id="fc932-106">**Symptom**</span></span>

<span data-ttu-id="fc932-107">El cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes.</span><span class="sxs-lookup"><span data-stu-id="fc932-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="fc932-108">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="fc932-108">**Issue**</span></span>

<span data-ttu-id="fc932-109">El usuario no puede personalizar los informes incrustados de Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="fc932-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="fc932-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="fc932-110">**Solution**</span></span>

- <span data-ttu-id="fc932-111">Los datos de Core HR que fluyen a Common Data Service se pueden notificar mediante el conector de PowerApps Common Data Service a Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="fc932-111">The Core HR data that flows to Common Data Service can be reported on via the PowerApps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="fc932-112">Tenga en cuenta que Common Data Service contiene un subconjunto de datos de Core HR.</span><span class="sxs-lookup"><span data-stu-id="fc932-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="fc932-113">Para obtener más información sobre Power BI y los paneles, consulte [Crear informes y paneles de Power BI con PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="fc932-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="fc932-114">Los informes electrónicos (ER) están disponibles para algunos informes en Talent.</span><span class="sxs-lookup"><span data-stu-id="fc932-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="fc932-115">Las personalizaciones adaptadas a las necesidades del cliente se pueden realizar a través de las opciones de configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="fc932-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="fc932-116">Los datos se pueden exportar a Microsoft Excel o a Microsoft Word mediante diversas entidades de datos que Talent proporciona mediante la integración de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fc932-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="fc932-117">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="fc932-117">**Long-term solution**</span></span>

<span data-ttu-id="fc932-118">Las opciones adicionales de Power BI estarán disponibles, y más entidades y datos formarán parte de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fc932-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
