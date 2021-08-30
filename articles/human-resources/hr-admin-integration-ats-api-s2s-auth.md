---
title: Autenticación de servidor a servidor para la API de integración ATS
description: Este tema describe cómo configurar la autenticación de servidor a servidor para integraciones con la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aabe2cd9fd962c8f1c5bbf7fe911e7c6ceeae082f61fc4359aaf7bf197531eff
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778088"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Autenticación de servidor a servidor para la API de integración ATS

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe cómo configurar la autenticación de servidor a servidor para integraciones de aplicación con la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources. Hay un par de capas de seguridad que deben administrarse para que la entidad de servicio obtenga acceso a la tabla virtual y datos asociados de Microsoft Dataverse. El usuario debe tener acceso a la tabla virtual de Dataverse en Microsoft Power Platform y acceso a los datos en Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Habilitar el acceso a las tablas virtuales de Dataverse en Power Platform

El primer paso para habilitar el acceso a las tablas virtuales de Dataverse en Power Platform es configurar su aplicación en Power Platform para la autenticación contra los puntos finales de tabla virtual de Dataverse. Los pasos para hacer esto se describen en la [guía para desarrolladores de Microsoft Dataverse](/powerapps/developer/data-platform).

  - Para registros de aplicaciones de un solo inquilino: [Utilice la autenticación de servidor a servidor de inquilino único](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Para registros de aplicaciones de un varios inquilinos: [Utilice la autenticación de servidor a servidor de multiinquilino](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Creación de un rol de seguridad para integraciones ATS

Uno de los pasos después de crear el usuario de la aplicación es asignarle un rol de seguridad que defina el acceso que tendrá la aplicación a los puntos finales. Este es el paso 7 en [Creación de usuarios de aplicaciones](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) para registros de aplicaciones de un solo inquilino y [Cree un rol de seguridad para el usuario de la aplicación](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) para registros de múltiples inquilinos. 

El rol al que asigna el usuario de la aplicación debe tener acceso a las entidades de datos utilizadas para su integración ATS. Esto no existe de fábrica, por lo que será necesario crear un nuevo rol de seguridad. El nuevo rol se puede crear siguiendo los pasos descritos en [Crear un rol de seguridad](/power-platform/admin/create-edit-security-role#create-a-security-role).

Para el nuevo rol, se debe asignar el acceso apropiado a, como mínimo, las siguientes entidades en la pestaña **Entidades personalizadas** del nuevo rol. Tenga en cuenta que es posible que deba agregar entidades adicionales si la integración utiliza datos de aplicación más extensos. Una vez creado el nuevo rol, se puede asignar al usuario de la aplicación.

  - Trabajador de base (mshr)
  - Candidato a contratar (mshr)
  - Capacidad de certificados (mshr)
  - Tipo de certificado (mshr)
  - Empresa
  - Función de trabajo de compensación (mshr)
  - Tipo de trabajo de compensación (mshr)
  - Países/regiones (mshr)
  - Departamento (mshr)
  - Competencia educativa (mshr)
  - Título de educación (mshr)
  - Disciplinas de formación (mshr)
  - Requisitos educativos (mshr)
  - Identificación (mshr)
  - Tipo de identificación (mshr)
  - Institución (mshr)
  - Agencia emisora (mshr)
  - Compesación de trabajo (mshr)
  - Empleos (mshr)
  - Nivel de educación (mshr)
  - Contactos de la parte (mshr)
  - Personas (mshr)
  - Direcciones de personas (mshr)
  - Filtrado de persona (mshr)
  - Tipo de puesto (mshr)
  - Puestos V2 (mshr)
  - Competencia de experiencia profesional (mshr)
  - Nivel de evaluación (mshr)
  - Modelos de tasación (mshr)
  - Códigos de motivo (mshr)
  - Solicitud de contratación (mshr)
  - Ubicación de la solicitud de contratación (mshr)
  - Puesto de solicitud de contratación (mshr)
  - Aptitudes de solicitud de contratación (mshr)
  - Tipo de filtrado (mshr)
  - Competencia de habilidades (mshr)
  - Habilidades (mshr)
  - Títulos (mshr)
  - Estado de excombatiente (mshr)
  - Trabajador (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Otorgar permisos de aplicación a los datos de recursos humanos

El segundo paso es asegurarse de que la aplicación tenga los permisos adecuados para los datos de Recursos humanos vinculándola a un usuario en la aplicación de Recursos humanos. Para un usuario de la aplicación, las llamadas de servidor a servidor a través de tablas virtuales de Dataverse se realizan en el contexto de la identidad del usuario (aplicación) en Dataverse que está invocando la acción. A continuación, el servicio de adaptador de tabla virtual busca al usuario asociado en Recursos humanos y ejecuta la consulta en el contexto de ese usuario. Esto significa que se debe crear un usuario en Recursos Humanos con los roles correctos asignados para brindar acceso a los datos que necesitará la aplicación integradora.

El usuario de Recursos Humanos también deberá tener asignados los permisos correctos para los datos en Recursos Humanos. La función **Solicitud de reclutamiento** (HcmRecruitingIntegrator) está disponible con privilegios para las entidades principales necesarias para la integración con los datos de contratación. Este rol se puede asignar al usuario de la aplicación en la página **Usuarios** para otorgar el acceso adecuado a los datos. Para obtener más información sobre los roles de seguridad de Recursos humanos, consulte [Seguridad basada en roles](/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Configurar el nuevo usuario con los permisos adecuados

Para configurar el nuevo usuario con los permisos adecuados, siga estos pasos:

  1. Abra la página **Usuarios** en Recursos Humanos y seleccione **Nuevo**.
  2. Introduzca un **ID de usuario** y un **Nombre de usuario** para el nuevo usuario de la aplicación. Por ejemplo, puede ingresar "RecruitingIntegration".

      > [!NOTE]
      > Si la aplicación no tiene una cuenta de usuario o dirección de correo electrónico de Microsoft Azure Active Directory (Azure AD), puede poner algo como "RecruitingApp" en los campos de dirección de correo electrónico y proveedor del usuario.

  3. En la ficha desplegable **Roles de usuarios** seleccione la acción **Asignar roles**.
  4. En el panel **Asignar roles al usuario**, seleccione **Solicitud de reclutamiento** y seleccione **OK**.
  5. Guarde el nuevo registro de usuario.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Vincular al nuevo usuario de Recursos Humanos a la aplicación

Una vez creado el usuario, se debe crear un registro para la aplicación en el formulario **Aplicaciones de Azure Active Directory** para vincular la aplicación al usuario de Recursos Humanos.

  1. Abra el formulario de **Aplicaciones de Azure Active Directory** y seleccione **Nuevo**.
  2. En el campo **Id. del cliente**, ingrese el ID de cliente del usuario de la aplicación creado para la aplicación.
  3. En el campo **Nombre**, especifique el nombre de la aplicación de integración.
  4. En el campo **ID de usuario**, seleccione el nuevo usuario de Recursos Humanos creado para la integración de contratación.
  5. Guarde el nuevo registro.

Entonces, la aplicación tendrá acceso a los datos de Recursos Humanos, limitado solo a los datos necesarios para la integración de aplicaciones de contratación.

## <a name="see-also"></a>Consulte también

[Contratar candidatos de trabajo](hr-personnel-recruit.md)<br>
[¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Utilizar la API web de Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Crear y actualizar conjuntos de opciones usando la API web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
