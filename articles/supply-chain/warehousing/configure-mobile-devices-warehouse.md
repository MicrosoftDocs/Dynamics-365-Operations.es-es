---
title: Configurar dispositivos móviles para el trabajo de almacén
description: En este tema se describe cómo configurar los elementos de menú que usan los trabajadores del almacén para trabajar en un dispositivo móvil.
author: MarkusFogelberg
manager: tfehr
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ae7587fc46d2907241a5da3b6329465d77b3555
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383099"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Configurar dispositivos móviles para el trabajo de almacén

[!include [banner](../includes/banner.md)]

En este tema se describe cómo configurar los elementos de menú que usan los trabajadores del almacén para trabajar en un dispositivo móvil.

> [!NOTE]
> Este tema se aplica a las funciones de gestión de almacenes. No se aplica a las funciones de gestión del inventario. Los elementos de menú que aparecen en los menús en un dispositivo móvil del almacén se configuran en la página **Elementos de menú del dispositivo móvil**. Dado que los elementos de menú se pueden colocar en diferentes menús, resulta fácil configurar las estructuras de menú para que solo tipos específicos de trabajo se expongan a usuarios específicos. Puede configurar los elementos de menú para realizar las tareas siguientes:

-   Procese una consulta o realice una actividad, como imprimir una etiqueta, generar matrículas de entidad de almacén, iniciar un pedido de producción o buscar rápidamente información sobre los elementos en una ubicación.
-   Cree el trabajo que se realizará con otro proceso. Por ejemplo, la recepción de un artículo para un pedido de compra puede crear un trabajo de ubicación para otro trabajador.
-   Realice el trabajo que se creó por otro proceso (trabajo existente), como trabajo de ubicación que se creó cuando un artículo se recibió para un pedido de compra.

Para crear un elemento de menú para una actividad o una consulta, establezca el campo **Modo** como **Indirecto**. A continuación, se ofrece una lista de opciones de **Código de actividad** para seleccionar el tipo de consulta o actividad al que corresponde el elemento de menú. Para crear un elemento de menú para generar trabajo del almacén, establezca el campo **Modo** en **Trabajo**. A continuación, aparece una lista de opciones de **Proceso de creación de trabajo**. Para crear un elemento de menú para el trabajo existente del almacén de proceso, establezca el campo **Modo** en **Trabajo** y, a continuación, establezca la opción **Usar trabajo existente** en **Sí**. 

> [!NOTE]
> En función del modo seleccionado para el elemento de menú, y de si el elemento de menú se usa para realizar el trabajo existente, el elemento de menú puede ofrecer otros campos. Para obtener información sobre otras selecciones de campos, consulte la sección “Opciones del elemento de menú adicionales” más adelante en este artículo.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Configurar elementos de menú para las actividades y consultas
Si el campo **Modo** para un elemento de menú se establece en **Indirecto**, puede crear un elemento de menú para realizar una actividad o una consulta general que no cree el trabajo. Entre los ejemplos se incluyen la reimpresión de etiquetas de número de matrícula y una consulta sobre los artículos en una ubicación. En la tabla siguiente se muestran las opciones disponibles.

