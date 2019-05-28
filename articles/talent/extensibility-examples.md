---
title: Extender Talent mediante PowerApps y Microsoft Flow - escenarios de ejemplo
description: En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 for Talent que usan Microsoft PowerApps y Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
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
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519006"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Extender Talent mediante PowerApps y Microsoft Flow - escenarios de ejemplo

En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 for Talent que usan Microsoft PowerApps y Microsoft Flow. Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de PowerApps. Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.

> [!IMPORTANT]
> Si desea usar las plantillas y la aplicación que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.


## <a name="prerequisites"></a>Requisitos previos

- Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.
- Para exportar o importar aplicaciones, los usuarios deben tener una licencia PowerApps Plan 2 o una licencia de prueba de PowerApps Plan 2.

## <a name="flow--form-connect"></a>Flow - Conectar formulario

La plantilla **Flow - Conectar formulario** se puede usar para leer datos de Microsoft Forms y almacenarlos en una entidad Common Data Service.

Esta plantilla puede ser ampliada para que pueda usar otros escenarios. A continuación se incluyen algunos ejemplos:

- Captura evaluaciones de candidato.
- Captura resultados de los cuestionarios del curso.
- Compile una biblioteca de las preguntas de la entrevista para los administradores de recursos humanos (HR).
- Captura la evaluación de un candidato del proceso de la entrevista

En Microsoft Dynamics 365: Attract, los formularios pueden aparecer en portal del candidato y los candidatos pueden completar los detalles. Los formularios también se pueden insertar como actividades en una plantilla de trabajo.

Cuando un candidato envía un formulario, Microsoft Flow captura el envío del formulario, lee los datos y los almacena en la entidad Common Data Service.

Para descargar la plantilla **Flow - Conectar formulario** y la estructura de entidad personalizada, vaya a [Flow - Conectar formulario](https://go.microsoft.com/fwlink/?linkid=2081988) en el Centro de descarga de Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Iniciar y extraer parámetros pasados a PowerApps

La plantilla **Iniciar y extraer parámetros pasados a PowerApps** se puede usar como punto de partida para cualquier escenario de PowerApps que sea específico de Attract. Incluye todos los parámetros predeterminados que son pasados por Attract, por ejemplo, **Solicitud de trabajo**, **Identificador del candidato** y **JobID**.

Esta plantilla se puede usar para recuperar un formulario de evaluación del candidato, de modo que un director de contratación puede ver la evaluación que completó un candidato.

Las aplicaciones que se crean mediante PowerApps se pueden insertar en la plantilla de trabajo en Attract.

Para descargar la estructura de la plantilla **Iniciar y extraer parámetros pasados a PowerApps** y la estructura de entidad personalizada, vaya a [Iniciar y extraer parámetros pasados a PowerApps](https://go.microsoft.com/fwlink/?linkid=2081991) en el Centro de descarga de Microsoft.

## <a name="integration-with-office-365"></a>Integración con Office 365

La aplicación **Integración con Office 365** se puede utilizar para extraer información de equipos para usuarios registrados desde Microsoft Office 365. Hace referencia a trabajadores en Talent para extraer los datos de entrada y salida y los registros de excepción. Los detalles de hora de entrada y de salida se almacenan en entidades Common Data Service personalizadas. Se asume que estos detalles se completan desde sistemas de terceros mediante la integración.

Esta aplicación puede ser ampliada para que pueda usar otros escenarios. Por ejemplo, se puede usar para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.

Para descargar la aplicación **Integración con Office 365** y la estructura de entidad personalizada, vaya a [Integración con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft.

## <a name="flow--email-notification"></a>Flow - Notificación por correo electrónico

La plantilla **Flow – Notificación por correo electrónico** se puede usar para los escenarios de la notificación por correo electrónico. Puede ser utilizada para activar correos electrónicos de notificación a los candidatos que el equipo de contratación rechaza durante cualquier fase del proceso de contratación.

Esta plantilla puede ser ampliada para hacer un seguimiento de los cambios a la etapa del candidato en el proceso de contratación y enviar notificaciones al equipo de contratación y al candidato.

Normalmente, para las entidades que se almacenan en Common Data Service, los flujos se pueden configurar para enviar las notificaciones para los eventos que se producen en Core HR, Attract o Dynamics 365 Talent: Onboard.

Para descargar la plantilla **Flow – Notificación por correo electrónico**, vaya a [Flow – Notificación por correo electrónico](https://go.microsoft.com/fwlink/?linkid=2082103) en el Centro de descarga de Microsoft.

## <a name="flow--sql-connect-and-execute"></a>Flow – Conectar y ejecutar SQL

La plantilla **Flow - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.

Aunque esta plantilla se designa para leer y las tablas SQL actualizadas, puede ser ampliada para que pueda usarse para otros escenarios. Por ejemplo, se puede usar para rellenar una tabla de ensayo de Common Data Service con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental de SQL Server.

Para descargar la plantilla **Flow - Conectar y ejecutar SQL**, vaya a [Flow - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.

## <a name="flow--sharepoint-integration"></a>Flow - Integración con SharePoint

La plantilla **Flow – Integración con SharePoint** se puede usar para leer datos de una lista de Microsoft SharePoint , comparar la lista con los valores de campo de cualquier entidad Common Data Service , y enviar los resultados de la comparación como una notificación de correo electrónico. 

Una organización puede tener un conjunto de aptitudes que necesita con urgencia. Estos aptitudes se pueden almacenar en SharePoint como una lista SharePoint. Cuando un candidato solicita cualquier trabajo que cuenta con un conjunto de las aptitudes necesarias, si hay una coincidencia significativa entre las aptitudes del candidato y las aptitudes que se almacenan en SharePoint, se envía una notificación por correo electrónico. De esta manera, los puestos que se requieren con urgencia se ocupan antes, ya que las notificaciones ayudan a los reclutadores a contactar y contratar a candidatos a lo largo de la organización.

Esta plantilla puede ser ampliada para que pueda usar para cualquier escenario que implique la integración con SharePoint.

Para descargar la plantilla **Flow – Integración con SharePoint**, vaya a [Flow – Integración con SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) en el Centro de descarga de Microsoft.

## <a name="admin-console-to-manage-talent-pools"></a>Consola de administración para administrar las reservas de talentos

Si habilita la integración con LinkedIn, Attract automáticamente crea una reserva de talentos de LinkedIn. Cuando un reclutador intercambia InMail con un empleado nuevo mediante LinkedIn, Attract crea un perfil para el empleado nuevo, y este se hace miembro de la reserva de talentos de LinkedIn. Esta aplicación de PowerApps es útil para reorganizar candidatos en las reservas de talentos basadas en aptitudes.

Ejecute esta aplicación de PowerApps como consola de administración para realizar las siguientes tareas:

- Listar candidatos en un grupo de talentos
- Agregar y eliminar candidatos de un grupo de talentos
- Trasladar a los candidatos de una reserva de talentos a otra
- Determinar si los candidatos ya son parte de una reserva de talentos antes de moverlos
- Comprobar las aptitudes de los candidatos antes de moverlos a otras reservas de talentos

Esta aplicación de PowerApps usa relaciones de varios a varios, por lo que puede usarla como plantilla para otros escenarios donde debe extraer los registros con relaciones de varios a varios.

Para descargar la plantilla **Consola de administración administrar las reservas de talentos** vaya a la [Consola de administración administrar las reservas de talentos](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) en el Centro de descarga de Microsoft.

## <a name="additional-resources"></a>Recursos adicionales

[La Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrar la aplicación entre arrendatarios y entornos](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
