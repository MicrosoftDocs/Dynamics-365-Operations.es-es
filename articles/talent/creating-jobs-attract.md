---
title: Crear un trabajo en Attract
description: Este tema describe los elementos de un trabajo en Attract. También se explica cómo crear un trabajo.
author: hasrivas
manager: AnnBe
ms.date: 07/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 95bc75596f6f014b58160022f41ae86a825c5afc
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527275"
---
# <a name="create-a-job-in-attract"></a>Crear un trabajo en Attract

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe los elementos de un trabajo en Microsoft Dynamics 365 Talent: Attract. También se explica cómo crear un trabajo.

## <a name="job-creation"></a>Creación de trabajos

Las administraciones, los reclutadores, y los administradores de contratación pueden crear trabajos. Al crear un trabajo, se le pedirá que seleccione su rol en el proceso: administrador o reclutador de contratación. Tras seleccionar un rol, se le pedirá que seleccione una plantilla de proceso. Si selecciona **Omitir**, se usa la plantilla predeterminada. Para obtener más información acerca de las plantillas de proceso, consulte [Crear una plantilla de proceso en Attract](./process-templates-attract.md).

Un trabajo en Attract tiene detalles del trabajo, un equipo de contratación, un proceso de contratación, propuestas de empleo, y análisis.

## <a name="job-details"></a>Detalles del trabajo

La pestaña **Detalles del trabajo** contiene detalles sobre las responsabilidades y los atributos de trabajo. Los campos para el puesto, la descripción, y la ubicación del trabajo son necesarios. Los demás campos son opcionales.

De forma predeterminada, el campo **Número de vacantes** se establece en **1**. Sin embargo, se puede cambiar este valor. Cuando una oferta se ha preparado para un trabajo, el valor del campo **Número de vacantes disponibles** disminuye.

Si se ha activado la gestión del puesto en el Centro de administración, la búsqueda **Actualizar puestos** está disponible. Esta búsqueda lee la entidad JobPosition en el Common Data Service y devuelve una lista de puestos que se pueden seleccionar para el trabajo. Si el número de puestos que selecciona supera el número de puestos vacantes, se mostrará una advertencia. También recibe una advertencia si un puesto se utiliza en varios trabajos.

> [!NOTE]
> La gestión de puestos está disponible con el complemento de contratación completa.

En función de los valores de la actividad de la oferta del proceso de contratación, se puede usar dos veces un número de puesto en una oferta. Para obtener más información, consulte [Actividades en procesos de contratación](./activities-attract.md).

Attract incluye un conjunto predeterminado de **Aptitudes**. Estas aptitudes se muestran como sugerencias a medida que escribe. Puede agregar más aptitudes especificando el nuevo texto de aptitud en el campo y después presionando Intro.

Attract incluye un conjunto predeterminado de **Funciones de trabajo**. Puede agregar hasta tres funciones de trabajo más especificando la nueva función de trabajo en el campo y después presionando Intro.

Attract incluye un conjunto predeterminado de **Sector de la empresa**. Puede agregar hasta tres sectores de empresas más especificando el nuevo sector de empresa en el campo y después presionando Intro.

## <a name="hiring-team"></a>Equipo de contratación

La pestaña **Equipo de contratación** contiene la lista de personas que están implicadas en el trabajo. Cuando se agregan usuarios a un equipo de contratación, deben asignárseles un rol en el equipo de contratación. El rol determina los datos a los que los usuarios tienen acceso y las notificaciones que reciben. Los roles que se pueden seleccionar son **Reclutador**, **Administrador de contratación**, **delegado**, y **Entrevistador**. Para más información sobre los privilegios de los roles, consulte la documentación "Administración de roles". Los reclutadores y los administradores de contratación pueden designar uno o más delegados para trabajar en su nombre. Para obtener más información sobre los delegados, consulte [La seguridad y la gestión de roles en Attract](./security-attract.md).

