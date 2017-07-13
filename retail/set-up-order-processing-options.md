---
title: Configurar opciones de procesamiento de pedidos
description: "Este tema proporciona información relativa a cómo procesar los pedidos para los centros de llamadas mediante la venta minorista y comercio en Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: afdea84b7016fcc3214dc94f2d393a5f3d256370
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017



---

# Configurar opciones de procesamiento de pedidos
<a id="set-up-order-processing-options" class="xliff"></a>

[!include[banner](includes/banner.md)]


Este tema proporciona información relativa a cómo procesar los pedidos para los centros de llamadas mediante la venta minorista y comercio en Microsoft Dynamics 365 for Retail. 

Retail admite varios canales de venta, como tiendas en línea, almacenes físicos y centros de llamadas. En los centros de llamadas, los trabajadores realizan pedidos de clientes por teléfono y crean pedidos de ventas. En este tema se describe cómo crear un centro de llamadas y configurar sus opciones. Cada centro de llamadas puede tener sus propios usuarios, métodos de pago, grupos de precios, dimensiones financieras y modos de entrega. Puede configurar estas opciones cuando crea el centro de llamadas. **Importante:** para que los flujos de trabajo del centro de llamadas se puedan usar cuando un usuario crea pedidos de ventas, se debe asignar al usuario al centro de llamadas como usuario del centro de llamadas. Puede usar la página **Centro de llamadas** para habilitar o deshabilitar grupos de funcionalidades que son únicas a los centros de llamadas. Los siguientes grupos de características se pueden habilitar:

-   **Finalización del pedido:** este grupo incluye características relacionadas con los pagos y la finalización del pedido en la página **Pedido de ventas**.
-   **Venta dirigida:** este grupo incluye características relacionadas con los códigos fuente, las secuencias de comandos las y solicitudes del catálogo.

Cuando se activan estas funciones de la configuración del centro de llamadas, están disponibles en la página **Pedido de ventas** para los usuarios que estén asociados con el centro de llamadas. La mayoría de ellas requieren configuración adicional antes de que se puedan usar. Las imágenes y los scripts se habilitan como parte del ajuste de la venta dirigida para el centro de asistencia de llamadas. Si se habilitan estas funciones, los scripts y las imágenes de productos se muestran en el panel del cuadro informativo de la página **Pedido de venta**. Se muestra la imagen predeterminada que se establece para un producto. Los scripts se pueden configurar para un artículo, un catálogo, un cliente o un artículo en el contexto de un catálogo. Los pedidos de los centros de llamadas pueden mostrar detalles adicionales sobre cómo se derivó el precio de una línea de pedido específica. Por ejemplo, los pedidos muestran los descuentos que se han aplicado. Esta funcionalidad se activa en **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes** &gt; **Precios** &gt; **Detalles de precios**. Puede tener acceso a la página **Detalles de precios** desde la lista desplegable **Línea de pedido de ventas**. Puede usar el seguimiento de eventos de pedido para fines de auditoria, revisar las acciones que se realizan en contra de un pedido durante su ciclo de vida o realizar un seguimiento de las acciones de un usuario específico. Por ejemplo, puede registrar la acción cada vez que un usuario crea un pedido de ventas, pone una retención en un pedido, anula un gasto o actualiza una línea de pedido. Puede configurar eventos de pedido para realizar un seguimiento de las acciones de usuarios específicos, grupos de usuarios o todos los usuarios durante un período de tiempo específico. Puede ver las acciones que se realizaron en un documento al abrir la página **Eventos de pedido** en el Panel de acciones del formulario de documento específico. Puede configurar eventos de pedido en **Ventas y marketing** &gt; **Configuración** &gt; **Eventos** &gt; **Eventos de pedido**. Cuando el pedido de un cliente no puede enviarse a tiempo, una empresa puede enviar automáticamente mensajes de correo electrónico al cliente para explicar el estado del pedido y dar al cliente una oportunidad de cancelar el pedido. Si el retraso se extiende más allá de un umbral especificado, el pedido se podrá cancelar automáticamente. Se pueden enviar hasta tres mensajes de correo electrónico en los intervalos especificados:

1.  **Primer aviso de la cancelación:** el cliente puede decidir cancelar el pedido.
2.  **Segundo aviso de la cancelación:** el cliente puede decidir cancelar el pedido.
3.  **Último aviso de la cancelación:** el sistema cancelar el pedido, y el cliente es informado de la cancelación.

Puede eximir clientes y productos individuales del proceso automático de notificación y de cancelación. Una alerta de margen se activa al agregar un artículo a un pedido. La alerta contiene información importante sobre el artículo, como el margen de precio y la rentabilidad del artículo. Puede usar esta información para decidir si una anulación de precios es adecuada al agregar un artículo al pedido de ventas. Por ejemplo, puede configurar los umbrales para que los márgenes comerciales especifiquen que un umbral del 40 por ciento o más por encima del coste es aceptable para un artículo, pero un umbral del 20 al 39 por ciento por encima del coste es cuestionable. En este caso, cualquier artículo con un umbral entre el 20 y 39 por ciento desencadena una advertencia. Cualquier artículo con un umbral menor del 20 por ciento por encima del coste no se puede vender, y el precio del artículo no se puede ajustar. Puede configurar alertas de margen en **Clientes** &gt; **Configuración** &gt; **Parámetros de cuentas** &gt; **Alertas de margen**. Al configurar la asignación de los impuestos basándose en reglas predeterminadas, puede determinar una prioridad coincidente para los elementos de la dirección. Por ejemplo, puede especificar que la coincidencia de un grupo de impuestos por código postal tiene una prioridad mayor que la coincidencia de un grupo de impuestos por estado. A medida que especifica nuevos registros de direcciones del cliente, el grupo de impuestos se asigna automáticamente en función de la coincidencia de la dirección del cliente con las reglas y la prioridad predeterminadas que ha definido. Puede configurar esta función en la página **Parámetros de contabilidad general**.




