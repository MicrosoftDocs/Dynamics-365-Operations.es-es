---
title: Opciones del informe
description: El artículo explica cómo resolver la incidencia cuando un cliente quiere personalizar informes de Microsoft Dynamics 365 Human Resources o crear nuevos informes.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a03724d81745373d028d76a8cc64aab66efdbb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053308"
---
# <a name="reporting-options"></a><span data-ttu-id="97368-103">Opciones del informe</span><span class="sxs-lookup"><span data-stu-id="97368-103">Reporting options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="97368-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="97368-104">**Environment details**</span></span>

<span data-ttu-id="97368-105">Este problema se aplica a todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="97368-105">This issue applies to all environments.</span></span>

<span data-ttu-id="97368-106">**Síntoma**</span><span class="sxs-lookup"><span data-stu-id="97368-106">**Symptom**</span></span>

<span data-ttu-id="97368-107">El cliente desea personalizar informes de Microsoft Dynamics 365 Human Resources o crear nuevos informes.</span><span class="sxs-lookup"><span data-stu-id="97368-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="97368-108">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="97368-108">**Issue**</span></span>

<span data-ttu-id="97368-109">El usuario no puede personalizar los informes incrustados de Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="97368-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="97368-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="97368-110">**Solution**</span></span>

- <span data-ttu-id="97368-111">Los datos de Recursos humanos que fluyen a Dataverse pueden notificarse por medio del conector de Dataverse de Power Apps a Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="97368-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="97368-112">Tenga en cuenta que Dataverse contiene un subconjunto de datos de Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="97368-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="97368-113">Para obtener más información sobre Power BI y los paneles, consulte [Crear informes y paneles de Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="97368-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="97368-114">La generación de informes (ER) está disponible para algunos informe en Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="97368-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="97368-115">Las personalizaciones adaptadas a las necesidades del cliente se pueden realizar a través de las opciones de configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="97368-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="97368-116">Los datos se pueden exportar a Microsoft Excel o Microsoft Word mediante varias entidades de datos que los Recursos humanos proporcionan a través de la integración de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="97368-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="97368-117">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="97368-117">**Long-term solution**</span></span>

<span data-ttu-id="97368-118">Las opciones adicionales de Power BI estarán disponibles, y más entidades y datos formarán parte de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="97368-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]