El equipo de contratación se puede actualizar después de activar el trabajo.

## <a name="process"></a>Proceso

La información predeterminada sobre el proceso de contratación se basa en la plantilla de proceso que se activó cuando el trabajo se creó. Si una plantilla específica no se activó en ese momento, se usa la plantilla predeterminada. Al definir el proceso de contratación, puede agregar o quitar las distintas etapas, salvo las etapas Cliente potencial, Solicitud y Oferta. Aunque la etapa de cliente potencial no se pueda quitar, puede desactivarse. Dentro de cada etapa, puede agregar o quitar una o varias actividades predefinidas.

Para obtener más información sobre las actividades que se pueden agregar al proceso de contratación, consulte [Actividades en procesos de contratación](./activities-attract.md).

> [!NOTE]
> El proceso de contratación no se puede actualizar después de activar el trabajo.

## <a name="postings"></a>Registros

Después de que se active un trabajo, este se puede registrar. Solo los reclutadores y los administradores pueden registrar trabajos. El trabajo se puede registrar en Talent Careers (un sitio de carreras de Dynamics 365 Talent) o LinkedIn. El equipo de Attract trabaja continuamente para asociarse con los agregadores tableros de trabajo. Esta lista se expandirá con el tiempo. Cuando un trabajo se registra como interno únicamente, los candidatos necesitan una cuenta de DAA para ver y solicitar el trabajo. Si el trabajo se muestra como público, los candidatos pueden ver y solicitar trabajos usando todas las opciones de autenticación. 

Para obtener más información acerca de registros de trabajo, consulte [Configurar su sitio de desarrollo profesional en Microsoft Dynamics 365 Talent - Attract](career-site.md).

> [!NOTE]
> La funcionalidad de registro de trabajo está disponible únicamente con el complemento de contratación completa de Attract.

## <a name="activate"></a>Activar

Después de que se active un trabajo, este se puede registrar, y se le pueden agregar los clientes potenciales y los candidatos. La opción para agregar clientes potenciales a un trabajo se establece en la actividad del cliente potencial en el proceso de contratación.

> [!NOTE]
> El proceso de contratación no se puede actualizar después de activar el trabajo.

## <a name="prospects-and-applicants"></a>Clientes potenciales y candidatos

