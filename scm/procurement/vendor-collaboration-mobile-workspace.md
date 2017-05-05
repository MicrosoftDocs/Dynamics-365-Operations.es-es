---
title: "Espacio de trabajo móvil de colaboración de proveedor para la aplicación Microsoft Dynamics 365 for Operations"
description: "Con el espacio de trabajo móvil de colaboración de proveedor, sus proveedores pueden mantenerse al día de los pedidos de compra que se hayan enviado para su aprobación y ver la información sobre pedidos de compra y contactos nuevos y actualizados."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espacio de trabajo móvil de colaboración de proveedor para la aplicación Microsoft Dynamics 365 for Operations

Con el espacio de trabajo móvil de colaboración de proveedor, sus proveedores pueden mantenerse al día de los pedidos de compra que se hayan enviado para su aprobación y ver la información sobre pedidos de compra y contactos nuevos y actualizados.

<a name="prerequisites"></a>Requisitos previos
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Obtenga información sobre la plataforma móvil de Microsoft Dynamics 365 for Operations</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Plataforma móvil de Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Compruebe que utiliza un entorno que tiene la versión 1611 de Microsoft Dynamics 365 for Operations y la actualización 3 de la plataforma de Microsoft Dynamics for Operations (noviembre de 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Dispositivo móvil que tiene instalada la aplicación Dynamics 365 for Operations</span></td>
<td><span style="color: #000000;">Descargue la aplicación Dynamics 365 for Operations desde su tienda de aplicaciones móviles.</span></td>
</tr>
<tr class="even">
<td>Revisión 3215650 KB</td>
<td>Instale la revisión para habilitar los espacios de trabajo que ofrece Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">Revisión 3216943 KB</span> </span></td>
<td>Instale la revisión para habilitar el espacio de trabajo móvil de colaboración de proveedor.</td>
</tr>
<tr class="even">
<td>El usuario proveedor debe tener acceso a la interfaz web de colaboración de proveedor en Dynamics 365 for Operations y configurar un usuario de colaboración de proveedor.</td>
<td>Siga los pasos descritos en los temas siguientes para configurar y trabajar en la interfaz web de colaboración de proveedor.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Use la colaboración de proveedor para trabajar con proveedores externos</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gestionar usuarios de colaboración de proveedor</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Configurar y mantener la colaboración de proveedor</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Use la colaboración de proveedor para trabajar con los clientes en Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Visión general
El espacio de trabajo móvil de colaboración de proveedor mantiene a los proveedores informados sobre nuevos pedidos de compra de modo que puedan ver y responder a los pedidos de compra en el cliente web de Dynamics 365 for Operations.  

**Nota:** el espacio de trabajo móvil se debe utilizar como un suplemento a la interfaz web de colaboración de proveedor, pero no como sustituto.  

Con el espacio de trabajo móvil de colaboración de proveedor, sus proveedores pueden ver los nuevos pedidos de compra que se envían para aprobación. Muestra información del pedido de compra, como productos, cantidad y fechas de entrega solicitadas. La información de precios está disponible, en función de la configuración de cada proveedor.  

Si un usuario inicia sesión como proveedor, verá qué pedidos de compra se han respondido, o qué pedidos de compra aún están en espera de la acción del cliente. El proveedor puede haber sugerido otra fecha de entrega que aún no se haya acordado con el cliente por lo que el pedido de compra está esperando la acción del cliente. El proveedor también verá una lista de pedidos de compra que están confirmados pero aún no entregados.  

Para responder a un pedido de compra, el proveedor tiene que usar la interfaz web de colaboración de proveedor que está disponible en el cliente web de Dynamics 365 for Operations. Aquí el proveedor también obtendrá más información sobre el pedido, como documentos adjuntos, la dirección de entrega por línea y los cargos asociados al proveedor.  

Con un rol de seguridad especial, el proveedor puede ver las personas de contacto registradas en una cuenta de proveedor. Con el mismo rol de seguridad, el proveedor puede ver el estado de cualquier solicitud de usuario que se haya enviado.  

La creación de nuevos contactos y el envío de nuevas solicitudes de usuario se debe realizar en la interfaz de colaboración de proveedor que está disponible en el cliente web de Dynamics 365 for Operations.  

Con el espacio de trabajo móvil, el proveedor puede:

-   Ver nuevos pedidos de compra enviados al proveedor.
-   Ver los pedidos de compra a los que ha respondido el proveedor y que están a la espera de la acción del cliente.
-   Ver los pedidos de compra que se encuentran en estado confirmado pero que no se han recibido completamente.
-   Ver la información de la persona de contacto registrada en la cuenta del proveedor (requiere un rol de seguridad adicional).
-   Ver la información y seguir el estado de una solicitud de usuario enviada por el proveedor (requiere un rol de seguridad adicional).

## <a name="get-started"></a>Introducción
Para comenzar en su dispositivo móvil:

1.  En su tienda de aplicaciones móviles, descargue e instale la aplicación Microsoft Dynamics 365 for Operations.
2.  Inicie la aplicación en su dispositivo.
3.  Escriba la URL de Dynamics 365.
4.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
5.  La primera vez que inicia sesión, se le pediré el nombre de usuario y la contraseña de su cuenta Microsoft Dynamics 365 for Operations. 

Tras iniciar sesión en la aplicación, no hay espacios de trabajo visibles. Para ver los espacios de trabajo en su aplicación móvil, primero debe publicar los espacios de trabajo deseados para la aplicación Dynamics 365 for Operations. Necesita el permiso de administración del sistema para publicar el espacio de trabajo.

1.  Inicie Dynamics 365 for Operations.
2.  Vaya a **Administración del sistema** &gt; **Configurar** &gt; **parámetros del sistema**.
3.  Seleccionar **Administrar aplicación móvil**.
4.  Seleccione el espacio de trabajo **Colaboración de proveedor** para publicar en la plataforma móvil.
5.  Seleccione **Publicar área de trabajo**.
6.  Actualice su dispositivo para ver los espacios de trabajo publicados.
7.  Seleccione el espacio de trabajo **Colaboración de proveedor**. Verá la página siguiente.

[![vendor-collaboration-mobile-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contactos
La página **Contactos** le permite ver todos los contactos que se han configurado para la cuenta de proveedor. Muestra el nombre de la persona de contacto, el correo electrónico principal y los alias de usuario, si los hay. También muestra si la cuenta de usuario de la persona de contacto está activa. Al seleccionar un contacto, verá los detalles del contacto como las entidades jurídicas para las que la persona es un contacto y la información de contacto, como el número de teléfono u otra dirección de correo electrónico.

## <a name="user-requests"></a>Solicitudes de usuarios
La página **Solicitudes de usuario** le permite ver todas las solicitudes de usuario que ha enviado a través de la interfaz web de colaboración de proveedor y realizar el seguimiento del estado. Al seleccionar una solicitud de usuario, puede ver lo que se ha solicitado, agregar o desactivar un usuario, cambiar la seguridad y ver qué roles de seguridad se solicitaron para el usuario.

## <a name="purchase-orders-ready-for-review"></a>Pedidos de compra listos para revisión
La página **Pedidos de compra listos para revisión** le permite ver todos los pedidos de compra enviados por el cliente y que no han recibido respuesta. Puede ver la información seleccionada sobre el pedido, como los productos que se han solicitado y cuándo se entregan. La información de precios solo está disponible si se ha configurado esto para el proveedor.  

Puede ver si el pedido de compra tiene notas o adjuntos. Para abrir los adjuntos, necesita utilizar la colaboración de proveedor en el cliente web. Seleccione **Línea de pedido de compra** para ver todas las líneas con los detalles. Tenga en cuenta que en cada línea un indicador mostrará si hay notas o adjuntos o si hay una dirección de entrega diferente a la que se muestra en el encabezado.  

Para responder al pedido de compra, debe usar el cliente web de colaboración de proveedor.

## <a name="awaiting-customer-action"></a>Esperando acción del cliente
La página **Esperando acción del cliente** le permite encontrar los pedidos de compra a los que ha respondido usted o alguien de la empresa que también tiene acceso a la colaboración de proveedor. Los pedidos de compra solo están visibles en esta lista si el cliente necesita realizar una de las siguientes acciones en el pedido de compra.

-   Si el pedido de compra se ha rechazado, el cliente necesitará actualizar el pedido enviado y enviarlo otra vez o cancelar el pedido y volver a enviar. Si el pedido de compra se vuelve a enviar, desaparecerá de la página **Esperando acción del cliente**.
-   Si el pedido de compra se acepta con cambios, el cliente necesitará actualizar el pedido original y reenviarlo para su revisión o actualizarlo con los cambios y confirmarlo inmediatamente. En ambos casos, el pedido de compra desaparecerá de la página **Esperando acción del cliente**.
-   Si el pedido de compra ha sido aceptado y aparece en la página **Esperando acción del cliente** es porque el pedido de compra no se ha confirmado automáticamente cuando la aceptación se ha realizado. Está esperando a que un agente de compras cambie el pedido a Confirmado. Normalmente, el pedido de compra sería considerado un contrato entre el cliente y el proveedor cuando el proveedor acepta el pedido. Mover el pedido de compra al estado Confirmado sería una formalidad.

Al seleccionar el pedido de compra, aparecen detalles adicionales sobre la respuesta. Puede ver los detalles de línea y responder a cada línea. El estado de línea muestra cuáles de las respuestas siguientes se han dado.

-   Aceptado
-   Rechazadas
-   Aceptado con cambios
-   Sustituido/Sustituir
-   Dividir en programar/línea de programación

Tenga en cuenta que un indicador muestra **En entrega**=sí/no, que se usa para indicar que las líneas no se entregarán. Esto podría deberse a que la línea se ha rechazado o sustituido en los casos en que no se espera que se entreguen las líneas originales o a que una línea se ha dividido en varias líneas de programación y no se espera que la línea original se entregue de la forma solicitada en el pedido recibido.  

Se muestran los cambios realizados en la respuesta de la línea de pedido, excepto las notas y los adjuntos cargados, que puede ver mediante la interfaz web de colaboración del proveedor.

## <a name="open-confirmed-orders"></a>Pedidos confirmados abiertos
Si el pedido de compra está confirmado, lo que significa que ha cambiado al estado Confirmado, aparecerá en el pedido confirmado abierto. Permanecerá en la lista hasta que se registre como recibido por el cliente.


