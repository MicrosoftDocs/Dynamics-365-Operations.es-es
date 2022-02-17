---
title: Ampliar Talent con Power Apps y Power Automate
description: En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fedf9b35e5dc8372fd82c6308ec5b1452eab7e8f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070309"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Ampliar con Power Apps y Power Automate


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate. Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps. Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.

> [!IMPORTANT]
> Si desea usar las plantillas y las aplicaciones que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.

## <a name="prerequisites"></a>Requisitos previos

- Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.
- Para exportar o importar aplicaciones, los usuarios deben tener una licencia Power Apps Plan 2 o una licencia de prueba de Power Apps Plan 2.

## <a name="integration-with-microsoft-365-power-automate"></a>Integración con Microsoft 365, Power Automate

La aplicación **Integración con Microsoft 365** se puede utilizar para extraer información de equipos para usuarios registrados desde Microsoft 365. Hace referencia a los trabajadores de Recursos Humanos para extraer tipos de identificación de empleados. Los directores pueden comprobar las fechas de vencimiento de los tipos de identificación de empleados. También pueden enviar un recordatorio por correo electrónico si el tipo de id. de empleado va a expirar. Power Automate se integra con Power Apps para enviar este recordatorio. La confirmación se devolverá a Power Apps desde Power Automate cuando se envíe el recordatorio. Los tipos de identificación incluyen el permiso de conducir, el pasaporte y otras formas aceptables de identificación.

Puede ampliar esta aplicación para otros escenarios. Por ejemplo, puede usarla para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.

Para descargar la aplicación **Integración con Microsoft 365, Power Automate**, vaya a [Integración con Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Conectar y ejecutar SQL

La plantilla **Power Automate - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.

Aunque esta plantilla lee y actualiza las tablas SQL, puede ampliarla y usarla para otros escenarios. Por ejemplo, puede usarla para rellenar una tabla de ensayo de Dataverse con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental desde SQL Server.

La consulta avanzada está integrada con Flow para permitir la transformación de datos y la inserción incremental.

Para descargar la plantilla **Power Automate - Conectar y ejecutar SQL**, vaya a [Power Automate - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.

## <a name="additional-resources"></a>Recursos adicionales

[La Microsoft Power Platform](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