La opción para agregar clientes potenciales a un trabajo se establece en las [Actividades de los procesos de contratación](./activities-attract.md#prospect-activity) en el proceso de contratación. Esta opción debe ser establecida antes de activar el trabajo. Después de que se active un trabajo, se le pueden agregar los clientes potenciales y los candidatos.

## <a name="approvals"></a>Aprobaciones

Los trabajos de Attract pueden ser enviados para su aprobación. No todos los trabajos requieren aprobación. El requisito se establece en el nivel de la plantilla. De forma predeterminada, las aprobaciones se desactivan en la plantilla. Para configurar aprobaciones, vaya a una plantilla de proceso, y establezca el campo **Aprobación** en Valor predeterminado. A continuación seleccione dicha plantilla al crear el trabajo.

Una vez guardado un trabajo, puede ser enviado para su aprobación. En la tabla siguiente se muestran los estados de un documento que utiliza aprobaciones.

| Estado   | Comunidad autónoma                                                               |
|----------|---------------------------------------------------------------------|
| Borrador    | Se ha guardado el trabajo, pero no se ha enviado a un flujo de trabajo. |
| Pendientes  | El trabajo se envió a aprobadores.                            |
| Aprobados | Se ha aprobado el trabajo, pero no se ha activado.            |
| Rechazados | Se ha rechazado el trabajo, y no se puede activar.               |
| Activas   | Se ha aprobado y se ha activado el trabajo.                            |

En la lista de trabajos, puede filtrar por los estados de trabajo.

Las aprobaciones se pueden enviar a cualquier usuario de Microsoft Azure Active Directory (Azure AD) en la empresa. Las aprobaciones se envían en paralelo a todas las personas que aparecen como aprobadores. Todos los aprobadores deben aprobar el trabajo antes de que este pueda avanzar. Si un único aprobador rechaza el trabajo, el trabajo mostrará un estado **Rechazado**. Después de que se apruebe un trabajo, este se puede activar.

Si un usuario edita el trabajo después de que se apruebe, pero no está activado, restablecerá el estado del trabajo a **Borrador**, y el trabajo se debe volver a aprobar. Una vez un trabajo aprobado es activado, no se puede editar.

Las personas que figuran como aprobadores recibirán una notificación en Attract y un correo electrónico para informarles de que tienen un elemento por aprobar.  En el correo electrónico, los aprobadores pueden hacer clic en el vínculo para abrir el trabajo, revisar los detalles, y aprobarlo o rechazarlo. Después de que el valor del estado del trabajo pase a **Aprobado** o **Rechazado**, se notificará al usuario en Attract y recibirá un correo electrónico. Además, los aprobadores recibirán un correo electrónico de alerta si no han respondido a la solicitud de aprobación en 24 horas.

> [!NOTE]
> Puede crear plantillas de correo electrónico personalizadas de los correos electrónicos de aprobación. Para obtener más información, consulte [Crear y gestionar plantillas de correo electrónico](https://docs.microsoft.com/dynamics365/unified-operations/talent/email-templates).

## <a name="create-a-job"></a>Creación de un trabajo

Siga estos pasos para crear un trabajo.

1. Vaya a **Trabajos**.
2. Seleccione **Nuevo**.
3. En el campo **Cargo**, especifique el puesto. En el campo **Rol**, escriba su rol.
4. En el campo **Plantilla**, seleccione una plantilla. De forma alternativa, seleccione **Omitir**. Si se selecciona **Omitir**, la plantilla se usará la plantilla marcada como predeterminada.

    Si el documento pasa con un proceso de aprobación, seleccione una plantilla donde el campo **Proceso de aprobación** se establece en **Predeterminado**.

5. En la ficha **Detalles**, especifique la información detallada del trabajo. Los campos **Título**, **Descripción del trabajo** y **Ubicación** son necesarios.
6. Seleccione **Guardar**.
7. En la pestaña **Equipo de contratación**, agregue un administrador, un reclutador, o un entrevistador de contratación.
8. Seleccione **Guardar**.
9. En la pestaña **proceso**, agregue o quite etapas como sea necesario:

    - Para agregar una etapa, seleccione **+ Nueva etapa**.
    - Para quitar una etapa, mantenga el puntero del mouse sobre la etapa que desea quitar, y seleccione el botón de papelera que aparece.

        > [!NOTE]
        > Las etapas de candidatos potenciales, solicitud u oferta no se pueden eliminar.

10. Agregue o quite actividades como sea necesario:

    - Para agregar una actividad, arrástrela desde la lista de la derecha a la etapa adecuada. De forma alternativa, haga doble clic en la actividad, y luego seleccione la etapa a la que la agregará.
    - Para quitar una actividad, expanda la actividad, y seleccione el botón de papelera en el encabezado de la actividad.

11. Seleccione **Guardar**.
12. Si ha seleccionado usar un proceso de aprobación, siga estos pasos:

    1. Seleccione **+ Agregar aprobador** y, a continuación, especifique un usuario que tenga una cuenta Azure AD. Puede agregar varios aprobadores.
    2. Seleccione **Enviar a aprobadores**.

    El campo **Estado del trabajo** del trabajo se establece en **Pendiente**. Una vez que el valor de **Estado del trabajo** cambia a **Aprobado**, el trabajo se puede activar.

13. Para activar el trabajo, seleccione **Activar**.
14. Para registrar el trabajo, vaya a **Registros** y, a continuación, seleccione **Registrar ahora** en el sitio de carreras de Talent o en LinkedIn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]