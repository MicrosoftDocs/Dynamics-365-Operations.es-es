---
title: Opciones de informes en Talent
description: "Este tema explica cómo resolver el problema en que el cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a>Opciones de informes en Talent

[!include [banner](includes/banner.md)]

**Detalles del entorno**

Este problema se aplica a todos los entornos.

**Síntoma**

El cliente desea personalizar informes de Microsoft Dynamics 365 for Talent o crear nuevos informes.

**Emisión**

El usuario no puede personalizar los informes incrustados de Microsoft Power BI.

**Solución**

- Los datos de Core HR que fluyen a Common Data Service for Apps se pueden notificar mediante el conector de PowerApps CDS a Power BI Desktop. Tenga en cuenta que Common Data Service for Apps contiene un subconjunto de datos de Core HR. Para obtener más información sobre Power BI y los paneles, consulte [Crear informes y los paneles con PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- Los informes electrónicos (ER) están disponibles para algunos informes en Talent. Las personalizaciones adaptadas a las necesidades del cliente se pueden realizar a través de las opciones de configuración de ER.
- Los datos se pueden exportar a Microsoft Excel o a Microsoft Word mediante diversas entidades de datos que Talent proporciona mediante la integración de Microsoft Office.

**Solución a largo plazo**

Las opciones adicionales de Power BI estarán disponibles, y más entidades y datos formarán parte de Common Data Service for Apps.

