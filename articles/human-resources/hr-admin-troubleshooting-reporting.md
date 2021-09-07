---
title: Opciones de informes
description: En este tema se explica cómo personalizar informes de Microsoft Dynamics 365 Human Resources o crear informes nuevos.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 706e901e89fa618540067d68546be1cef1ee7148
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413391"
---
# <a name="reporting-options"></a>Opciones de informes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Detalles del entorno**

Este problema se aplica a todos los entornos.

**Síntoma**

El cliente desea personalizar informes de Microsoft Dynamics 365 Human Resources o crear nuevos informes.

**Emitir**

El usuario no puede personalizar los informes incrustados de Microsoft Power BI.

**Solución**

- Los datos de Recursos humanos que fluyen a Dataverse pueden notificarse por medio del conector de Dataverse de Power Apps a Power BI Desktop. Tenga en cuenta que Dataverse contiene un subconjunto de datos de Recursos humanos. Para obtener más información sobre Power BI y los paneles, consulte [Crear informes y paneles de Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- La generación de informes (ER) está disponible para algunos informe en Recursos humanos. Las personalizaciones adaptadas a las necesidades del cliente se pueden realizar a través de las opciones de configuración de ER.
- Los datos se pueden exportar a Microsoft Excel o Microsoft Word mediante varias entidades de datos que los Recursos humanos proporcionan a través de la integración de Microsoft Office.

**Solución a largo plazo**

Las opciones adicionales de Power BI estarán disponibles, y más entidades y datos formarán parte de Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
