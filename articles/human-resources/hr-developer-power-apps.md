---
title: Ampliar Talent con Power Apps y Power Automate
description: En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e89347829ccd6569d568db42c79b5fea2316ba3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527035"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Ampliar con Power Apps y Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate. Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps. Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.

> [!IMPORTANT]
> Si desea usar las plantillas y las aplicaciones que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.

## <a name="prerequisites"></a>Requisitos previos

- Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.
- Para exportar o importar aplicaciones, los usuarios deben tener una licencia Power Apps Plan 2 o una licencia de prueba de Power Apps Plan 2.

## <a name="integration-with-microsoft-365-power-automate"></a>Integration con Microsoft 365, Power Automate

La aplicación **Integración con Microsoft 365** se puede utilizar para extraer información de equipos para usuarios que han iniciado sesión desde Microsoft 365. Hace referencia a los trabajadores de Recursos Humanos para extraer tipos de identificación de empleados. Los directores pueden comprobar las fechas de vencimiento de los tipos de identificación de empleados. También pueden enviar un recordatorio por correo electrónico si el tipo de id. de empleado va a expirar. Power Automate se integra con Power Apps para enviar este recordatorio. La confirmación se devolverá a Power Apps desde Power Automate cuando se envíe el recordatorio. Los tipos de identificación incluyen el permiso de conducir, el pasaporte y otras formas aceptables de identificación.

Puede ampliar esta aplicación para otros escenarios. Por ejemplo, puede usarla para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.

Para descargar la aplicación **Integración con Microsoft 365, Power Automate**, vaya a [Integración con Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Conectar y ejecutar SQL

La plantilla **Power Automate - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.

Aunque esta plantilla lee y actualiza las tablas SQL, puede ampliarla y usarla para otros escenarios. Por ejemplo, puede usarla para rellenar una tabla de ensayo de Common Data Service con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental desde SQL Server.

La consulta avanzada está integrada con Flow para permitir la transformación de datos y la inserción incremental.

Para descargar la plantilla **Power Automate - Conectar y ejecutar SQL**, vaya a [Power Automate - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.

## <a name="additional-resources"></a>Recursos adicionales

[La Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]