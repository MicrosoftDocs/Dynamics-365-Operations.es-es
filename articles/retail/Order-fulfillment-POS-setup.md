---
title: "Configuración de cumplimiento de almacén"
description: "Este tema proporciona una visión general de cómo configurar el cumplimiento de los pedidos de almacén."
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: ccff6533257379c0305f7414dd36e17d1c323c21
ms.contentlocale: es-es
ms.lasthandoff: 03/08/2018

---


# <a name="set-up-order-fulfillment-for-stores"></a>Configuración del cumplimiento de pedido para almacenes

[!include[banner](includes/banner.md)]

## <a name="overview"></a>Información general
Muchos minoristas quisieran optimizar el cumplimiento de pedidos habilitando almacenes para atender pedidos. El cumplimiento de pedidos a nivel del almacén puede facilitar las escenarios de sobreabastecimiento para un almacén específico, o puede ser necesario desde un punto de vista logístico en caso de que tenga un almacén de capacidad adicional o se encuentre dentro de una distancia más cercana de envío al cliente. Para dirigir esta necesidad, una operación unificada de cumplimiento de pedido está disponible en el punto de venta.

Los pedidos para el cumplimiento en un almacén específico tienen el almacén de tienda designado en la cabecera o líneas del pedido. 

La operación de cumplimiento en el punto de venta ofrece una sola área de trabajo en el punto de venta que se puede usar para procesar pedidos. Esto incluye todo, desde aceptar el pedido, a marcarlo como enviado o iniciar la recogida del almacén. 

## <a name="set-up-the-order-fulfillment-operation"></a>Configuración de la operación de cumplimiento de pedido

El cumplimiento de pedido, [Operación ID 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), puede usarse para tener acceso al área de trabajo de cumplimiento de pedido del almacén en el punto de venta. 

Siga los pasos de [Agregar la operación a una cuadrícula de botones](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) para especificar que parámetro usar cuando invoque el cumplimiento de pedido en el punto de venta. De forma predeterminada, después de especificar las operaciones de cumplimiento, se selecciona **Todos los pedidos**. Cuando está configurado con este parámetro, la operación mostrará todas las líneas de pedido para cumplimiento en el almacén actual. También está disponible **Pedidos para enviar**, que se puede asignar a un botón y utilizar cuando el usuario solo desea consultar los pedidos que se enviarán fuera del almacén. Finalmente, hay **Pedidos para recogida**. Cuando está invocada en el punto de venta, esto solo muestra los pedidos para recoger en el almacén. Los distintos parámetros se pueden asignar a distintos botones para otorgar al usuario varias maneras para ver el cumplimiento de pedido. 

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Habilitar usuarios para acceder al cumplimiento de pedido en el punto de venta. 

La operación de cumplimiento de pedido no tiene su propio permiso listo para usar, pero en el futuro, los usuarios podrán necesitar el permiso **Permitir recuperar pedido** para invocar la operación desde el punto de venta.

A nivel de almacén, una opción de configuración está disponible para determinar si una línea de pedido se debe aceptar manualmente desde el punto de venta. Si dicha opción de configuración no se establece, las líneas de pedido serán aceptadas de forma predeterminada. Si está activada dicha opción de configuración, los usuarios en el punto de venta necesitarán contar con el permiso **Permitir aceptar pedido** para aceptar pedidos desde el punto de venta. 


### <a name="enable-manual-order-acceptance"></a>Habilitar aceptación manual de pedidos

De manera predeterminada, las líneas de pedido asignadas a un almacén se marcan como **Aceptado**. Esto significa que se asume que se cumplirán desde el almacén asignado y que no estarán sujetas a más asignaciones. En algunos casos, los minoristas pueden querer aceptar pedidos manualmente antes de que se puedan cumplir. Por ejemplo, si un almacén está corto de personal y no puede cumplir pedidos, un encargado de almacén aceptará sólo tantos pedidos para procesar como sienta que se puedan procesar adecuadamente en un día determinado. Hasta que un pedido sea aceptado, puede ser reasignado por back office a otro almacén. De esta manera, la aceptación de pedidos también proporciona una forma de indicar que el pedido se ha confirmado por un almacén y que se cumplirá. 

