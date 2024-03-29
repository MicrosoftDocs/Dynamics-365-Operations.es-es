---
title: Sincronizar fecha y hora en trabajos de importación
description: Utilice las zonas horarias UTC en los trabajos de importación para evitar problemas con las conversiones de zona horaria.
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8faa7b73349c48d3a02b685546b47c4969c6027
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109444"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Sincronizar fecha y hora en trabajos de importación

[!include [banner](../includes/banner.md)]

Es importante establecer la zona horaria de su trabajo de importación en la hora universal coordinada (UTC). Es posible que vea fechas y horas inesperadas en sus datos importados si usa una configuración diferente. Sin la configuración correcta, el proceso de importación convierte la fecha UTC al formato local y, después, la configuración del sistema la convierte nuevamente.

Esta conversión dual hace que las fechas cambien entre aplicaciones. Por ejemplo, la conversión dual podría hacer que la fecha de inicio de un empleado sea diferente entre Dynamics 365 Human Resources y Dynamics 365 Finance debido a las diferencias en las zonas horarias locales. Establecer el trabajo de importación en UTC resuelve este problema.

1. En finanzas y operaciones de Dynamics 365, seleccione **Administración de datos**.

2. Seleccione **Importar proyectos** y luego seleccione el proyecto.

3. En **Formato de fecha de origen**, seleccione **CSV-Unicode**.

   [![Cambiar el formato de la fecha de origen a UTC.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Cambie la **Zona horaria** a **Zona horaria universal coordinada**, y cambie **Idioma** a **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