| Opción                      | Descripción                                                                                                                                                                           |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ninguna                        | Este valor predeterminado no habilita una actividad o una consulta.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Acerca de                       | Vea información acerca del sistema, como el número de versión, la identificación del almacén y el trabajador que ha iniciado sesión actualmente.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Cambiar almacén            | Cambie el almacén al que ha iniciado sesión un trabajador.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Consulta de ubicación            | Ver información sobre todos los artículos y cantidades de una ubicación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Consulta de número de licencia       | Muestra la cantidad de artículos de un número de matrícula y la ubicación del número de matrícula.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Iniciar pedido de producción      | Iniciar un pedido de producción.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Residuo de producción            | Especifique la cantidad de residuos creados durante la producción para cada línea de la lista de materiales (L. MAT.).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Último pallet de producción      | Indique el último pallet de artículos que se ha producido para un pedido de producción y que el estado del pedido de producción debe actualizarse a **Notificado como terminado**. El estado de las materias primas que no se han consumido durante la producción se vuelve a cambiar de **Seleccionado** a **En pedido** y los artículos pueden devolverse al inventario.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Consulta de artículo                | Explore un artículo para determinar dónde se encuentra en el almacén. La consulta devuelve todas las ubicaciones y cantidades para el artículo explorado.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Volver a imprimir etiqueta               | Vuelva a imprimir la etiqueta de matrícula de entidad de almacén.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Creación de matrícula de entidad de almacén         | Cree una matrícula principal combinando varias matrículas en la misma ubicación. Esta opción resulta útil si mueve varias matrículas de entidad de almacén simultáneamente. Después de que se mueva el número de matrícula principal, debe realizar una interrupción del número de matrícula antes de poder seleccionar artículos de cada número de matrícula. <p></p>**Sugerencia**: para mover una matrícula de entidad de almacén, debe usar un dispositivo móvil que está configurado para crear el trabajo para los movimientos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Interrupción de matrícula de entidad de almacén         | Interrumpa una estructura del número de matrícula de manera que pueda seleccionar artículos de las matrícula que se encontraban en la estructura.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Registro de entrada del conductor             | Si está usando Gestión de transporte, registre la llegada de un conductor explorando la identificación de carga de salida, la identificación de la cita o la identificación del envío. Para esta opción, una carga tiene que estar asignada a la cita y el estado de la carga tiene que ser **Cargado**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Registro de salida del conductor            | Registre que un conductor ha completado la cita.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Vaciar caché de secuencia numérica | Elimine números de la secuencia numérica de la caché de la secuencia numérica. Esta actividad la realizará normalmente un administrador del sistema para solucionar los problemas de la memoria caché cuando se utilizan dispositivos móviles.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Cambiar disposición de lote    | Permita que un trabajador especifique un código de disposición de lote para un artículo y un lote. Esta selección actualiza el código de disposición que se especifica para el lote.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Mostrar lista de trabajo abierta      | Muestra una lista de trabajo disponible para un usuario concreto. El usuario puede seleccionar el trabajo para realizar y se le dirige a él. Esta lista está diseñada para verla en dispositivos de tableta que tienen tamaños de pantalla de 7 pulgadas o más. Cuando se selecciona esta opción, están disponibles los elementos de menú **Editar consulta** y **Lista de campos**. La página **Editar la consulta** permite configurar los criterios para el trabajo que aparece en la lista. La página **Lista de campos** permite seleccionar los campos que aparecen en la lista de trabajo. Por ejemplo, puede reducir el número de campos que aparecen para que el usuario pueda seleccionar con más rapidez el elemento de trabajo más adecuado. En la ficha desplegable **General**, en el campo **Registros por página**, también puede seleccionar cuántos registros se muestran por página. Si selecciona la opción **Permitir a los usuarios filtrar por tipo de transacción**, la lista de trabajos incluirá un control **Filtrar trabajo** que el usuario puede usar para filtrar por tipo de transacción. En la lista de trabajos, los usuarios solo verán aquellos trabajos para los que tienen permiso de acceso. Debe asegurarse de que esos usuarios tienen permiso para uno o más elementos de menú dirigidos al usuario que admiten los tipos de clase de trabajo específicos a los que deben poder tener acceso. Los permisos se verificarán cuando un usuario intente realizar el trabajo desde la lista. |

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Configurar elementos de menú para crear trabajo para otro trabajador o proceso
Puede configurar un elemento de menú que crea trabajo para otro trabajador tras realizar una acción inicial en el dispositivo móvil. Por ejemplo, cuando un trabajador usa un dispositivo móvil para recibir un artículo, el trabajo de ubicación se crea para otro trabajador. Para configurar un elemento de menú que crea el trabajo, en la página **Elementos de menú del dispositivo móvil**, en el campo **Modo**, seleccione **Trabajo**. En la tabla siguiente, las opciones del campo **Proceso de creación de trabajo** están organizadas por el tipo de pedido de trabajo.

