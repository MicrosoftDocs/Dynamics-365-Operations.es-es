---
title: Configuración y trabajo con alertas de fraudes de centro de asistencia telefónica
description: En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos. También puede definir códigos específicos que se usan para poner en espera los pedidos sospechosos automática o manualmente.
author: josaw1
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8334b46f7e943e888c3a4db7580eeca30d49ad39
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793978"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Configuración y trabajo con alertas de fraudes de centro de asistencia telefónica

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar criterios y reglas para poner en espera pedidos de ventas potencialmente fraudulentos para revisión adicional. La función de comprobación de fraudes se usa para determinar la validez de la información en un pedido de ventas. Si la información del pedido de ventas parece ser cuestionable en función de los criterios y las reglas contra el fraude de una organización, el pedido puede ser puesto en espera para una revisión adicional. En este caso, el pedido no se puede liberar al almacén para continuar procesándose hasta que no se haya borrado el bloqueo.

> [!NOTE]
> Esta función solo se puede usar con el procesamiento de pedidos de ventas del canal de centro de llamadas de Commerce.

## <a name="turning-on-the-fraud-check-feature"></a>Activación de la función de comprobación de fraudes

Para usar la función de comprobación de fraudes, debe establecer la opción **Realización de pedidos de permiso** en el canal en **Sí** cuando el canal del centro de llamadas está [definido](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-order-processing-options). Cuando está activada la finalización del pedido, los usuarios del centro de asistencia telefónica deben seleccionar **Completado** en la página del pedido de ventas para todos los pedidos de ventas que se creen. La acción completado hace que la página **Resumen de pedido de ventas** se abra. Una vez que los usuarios especifiquen los datos de pago requeridos en la página **Resumen de pedido de ventas**, seleccionan **Enviar** para finalizar el pedido. Cuando se envía el pedido, se activa la función de comprobación de fraudes y las reglas que están activas en el sistema se validan automáticamente.

Los usuarios de centro de asistencia telefónica también pueden poner en espera manualmente los pedidos de ventas para que se revisen posibles fraudes antes de seleccionar **Enviar**. Para poner manualmente un pedido de ventas en espera, en la página **Resumen de pedido de ventas**, seleccione **En espera** \> **Retención manual por fraude**. A continuación se le pedirá que escriba un comentario para explicar el motivo de poner pedido en espera. Este comentario aparecerá en el banco de trabajo [bloqueos del pedido](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) para proporcionar contexto al usuario que revisa los pedidos que están en espera para determinar si el pedido debe liberarse.

Además de configurar la opción **Habilitar finalización de pedidos** en el canal, debe configurar la función de comprobación de fraudes en los parámetros del centro de llamadas. Vaya a **Retail y Commerce** \> **Configuración del canal** \> **Configuración de centro de llamadas** \> **Parámetros de centro de llamadas**. En la página **Parámetros de centro de llamadas**, en la pestaña **Esperas**, establezca la opción **Comprobación de fraudes** en **Sí**.

En la pestaña **Esperas**, también deberá definir los [códigos de bloqueo](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) que se aplicarán a un pedido que se haya puesto en espera manualmente o automáticamente para revisar los posibles fraudes. Defina los códigos de bloqueo en los campos **Código de retención manual por fraude** y **Código de retención por fraude**. Es posible que encuentre útil crear dos códigos exclusivos del bloqueo, de modo que los usuarios que trabajan en el banco de trabajo de los bloqueos pueda filtrar y distinguir fácilmente los bloqueos automáticos de los bloqueos manuales.

Para que la función de comprobación de fraudes funcione de manera eficaz, debe establecer el campo **Puntuación mínima**. Cada criterio y regla de fraude que se define en el sistema tiene una puntuación. Cuando un pedido de ventas se comprueba para detectar la existencia de coincidencias de fraude, si se encuentran una o más coincidencias, las puntuaciones se agregan conjuntamente para dar al pedido una puntuación total por fraude. Si la puntuación total para fraude de un pedido supera el valor del campo **Puntuación mínima**, el pedido se pone en espera automáticamenta. Puede usar opcionalmente los demás campos relacionados con la puntuación-en la pestaña **Esperas** para definir la puntuación de correo electrónico, la puntuación del teléfono, la puntuación del código postal, y la puntuación extendida del código postal. Si no especifica una puntuación de alguno de estos criterios estáticos de fraude cuando los define en la página **Datos de fraude estáticos**, el sistema los puntuará usando las puntuaciones predeterminadas que especifique en la pestaña **Esperas** de la página **Parámetros de centro de asistencia telefónica**.

Finalmente, use el campo **Tipo de comentarios de fraudes** para especificar el tipo de documento que se debe usar cuando los usuarios especifican comentarios cuando configuran manualmente un pedido en espera para la detección de fraudes. Normalmente, este campo se establece en **Nota**.

## <a name="defining-fraud-criteria-and-rules"></a>Definición de criterios y de reglas de fraudes

El sistema hace referencia a dos tipos de criterios de fraudes para determinar si un pedido se debe mantener en espera para la revisión de fraudes:

