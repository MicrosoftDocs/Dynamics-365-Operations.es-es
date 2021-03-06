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
# <a name="reporting-options"></a>Opciones del informe

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