<table>
<tbody>
<tr>
<th>Tipo de pedido de trabajo</th>
<th>Opción</th>
<th>Descripción</th>
</tr>
<tr>
<td rowspan="8">Pedido de compra</td>
<td>Recepción de línea del pedido de compra</td>
<td>Registre la recepción de una cantidad de un artículo mediante el número de pedido de compra y el número de la línea de pedido de compra y cree trabajo de ubicación para otro trabajador.</td>
</tr>
<tr>
<td>Recepción de línea del pedido de compra y ubicación</td>
<td>Registre la recepción de una cantidad de un artículo mediante el número de pedido de compra y el número de la línea de pedido de compra y ubique los artículos. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td>Recepción de artículo del pedido de compra</td>
<td>Registre la recepción de una cantidad de un artículo para un pedido de compra mediante el número de pedido de compra y el número de artículo, y cree trabajo de ubicación para otro trabajador.</td>
</tr>
<tr>
<td>Recepción de artículo del pedido de compra y ubicación</td>
<td>Registre la recepción de una cantidad de un artículo para el pedido de compra al registrar el número del pedido de compra y ubicar el artículo. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td>Recepción de matrícula de entidad de almacén</td>
<td>Reciba un aviso de envío por adelantado (ASN) entrante mediante la identificación de matrícula de entidad de almacén.</td>
</tr>
<tr>
<td>Recepción de matrícula de entidad de almacén y ubicación</td>
<td>Reciba y aparte un aviso de envío por adelantado (ASN) entrante mediante la identificación de matrícula de entidad de almacén.</td>
</tr>
<tr>
<td>Recepción de artículo de carga</td>
<td>Registre la recepción de una cantidad para una carga mediante la identificación de carga y cree el trabajo de ubicación para otro trabajador. El número de artículo y las dimensiones del producto coinciden con la recepción de las líneas de pedido de compra.</td>
</tr>
<tr>
<td>Recepción de artículo de carga y ubicación</td>
<td>Registre la recepción de una carga mediante la identificación de carga y ubique los artículos. El número de artículo y las dimensiones del producto coinciden con la recepción de las líneas de pedido de compra. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td rowspan="2">Pedido de devolución</td>
<td>Recepción de pedido de devolución</td>
<td>Registre la recepción de una cantidad de un artículo registrando el número RMA y cree el trabajo de ubicación para otro trabajador.</td>
</tr>
<tr>
<td>Recepción de pedido de devolución y ubicación</td>
<td>Registre la recepción de una cantidad de un artículo registrando el número RMA y ubique los artículos. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td rowspan="6">Orden de transferencia</td>
<td>Recepción de artículo de pedido de transferencia</td>
<td>Registre la recepción de una cantidad de un artículo y cree el trabajo de ubicación para otro trabajador.

<strong>Nota</strong>: use esta opción solo si los artículos se han enviado desde un almacén que no está habilitado para procesos de gestión de almacenes.</td>
</tr>
<tr>
<td>Recepción de artículo del pedido de transferencia y ubicación</td>
<td>Registre la recepción de una cantidad de un artículo y ubique los artículos. El mismo trabajador realiza ambas acciones.

<strong>Nota</strong>: use esta opción solo si los artículos se han enviado desde un almacén que no está habilitado para procesos de gestión de almacenes.</td>
</tr>
<tr>
<td>Recepción de línea de pedido de transferencia</td>
<td>Registre la recepción de una cantidad de un artículo y cree el trabajo de ubicación para otro trabajador.</td>
</tr>
<tr>
<td>Recepción de línea del pedido de transferencia y ubicación</td>
<td>Registre la recepción de una cantidad de un artículo y ubique los artículos. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td>Recepción de matrícula de entidad de almacén</td>
<td>Reciba un aviso de envío por adelantado (ASN) entrante mediante la identificación de matrícula de entidad de almacén.</td>
</tr>
<tr>
<td>Recepción de matrícula de entidad de almacén y ubicación</td>
<td>Reciba y aparte un aviso de envío por adelantado (ASN) entrante mediante la identificación de matrícula de entidad de almacén.</td>
</tr>
<tr>
<td rowspan="4">Producción</td>
<td>Notificar como terminado</td>
<td>Registre una cantidad de un artículo terminado que se ha terminado para una producción y cree trabajo de ubicación para otro trabajador. La cantidad puede ser un poco o toda la cantidad que se planificó para la producción.</td>
</tr>
<tr>
<td>Notificar como terminado y poner en ubicación</td>
<td>Registre una cantidad de un artículo terminado que se ha terminado para una producción y ubique los elementos. La cantidad puede ser un poco o toda la cantidad que se planificó para la producción. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Indique que un kanban se ha completado y cree trabajo de ubicación para otro trabajador.</td>
</tr>
<tr>
<td>Ubicación de kanban</td>
<td>Indique que un kanban se ha completado y ubique los artículos. El mismo trabajador realiza ambas acciones.</td>
</tr>
<tr>
<td rowspan="5">Inventario</td>
<td>Movimiento</td>
<td>Registrar que los artículos se han movido desde una ubicación a otra. El trabajador especifica la ubicación desde la que los artículos se mueven y hasta donde se mueven.</td>
</tr>
<tr>
<td>Cuarentena</td>
<td>Cambiar el estado del inventario disponible para que una matrícula de entidad de almacén o una ubicación pasen al estado no disponible los artículos de inventario dañados o que faltan.</td>
</tr>
<tr>
<td>Plantilla de movimiento por</td>
<td>Mover artículos desde una ubicación a otra de manera semiautomatizada. El trabajador selecciona la ubicación desde la que mover los artículos y el sistema usa la directiva de ubicación para determinar dónde mover los artículos.</td>
</tr>
<tr>
<td>Transferencia de almacén</td>
<td>Registrar que los artículos se han transmitido desde un almacén a otro. Esta opción requiere que el trabajador esté autorizado a llevar a cabo el trabajo en ambos almacenes.

