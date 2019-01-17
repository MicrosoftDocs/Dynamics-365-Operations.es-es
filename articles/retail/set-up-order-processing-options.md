---
title: Configurar canales de centro de llamadas
description: "Este tema proporciona información relativa a cómo procesar los pedidos para los centros de llamadas mediante el uso de Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 04/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 0bfbb763b8ded2a0ce90b66eb686379b1dc92a6d
ms.contentlocale: es-es
ms.lasthandoff: 01/04/2019

---

# <a name="set-up-call-center-channels"></a>Configurar canales de centro de llamadas

[!include [banner](includes/banner.md)]

Una empresa puede definir varios canales de centro de llamadas en Microsoft Dynamics 365 for Retail. Los canales de centro de llamadas se configuran en **Venta minorista** \> **Canales** \> **Centros de llamadas** \> **Todos los centros de llamadas**, y son específicos de una entidad jurídica.

Cuando se crea un canal nuevo del centro de llamadas, se le asigna sistemáticamente un número de unidad operativa. Puesto que los centros de llamadas se crean como unidades operativas, los usuarios pueden vincular el canal del centro de llamadas a varias funciones de Retail, como selecciones, catálogos y modos de entrega específicos.

Un almacén predeterminado se puede configurar en el canal del centro de llamadas. A continuación, cuando los pedidos de ventas se crean en ese canal, el almacén predeterminado se introduce automáticamente en la cabecera del pedido de ventas, salvo que se haya definido otro almacén en el cliente seleccionado para el pedido de ventas. En ese caso, el almacén del cliente se introduce de forma predeterminada.

Los usuarios deben estar vinculados a un canal del centro de llamadas para utilizar las funcioens del centro de llamadas. Cualquier pedido de ventas que un usuario cree en Retail se vincula automáticamente al canal del centro de llamadas de ese usuario. Actualmente, no puede vincular un único usuario a varios canales del centro de llamadas al mismo tiempo.

También se puede configurar un perfil de notificación por correo electrónico en el canal del centro de llamadas. El perfil define el conjunto de plantillas de correo electrónico que se utiliza cuando se envía un correo electrónico a los clientes que realizan pedidos a través del canal del centro de llamadas. Los desencadenadores de correo electrónico se pueden configurar con eventos del sistema, como la presentación del pedido o el envío del pedido.

Antes de poder procesar correctamente las ventas a través de un canal del centro de llamadas, deben definirse los [métodos de pago](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-payments) y modos de entrega correctos para el canal.

En el nivel del canal del centro de llamadas, puede definir otros valores predeterminados relacionados con las dimensiones financieras que se vincularán a los pedidos creados por ese canal.

## <a name="options-for-order-processing-behavior"></a>Opciones para el comportamiento del procesamiento de pedidos

Tres parámetros en la configuración de un centro de llamadas tienen un efecto importante en las características y funciones disponibles para pedidos de ventas que se crean con dicho centro de llamadas: **Habilitar finalización de pedidos**, **Habilitar venta directa** y **Habilitar control de precios de pedidos**.

### <a name="enable-order-completion"></a>Habilitar finalización de pedidos

La configuración **Habilitar finalización de pedidos** en el canal del centro de llamadas tiene un efecto importante en el flujo del procesamiento de los pedidos de ventas que se introducen para dicho canal. Cuando esta configuración está activada, todos los pedidos de ventas deben someterse a un conjunto de reglas de validación antes de que se puedan confirmar. Ejecute estas reglas seleccionando el botón **Completar** que se agrega en el Panel de acciones de la página del pedido de ventas. Todos los pedidos de ventas que se crean cuando cuando está activada la configuración **Habilitar finalización de pedidos** deben someterse al proceso de finalización de pedidos. Este proceso se aplica la captura de pago y la lógica de validación de pagos. Además de la ejecución de pagos, el proceso de presentación de pedidos puede desencadenar [comprobaciones de fraudes](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts) que configura en el sistema. Los pedidos que no cumplen con las validaciones de pago o fraude se ponen en espera y no se pueden liberar para su posterior procesamiento (como la recogida o el envío) hasta que se resuelva el problema que provocó la retención.

Cuando está activada la configuración **Habilitar finalización de pedidos** para el canal del centro de llamadas, en caso de que se introduzcan artículos de línea en un pedido de ventas y el usuario del canal intente cerrar o abandonar el formulario de pedidos de ventas sin seleccionar primero **Completar**, el sistema aplica el proceso de finalización de pedidos abriendo la página de resumen de pedido de ventas y requiere que el usuario envíe correctamente el pedido. Si el pedido no se puede registrar correctamente junto con el pago, el usuario puede utilizar la funcionalidad de [retenciones de pedidos](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) para poner el pedido en espera. Si el usuario intenta cancelar el pedido, debe cancelarlo correctamente mediante la función Cancelar o la función Eliminar, dependiendo de la función que permita la seguridad del usuario.

Si está activada la configuración **Habilitar finalización de pedidos** para el canal del centro de llamadas, se realizará un seguimiento al campo **Estado de pago** en el pedido. El sistema calcula el **Estado de pago** cuando se envía el pedido de ventas. Solo los pedidos con un estado de pago aprobado pueden desplazarse por el sistema para unos pasos adicionales de procesamiento de pedidos, como la recogida y el envío. Si se rechazan los pagos, aparecerá el indicador **no procesar** en el estado detallado del pedido, esto coloca el pedido en espera hasta que se resuelva el problema de pago.

