---
title: Seguridad y gestión de roles en Attract
description: Este tema proporciona información sobre la seguridad de los roles en Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9c0f9d3304b1b15aa84fd1a296267d606bf9c59d
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2019
ms.locfileid: "993700"
---
# <a name="security-and-role-management-in-attract"></a>Seguridad y gestión de roles en Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent: Attract usa seguridad basada en roles. Es decir el acceso no se concede a usuarios individuales, sino a los roles de seguridad a los que se asignan los usuarios. Un usuario al que se ha asignado un rol de seguridad tiene acceso al conjunto de privilegios que está asociado a dicho rol.

Attract proporciona roles de usuario básicos:

- Administrador
- Responsable de contratación
- Técnico de selección de personal
- Entrevistador
- Sólo lectura

El rol Administrador es el único rol que tiene permiso para agregar otros usuarios y cambiar sus permisos.

- **Agregar** En el Centro de administración, en la pestaña **Permisos de usuario**, seleccione **Asignar roles**, busque el usuario que quiere agregar y, a continuación, asigne permisos a dicho usuario.
- **Editar** Busque el usuario, o encuentre el usuario en la lista y, a continuación, seleccione **Editar** para cambiar sus permisos.
- **Eliminar** Si elimina los permisos de un usuario, no quita el usuario del sistema. Sin embargo, restringe el acceso y los privilegios de usuario en Attract. Por ejemplo, a Hilda se le ha asignado el rol de director de contratación, y la agregan a un trabajo como director de contratación. Si después se elimina a Hilda de la función de director de contratación, ella permanecerá como Director de contratación en el trabajo y seguirá teniendo acceso a ese trabajo. Sin embargo, no puede crear otros trabajos.

Las secciones siguientes proporcionan una descripción de alto nivel de cada rol. Las tablas que se proporcionan más adelante en este tema proporcionan información más detallada.

> [!NOTE]
> Algunas características solo están disponibles con el complemento de contratación completa para Attract.

## <a name="administrator"></a>Administrador

Los usuarios asignados al rol Administrador tienen acceso a todos los datos de Attract y pueden cambiarlos. Las administraciones pueden crear, leer, actualizar, y eliminar datos. También tienen acceso al centro de gestión, donde pueden configurar la aplicación Attract y la información sobre el usuario. Recomendamos que al menos está asignado un individuo al rol Administrador. De forma predeterminada, el administrador de entorno de Microsoft PowerApps se establece como administrador en Attract. Si se inscribió a la versión de prueba de Attract, el rol Administrador automáticamente se le asigna. Actualmente, para crear trabajos, los usuarios que tienen la función Administrador también deben tener el rol de reclutador o el rol de director de contratación.

## <a name="hiring-manager"></a>Responsable de contratación

Los usuarios que tienen asignado el rol de director de contratación pueden crear y actualizar trabajos que crearon anteriormente. Los directores de contratación solo pueden realizar un conjunto de acciones limitado en un trabajo y en las solicitudes que están asociadas a ese trabajo. Solo los usuarios que tienen asignado el rol de director de contratación se pueden agregar a un equipo de contratación como directores de contratación.

## <a name="recruiter-role"></a>Rol de contratante

Los usuarios que tienen asignado el rol de reclutador tienen privilegios completos de lectura, creación, actualización y eliminación para los trabajos que han creado. También tienen privilegios completos de creación, lectura, actualización y eliminación para las solicitudes que están asociadas a los trabajos que poseen. Solo los usuarios que tienen asignado el rol de técnico de selección de personal se pueden agregar a un equipo de contratación como técnico de selección de personal.

## <a name="interviewer"></a>Entrevistador