<strong>Nota</strong>: este elemento de menú requiere un diario de transferencia de inventario predeterminado donde el campo <strong>Crear asiento</strong> está establecido en <strong>Registrar</strong>.</td>
</tr>
<tr>
<td>Carga de matrícula de entidad de almacén</td>
<td>Use esta opción cuando configure su almacén por primera vez. Explore todas las matrículas de entidad de almacén en todas las ubicaciones del almacén. Las ubicaciones deben controlarse por matrículas de entidad de almacén. No puede usar esta opción si <strong>Número de serie</strong> o <strong>Número de lote</strong> se muestran encima de <strong>Ubicación</strong> en la jerarquía de reservas de inventario.</td>
</tr>
<tr>
<td rowspan="3">Recuento cíclico</td>
<td>Entrada de ajuste</td>
<td>Aumente la cantidad de artículos de inventario. Especifique la ubicación, la matrícula de entidad de almacén, el artículo, la cantidad, la unidad de medida y el estado.</td>
</tr>
<tr>
<td>Salida de ajuste</td>
<td>Reduzca la cantidad de artículos de inventario. Especifique la ubicación, la matrícula de entidad de almacén, el artículo, la cantidad, la unidad de medida y el estado del inventario.</td>
</tr>
<tr>
<td>Recuento cíclicos puntual</td>
<td>Inicie una cuenta de una ubicación. El trabajador debe contar todos los artículos en la ubicación. Cuando el resultado de una cuenta es inferior a la cantidad planificada, la cantidad que falta se considera una pérdida.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Configurar elementos de menú para el trabajo existente del proceso
Además de los elementos de menú de la configuración para crear el trabajo del almacén, puede configurar los elementos de menú para procesar el trabajo que ya se ha creado. Defina el campo **Modo** en **Trabajo** y seleccione la opción **Usar trabajo existente**. A continuación, algunas opciones adicionales están disponibles en la ficha **General**. Puede controlar el acceso al elemento de menú si asigna una o varias clases de trabajo en la ficha desplegable **Clase de trabajo**. Las clases de trabajo definen el trabajo que el elemento de menú puede procesar. La clase de trabajo también se puede usar para conceder acceso a los roles de usuario específicos o al proceso independiente para distintos tipos de operaciones. En la tabla siguiente se describen las opciones disponibles. La opción se puede elegir en el campo **Dirigido por** en la página **Elementos de menú del dispositivo móvil**. 

<table>