Las líneas de pedido para la recogida del almacén se marcan como **Pendiente** y no están sujetas a aceptación.

Para activar la aceptación manual de líneas de pedido, desplácese a **Retail** > **Canales** > **Almacenes al por menor** > **Todos los almacenes al por menor**. Seleccione el almacén y haga clic en el identificador del almacén para ver los detalles del almacén. Haga clic en **Editar**. En la ficha desplegable **General**, busque el subtítulo **Cumplimiento del pedido** y modifique **Aceptación manual** de **No** a **Sí**. 

### <a name="enable-reject-order-line-capability"></a>Habilitar la capacidad de rechazar una la línea de pedido

Las líneas de pedido también se pueden rechazar desde el punto de venta. Rechazar una línea de pedido significa que no se completará en dicho almacén y envía de nuevo la línea de pedido para la reasignación a otro almacén. El permiso de rechazo de la línea de pedido se concede con **Permitir el rechazo de pedido** del grupo de permisos de PDV asociado al trabajador. Mientras rechazan una línea, los minoristas pueden ordenar a sus trabajadores que proporcionen el motivo del rechazo. Esto se puede conseguir mediante códigos de información del tipo **Actividad de código de información**, **Cumplimiento del pedido** y asignación del código de información en **Rechazar línea de pedido** en el perfil de funcionalidad asociado al canal. 

>[!Note]
>Solo los códigos de información del tipo **Actividad de código de información** **Cumplimiento del pedido** se pueden asignar a la acción **"Rechazar línea de pedido**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar cambios en la base de datos del canal

Después de que la operación se haya asignado a una cuadrícula de botones, se hayan asignado los permisos apropiados y se haya configurado el canal, los cambios se debe sincronizar a la base de datos de canal. Para ello, vaya a **Retail** > **TI de Retail** > **Programación de distribución**. Seleccione la programación "1090-Registros" para sincronizar la cuadrícula de botones y después haga click en **Ejecutar ahora**. A continuación, sincronice los cambios de los permisos seleccionando "1060-Personal" y, continuación, haga click en **Ejecutar ahora**. A continuación, sincronice los cambios de canal seleccionando "1070-Configuración del canal" y, continuación, haga click en **Ejecutar ahora**. Finalmente, sincronice el código de información que se acaba de crear por motivo del rechazo seleccionando "1110-Configuración global" y hace click en **Ejecutar ahora**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Uso de cumplimiento del pedido en el punto de venta

Abra el punto de venta y seleccione la operación de cumplimiento del pedido. En función de cómo esté configurado, se enumerarán todas las líneas, las líneas de pedido para la recogida o las líneas de pedido para envío. 

### <a name="order-fulfillment-view"></a>Vista de cumplimiento de pedido 

La vista de cumplimiento de pedido enumera las líneas de pedido para el cumplimiento en el almacén y ofrece las siguientes columnas:

  - Número de pedido
  - Código de producto
  - Descripción
  - Cantidad pedida
  - Fecha de entrega solicitada
  - Nombre de cliente
  - Estado de cumplimiento
  
La información adicional para una línea de pedido específica se puede ver si selecciona la línea de pedido y después abre el menú flotante situado justo debajo de la información de usuario/turno registrado que se muestra en el encabezado del punto de venta. Este menú incluye 2 pestañas: una para los detalles de la línea y otro para los detalles del pedido. La pestaña de los detalles de la línea incluye la información siguiente:

  - Cantidad pedida
  - Cantidad restante que se debe enviar/recoger
  - Cantidad seleccionada
  - Cantidad empaquetada
  - Cantidad facturada (ya recogida o enviada)
  - Modo de entrega
  - Dirección de entrega
  
El menú flotante de detalles también tiene una pestaña que proporciona más detalles a nivel del pedido, incluyendo:

  - Nombre de cliente
  - Id. de cliente
  - Número de pedido
  - Total del pedido
  - Saldo de pedido
  
En la parte inferior de la vista de cumplimiento de pedido hay un panel de acciones. Esto contiene todas las acciones que se pueden realizar con una línea de pedido. Si una acción no está disponible en función del estado de una línea, dicha acción no estará disponible. 

