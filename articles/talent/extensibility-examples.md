---
title: Ampliar Talent con Power Apps y Power Automate
description: 'En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent: Attract que usan Microsoft Power Apps y Microsoft Power Automate.'
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 1051fa4db16bb94cc9d60a91fc3637d7e5305cc2
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029920"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Ampliar Talent con Power Apps y Power Automate

En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent: Attract que usan Microsoft Power Apps y Microsoft Power Automate. Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps. Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.

> [!IMPORTANT]
> Si desea usar las plantillas y la aplicación que se describen en este artículo “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.


## <a name="prerequisites"></a>Requisitos previos

- Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.
- Para exportar o importar aplicaciones, los usuarios deben tener una licencia Power Apps Plan 2 o una licencia de prueba de Power Apps Plan 2.

## <a name="power-automate--form-connect"></a>Power Automate - Conectar formulario

La plantilla **Power Automate - Conectar formulario** se puede usar para leer datos de Microsoft Forms y almacenarlos en una entidad de Common Data Service.

Esta plantilla puede ser ampliada para que pueda usar otros escenarios. A continuación se incluyen algunos ejemplos:

- Captura evaluaciones de candidato.
- Captura resultados de los cuestionarios del curso.
- Compile una biblioteca de las preguntas de la entrevista para los administradores de recursos humanos (HR).
- Captura la evaluación de un candidato del proceso de la entrevista

En Microsoft Dynamics 365: Attract, puede usar formularios en el portal de candidatos, donde los candidatos pueden completar los detalles. Los formularios también se pueden insertar como actividades en una plantilla de trabajo.

Cuando un candidato envía un formulario, Microsoft Power Automate captura el envío del formulario, lee los datos y los almacena en la entidad Common Data Service.

Para descargar la plantilla **Power Automate - Conectar formulario** y la estructura de entidad personalizada, vaya a [Power Automate - Conectar formulario](https://go.microsoft.com/fwlink/?linkid=2081988) en el Centro de descarga de Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Integración de Power Automate - SharePoint

La plantilla **Power Automate – Integración con SharePoint** se puede usar para leer datos de una lista de Microsoft SharePoint, comparar la lista con los valores de campo de cualquier entidad de Common Data Service, y enviar los resultados de la comparación como una notificación de correo electrónico. 

Una organización puede tener un conjunto de aptitudes que necesita con urgencia. Estos aptitudes se pueden almacenar en SharePoint como una lista SharePoint. Cuando un candidato solicita cualquier trabajo que cuenta con un conjunto de las aptitudes necesarias, si hay una coincidencia significativa entre las aptitudes del candidato y las aptitudes que se almacenan en SharePoint, se envía una notificación por correo electrónico. Esto ayuda a ocupar más rápidamente los puestos que se requieren con urgencia, ya que las notificaciones ayudan a los reclutadores a contratar a candidatos en toda la organización.

Esta plantilla puede ser ampliada para que pueda usar para cualquier escenario que implique la integración con SharePoint.

Para descargar la plantilla **Integración de Power Automate – SharePoint** con , vaya a Integración de [Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) en el Centro de descarga de Microsoft.

## <a name="referral-app"></a>Aplicación de referencia

Puede usar la aplicación de referencia para agregar candidatos a una reserva de talentos compartida. La persona que hace la referencia puede especificar **Nombre**, **Apellidos**, **Correo electrónico** y **Dirección URL de Linkedln**, al registrar un candidato. Luego los metadatos de origen del candidato se rellenan con la información de la persona que hace la referencia.

Puede insertar esta aplicación en el autoservicio para empleados para enviar referencias o puede usarla como hipervínculo en el portal corporativo y ejecutarla como aplicación independiente.

Para descargar **Aplicación de referencia**, [solución de extensibilidad de Dynamics 365 Talent: Aplicación de referencia](https://www.microsoft.com/download/details.aspx?id=58497) en al Centro de descargas de Microsoft. Puede importar esta aplicación y personalizarla para agregar una funcionalidad adicional.

## <a name="additional-resources"></a>Recursos adicionales

[La Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migrar la aplicación entre arrendatarios y entornos](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