<thead>
<tr class="header">
<th>Opción</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ninguno</td>
<td>Este valor predeterminado no procesa trabajo.</td>
</tr>
<tr class="even">
<td>Dirigido por el sistema</td>
<td>Supply Chain Management controla el tipo de trabajo asignado a un trabajador y el pedido en el que el trabajador realiza el trabajo. Cuando selecciona esta opción, puede hacer clic en <strong>Trabajo dirigido por el sistema</strong>, en el panel Acciones para abrir la página <strong>Orden de clasificación dirigido por el sistema</strong>, donde puede configurar los criterios de clasificación para el trabajo. Los criterios de ordenación controlan el orden en que el trabajador realiza el trabajo. Puede agregar tantos criterios como sea necesario.</td>
</tr>
<tr class="odd">
<td>Dirigido por el usuario</td>
<td>El trabajador selecciona el trabajo para realizar y el orden en el que desea realizarlo.</td>
</tr>
<tr class="even">
<td>Agrupación de usuarios</td>
<td>El trabajador agrupa trabajo manualmente. Esta opción es útil cuando, por ejemplo, un trabajador puede seleccionar varios artículos al mismo tiempo en una ubicación. Después de que el trabajador haya terminado de seleccionar todos los artículos requeridos, puede ubicar los artículos.</td>
</tr>
<tr class="odd">
<td>Agrupamiento del sistema</td>
<td>Supply Chain Management agrupa trabajo para el trabajador en función de un campo especificado. Por ejemplo, el trabajo de picking se agrupa cuando un trabajador analiza una identificación de envío, la identificación de carga o cualquier valor que pueda vincular cada unidad de trabajo. Si selecciona esta opción, los siguientes campos son necesarios:
<ul>
<li><strong>Campo de agrupamiento del sistema</strong>: seleccione el campo que el trabajador analizará para agrupar el trabajo.</li>
<li><strong>Etiqueta de agrupamiento del sistema</strong>: especifique el texto para indicar al trabajador qué debe escanear para agrupar el trabajo.</li>
</ul></td>
</tr>
<tr class="even">
<td>Dirigido por el usuario validado</td>
<td>El trabajador selecciona el trabajo para realizar cuando el trabajo se asocia a una entidad mayor, como una carga o un envío. El trabajador determina el orden en que los artículos son seleccionados. Si selecciona esta opción, los siguientes campos son necesarios:
<ul>
<li><strong>Campo Dirigido por el usuario validado</strong>: seleccione el campo que el trabajador analizará para agrupar el trabajo.</li>
<li><strong>Etiqueta de dirigido por el usuario validado</strong>: especifique el texto que indica al trabajador qué escanear cuando el sistema agrupe el trabajo de picking.</li>
</ul>
Esta opción es útil, por ejemplo, cuando varios pallets se almacenan provisionalmente para una carga. Si selecciona <strong>LoadId</strong> en el campo <strong>Dirigido por el usuario validado</strong>, el trabajador puede seleccionar cualquier pallet que esté asociado a la carga. El trabajador recibe un mensaje de error si escanea un artículo que no está asociado con la carga.</td>
</tr>
<tr class="odd">
<td>Picking en clúster</td>
<td>El trabajador agrupa trabajo en clústeres. Los clústeres permiten a los trabajadores seleccionar artículos de una única ubicación para varios pedidos de trabajo al mismo tiempo.</td>
</tr>
<tr class="even">
<td>Agrupación de recuentos cíclicos</td>
<td>El trabajador selecciona una zona, un grupo de trabajo o una ubicación y Supply Chain Management asigna el trabajo basándose en la selección. Si selecciona esta opción, puede hacer clic en <strong>Recuento cíclico</strong> en el panel Acciones para especificar información adicional para mostrar y también puede especificar el número de veces que el trabajador debe repetir el recuento si se encuentra una diferencia.</td>
</tr>
 <tr class="odd">
<td>Carga de transporte</td>
<td>Esta función permite que varios trabajadores de almacén carguen el inventario desde la misma carga o diferentes cargas en el mismo camión, con cargas que se envían completamente o parcialmente.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Opciones del elemento de menú adicionales
Las opciones adicionales de los elementos de menú estarán disponibles en la página **Elementos de menú del dispositivo móvil**. Las opciones varían, en función del proceso para el que está configurando el elemento de menú. 

La siguiente tabla describe estas opciones.

<table>




