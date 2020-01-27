---
title: Ampliar el talento con Power Apps y Power Automate
description: En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent que usan Microsoft Power Apps y Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 05/01/2019
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
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 6c8a583a93c2ceb70d8c3b0e0047e2bf2047b56d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898326"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Ampliar el talento con Power Apps y Power Automate

En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent que usan Microsoft Power Apps y Microsoft Power Automate. Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps. Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.

> [!IMPORTANT]
> Si desea usar las plantillas y la aplicación que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.


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

En Microsoft Dynamics 365: Attract, los formularios pueden aparecer en portal del candidato y los candidatos pueden completar los detalles. Los formularios también se pueden insertar como actividades en una plantilla de trabajo.

Cuando un candidato envía un formulario, Microsoft Power Automate captura el envío del formulario, lee los datos y los almacena en la entidad Common Data Service.

Para descargar la plantilla **Power Automate - Conectar formulario** y la estructura de entidad personalizada, vaya a [Power Automate - Conectar formulario](https://go.microsoft.com/fwlink/?linkid=2081988) en el Centro de descarga de Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-power-apps"></a>Iniciar y extraer parámetros pasados a Power Apps

La plantilla **Iniciar y extraer parámetros pasados a Power Apps** se puede usar como punto de partida para cualquier escenario de Power Apps que sea específico de Attract. Incluye todos los parámetros predeterminados que son pasados por Attract, por ejemplo, **Solicitud de trabajo**, **Identificador del candidato** y **JobID**.

Esta plantilla se puede usar para recuperar un formulario de evaluación del candidato, de modo que un director de contratación puede ver la evaluación que completó un candidato.

Las aplicaciones que se crean mediante Power Apps se pueden insertar en la plantilla de trabajo en Attract.

Para descargar la estructura de la plantilla **Iniciar y extraer parámetros pasados a Power Apps** y la estructura de entidad personalizada, vaya a [Iniciar y extraer parámetros pasados a Power Apps](https://go.microsoft.com/fwlink/?linkid=2081991) en el Centro de descarga de Microsoft.

## <a name="integration-with-office-365"></a>Integración con Office 365

La aplicación **Integración con Office 365** se puede utilizar para extraer información de equipos para usuarios registrados desde Microsoft Office 365. Hace referencia a trabajadores en Talent para extraer los datos de entrada y salida y los registros de excepción. Los detalles de hora de entrada y de salida se almacenan en entidades Common Data Service personalizadas. Se asume que estos detalles se completan desde sistemas de terceros mediante la integración.

Esta aplicación puede ser ampliada para que pueda usar otros escenarios. Por ejemplo, se puede usar para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.

Para descargar la aplicación **Integración con Office 365** y la estructura de entidad personalizada, vaya a [Integración con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft.

## <a name="power-automate--email-notification"></a>Power Automate - Notificación por correo electrónico

La plantilla **Power Automate – Notificación por correo electrónico** se puede usar para los escenarios de la notificación por correo electrónico. Puede ser utilizada para activar correos electrónicos de notificación a los candidatos que el equipo de contratación rechaza durante cualquier fase del proceso de contratación.

Esta plantilla puede ser ampliada para hacer un seguimiento de los cambios a la etapa del candidato en el proceso de contratación y enviar notificaciones al equipo de contratación y al candidato.

Normalmente, para las entidades que se almacenan en Common Data Service, los flujos se pueden configurar para enviar las notificaciones para los eventos que se producen en Core HR, Attract o Onboard.

Para descargar la plantilla **Power Automate – Notificación por correo electrónico**, vaya a [Power Automate – Notificación por correo electrónico](https://go.microsoft.com/fwlink/?linkid=2082103) en el Centro de descarga de Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Conectar y ejecutar SQL

La plantilla **Power Automate - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.

Aunque esta plantilla se designa para leer y las tablas SQL actualizadas, puede ser ampliada para que pueda usarse para otros escenarios. Por ejemplo, se puede usar para rellenar una tabla de ensayo de Common Data Service con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental de SQL Server.

Para descargar la plantilla **Power Automate - Conectar y ejecutar SQL**, vaya a [Power Automate - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Integración de Power Automate - SharePoint

La plantilla **Power Automate – Integración con SharePoint** se puede usar para leer datos de una lista de Microsoft SharePoint, comparar la lista con los valores de campo de cualquier entidad de Common Data Service, y enviar los resultados de la comparación como una notificación de correo electrónico. 

Una organización puede tener un conjunto de aptitudes que necesita con urgencia. Estos aptitudes se pueden almacenar en SharePoint como una lista SharePoint. Cuando un candidato solicita cualquier trabajo que cuenta con un conjunto de las aptitudes necesarias, si hay una coincidencia significativa entre las aptitudes del candidato y las aptitudes que se almacenan en SharePoint, se envía una notificación por correo electrónico. De esta manera, los puestos que se requieren con urgencia se ocupan antes, ya que las notificaciones ayudan a los reclutadores a contactar y contratar a candidatos a lo largo de la organización.

Esta plantilla puede ser ampliada para que pueda usar para cualquier escenario que implique la integración con SharePoint.

Para descargar la plantilla **Integración de Power Automate – SharePoint** con , vaya a Integración de [Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) en el Centro de descarga de Microsoft.

## <a name="referral-app"></a>Aplicación de referencia
Puede usar la aplicación de referencia para agregar candidatos a una reserva de talentos compartida. La persona que hace la referencia puede especificar el **Nombre**, **Apellidos**, **Correo electrónico**y **Dirección URL de Linkedln** , al registrar un candidato. Luego los metadatos de origen del candidato se rellenan con la información de la persona que hace la referencia.

Puede insertar esta aplicación en el autoservicio para empleados (ESS) para enviar referencias o puede usarla como hipervínculo en el portal corporativo y ejecutarla como aplicación independiente.

Para descargar **Aplicación de referencia**, [solución de extensibilidad de Dynamics 365 Talent: Aplicación de referencia](https://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) en al Centro de descargas de Microsoft. Puede importar esta aplicación y personalizarla para agregar una funcionalidad adicional.

## <a name="additional-resources"></a>Recursos adicionales

[La Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrar la aplicación entre arrendatarios y entornos](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
