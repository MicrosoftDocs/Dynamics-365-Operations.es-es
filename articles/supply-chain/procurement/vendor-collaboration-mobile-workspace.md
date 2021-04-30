---
title: Espacio de trabajo de móvil de colaboración de proveedor
description: Este tema proporciona información acerca del espacio de trabajo móvil de colaboración de proveedor. Este espacio de trabajo ayuda a los proveedores estar informados sobre los pedidos de compra que les han enviado para su aprobación. También pueden ver la información sobre los pedidos y contactos nuevos y actualizados.
author: kamaybac
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: dabourq
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 8f6affd05e658f39d567f7512c71d944636588ff
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907948"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Espacio de trabajo de móvil de colaboración de proveedor

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca del espacio de trabajo móvil **Colaboración de proveedor**. Este espacio de trabajo ayuda a los proveedores estar informados sobre los pedidos de compra que les han enviado para su aprobación. También pueden ver la información sobre los pedidos y contactos nuevos y actualizados.

Este espacio de trabajo móvil se debe usar con la aplicación móvil Finance and Operations.

## <a name="overview"></a>Información general 
El espacio de trabajo móvil de **Colaboración de proveedores** mantiene a los proveedores informados sobre nuevos pedidos de compra de modo que puedan ver pedidos y responder a ellos en el cliente web. 

>[!NOTE]
> El espacio de trabajo móvil se debe utilizar como un suplemento a la interfaz web de colaboración de proveedor, pero no como sustituto de esta. 

Sus proveedores pueden utilizar el espacio de trabajo móvil **Colaboración de proveedor** para ver los nuevos pedidos de compra que se envían para aprobación. Muestra información del pedido de compra, como productos, cantidades y fechas de entrega solicitadas. La información de precios también está disponible, en función de la configuración de cada proveedor. 

Un usuario que se registra como proveedor verá qué pedidos de compra se han respondido y qué pedidos de compra aún están en espera de la acción del cliente. Por ejemplo, un pedido de compra puede estar esperando la acción del cliente porque el proveedor sugirió otra fecha de entrega, pero el cliente aún no ha acordado esa fecha. El proveedor también verá una lista de pedidos de compra que se han confirmado pero aún no se han entregado. 

Para responder a un pedido de compra, el proveedor debe usar la interfaz web de colaboración de proveedor que está disponible en el cliente web. Aquí, el proveedor también puede obtener más información sobre el pedido, como documentos adjuntos, la dirección de entrega por línea y los cargos asociados al proveedor. 

Los proveedores que tiene un rol de seguridad especial pueden ver las personas de contacto registradas en una cuenta de proveedor. El mismo rol de seguridad permite a un proveedor ver el estado de cualquier solicitud de usuario que se haya enviado. 

La interfaz web de colaboración de proveedor en el cliente web debe utilizarse para crear nuevos contactos y para enviar nuevas solicitudes de usuario. 

El espacio de trabajo móvil **Colaboración de proveedor** permite a un proveedor realizar las tareas siguientes:

-   Ver nuevos pedidos de compra que se han enviado al proveedor.
-   Ver los pedidos de compra a los que ha respondido el proveedor y que están a la espera de la acción del cliente.
-   Ver los pedidos de compra que se han confirmado pero que aún no se han recibido completamente.
-   Ver la información de la persona de contacto registrada en la cuenta de proveedor. (Esta tarea requiere un rol de seguridad adicional.)
-   Ver la información sobre una solicitud de usuario que el proveedor envió y seguir el estado de la solicitud. (Esta tarea requiere un rol de seguridad adicional.)

## <a name="prerequisites"></a>Requisitos previos
Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Requisitos previos si usa Supply Chain Management
Si Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Colaboración de proveedor**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior
Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes. 