<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Permitir división del trabajo</td>
<td>Active esta opción para permitir a los usuarios configurar artículos de un pedido de trabajo en más de una matrícula de entidad de almacén de destino. Esta opción resulta útil, por ejemplo, cuando una matrícula de entidad de almacén de destino está llena y el trabajador debe agregar los artículos restantes a otra matrícula de entidad de almacén. El trabajador puede hacer clic en <strong>Completo</strong> para indicar que el número de matrícula está lleno y dejar de recibir trabajo de picking para el mismo. La ubicación de colocación para los artículos seleccionados se muestra a continuación y el trabajo de picking que ya se ha completado se trasladará a un pedido de trabajo nuevo. El trabajo de picking restante para el número de matrícula de destino permanece en el pedido de trabajo original.</td>
</tr>
<tr class="even">
<td>Anclaje</td>
<td>Active esta opción para permitir a los trabajadores especificar una ubicación que sustituya la ubicación provisional o de carga sugerida. Todo el trabajo de ubicación restante se dirige a la nueva ubicación. Esta opción es útil, por ejemplo, cuando un trabajador debe colocar los artículos para el pedido 1 en una ubicación provisional del muelle 1, pero no puede porque una carga anterior no ha despejado la ubicación. En lugar de esperar a que la ubicación provisional del muelle 1 esté disponible, el trabajador puede decidir usar la ubicación provisional para el muelle 2. En este caso, el trabajador sobrescribe la ubicación provisional sugerida. La ubicación de colocación para todos los artículos restantes del pedido de trabajo se actualiza a la ubicación provisional del muelle 2. Si selecciona esta opción, debe definir el campo <strong>Anclar por</strong>.</td>
</tr>
<tr class="odd">
<td>Anclar por</td>
<td>Si está usando el anclaje, debe especificar si desea anclar por envío o por carga.</td>
</tr>
<tr class="even">
<td>Id. de plantilla de auditoría</td>
<td>Seleccione la plantilla de auditoría del trabajo que interrumpirá el proceso de trabajo de este elemento de menú para que se pueda realizar otra operación. Por ejemplo, si este elemento de menú es para trabajo de entrada, la plantilla de auditoría puede requerir que el trabajador compruebe la temperatura del contenedor de entrega. El punto en el que se interrumpe el proceso se especifica en la plantilla de auditoría. Este punto puede ser, por ejemplo, cuando el trabajo se inicia o se completa, o cuando cambia de estado.</td>
</tr>
<tr class="odd">
<td>Id. de perfil de clúster</td>
<td>Seleccione el perfil del clúster para usar para el picking de clústeres. El perfil del clúster incluye ajustes como, por ejemplo, si desea crear automáticamente clústeres, los nombres de puestos y el número de unidades de trabajo que se pueden asignar, cuándo dividir los clústeres en unidades individuales y si la comprobación es necesaria. Este campo solo está disponible si se selecciona el <strong>Picking en clúster</strong> en el campo <strong>Dirigido por</strong>.</td>
</tr>
<tr class="even">
<td>Contar primero el total de la cantidad de artículos</td>
<td>Seleccione esta opción para requerir que un trabajador cuente la cantidad total primero durante un recuento. Si se encuentra una diferencia, el trabajador debe proporcionar información adicional, como la matrícula de entidad de almacén, el número de lote y los números de serie.</td>
</tr>
<tr class="odd">
<td>Crear movimiento</td>
<td>Active esta opción para permitir a un trabajador crear el trabajo para un movimiento, pero sin requerir que el trabajador lleve a cabo el trabajo inmediatamente. Esta opción resulta útil, por ejemplo, si una inspección de calidad se ha completado y el inspector desea que el artículo se- mueva del área de inspección de calidad.</td>
</tr>
<tr class="even">
<td>Código de directiva</td>
<td>Para usar una directiva específica de la ubicación, seleccione el código de directiva que está asociado a la directiva de la ubicación. Este campo está disponible cuando se crea el trabajo y el proceso de creación del trabajo es <strong>Plantilla de movimiento</strong>.</td>
</tr>
<tr class="odd">
<td>Deshabilitar umbrales de recuento cíclico</td>
<td>Active esta opción para omitir los umbrales de recuento cíclico. Si activa esta opción, el trabajo de recuento cíclico no se crea cuando se sobrepasen los valores de umbral.</td>
</tr>
<tr class="even">
<td>Mostrar código de disposición de lote</td>
<td>Active esta opción para visualizar los códigos de disposición de lote. Por ejemplo, puede mostrar los códigos de disposición de lote cuando recibe un lote devuelto. Después, los trabajadores pueden evaluar el estado o la calidad de un lote, y seleccionar el código apropiado. Las reglas del código de disposición de lote determinan si el lote estará disponible para otros procesos de almacén. Si no selecciona esta opción, se utiliza uno de los códigos de disposición de lotes siguientes:
<ul>
<li>Si recibe un nuevo número de lote, se usa el código de disposición de lote predeterminado que se especifica en el grupo de modelos de artículo.</li>
<li>Se usa el código de disposición de lote que ya está asignado al lote.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Mostrar código de disposición</td>
<td>Active esta opción para visualizar los códigos de disposición. Por ejemplo, puede mostrar los códigos de disposición cuando recibe artículos devueltos. Después, los trabajadores pueden evaluar el estado o la calidad de los artículos, y seleccionar el código apropiado. Las reglas del código de disposición determinan si los artículos estarán disponibles para otros procesos de almacén.</td>
</tr>
<tr class="even">
<td>Mostrar estado de inventario</td>
<td>Active esta opción para visualizar el estado de los artículos en el inventario. Esta opción solo está disponible para todos los elementos de menú que usan el trabajo existente, excepto el recuento de ciclo.</td>
</tr>
<tr class="odd">
<td>Mostrar resumen de la pantalla de picking</td>
<td>Seleccione esta opción para mostrar un resumen del trabajo de picking para el pedido de trabajo seleccionado. Se muestra el resumen hasta que la primera línea del trabajo se procesa para el pedido de trabajo.</td>
</tr>
<tr class="even">
<td>Generar matrícula de entidad de almacén</td>
<td>Active esta opción para generar una matrícula de entidad de almacén única basada en la selección de la secuencia numérica. Por ejemplo, puede generar una matrícula de entidad de almacén para los artículos recibidos para los pedidos de compra.</td>
</tr>
<tr class="odd">
<td>Ubicaciones en grupo</td>
<td>Seleccione esta opción para agrupar el trabajo de ubicación. Esta opción está disponible cuando el trabajo fue agrupado por el trabajador o por Supply Chain Management. Cuando el trabajador haya acabado todo el trabajo de picking en el grupo, se creará trabajo de traslado para el mismo grupo.</td>
</tr>
<tr class="even">
<td>Tipos de ajuste de inventario</td>
<td>Seleccione el tipo de ajuste de inventario que determina el diario de recuento de inventario que se usa para registrar el ajuste, y si desea quitar las reservas. Este campo solo está disponible para el proceso de creación de trabajo <strong>Ajuste dentro</strong> o <strong>Ajuste fuera</strong>.</td>
</tr>
<tr class="odd">
<td>Anular número de lote</td>
<td>Active esta opción para permitir que los trabajadores que notifican una cantidad como terminada para un pedido de producción especifiquen un número de lote que difiera de número de lote asignado al pedido de producción.</td>
</tr>
<tr class="even">
<td>Anular matrícula de entidad de almacén de destino</td>
<td>Active esta opción para permitir que los trabajadores especifiquen una matrícula de entidad de almacén de destino diferente de la matrícula de entidad de almacén de destino sugerida. Use esta opción cuando el primer picking de un pedido de trabajo sea para la cantidad total de un artículo de una matrícula de entidad de almacén. Esta opción resulta útil, por ejemplo, cuando se reutiliza un pallet.</td>
</tr>
<tr class="odd">
<td>Seleccionar y empaquetar</td>
<td>Active esta opción para permitir a los trabajadores que combinen el trabajo de un pedido de ventas o que lo carguen en una sola unidad de trabajo. Un trabajador puede realizar el trabajo solo para el pedido de ventas o de carga. Esta opción resulta útil, por ejemplo, si debe aumentar una cantidad de un pedido de ventas después de que la carga, el envío y el trabajo se hayan creado para el pedido de ventas. Esta opción solo está disponible cuando el elemento de menú usa el trabajo existente, y el trabajo está dirigido por parte del usuario o el sistema.</td>
</tr>
<tr class="even">
<td>Seleccionar lote más antiguo</td>
<td>Indique si el trabajador debe seleccionar primero el lote más antiguo de una ubicación. Están disponibles las siguientes opciones:
<ul>
<li><strong>Ninguno</strong>: el trabajador puede seleccionar cualquier lote en la ubicación. El trabajador no recibirá ningún mensaje.</li>
<li><strong>Advertencia</strong>: el trabajador puede seleccionar cualquier lote en la ubicación, pero aparecerá un mensaje de advertencia si un lote no es el más antiguo.</li>
<li><strong>Forzar</strong>: el trabajador debe seleccionar el lote más antiguo de la ubicación. El trabajador recibe un mensaje de error si un lote no es el más antiguo. <strong>Nota</strong>: esta opción solo es relevante si <strong>Número de lote</strong> es inferior a <strong>Ubicación</strong> en la jerarquía de reserva que se asigna al artículo.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Imprimir etiqueta</td>
<td>Active esta opción para permitir a los trabajadores imprimir etiquetas de matrícula de entidad de almacén.</td>
</tr>
<tr class="even">
<td>Campo de agrupamiento del sistema</td>
<td>Seleccione el campo que determinará cómo Supply Chain Management agrupará el trabajo de picking para los trabajadores. Por ejemplo, si selecciona el campo <strong>ShipmentId</strong>, el trabajador explorará la identificación del envío para agrupar el trabajo de picking. Todo el trabajo para el envío se asigna al trabajador. Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado. Debe escribir texto también en el campo <strong>Etiqueta de agrupamiento del sistema</strong> para indicar al trabajador qué debe escanear.</td>
</tr>
<tr class="odd">
<td>Etiqueta de agrupamiento del sistema</td>
<td>Especifique el texto que indicará al trabajador sobre qué escanear cuando Supply Chain Management agrupa el trabajo de picking. Por ejemplo, si está usando el campo <strong>ShipmentId</strong> para agrupar el trabajo de picking por envíos, puede especificar <strong>Id. del envío</strong> en el campo. Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado. También debe seleccionar el campo por el que desea agrupar en <strong>Campo de agrupamiento del sistema</strong>.</td>
</tr>
<tr class="even">
<td>Usar datos predeterminados</td>
<td>Active esta opción para habilitar el botón <strong>Datos predeterminados</strong> del panel Acciones, donde puede seleccionar campos para mostrar los datos que un trabajador necesita normalmente en su trabajo diario. Esta opción resulta útil, por ejemplo, si un trabajador a menudo selecciona artículos de la misma ubicación. Puede seleccionar el campo <strong>Desde ubicación</strong> para mostrar la ubicación de forma predeterminada.</td>
</tr>
<tr class="odd">
<td>Campo Dirigido por el usuario validado</td>
<td>Seleccione el campo que analizará el trabajador para agrupar el trabajo. Por ejemplo, si selecciona <strong>LoadId</strong>, un trabajador puede seleccionar cualquier trabajo asociado con una carga seleccionada. Debe escribir texto también en el campo <strong>Etiqueta de dirigido por el usuario validado</strong> para indicar al trabajador qué debe escanear.</td>
</tr>
<tr class="even">
<td>Etiqueta de dirigido por el usuario validado</td>
<td>Especifique el texto que indicará al trabajador sobre qué escanear cuando el trabajo de picking se agrupe por un campo dirigido por el usuario validado. Por ejemplo, si está usando el campo <strong>LoadId</strong> para agrupar el trabajo de picking para una carga, puede especificar la <strong>Identificación de carga</strong> en el campo.</td>
</tr>
<tr class="odd">
<td>Código de plantilla de trabajo</td>
<td>Seleccione la plantilla de trabajo que creará el trabajo de un proceso. Por ejemplo, si recibe un artículo para un pedido de compra, el trabajo de ubicación se generará en función de la plantilla de trabajo. Si no selecciona una plantilla de trabajo, Supply Chain Management asignará una plantilla basada en criterios de consulta. Para obtener más información sobre plantillas de trabajo, vea <a href="control-warehouse-location-directives.md">Controlar el trabajo de almacén con plantillas de trabajo y directivas de ubicación</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Requerir a los trabajadores confirmar el producto, la ubicación o la cantidad cuando seleccionan artículos
Puede configurar las confirmaciones de trabajo que requieren que un trabajador use un dispositivo móvil para registrar la ubicación o la cantidad cuando realiza el trabajo en el almacén. Las confirmaciones de trabajo ayudan a garantizar que el trabajador esté en la ubicación correcta o que está manejando la cantidad correcta de artículos. También puede habilitar Supply Chain Management para confirmar automáticamente el registro del trabajador. Si permite la confirmación automática, no puede requerir también las confirmaciones para la ubicación o la cantidad. Las confirmaciones de trabajo también incluyen los productos y las variantes de producto. Además, puede registrar confirmaciones explorando un código de barras. Para confirmar los productos y las variantes de producto, debe especificar una identificación del producto o la variante del producto. Este identificador puede ser un id. del producto, un id. de búsqueda del producto, un id. externo, GTIN o un código de barras. Tras escribir la identificación o explorar el código de barras, las dimensiones para la variante del producto se muestran en el dispositivo móvil. 

