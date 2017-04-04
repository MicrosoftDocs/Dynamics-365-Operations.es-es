---
title: "Área de trabajo móvil de colaboración del proveedor para Microsoft Dynamics 365 para la aplicación de operaciones"
description: "Con el área de trabajo móvil de colaboración del proveedor, sus proveedores pueden permanecer actualizaron en los pedidos de compra que se hayan registrado ellos para su aprobación y ver la información sobre nuevos y actualizados pedidos de compra y contactos."
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

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Área de trabajo móvil de colaboración del proveedor para Microsoft Dynamics 365 para la aplicación de operaciones

Con el área de trabajo móvil de colaboración del proveedor, sus proveedores pueden permanecer actualizaron en los pedidos de compra que se hayan registrado ellos para su aprobación y ver la información sobre nuevos y actualizados pedidos de compra y contactos.

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
<td>Lea sobre el Microsoft Dynamics 365 para la plataforma de móvil de las operaciones</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dinámica 365 para la plataforma de móvil de las operaciones</a></td>
</tr>
<tr class="even">
<td>Dinámica 365 para las operaciones</td>
<td>Asegúrese de que utiliza un entorno con Microsoft Dynamics 365 para la versión 1611 de las operaciones y Microsoft Dynamics para la plataforma de las operaciones actualiza 3 (noviembre de 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Dispositivo móvil que tiene Dynamics 365 para la aplicación de las operaciones instalada</span></td>
<td><span style="color: #000000;">Descargue Dynamics 365 para la aplicación de las operaciones de la tienda móvil de la aplicación.</span></td>
</tr>
<tr class="even">
<td>Sustitución 3215650 KB</td>
<td>Instale el reemplazo para habilitar las áreas de trabajo que se proporcionan en Dynamics 365 para las operaciones.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">Sustitución 3216943 KB</span></span></td>
<td>Instale el reemplazo para habilitar el espacio de trabajo del móvil de colaboración del proveedor.</td>
</tr>
<tr class="even">
<td>El usuario proveedor debe tener acceso a la interfaz web de colaboración del proveedor en Dynamics 365 para las operaciones y se configuran un usuario de colaboración del proveedor.</td>
<td>Siga los pasos descritos en los temas siguientes para configurar y ejecutar la interfaz web de colaboración del proveedor.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Use la colaboración de proveedor para ejecutar los proveedores externos</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gestionar usuarios de colaboración de proveedor</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Configurar y mantener la colaboración de proveedor</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Use la colaboración de proveedor para ejecutar los clientes de Dynamics 365 para las operaciones</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Visión general
El área de trabajo móvil de colaboración del proveedor dispone de los proveedores informados sobre nuevos pedidos de compra de modo que puedan ver y responder a los pedidos de compra en Dynamics 365 para el clientes Web de las operaciones.  

** Nota: ** El área de trabajo móvil se debe utilizar como un suplemento a la interfaz Web de colaboración del proveedor, pero no sustitución.  

Con el área de trabajo móvil de colaboración del proveedor, sus proveedores pueden ver los nuevos pedidos de compra que se envían para aprobación. Muestra información del pedido de compra, como productos, cantidad, y fechas de entrega solicitada. La información de precios está disponible, en función de la configuración para cada proveedor.  

Cuando un usuario inicia sesión como proveedor, verán qué pedidos de compra se han respondido, o qué pedidos de compra aún están en espera de la acción del cliente. El proveedor puede haber sugerido otra fecha de entrega que aún no se acuerda con el cliente por lo que el pedido de compra está esperando la acción del cliente. El proveedor también verá una lista de pedidos de compra se hayan confirmado pero aún no se entregan que.  

Para responder a un pedido de compra, el proveedor tiene que usar la interfaz web de colaboración del proveedor que está disponible en Dynamics 365 para el clientes Web de las operaciones. Aquí también el proveedor obtendrán obtener más información sobre el pedido, como datos adjuntos de documento, la dirección de entrega por línea, y los cargos asociados al proveedor.  

Con un rol de seguridad especial, el proveedor puede ver que registran las personas de contacto para una cuenta de proveedor. Con el mismo rol de seguridad, el proveedor puede ver el estado de cualquier solicitud de usuario se haya enviado.  

Crear nuevos contactos y enviar solicitudes de usuario nuevas se deben realizar en la interfaz de colaboración del proveedor que está disponible en Dynamics 365 para el clientes Web de las operaciones.  

Con el área de trabajo móvil, el proveedor puede:

-   Nuevos pedidos de compra de la vista registrados para el proveedor.
-   Los pedidos de compra de la vista que el proveedor ha respondido a y esperan la acción del cliente.
-   Ver los pedidos de compra que se encuentran en una estado confirmado y no se han recibido completamente.
-   Ver la información de la persona de contacto registrada en la cuenta del proveedor (requiere un rol de seguridad adicional).
-   Ver información y siga el estado de una solicitud de usuario que envió el proveedor (requiere un rol de seguridad adicional).

## <a name="get-started"></a>Introducción
Para obtener iniciado en su dispositivo móvil:

1.  En su tienda móvil de la aplicación, y descarga el instalar Microsoft Dynamics 365 para la aplicación de las operaciones.
2.  Iniciar la aplicación del dispositivo.
3.  Especifique la dirección URL de Dynamics 365.
4.  Especifique la empresa para iniciar sesión en. Por ejemplo, escriba USMF ** **.
5.  La primera vez que se iniciar sesión, se le solicitará el nombre de usuario y la contraseña para su Microsoft Dynamics 365 para la cuenta de operaciones. 

Tras inicie sesión la aplicación, no hay áreas de trabajo visible. Para ver Áreas de trabajo en su aplicación móvil, primero debe publicar las áreas de trabajo deseadas a Dynamics 365 para la aplicación de las operaciones. Necesita el permiso de administración del sistema para publicar el área de trabajo.

1.  Dinámica 365 de inicio de las operaciones.
2.  Retroceda ** Administración del sistema ** &gt; ** la configuración ** &gt; ** los parámetros del sistema **.
3.  Seleccione ** gestionar la aplicación móvil **.
4.  Seleccione el área de trabajo de colaboración ** ** proveedor para publicar en esta plataforma móvil.
5.  Seleccione ** publique el área de trabajo **.
6.  Actualización del dispositivo para ver las áreas de trabajo publicadas.
7.  Seleccione ** colaboración del proveedor ** el área de trabajo. Es la página siguiente.

[proveedor-colaboración-Mobile-aplicación de![] (. /media/vendor-collaboration-mobile-app.png])(. /media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contactos
** Contactos ** la página le permite ver todos los contactos que se han configurado para la cuenta de proveedor. Muestra el nombre de la persona de contacto, el correo electrónico principal, y los usuarios alias, si está disponible. También muestra si la cuenta de usuario de la persona de contacto está activo. Al seleccionar un contacto, verá los detalles de contacto, como cuyas para entidades jurídicas la persona es un contacto, y la información de contacto como el número de teléfono o otra dirección de correo electrónico.

## <a name="user-requests"></a>Solicitudes de usuarios
** Solicitudes de usuario ** la página le permite ver todas las solicitudes de usuario que ha enviado a través de la interfaz web de colaboración del proveedor y realizar el seguimiento del estado. Al seleccionar una solicitud de usuario, puede ver lo que se ha solicitado, agrega o desactivar un usuario cambia, seguridad, y qué consulta roles de seguridad se solicitaron para el usuario.

## <a name="purchase-orders-ready-for-review"></a>Pedidos de compra requieran de su revisión
** Pedidos de compra requieran de su revisión ** la página le permite ver todos los pedidos de compra enviadas por el cliente y que se han respondido. Puede ver la información seleccionada sobre el pedido, como la que se han solicitado los productos y cuándo entregar. La información de precios sólo está disponible si se configura para el proveedor.  

Puede ver si el pedido de compra tiene notas o datos adjuntos. Para abrir los datos adjuntos, necesita la colaboración del proveedor en el clientes Web. Seleccione ** línea de pedido de compra ** para ver todas las líneas con detalles. Tenga en cuenta que para cada línea, un indicador mostrará si hay notas o un adjunto o si hay una dirección de entrega que es diferente que lo que se muestra en el encabezado.  

Para responder al pedido de compra, debe usar el clientes Web de colaboración del proveedor.

## <a name="awaiting-customer-action"></a>Esperando acción del cliente
** Aguardando la acción del cliente ** la página le permite encontrar los pedidos de compra a los que usted, o alguien de la empresa que también tenga acceso a la colaboración del proveedor, ha respondido. Los pedidos de compra son está visible en esta lista si el cliente necesita realizar una de las siguientes acciones en el pedido de compra.

-   Si el pedido de compra fuera rechazado el cliente, necesitará actualizar la orden registrada y enviarla de nuevo, o cancelar el pedido y reenviarla. Cuando un pedido de compra se volverá a enviar, desaparecerá ** en espera acción del cliente ** de la página.
-   Si el pedido de compra fuera aceptado con turnos, el cliente necesitará actualizar el pedido original y hacia atrás a revisión, o sólo actualizarlo en función de los cambios y confirmelo inmediatamente. En ambos casos, el pedido de compra desaparecerá ** en espera acción del cliente ** de la página.
-   Si el pedido de compra se aceptó y aparece en ** en espera acción del cliente ** la página, se debe a que el pedido de compra automáticamente no se confirmó cuando la aceptación se ha realizado. Está esperando un agente de compras para cambiar el orden a Confirmado. Normalmente, el pedido de compra sería considerado como el contrato entre el cliente y el proveedor tan pronto como el proveedor acepte el pedido. Mover el pedido de compra a la estado confirmado sería una formalidad.

Mediante la selección del pedido de compra, detalles adicionales se producen de la respuesta. Puede ver los detalles de línea y respuesta de cada línea. Las muestra el estado de línea se ha dado que las respuestas de siguientes.

-   Aceptado
-   Rechazadas
-   Aceptado con cambios
-   Sustituido/simple sustituto
-   Dividir en la programación o la línea de la programación

Tenga en cuenta que un indicador muestra ** entregando ** =yes/no, que se usa para indicar que las líneas no se entregarán. Esto podría ser porque la línea se rechazó, o sustituido donde no se espera que las líneas del original se entreguen, o no se espera que una línea que ha estado divide en las líneas múltiples de programación y la línea original se haya entregado como se solicita en el pedido recibida.  

Los cambios realizados en la respuesta de la línea de pedido se muestra, excepto las notas y los datos adjuntos cargados, que puede ver mediante la interfaz web de colaboración del proveedor.

## <a name="open-confirmed-orders"></a>Pedidos confirmadas Abrir
Cuando un pedido de compra es confirmado el cliente, que significa que el pedido de compra se modifican a la estado confirmado, aparecerá en el orden confirmado abierto. Permanecerá en la lista hasta que se registre como recibido por el cliente.


