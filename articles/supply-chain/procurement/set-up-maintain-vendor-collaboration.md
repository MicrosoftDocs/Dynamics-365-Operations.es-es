---
title: Configurar y mantener la colaboración de proveedor
description: En este tema se explica cómo configurar la colaboración del proveedor en Dynamics 365 Supply Chain Management. También explica cómo proporcionar nuevos usuarios de colaboración de proveedores y administrar los roles de seguridad para esos usuarios.
author: Henrikan
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b635255fffa6fd3c6612cd248dc692df204aa76d
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652086"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Configurar y mantener la colaboración de proveedor

[!include [banner](../includes/banner.md)]

La interfaz de colaboración del proveedor expone un conjunto limitado de información a los usuarios de proveedores externos acerca de pedidos de compra, facturas y consignación de existencias. Desde esta interfaz, un proveedor también puede responder a las solicitudes de cotización (RFQ) y ver y editar la información básica de la empresa.

En este tema se explica cómo configurar la colaboración del proveedor en Dynamics 365 Supply Chain Management. También explica cómo configurar un flujo de trabajo para aprovisionar nuevos usuarios de colaboración de proveedores y cómo administrar los roles de seguridad para esos usuarios.

> [!NOTE]
> La información sobre la configuración de roles de seguridad para la colaboración de proveedores se aplica solo a la versión actual de Finance and Operations. En Microsoft Dynamics AX 7.0 (febrero de 2016) y en Microsoft Dynamics AX versión de aplicación 7.0.1 (mayo de 2016), colabora con proveedores a través del módulo **Portal de proveedores**. Para obtener información sobre los permisos de usuario para el portal de proveedores en Microsoft Dynamics AX, vea [Seguridad del usuario del portal de proveedores](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Configurar roles de seguridad de colaboración de proveedor

Un profesional de adquisiciones o un proveedor que tenga suficientes permisos puede solicitar que se proporcione una persona de contacto como usuario habilitando **Usuario proveedor de aprovisionamiento** en el registro de la persona de contacto. Durante el proceso de aprovisionamiento, se seleccionan los permisos de usuario para el nuevo usuario externo y se envía la solicitud de usuario del nuevo proveedor. Es importante que configure correctamente los permisos de usuario que están disponibles para su selección en la solicitud de usuario del proveedor. De lo contrario, los proveedores podrían tener acceso a información a la que no deberían tener acceso en Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Configure los roles de seguridad que están disponibles para su selección cuando se usa una nueva solicitud de usuario para una persona de contacto

1. Seleccione **Administracion del sistema** &gt; **Seguridad** &gt; **Roles externos**.
2. Seleccione **Nuevo** y luego seleccione un rol de seguridad y el rol de parte **Proveedor**.

Es posible que desee agregar los roles **Administrador de proveedores (externo)** y **Proveedor (externo)** que se proporcionan en Supply Chain Management. Alternativamente, puede utilizar roles de seguridad que haya creado su empresa.

Debería hacer que el rol **Administrador de proveedores (externo)** esté disponible solo si los proveedores deben poder crear nuevos contactos, enviar solicitudes de usuarios de colaboración de proveedores para nuevos usuarios y cambios en la información del usuario, y manejar esas solicitudes a través de un flujo de trabajo.

Si planea configurar manualmente los contactos y usuarios de proveedores, puede hacer que solo el **Rol de proveedor (externo)** esté disponible. Este rol será entonces el único rol que se puede solicitar a través de una solicitud de usuario de proveedor.

> [!NOTE]
> El rol **SystemUser** se concede automáticamente cuando se crea de forma manual una nueva cuenta de usuario. Por lo tanto, debe eliminar ese rol y asignar el rol **SystemExternalUser**. Si se crean nuevas cuentas de usuario a través del flujo de trabajo iniciado por una solicitud de usuario de proveedor para aprovisionar un nuevo usuario, uno o más de los roles que ha configurado para la colaboración de proveedores y se le asignará el rol **SystemExternalUser**.

#### <a name="vendor-admin-external-security-role"></a>Rol de seguridad de administrador de proveedor (externo)

El rol **Administrador de proveedores (externo)** se puede utilizar para proveedores externos que mantienen la información de contacto de proveedores y realizan solicitudes para proporcionar nuevos usuarios de colaboración de proveedores. Los usuarios externos que tienen este rol de seguridad pueden realizar las siguientes tareas:

- Ver y modificar la información de la persona de contacto, como el cargo, la dirección de correo electrónico y el número de teléfono de la persona.
- Agregue una persona de contacto nueva o existente a las cuentas de proveedor para las que es un contacto.
- Elimine cualquier persona de contacto que hayan creado.
- Active o desactive la asociación entre una persona de contacto y una cuenta de proveedor. Una vez que se desactiva la asociación entre una persona de contacto y una cuenta de proveedor, no se puede hacer referencia a la persona de contacto en nuevas órdenes de compra u otros documentos.
- Denegue o permita el acceso de una persona de contacto a los documentos de la interfaz de colaboración del proveedor que sean específicos de la cuenta del proveedor. Después de que se desactiva la asociación entre una persona de contacto y una cuenta de proveedor, siempre se deniega el acceso a los documentos que son específicos de la cuenta de proveedor.
- Solicite una nueva cuenta de usuario para una persona de contacto utilizando la acción **Provisionar usuario**.
- Solicite que se desactive la cuenta de usuario de una persona de contacto.
- Solicite que se modifique la cuenta de usuario de una persona de contacto para agregar o eliminar roles de seguridad.
- Ver RFQ.

#### <a name="vendor-external-security-role"></a>Rol de seguridad de proveedor (externo)

El **Rol de proveedor (externo)** se puede utilizar para proveedores externos que trabajarán con órdenes de compra. Los usuarios externos que tienen este rol de seguridad pueden realizar las siguientes tareas:

- Responder y ver información sobre órdenes de compra.
- Mantener facturas de colaboración de proveedor.
- Ver inventario de entrega.
- Visualización y respuesta a RFQ.
- Ver información del proveedor.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Configurar roles de seguridad que se utilizan cuando se incorporan posibles proveedores

Para incorporar proveedores que se inician a través de una solicitud de registro de proveedor potencial, debe configurar un rol de seguridad externo. Este rol se asignará a los nuevos usuarios durante el proceso de aprovisionamiento que está controlado por el flujo de trabajo del tipo **Flujo de trabajo de solicitud de usuario (plataforma)**. Para obtener más información, consulte la sección [Configurar flujos de trabajo para procesar solicitudes de usuarios de colaboración de proveedores](#set-up-workflows-to-process-vendor-collaboration-user-requests) más adelante en este tema.

Para obtener información sobre cómo incorporar a los posibles proveedores, consulte [Proveedores a bordo](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Configurar un rol de seguridad que se usa cuando se envía una nueva solicitud de usuario de proveedor potencial

1. Seleccione **Administracion del sistema** > **Seguridad** > **Roles externos**.
2. Seleccione **Nuevo** y luego seleccione un rol de seguridad y el rol de parte **Proveedor potencial**.

Debería agregar el rol **Proveedor potencial (externo)** que se proporciona en Supply Chain Management.

El rol de seguridad otorgará acceso solo al asistente de registro de nuevos proveedores.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Configurar flujos de trabajo para procesar solicitudes de usuarios de colaboración de proveedores

Para ayudar a garantizar que se completen todas las tareas relevantes y que se otorguen las aprobaciones adecuadas, debe configurar flujos de trabajo para manejar las solicitudes de los usuarios de colaboración de proveedores.

Las solicitudes de los usuarios de colaboración de proveedores son enviadas por proveedores externos que tienen el rol de seguridad **Administrador de proveedores (externo)** o permisos similares, o por profesionales de adquisiciones en su empresa. También se pueden generar a partir de solicitudes de registro de posibles proveedores durante el proceso de incorporación de proveedores.

Hay tres tipos de solicitudes:

- Solicitudes para aprovisionar un nuevo usuario
- Solicitudes para desactivar un usuario existente
- Solicitudes para modificar los roles de seguridad de un usuario existente

Para obtener más información sobre las solicitudes de usuarios de colaboración de proveedor, consulte [Gestionar usuarios de colaboración del proveedor](manage-vendor-collaboration-users.md).

Debe crear dos o más flujos de trabajo para procesar los tres tipos de solicitudes de usuarios de colaboración de proveedores. Se crean nuevos flujos de trabajo en la página **Flujos de trabajo de usuario**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Ejemplo de un flujo de trabajo para aprovisionar nuevos usuarios y modificar roles de seguridad

Para manejar las solicitudes de los usuarios de proveedores para crear nuevos usuarios y modificar roles de seguridad, puede poner una condición de bifurcación al comienzo del flujo de trabajo. De esta forma, se utiliza una rama diferente del flujo de trabajo, dependiendo de si la solicitud es crear un nuevo usuario o modificar un usuario existente.

Para configurar esta ramificación, cree un nuevo flujo de trabajo del tipo **Flujo de trabajo de solicitud de usuario (plataforma)**. Las ramas de este flujo de trabajo pueden contener los siguientes elementos.

#### <a name="branch-to-provision-new-users"></a>Rama para aprovisionar nuevos usuarios

1. Asigne una tarea de aprobación a la persona responsable de aprobar que los nuevos usuarios deben tener acceso a la información de colaboración del proveedor.
2. Asignar una tarea a la persona responsable de solicitar nuevas cuentas de usuario de Microsoft Azure Active Directory (Azure AD) en Azure Portal. Utilice la tarea predefinida **Enviar invitación de usuario de Azure B2B** para este paso. Los usuarios de B2B se pueden exportar automáticamente a Azure AD. Utilice el **Usuario B2B de Azure AD de aprovisionamiento** predefinido. Para obtener más información, consulte [Exportar usuarios B2B a Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Asigne una tarea de aprobación a la persona que carga en Azure. Si una cuenta no se crea correctamente, esta persona rechaza la tarea y finaliza el flujo de trabajo. Esta tarea de aprobación se puede omitir si ha incluido el paso que exporta automáticamente nuevas cuentas de usuario a Azure a través de la interfaz de programación de aplicaciones (API) B2B.
4. Agregue una tarea automatizada que aprovisiona a un nuevo usuario. Utilice la tarea predefinida **Usuario de aprovisionamiento automatizado** para este paso.
5. Agregue una tarea que notifique al nuevo usuario. Es posible que desee enviar al nuevo usuario un correo electrónico de bienvenida que incluya una URL para Supply Chain Management. Este correo electrónico puede utilizar una plantilla que cree en la página **Mensajes de correo electrónico** y luego seleccione en la página **Parámetros del flujo de trabajo del usuario**. La plantilla puede incluir la etiqueta **%portalURL%**. Cuando se genera el correo electrónico de bienvenida, esta etiqueta será reemplazada por la URL del inquilino de Supply Chain Management.

    > [!NOTE]
    > Este flujo de trabajo se puede utilizar en múltiples escenarios que involucran la incorporación de usuarios. Por ejemplo, se puede utilizar cuando los posibles proveedores o personas de contacto requieren una cuenta de colaboración de proveedor. Por lo tanto, debe formular el correo electrónico como una declaración general que se puede utilizar para múltiples propósitos.

#### <a name="branch-to-modify-security-roles"></a>Rama para modificar roles de seguridad

1. Asigne una tarea de aprobación a la persona responsable de aprobar los cambios en los roles de seguridad.
2. Agregue una tarea automatizada que agregue o elimine los roles de seguridad relevantes. Utilice la tarea **Usuario de aprovisionamiento automatizado** para este paso.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Ejemplo de un flujo de trabajo para inactivar a un usuario

Cree un flujo de trabajo del tipo **Desactivar la plataforma de flujo de trabajo de solicitudes de usuario** y luego agregue las siguientes tareas.

1. Asigne una tarea de aprobación a la persona responsable de aceptar las solicitudes para desactivar usuarios. Puede agregar condiciones para automatizar este paso de aprobación.
2. Agrega una tarea automatizada que inactiva al usuario. Utilice la tarea **Inactivación de usuario automatizada** para este paso.
3. Agregue las tareas de limpieza necesarias. Por ejemplo, puede agregar una tarea que elimine la cuenta de su directorio en Azure Portal.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Habilitar la colaboración de proveedor para un proveedor específico

Antes de crear una cuenta de usuario para alguien que utilizará la colaboración de proveedores, debe configurar el proveedor para que pueda usar la colaboración de proveedores. En la página **Proveedores**, en la pestaña **General** configure el campo **Activación de colaboración**. Las siguientes opciones están disponibles:

- **Activo (el PO se confirma automáticamente)**: los pedidos de compra se confirman de forma automática si el vendedor los acepta sin solicitar cambios.
- **Activo (el PO no se confirma automáticamente)**: es necesario que su oganización confirme los pedidos de compra manualmente cuando el proveedor los haya aceptado.

> [!NOTE]
> Los profesionales de adquisiciones de su empresa también pueden realizar esta tarea.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Solucionar problemas de aprovisionamiento de nuevos usuarios de colaboración de proveedores

Los nuevos usuarios de colaboración de proveedores se aprovisionan a través del flujo de trabajo que configura para procesar las solicitudes de usuarios de colaboración de proveedores del tipo **Usuario proveedor de aprovisionamiento**.

Si la dirección de correo electrónico de un nuevo usuario de colaboración de proveedor pertenece a un dominio que está registrado en Azure como inquilino (es decir, si es una cuenta de dominio administrado), la dirección de correo electrónico debe ser una cuenta existente de Azure AD. De lo contrario, el proceso de aprovisionamiento no se puede completar.

Para obtener más información sobre el proceso que se utiliza en la tarea **Enviar invitación de usuario de Azure B2B** en el flujo de trabajo para gestión de cuentas de Azure AD, vea [Colaboración B2B de Azure Active Directory](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Recursos adicionales

[Colaboración de proveedor con proveedores externos](vendor-collaboration-work-external-vendors.md)

Vea un breve video sobre el proceso de incorporación de proveedores: [A bordo de un nuevo proveedor](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