Además, si está activada la configuración **Habilitar finalización de pedidos**, cuando los usuarios crean pedidos de ventas y están en modo de entrada de artículo de línea, el campo **Origen** estará disponible en el encabezado principal del pedido de ventas. El campo **Origen** se utiliza para capturar un [código fuente del catálogo](https://docs.microsoft.com/dynamics365/unified-operations/retail/call-center-catalogs) en un escenario de venta de marketing directo. Este código puede generar precios y promociones especiales.

Incluso si está desactivada la configuración **Habilitar finalización de pedidos**, los usuarios todavía pueden aplicar un código fuente a un pedido de ventas. No obstante, primero deben abrir los detalles del encabezado del pedido de ventas para acceder al campo **Origen** . En otras palabras, son necesarios algunos clics adicionales. El mismo comportamiento se aplica a funciones como envío completado y pedidos urgentes. Estas funciones están disponibles para todos los pedidos que se creen en el centro de llamadas. Sin embargo, cuando está activada la configuración **Habilitar finalización de pedidos**, los usuarios pueden ver la configuración de estas funciones en el encabezado de ventas mientras están en la vista de entrada de línea. No tienen que explorar en los detalles del encabezado del pedido de ventas para encontrar la configuración y los campos adecuados.

### <a name="enable-direct-selling"></a>Habilitar venta directa

Si está activada la configuración **Habilitar venta directa** para el canal de centro de llamadas, los usuarios pueden aprovecharse de las funciones de venta vertical y venta cruzada de Retail. En este caso, aparecen ventanas emergentes durante la entrada de pedidos y sugieren otros productos que el usuario del centro de llamadas puede ofrecer al cliente. Los productos que se sugieren se basan en el producto que se acabó de pedir en la línea de pedido de ventas. Actualmente, las sugerencias de venta vertical y venta cruzada se configuran en el nivel de artículo en productos o catálogos. Si está desactivada la configuración **Habilitar venta directa** para el canal del centro de llamadas, no aparecen ventanas emergentes durante la entrada de pedidos, incluso si se definió una venta vertical o venta cruzada para un artículo que se está pidiendo.

Cuando está activada la configuración **Habilitar venta directa**, también se activan las funciones de scripts e imágenes de la página de entrada de pedidos de ventas. En este caso, un panel de información está disponible en el lado derecho de la página durante la entrada de pedidos. Este panel puede mostrar scripts relacionados con el proceso genérico de entrada de pedidos, el código fuente del catálogo que se aplicó o los scripts relacionados con los artículos que se están pidiendo. Además, el panel de imágenes puede mostrar una imagen de productos para los artículos que se están pidiendo, en caso de que se haya definido una imagen para el artículo en la configuración del producto.

### <a name="enable-order-price-control"></a>Habilitar control de precios de pedidos

Cuando está activada la configuración **Habilitar control de precios de pedidos**, solo los usuarios autorizados pueden cambiar el precio de venta de un artículo durante la entrada de pedidos. Los cambios deben encontrarse dentro de las tolerancias definidas. Los usuarios que no cuentan con la autorización adecuada deben enviar una solicitud para un cambio de precio en su lugar. La solicitud se procesará a través de flujos de trabajo del sistema para su revisión y aprobación.

## <a name="channel-users"></a>Usuarios de canal

Al definir el canal del centro de llamadas, debe vincular usuarios del canal al centro de llamadas. De lo contrario, el centro de llamadas no se puede utilizar en el sistema. Cuando los usuarios inician sesión en Retail e introducen pedidos de venta o pedidos de devolución en una página relacionada con la entrada de pedidos, su id. de usuario se valida con la configuración del canal del centro de llamadas. Si un usuario se vincula a un canal del centro de llamadas concreto, los pedidos que crea el usuario heredan los rasgos y los valores predeterminados de ese canal.

De forma predeterminada, el indicador **Venta minorista** en el encabezado del pedido de ventas está activado para todos los pedidos que creen los usuarios del centro de llamadas. Los pedidos pueden aprovechar las funciones de precios y promociones ventas específicas para minoristas del sistema.

Los usuarios que no están vinculados a un canal del centro de llamadas utilizan las funciones de entrada de pedidos estándar de Microsoft Dynamics 365 for Finance and Operations. Los pedidos que estos usuarios introducen a través del formulario de entrada de pedidos de ventas no se identificarán sistemáticamente al pedidos de Retail. Además, estos pedidos introducidos por dichos usuarios no estarán sujetos a ninguna regla de procesamiento de finalización de pedidos, lógica de precios al por menor u otras validaciones de pedidos que se pueden definir en la configuración del canal del centro de llamadas o los parámetros del sistema del centro de llamadas.

Una vez que haya terminado de configurar el canal del centro de llamadas y de definir los usuarios del canal, para ayudar a garantizar el comportamiento deseado del sistema, asegúrese de que están definidos todos los parámetros necesarios del centro de llamadas en **Venta minorista** \> **Configuración del canal** \> **Configuración del centro de llamadas** \> **Parámetros del centro de llamadas**. Asegúrese de que también están definidas las secuencias numéricas relacionadas.

