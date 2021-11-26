---
title: Crear y administrar usuarios del portal del cliente
description: Este tema explica cómo crear cuentas de usuario del portal del Cliente y establecer permisos para ellas.
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 448f315b888b63eba74dcb8b47a9b238e371bb2b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573498"
---
# <a name="create-and-manage-customer-portal-users"></a>Crear y administrar usuarios del portal del cliente

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

En la implementación lista para usar, no hay forma de que los usuarios se registren por sí mismos para los sitios web que se crean utilizando el portal del Cliente. Para iniciar sesión y usar un sitio web, los usuarios deben ser invitados por el administrador. Microsoft ha bloqueado intencionalmente la capacidad de los usuarios para registrarse.

Para que un usuario pueda usar un sitio web, se debe crear un registro de contacto para ese usuario. Este registro indica a qué cuenta de cliente y entidad legal pertenece el usuario. Esta información es esencial para garantizar que el usuario pueda crear y ver pedidos de ventas.

Cuando los usuarios se registran por sí mismos, los registros de contacto se crean automáticamente para ellos. Por lo tanto, no puede asegurarse de que un usuario seleccione la cuenta de cliente y la entidad jurídica correctas. Sin embargo, el proceso de invitación permite que un administrador asigne la cuenta de cliente correcta y la entidad legal al registro de contacto antes de enviar una invitación. Si está pensando en personalizar la solución para que los usuarios puedan registrarse por sí mismos, asegúrese de considerar las posibles consecuencias.

## <a name="video"></a>Vídeo
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

El vídeo [Invitar a los clientes a registrarse y usar el portal de clientes](https://youtu.be/drGUYHX9QIQ) (se muestra arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="prerequisite-setup"></a>Requisitos previos de configuración

Los contactos en los portales Power Apps se almacenan como registros en la tabla **Contactos** en Microsoft Dataverse. La escritura dual luego sincroniza estos registros con Microsoft Dynamics 365 Supply Chain Management según sea necesario.

![Diagrama del sistema para contactos del portal del cliente.](media/customer-portal-contacts.png "Diagrama del sistema para contactos del portal del cliente")

Antes de comenzar a invitar a nuevos clientes, asegúrese de haber habilitado la asignación de tablas del **Contacto** en doble escritura.

## <a name="the-invitation-process"></a>El proceso de invitación

Para invitar a un contacto existente al portal del Cliente, siga los pasos de [Invitar contactos a los portales](/powerapps/maker/portals/configure/invite-contacts) en la documentación de portales Power Apps.

Antes de invitar a un cliente a unirse al portal del cliente, asegúrese de que el [registro de contacto](/powerapps/maker/portals/configure/configure-contacts) del cliente está disponible y configurado de la siguiente manera:

1. Establezca el campo **Empresa** en la entidad jurídica a la que desea que pertenezca el cliente en Supply Chain Management.
2. Establezca el campo **Número de cuenta** en el número de cuenta de cliente que desea que tenga el usuario en Supply Chain Management.

Después de crear un contacto, debería poder verlo en Supply Chain Management.

Para más información, consulte [Configurar un contacto para usarlo en un portal](/powerapps/maker/portals/configure/configure-contacts) en la documentación de portales Power Apps.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Roles web y permisos de tabla listos para usar

Los roles de usuario en los portales Power Apps se definen mediante [roles web](/powerapps/maker/portals/configure/create-web-roles) y [permisos de tabla](/powerapps/maker/portals/configure/assign-entity-permissions). El Portal del cliente ofrece algunos roles listos para usar. Puede crear nuevos roles y puede modificar o eliminar roles existentes.

### <a name="out-of-box-web-roles"></a>Roles web listos para usar

Esta sección describe los roles web que se entregan con el portal del Cliente.

Para obtener más información sobre cómo modificar los roles de usuario listos para usar, consulte [Crear roles web para portales](/powerapps/maker/portals/configure/create-web-roles) y [Agregar seguridad basada en registros mediante el uso de permisos de tabla para portales](/powerapps/maker/portals/configure/assign-entity-permissions) en la documentación de portales Power Apps.

#### <a name="administrator"></a>Administrador

El administrador supervisa y mantiene el sitio web. Esta persona aprovisionará y configurará el portal del Cliente. El administrador mantiene los aspectos de TI y seguridad del portal, y se asegura de que todo funcione sin problemas. El administrador también puede personalizar y/o cambiar el portal agregando nuevas funcionalidades, creando nuevos roles y otras cosas más.

#### <a name="customer-representative"></a>Representante del cliente

Un representante del cliente trabaja para una empresa cliente y es responsable de administrar los pedidos que realiza la empresa. El representante del cliente puede ver todos los pedidos que se han realizado para la empresa y los usuarios que los realizaron. Además, el representante del cliente puede ver información sobre la cuenta general y qué contactos pueden realizar pedidos en nombre de esa cuenta.

#### <a name="authorized-users"></a>Usuarios autorizados

Los usuarios autorizados pueden realizar pedidos y ver el estado de los pedidos que han realizado. Sin embargo, no pueden ver el estado de los pedidos que han realizado otros usuarios de su empresa.

#### <a name="unauthorized-users"></a>Usuarios no autorizados

Los usuarios no autorizados no pueden ver ningún dato. Solo pueden ver información pública, como términos y condiciones, y detalles sobre la empresa que administra el portal del Cliente.

#### <a name="example"></a>Ejemplo

La siguiente tabla muestra qué pedidos de ventas pueden ver los usuarios en cada rol web del sistema.

| Pedido de ventas | Administrador | Representante del cliente para el cliente&nbsp;X | Usuario autorizado: Jane | Usuario autorizado: Sam | Usuario no autorizado: May |
|---|---|---|---|---|---|
| Solicitante del cliente&nbsp;X:&nbsp;Jane | Sí | Sí | Sí | No | No |
| Solicitante del cliente&nbsp;X:&nbsp;Sam | Sí | Sí | No | Sí | No |
| Solicitante del cliente&nbsp;Y:&nbsp;May | Sí | No | No | No | No |

> [!NOTE]
> Aunque tanto Sam como Jane son contactos que trabajan para el cliente X, solo pueden ver los pedidos que ellos mismos han realizado y nada más. Aunque May tiene un pedido en el sistema, no puede ver ese pedido en el portal del Cliente, porque es un usuario no autorizado. (Además, debería haber realizado el pedido a través de algún canal que no sea el portal del Cliente).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]