De forma predeterminada, los pedidos tendrán estado **Aceptado**. El estado del pedido se puede visualizar como columna en la lista de líneas de pedido. Si la **Aceptación manual** está configurada en el nivel de canal, todas las líneas para enviar se mostrarán como **Pendiente** y deben aceptarse antes de que puedan ser cumplidas. Los pedidos para la recogida de almacén están **Pendiente** de forma predeterminada y no necesitan ser aceptados.

### <a name="order-fulfillment-line-actions"></a>Acciones de la línea de cumplimiento de pedido

**Editar** - Si el estado del pedido es pendiente, se puede editar en el punto de venta. Los pedidos que ya se han seleccionado, se han empaquetado, o se han facturado parcialmente no se pueden editar desde la vista de cumplimiento de pedido.

**Aceptar** - Si la **Aceptación manual** está configurada en el nivel de canal, las líneas primero se deben aceptar antes de que se puedan desplazar en el proceso de cumplimiento de pedido.

**Selección** - La opción de selección admite varias acciones. En primer lugar, **Seleccionado** actualiza el estado de la línea de pedido para que otros en el almacén no intenten seleccionar la misma línea. A continuación, **Imprimir lista de selección** imprime una lista de selección para la línea seleccionada o las líneas y también actualiza el estado a **Seleccionado**. Los formatos de la lista de selección se controlan como parte de formatos de recibo. Para obtener más información sobre cómo configurar formatos de recibo, consulte [Plantillas e impresión de recibos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing). Finalmente, **Marcar como seleccionado** indica que se ha seleccionado la línea. **Marcar comos seleccionado** inicia transacciones de inventario correspondiente en back-office. Las acciones de selección se pueden realizar al mismo tiempo para varias líneas de pedido a través de pedidos y para todos los modos de entrega.

**Rechazar** - Las líneas o las líneas parciales se pueden rechazar. Esto permite que se reasignen desde back-office a otro almacén. Las líneas solo se pueden rechazar si aún no se han seleccionado ni empaquetado. Para rechazar una línea que ya se ha seleccionado o se ha empaquetado, dicha línea se debe quitar o desempaquetar desde back-office. 

**Empaquetar** - La opción de embalaje admite dos acciones: **Imprimir albarán** imprimirá un albarán para las líneas seleccionadas y **Marcar como empaquetado** marcará las líneas como empaquetadas y marcará las líneas como entregadas en back-office. Sólo las líneas de pedido que pertenecen al mismo pedido y tienen el mismo modo de entrega se pueden empaquetar al mismo tiempo. Los formatos de albarán se controlan como parte de formatos de recibo. Para obtener más información sobre cómo configurar formatos de recibo, consulte [Plantillas e impresión de recibos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

**Envíar** - La acción de envío marca las líneas seleccionadas como **Entregado** en back-office. Después de que la línea se haya enviado completamente, no aparecerá en la vista de cumplimiento de pedidos.

**Recogida** - La acción de recogida agregar líneas a la vista de la transacción para la recogida. Si hay otras líneas en el pedido que no se están actualmente siendo recogidas, se agregarán a la vista de la transacción con la cantidad cero. Después de que la línea se haya recogido completamente, no aparecerá en la vista de cumplimiento de pedido. 

### <a name="order-fulfillment-filtering"></a>Filtrado de cumplimiento de pedido

El cumplimiento de pedido en el punto de venta incluye un filtrado para ayudar al usuario a buscar fácilmente lo que necesite. Los filtros se pueden cambiar en el panel de acciones en la parte inferior de la pantalla de **Punto de venta**. De forma predeterminada, un filtro **Tipo de entrega** se aplica, en función de cómo se haya configurado la operación. Si la operación está configurada con el parámetro **Todos los pedidos**, se aplica dicho filtro al acceder al cumplimiento de pedido. Lo mismo aplica a los parámetros **Recogida de almacén** y **Envío desde almacén**. Otros filtros que se pueden aplicar a la vista de cumplimiento de pedido incluye:

  - Número de cliente
  - Nombre de cliente
  - Correo electrónico del cliente
  - Número de pedido
  - Modo de entrega
  - Número de recibo
  - Id. de referencia del canal
  - Número de tienda de origen
  - Estado de línea
  - Fecha de creación
  - Fecha de entrega
  - Fecha de recepción