Cualquier usuario que tenga una cuenta de Microsoft Azure Active Directory (Azure AD) en la organización se puede agregar a un equipo de contratación como entrevistador. Los usuarios que tienen asignado el rol de entrevistador pueden ver los detalles del trabajo y los datos del candidato para los trabajos para los que han sido incluidos en el equipo de contratación. Para esos trabajos, los entrevistadores también pueden hacer recomendaciones de contratación y proporcionar valoraciones sobre los candidatos. Sin embargo, no pueden actualizar los detalles del trabajo o los datos del candidato.

## <a name="read-only"></a>Sólo lectura

Los usuarios que tienen asignado el rol de solo lectura tienen acceso de solo lectura a todos los datos del entorno de Attract. Sin embargo, no pueden crear o editar los datos.

## <a name="find-out-which-roles-you-have"></a>Descubra qué roles tiene

1.  En Attract, haga clic en el signo de interrogación (**?**) en la esquina superior derecha de la página.

2.  Haga clic en **Acerca de**.

    Verá los roles que tiene para Attract en la ventana que aparece:

    ![Vea su tipo de licencia de Attract](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Roles delegados

Para cada trabajo para el que se encuentren en el equipo de contratación, los reclutadores, y los directores de contratación pueden designar uno o más delegados que los representen. Sin embargo, no pueden designar delegados para otras personas que estén en el equipo de contratación.

Los delegados tienen los mismos privilegios que la persona que los designó. Por ejemplo, si una jefa de contratación designa un delegado para que la represente para un trabajo, el delegado tendrá los mismos privilegios que la jefa de contratación para el trabajo. Los delegados no pueden quitar otros delegados del equipo de contratación. Tampoco pueden quitar a las personas que las designaron como delegados.

## <a name="job-details-and-actions"></a>Detalles y acciones del trabajo

Los usuarios que tengan el rol de reclutador o de director de contratación no pueden crear trabajos. Los privilegios siguientes se aplican en los detalles del trabajo y las acciones que se pueden llevar a cabo en trabajos.

| Datos o acciones    | Técnico de selección de personal | Responsable de contratación | Entrevistador |
|-------------------|-----------|----------------|-------------|
| Detalles del trabajo       | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura |
| Equipo de contratación       | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura |
| Registro de trabajo       | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura | Sólo lectura |
| Proceso           | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura |
| Agregar candidatos    | Agregar candidatos para trabajos para los que el usuario se encuentra en el equipo de contratación | Agregar candidatos para trabajos para los que el usuario se encuentra en el equipo de contratación | No permitido |
| Agregar candidatos viables     | Agregar candidatos viables para trabajos para los que el usuario se encuentra en el equipo de contratación | Una opción de configuración en la [configuración de actividad de candidato potencial](./activities-attract.md#prospect-activity) controla si los entrevistadores pueden agregar y ver los candidatos potenciales. | No permitido |
| Activar trabajo      | Activar trabajos para los que el usuario se encuentra en el equipo de contratación | Activar trabajos para los que el usuario se encuentra en el equipo de contratación | No permitido |
| Cerrar trabajo         | Cerrar trabajos para los que el usuario se encuentra en el equipo de contratación | No permitido | No permitido |
| Eliminar trabajo        | Eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Solo si no se han agregado candidatos al trabajo | No permitido |
| Eliminar candidatos | Eliminar candidatos si el usuario se encuentra en el equipo de contratación | No permitido | No permitido |

## <a name="application-details-and-actions"></a>Detalles y acciones de la solicitud

Los privilegios siguientes se aplican a los datos específicos del trabajo y las acciones que se pueden llevar a cabo en las solicitudes.

| Datos o acciones          | Técnico de selección de personal | Responsable de contratación | Entrevistador |
|-------------------------|-----------|----------------|-------------|
| Documentos de solicitudes   | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura |
| Notas de solicitudes       | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Crear, leer, actualizar y eliminar trabajos para los que el usuario se encuentra en el equipo de contratación | Sólo lectura|
| Actividad de solicitud    | Ver, si el usuario se encuentra en el equipo de contratación | Ver, si el usuario se encuentra en el equipo de contratación | Sólo lectura |
| Valoración de solicitud    | Agregar y ver todas las valoraciones si el usuario se encuentra en el equipo de contratación | Agregar y ver todas las valoraciones si el usuario se encuentra en el equipo de contratación | Se pueden agregar valoraciones\*\* |
| Rechazar valoración      | Se puede rechazar si el usuario se encuentra en el equipo de contratación | No permitido | No permitido |
| Avanzar etapa           | Se puede rechazar si el usuario se encuentra en el equipo de contratación | Se puede avanzar si el usuario se encuentra en el equipo de contratación | No permitido |
| Lazar administración de ofertas | Puede iniciar la administración de la propuesta | Hay una opción de configuración en la actividad de la propuesta. | No permitido |


\*\* Una opción de configuración en la [configuración de actividad de valoración](./activities-attract.md) controla si los entrevistadores pueden ver las valoraciones de los demás.


## <a name="process-templates"></a>Plantillas de proceso

Los privilegios siguientes se aplican a las plantillas de proceso de contratación. La capacidad de miembros del equipo para crear y editar plantillas se configura en **Administración de plantilla** en el centro de administración. Si está activada la administración de la plantilla, los reclutadores y los directores de contratación pueden crear y editar sus propias plantillas de proceso. Si se desactiva la administración de plantillas, solo los administradores pueden crear y editar plantillas de proceso. En la tabla siguiente se supone que se ha activado la gestión de plantillas.

| Datos              | Técnico de selección de personal                                           | Responsable de contratación                                      | Entrevistador |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Plantillas de proceso | Privilegios completos para las plantillas que el usuario crea | Privilegios completos para las plantillas que el usuario crea | Sin acceso   |

## <a name="email-and-email-templates"></a>Plantillas de correo electrónico y correo electrónico

Los privilegios siguientes se aplican en las plantillas de correo electrónico y las acciones que se pueden llevar a cabo en los correos electrónicos. Solo los administradores pueden crear y editar plantillas de correo electrónico.

| Datos o acciones     | Técnico de selección de personal          | Responsable de contratación     | Entrevistador |
|--------------------|--------------------|--------------------|-------------|
| Plantillas de correo electrónico    | Acceso de solo lectura   | Acceso de solo lectura   | Sin acceso   |
| Enviar correo electrónico         | Enviar por actividad  | Enviar por actividad  | Sin acceso   |
| Editar contenido de correo electrónico | Editar contenido de correo electrónico | Editar contenido de correo electrónico | Sin acceso   |

## <a name="talent-pools"></a>Grupos de talentos

Los privilegios siguientes se aplican a los grupos de talentos. Los grupos de talentos están visibles únicamente para la persona que los creó, a menos que dicha persona elija compartirlos. La búsqueda de candidatos se puede usar para buscar candidatos que no se han agregado a un grupo determinado.

| Datos o acciones   | Técnico de selección de personal                                       | Responsable de contratación                                  | Entrevistador |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Grupo con nombre       | Privilegios completos para los grupos que el usuario crea | Privilegios completos para los grupos que el usuario crea | Sin acceso   |
| Compartir grupo       | Solo grupos que el usuario crea                | Solo grupos que el usuario crea                | Sin acceso   |
| Búsqueda de candidatos | Capacidades completas de búsqueda                        | Capacidades completas de búsqueda                        | Sin acceso   |

## <a name="candidates"></a>Candidatos

Los candidatos son personas que se han agregado a un grupo de talentos pero no están asociados a un trabajo.

| Datos                        | Técnico de selección de personal                        | Responsable de contratación                   | Entrevistador |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Perfil: detalles del candidato | Crear, leer, actualizar y eliminar | Crear, leer, actualizar y eliminar | Sin acceso   |
| Documentos                   | Crear, leer, actualizar y eliminar | Crear, leer, actualizar y eliminar | Sin acceso   |