- **Datos de fraudes estáticos** usa un valor específico, como un número de teléfono que se ha puesto en una lista de números bloqueado o una dirección de correo electrónico que se ha marcado porque se sabe que ha sido utilizada para transacciones fraudulentas anteriores. Para configurar datos estáticos de fraudes, vaya **Retail y Commerce** \> **Configuración del canal** \> **Configuración de centro de asistencia telefónica** \> **Fraude** \> **Datos de fraudes estáticos**. En la página **Datos de fraudes estáticos**, puede agregar criterios de fraudes manualmente o a través de la importación de datos. Las puntuaciones se vinculan a la información fraudulenta. Si está activada la función de comprobación de fraudes, cada pedido de ventas especificado se comparará con los datos estáticos. Si los datos se encuentran en la dirección de la factura del cliente o la dirección de entrega vinculada al encabezado del pedido, o si los datos se encuentran en las direcciones de entrega que se vinculan a cualquiera de las líneas del pedido de ventas, las puntuaciones de todas las coincidencias únicas se agregan y se comparan al valor **Puntuación mínima** para determinar si el pedido se debe poner en espera.

- **Reglas de fraudes** consta de las variables definidas por el usuario y las condiciones que se definen para las variables. Para crear reglas, vaya a **Retail y Commerce** \> **Configuración del canal** \> **Configuración de centro de asistencia telefónica** \> **Fraude** \> **Reglas**. Las reglas de fraude permiten a una compañía configurar un conjunto de reglas más complejo que puede incluir declaraciones **AND** u **OR** para evaular varias condiciones. Por ejemplo, un usuario desea que todos los pedidos de los clientes que pertenecen a un grupo de clientes específico y que pidieron un producto específico se pongan en espera para detectar fraudes. En este caso, las condiciones para validar el cliente y los productos se definen en la página **Reglas** y se utiliza la condición Y. Se pone un pedido en espera solo si ambas condiciones son verdaderas, y si el valor de la puntuación asignada a esta regla, más el valor de puntuación de cualquier otra regla que coincide con el pedido, hacen que la puntuación total de fraude del pedido supere el valor **Puntuación mínima** que se define en la página **Parámetros de centro de asistencia telefónica**.

> [!NOTE]
> El uso de varias reglas o de reglas excesivamente complejas afectarán al rendimiento del sistema cuando se envíen pedidos de ventas. La característica de comprobación de fraudes no se ha optimizado para gestionar un volumen grande de entradas de datos estáticos de fraudes y muchas reglas activas. Recuerde que cada regla es evaluada cuando los usuarios del centro de asistencia telefónica seleccionan **Enviar** durante la entrada de pedido de ventas. Las reglas se evalúan con la cabecera del pedido de ventas y todas las líneas de pedido. Cuanto más reglas haya y más complejas sean las instrucciones de las reglas, más tiempo tardarán en procesarse. Si hay varios artículos de línea en el pedido, y un gran número de reglas activas y entradas de datos estáticos, el proceso automático de revisar y validar todos los datos y de calcular una puntuación de fraude puede tener un impacto severo en el rendimiento. Las organizaciones que usan esta característica deben probar y confirmar siempre que el tiempo de procesamiento de envío de pedidos sea aceptable antes de aplicar cambios a las reglas o los criterios de fraudes estáticos en el entorno de producción.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identificación de pedidos que están en espera para la detección de fraudes

Cuando los usuarios del centro de asistencia telefónica envían un pedido de ventas, si el pedido coincide con los criterios o las reglas de fraudes, y si la puntuación supera el mínimo, los usuarios reciben un mensaje de advertencia que indica que el pedido se ha puesto en espera. Los usuarios pueden cerrar este mensaje, ya que es meramente informativo. Los usuarios pueden comunicar opcionalmente esta información al cliente. El negocio debe determinar el protocolo que los usuarios deben seguir en esta situación.

Se guardará el pedido, pero el indicador **No procesar** se establecerá en él. Este indicador ayuda a garantizar que el pedido no se libere al almacén. En cualquier momento, los usuarios podrán ver el valor del indicador **No procesar** de cualquier pedido de ventas en la página **Estado detallado**. Esta página se puede abrir en las páginas **Todo el pedido de ventas** y **Servicio al cliente**. El sistema también actualiza el valor del campo **Estado detallado** del pedido **Bloqueo de fraudes**.

Para ver y administrar los pedidos que están en espera para detectar fraudes, vaya a **Retail y Commerce** \> **Clientes** \> **Bloqueos del pedido**. En la página **Bloqueos del pedido**, seleccione una entrada en la lista y, a continuación, haga clic en **Retención del pedido** para obtener una vista detallada que incluye información acerca del motivo de bloqueo. En la ficha desplegable  **Detalles del fraude**, puede ver los criterios sistemáticos de fraude que se han detectado en el pedido y las puntuaciones que se han aplicado. Si el pedido se coloca en el bloqueo manual, puede revisar los comentarios que realizó el usuario que puso el pedido en espera mirando la sección **Notas de fraudes** en la ficha desplegable **Notas**.

Para obtener más información sobre cómo trabajar con pedidos en espera, consulte [Retenciones de pedidos](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds).


[!INCLUDE[footer-include](../includes/footer-banner.md)]