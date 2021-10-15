---
title: Gestionar usuarios de colaboración de proveedor
description: Este tema describe cómo puede solicitar el aprovisionamiento de los nuevos usuarios de colaboración del proveedor, y cómo añadir nuevos contactos de colaboración.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ff0d11bf2c42f7ae63e3db5f31f3ffea2c28f693
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578137"
---
# <a name="manage-vendor-collaboration-users"></a>Gestionar usuarios de colaboración de proveedor

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede solicitar el aprovisionamiento de los nuevos usuarios de colaboración del proveedor, y cómo añadir nuevos contactos de colaboración. 

La interfaz de colaboración del proveedor en Dynamics 365 Supply Chain Management expone información a los proveedores externos acerca de pedidos de compra, facturas y consignación de existencias. Puede crear nuevos contactos de colaboración del proveedor y solicitar que se aprovisione a los nuevos usuarios si trabaja como proveedor externo con el rol de seguridad **Gestión de proveedores (externo)**, o con permisos similares. También puede realizar estas tareas si trabaja como profesional de compras. En este tema, este rol hace referencia a un responsable de compras que trabaja dentro de la empresa que posee la instancia de Supply Chain Management. Para obtener más información sobre cómo usar la colaboración del proveedor si es proveedor externo, consulte [Colaboración de proveedores con clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para obtener más información sobre cómo usar la colaboración del proveedor si es un profesional de compras, consulte [Colaboración de proveedor con proveedores externos](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Añadir nuevos contactos de colaboración de proveedor
Si desea que una persona pueda acceder a la colaboración de proveedor primero es necesario añadirla como contacto de colaboración del proveedor. También puede que quiera añadir contactos para los empleados de la empresa que no utilizan la colaboración de proveedor. Por ejemplo, podrían ser el punto de contacto para otras clases de información de compras. Los nuevos contactos se añaden en la página de **Todos los contactos**, a la que se accede desde el menú de **Colaboración de proveedor** &gt; **Contactos**. Para añadir un contacto nuevo:

1.  Haga clic en **Nuevo.**
2.  Introduzca los detalles de contacto de la persona.
3.  Elija a qué entidad jurídica representan en su empresa, y con cuál trabajarán dentro de la empresa con la que van a colaborar. Esto se hace seleccionando un par como **Entidad jurídica en mi empresa**/**/Entidad jurídica en la empresa del cliente**.
4.  Haga clic en **Crear.**

Si desea eliminar un contacto, solo se pueden eliminar los que ha creado.

## <a name="vendor-collaboration-user-requests"></a>Solicitudes de usuario de colaboración de proveedor
Las solicitudes de usuario de colaboración de proveedor pueden activarse mediante un responsable de compras, o un administrador de proveedor externo.

-   Si usted es proveedor externo, envía solicitudes desde la página **Todos los contactos** dentro del módulo **Colaboración de proveedor**.
-   Si es un profesional de compras, envía las solicitudes desde la página **Ver contactos**. Para ello, en el registro de proveedor, en la sección **Configuración** del panel Acciones, seleccione **Contactos** &gt; **Ver contactos**.

Puede hacer una solicitud para aprovisionar a un usuario, para desactivarlo o para modificar los roles de seguridad. Si es administrador de proveedor externo, debe estar registrado como persona de contacto para las cuentas de proveedor para las que desea realizar las solicitudes de usuario, y debe tener acceso a la interfaz de colaboración de proveedor para esas cuentas de proveedor.  

Cuando se envía una solicitud se añade a la lista **Solicitudes de usuario de colaboración de proveedor** en el módulo **Colaboración de proveedor**, y en la lista **Solicitud de usuario de colaboración de proveedor** del módulo de **Adquisición y abastecimiento** (el módulo de la adquisición y abastecimiento no es accesible a los usuarios externos).

### <a name="provision-a-user"></a>Aprovisionar un usuario

Para poder solicitar el aprovisionamiento de un nuevo usuario, esa persona debe figurar como contacto para una o más cuentas de proveedor. Para crear una solicitud de nuevo usuario de colaboración de proveedor:

1. En la página **Todos los contactos**, haga clic en **Suministrar un usuario de proveedor**.
2. Escriba una dirección de correo electrónico para el usuario. Esta dirección la usará el usuario para iniciar sesión en Supply Chain Management. Si la dirección de correo electrónico pertenece a un dominio registrado como usuario de Microsoft Azure, la dirección de correo electrónico tiene que ser una cuenta existente de Azure Active Directory (AAD) para que el proceso de provisión finalice correctamente. Si la dirección de correo electrónico no pertenece a un dominio registrado con Microsoft Azure, se creará una cuenta AAD como parte del proceso de provisión y el nuevo usuario recibirá una invitación mediante un mensaje de correo. Las direcciones de correo electrónico de consumidor con dominios como @hotmail.com, @gmail.com o @comcast.net no pueden usarse para registrar a un usuario.
3. Configure la opción **Acceso de colaboración de proveedor permitido** a **Sí** para todas las entidades jurídicas para las que el usuario necesita acceso.
4. En la sección **Asignar roles de usuario**, seleccione la casilla **Asignar** para los roles de seguridad que debe tener el nuevo usuario.
5. Haga clic en **Enviar**.

Cuando se envíe la solicitud de usuario proveedor, el campo **Acceso a la colaboración de proveedor permitido** se establece en **Sí** para la cuenta de proveedor seleccionada y se inicia un flujo de trabajo de solicitud del usuario. Como parte del flujo de trabajo, se crea un nuevo usuario en y se asignan los roles de seguridad. Además, el servicio Azure B2B que inicia la interacción con el portal Azure se activa y se asocia a una cuenta nueva o existente de AAD con la cuenta de usuario de Supply Chain Management. Para obtener más información, consulte [¿Qué es la colaboración B2B de Azure AD?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

### <a name="inactivate-a-user"></a>Desactivar un usuario

Hay dos formas de eliminar el acceso a la colaboración del proveedor de un usuario:

-   En la página **Contactos** para el proveedor, defina la opción **Acceso permitido a la colaboración de proveedor** a **No** para el contacto. Esto se puede efectuar individualmente por la entidad jurídica para la que la persona es un contacto. Esta opción solo pueden usarla los profesionales de contratación.
-   Desactive la cuenta completa del usuario mediante el envío de una solicitud a **Desactivar usuario de proveedor**.

Para solicitar que se desactive un usuario:

1.  En la página **Todos los contactos**, haga clic en **Desactivar** **usuario de proveedor**.
2.  Escriba un comentario en el campo **Justificación comercial**.
3.  Haga clic en **Enviar**.

### <a name="modify-security-roles"></a>Modificar roles de seguridad

La página **Mantener los roles de usuario de proveedor** es la misma que la de **Provisión de un usuario de proveedor** excepto porque la lista de roles de seguridad se puede editar.  

Para solicitar que los roles de seguridad se modifiquen para un usuario:

1.  En la página **Todos los contactos**, haga clic en **Mantener** **roles de usuario de proveedor**.
2.  Escriba un comentario en el campo **Justificación comercial**.
3.  En la sección **Mantener los roles de usuario**, seleccione los roles de seguridad que desea asignar, o borre los que desea quitar.
4.  Haga clic en **Enviar**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]