<table>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>KB 3216943 debe implementarse si usa la actualización 3 de la plataforma.</td>
<td>Administrador del sistema</td>
<td>KB 3216943 es una actualización de binarios requerida si usa la actualización 3 de la plataforma. Para implementar este KB, el administrador del sistema debe seguir estos pasos.
<ol>
<li>Descargue KB 3216943 de Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Instalar la actualización de binarios, que se entrega como paquete implementable. Para obtener información acerca de cómo aplicar un paquete implementable, consulte <a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar un paquete implementable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>KB 4013633 debe implementarse.</td>
<td>Administrador del sistema</td>
<td>KB 4013633 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Inventario disponible</strong>. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Descargue la sustitución de metadatos de LCS</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete implementable</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>El espacio de trabajo móvil <strong>Colaboración de proveedor</strong> debe publicarse.</td><td>Administrador del sistema</td>
<td>Consulte <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
<tr class="even">
<td>El usuario proveedor debe tener acceso a la interfaz web de colaboración de proveedor en el cliente web y debe configurar un usuario de colaboración de proveedor.</td><td>Encargados de compras y el administrador del sistema</td>
<td>Siga los pasos en los temas siguientes para configurar y trabajar en la interfaz web de colaboración de proveedor.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Use la colaboración de proveedor para trabajar con proveedores externos</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gestionar usuarios de colaboración de proveedor</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Configurar y mantener la colaboración de proveedor</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Use la colaboración de proveedor para trabajar con los clientes en Supply Chain Management</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargar e instalar la aplicación móvil de Finance and Operations:

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil
1.  Inicie la aplicación en su dispositivo móvil.
2.  Especifique la dirección URL Microsoft Dynamics 365.
4.  La primera vez que inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
5.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

    [![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Utilice el espacio de trabajo de móvil Colaboración de proveedor
Si selecciona el espacio de trabajo **Colaboración de proveedor**, verá las siguientes opciones.

![Espacio de trabajo de móvil de colaboración de proveedor](./media/vendor-collaboration-mobile-app.png)

El espacio de trabajo **Colaboración de proveedor** incluye las siguientes páginas.

### <a name="contacts"></a>Contactos
La página **Contactos** le permite ver todos los contactos que se han configurado para la cuenta de proveedor. Muestra el nombre, la dirección de correo electrónico principal y el alias de usuario de la persona de contacto, si esta tiene un alias. Esta página también muestra si la cuenta de usuario de la persona de contacto está activa. Si selecciona un contacto, verá los detalles de contacto, como las entidades jurídicas para las que la persona es contacto. También verá la información de contacto, como un número de teléfono o una dirección de correo electrónico alternativa.

### <a name="user-requests"></a>Solicitudes de usuarios
La página **Solicitudes de usuario** le permite ver todas las solicitudes de usuario que ha enviado a través de la interfaz web de colaboración de proveedor. También puede seguir el estado de esas solicitudes. Al seleccionar una solicitud de usuario, puede ver lo que se ha solicitado, agregar o desactivar un usuario, cambiar la seguridad y ver qué roles de seguridad se solicitaron para el usuario.

### <a name="purchase-orders-ready-for-review"></a>Pedidos de compra listos para revisión
La página **Pedidos de compra listos para revisión** le permite ver todos los pedidos de compra enviados por el cliente, pero que todavía no se han respondido. Puede ver la información seleccionada sobre el pedido, como los productos que se solicitaron y cuándo deben entregarse esos productos. La información de precios también está disponible, en función de la configuración del proveedor.

También puede ver si el pedido de compra tiene notas o adjuntos. Sin embargo, para abrir las notas y los datos adjuntos, debe usar la interfaz web de colaboración de proveedor en el cliente web. Seleccione **Línea de pedido de compra** para ver todas las líneas junto con sus detalles. Para cada línea, un indicador mostrará si hay notas o adjuntos o si la dirección de entrega difiere de la que se muestra en el encabezado.

Para responder al pedido de compra, debe usar la interfaz web de colaboración de proveedor en el cliente web.

### <a name="awaiting-customer-action"></a>Esperando acción del cliente
La página **Esperando acción del cliente** le permite encontrar los pedidos de compra a los que ha respondido usted u otra persona de la empresa que también tiene acceso a la colaboración de proveedor. Los pedidos de compra solo están visibles en esta lista si el cliente tiene que realizar una de las siguientes acciones en el pedido de compra:

-   Si el pedido de compra se ha rechazado, el cliente debe actualizar o cancelar el pedido original y enviarlo otra vez. Si el pedido de compra se vuelve a enviar, ya no aparecerá en la página **Esperando acción del cliente**.
-   Si el pedido de compra se acepta con cambios, el cliente debe actualizar el pedido original y volverlo a enviar para su revisión o bien actualizar el pedido con los cambios solicitados y confirmarlo inmediatamente. En ambos casos, el pedido de compra ya no aparecerá en la página **Esperando acción del cliente**.
-   Si el pedido de compra se aceptó pero sigue apareciendo en la página **Esperando acción del cliente** es porque el pedido de compra no se confirmó automáticamente cuando se aceptó. Ahora está esperando a que un agente de compras cambie el estado del pedido a **Confirmado**. Normalmente, el pedido de compra se considera un contrato entre el cliente y el proveedor cuando el proveedor acepta el pedido. Por lo tanto, la actualización al estado de **Confirmado** suele ser solo una formalidad.

Si selecciona un pedido de compra, aparecen detalles adicionales sobre la respuesta. Puede ver los detalles de línea y responder a cada línea. El estado de la línea muestra cuáles de las respuestas siguientes se han dado:

-   Aceptada
-   Rechazado
-   Aceptado con cambios
-   Sustituido/Sustituir
-   Dividir en programar/línea de programación

Tenga en cuenta que el campo **En entrega** se establece en **Sí** o **No** para indicar si las líneas se entregarán. Una línea no puede entregarse debido a los siguientes motivos:

- La línea se rechazó.
- Se hizo una sustitución y no se espera que la línea original se entregue como se solicita en el pedido recibido.
- La línea se dividió en varias líneas de programación y no se espera que la línea original se entregue como se solicita en el pedido recibido.

Se muestran los cambios que se han realizado en la respuesta de la línea de pedido. Sin embargo, las notas y los datos adjuntos cargados no se muestran. Para ver las notas y los datos adjuntos, debe usar la interfaz web de colaboración de proveedor en el cliente web.

### <a name="open-confirmed-orders"></a>Pedidos confirmados abiertos
Si el cliente ha confirmado el pedido de compra, (es decir, el estado del pedido de compra ha cambiado a **Confirmado**), aparece en el pedido confirmado abierto. Permanecerá en la lista hasta que se registre como recibido por el cliente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]