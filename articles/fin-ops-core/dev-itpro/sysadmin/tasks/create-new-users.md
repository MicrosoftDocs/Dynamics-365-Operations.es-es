---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00da7c69ff18abd02ca0cd7984e9b2de5e453a0c
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103337"
---
# <a name="create-new-users"></a>Crear nuevos usuarios

[!include [banner](../../includes/banner.md)]

Antes de poder acceder a las aplicaciones de finanzas y operaciones, debe ser agregado a la página **Usuarios** (**Administración del sistema \> Usuarios \> Usuarios**). Los usuarios incluyen empleados internos de su organización o clientes y proveedores externos. Los usuarios se pueden importar o agregar manualmente. Todos los usuarios deben tener la licencia correcta para un uso compatible.

Para obtener información sobre cómo comprar y obtener licencia para las aplicaciones de finanzas y operaciones, consulte [Guía de licencias de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Asignar una licencia a un usuario
Las administraciones del sistema pueden [asignar licencias a los usuarios](/office365/admin/subscriptions-and-billing/assign-licenses-to-users) en el [Centro de administración de Microsoft 365](/office365/admin/admin-overview/about-the-admin-center).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Agregar un usuario externo en Azure AD y asignar una licencia 
Los usuarios externos deben estar representados en su directorio del inquilino (Azure Active Directory (Azure AD)) para que se les puedan asignar licencias. Esos usuarios externos deben agregarse al inquilino en Azure AD como usuarios invitados y luego se les deben asignar las licencias correspondientes. Un requisito para las aplicaciones de finanzas y operaciones es que la empresa del usuario invitado debe utilizar Azure AD. Para obtener más información, consulte [Agregar usuarios de colaboración B2B de Azure Active Directory en el portal de Azure](/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importar nuevos usuarios de Azure AD 
1. Vaya a **Administración del sistema** \> **Usuarios** \> **Usuarios**.
2. En el panel de acciones, seleccione **Importar usuarios**.
3. Seleccione los usuarios que desea importar. La lista incluye usuarios de Azure AD que actualmente no son usuarios en este entorno.
4. Seleccionar **Importar usuarios**.
5. Seleccione **Cerrar**.

> [!NOTE]
> El valor del campo **Empresa** se establecerá según la empresa de la sesión actual para el administrador. Después de la importación, debe asignar roles y organizaciones según corresponda. Para obtener más información, consulte [Asignar usuarios a roles de seguridad](assign-users-security-roles.md). De forma condicional, también puede ser necesario para asociar al usuario con una **Persona** y para actualizar las opciones del usuario, como el idioma.

## <a name="manually-add-a-new-user"></a>Agregar un nuevo usuario manualmente
1. Vaya a **Administración del sistema** \> **Usuarios** \> **Usuarios**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Id. de usuario**, especifique un identificador único para el usuario.   
4. En el campo **Nombre de usuario**, escriba el nombre de usuario.  
5. En el campo **Proveedor**:
 - Para usuarios internos, use el valor predeterminado. Por ejemplo, su inquilino de Azure AD con prefijo https://sts.windows.net/.  
 - Para usuarios que no son de Azure AD, como las cuentas de Service-2-Service, introduzca un valor de texto básico. Por ejemplo: NA. Este valor ayudará a evitar llamadas de autenticación incorrectas que podrían generar errores si se utiliza un valor de proveedor de identidad válido.  
 - Para usuarios externos o invitados, agregue su nombre de inquilino de Azure AD tras https://sts.windows.net/.
6. En el campo **Correo electrónico**, introduzca el correo electrónico o nombre principal del usuario completo.  
7. En el campo **Empresa**, seleccione la empresa startup predeterminada para el usuario. 
8. Seleccione **Guardar**.

Los valores para el proveedor de identidad y el Id. de telemetría se actualizarán en función de una llamada de [Microsoft Graph](/graph/overview), cuando se guarde el registro de usuario. El Id. de telemetría se basa en el Id. de objeto o el identificador de seguridad (SID) del usuario en Azure AD.

> [!NOTE]
> Después de agregar un usuario, debe asignar roles y organizaciones según corresponda. Para obtener más información, consulte [Asignar usuarios a roles de seguridad](assign-users-security-roles.md). De forma condicional, también puede ser necesario para asociar al usuario con una **Persona** y para actualizar las **Opciones del usuario**, como el idioma.

## <a name="change-a-user-id"></a>Cambiar un Id. de usuario
Para cambiar un Id. de usuario, debe cambiar el nombre de la clave en la base de datos. Cuando cambia un Id. de usuario mediante este procedimiento, todas las configuraciones de usuario relacionadas se modifican para utilizar el nuevo Id. de usuario. Por ejemplo, la información de uso en la tabla **SysLastValue** se actualiza para hacer referencia al nuevo Id. de usuario.

> [!NOTE]
> El Id. de usuario es la clave principal de la tabla de información del usuario. Cambiar el nombre de la clave principal puede llevar algún tiempo para los usuarios existentes porque todas las referencias a la clave también se actualizan en la base de datos. 

1. Vaya a **Administración del sistema \> Usuarios \> Usuarios**.
2. Seleccione un usuario de la lista y seleccione **Opciones\> Información de registro**.
3. Seleccione **Asignar un nuevo nombre**.
4. Introduzca un valor nuevo y único para el Id. de usuario y, después, seleccione **Aceptar**. 
5. Seleccione **Sí** para confirmar.

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más opciones para implementar usuarios B2B, consulte [Exportar usuarios B2B a Azure AD](../implement-b2b.md).

Para obtener información sobre las cuentas del sistema preconfiguradas, consulte [Cuentas del sistema preconfiguradas](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