La siguiente tabla describe los distintos tipos de trabajo con los que puede usar confirmaciones de trabajo.

| Opción                 | Descripción                                                                |
|------------------------|----------------------------------------------------------------------------|
| Seleccionar                   | Requiere confirmación al seleccionar los artículos.                                |
| Colocar                    | Requiere confirmación al colocar los artículos en una ubicación.                     |
| Recuento               | Requiere confirmación durante el recuento de ciclo.                                |
| Ajustes            | Requiere confirmación al ajustar las cantidades de inventario.               |
| Personalizado                 | Requiere la confirmación del trabajo personalizado.                                      |
| Cuarentena             | Requiere confirmación al mover los artículos en cuarentena.                   |
| Creación de matrículas de entidad de almacén | Requiere confirmación al consolidar los artículos para crear una matrícula de entidad de almacén. |
| Imprimir                  | Requiere confirmación al imprimir etiquetas de matrícula de entidad de almacén.                |
| Cambio de estado          | Requiere confirmación al cambiar el estado de inventario.              |

**Nota**: puede exigir la confirmación del producto solo para los tipos de trabajo de picking y ubicación.

<a name="additional-resources"></a>Recursos adicionales
--------

[Configurar un elemento de menú del dispositivo móvil para completar trabajo del tipo pedido de compra](tasks/set-up-mobile-device-menu.md)

[Configurar un elemento de menú del dispositivo móvil para registrar los artículos recibidos](tasks/set-up-mobile-device-menu-item-register-received-items.md)

[Estados de inventario](../inventory/inventory-statuses.md)


