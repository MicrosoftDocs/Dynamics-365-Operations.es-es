---
title: Configurar avisos de fraude
description: "En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos. También puede definir códigos específicos que puede usar para poner en espera los pedidos sospechosos automática o manualmente."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Configurar avisos de fraude

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar criterios y reglas para poner en espera pedidos de ventas potencialmente fraudulentos para revisión adicional. La funcionalidad de revisión de fraudes se usa para determinar la validez de la información en un pedido de ventas. Si la información del pedido de ventas parece para ser cuestionable en función de los criterios y las reglas contra el fraude de una organización, el pedido puede ser puesto en espera para revisión adicional a cargo de un gestor.

> [!NOTE]
> Esta función sólo se puede usar con el procesamiento de pedidos de ventas del canal de centro de llamadas de Retail. 

Cuando se define el canal de centro de llamadas, **Habilitar finalización de pedidos** se debe establecer en **Sí**. Cuando se habilita la finalización de pedidos, los usuarios pueden ver el resumen de pedidos y hacer clic en **Enviar** para finalizar el pedido. Los usuarios también tendrán opciones para poner en espera manualmente el pedido de ventas en la revisión de fraudes. Los pedidos de ventas introducidos por un usuario del centro de llamadas se procesan con reglas y criterios de comprobación de fraudes durante el proceso de envío.

Existen dos tipos de criterios de fraudes a los que el sistema hará referencia para comprobar si el pedido se debe mantener en espera para revisión de fraudes:

-   Las **reglas estáticas** utilizan un valor específico, como un número de teléfono que se ha puesto en una lista negra o una dirección de correo electrónico que se ha marcado porque se sabe que se ha usado para transacciones fraudulentas pasadas. En la página **Datos de fraudes estáticos**, la información de fraudes se puede agregar manualmente o mediante importación de datos, con puntuaciones adjuntas a la información fraudulenta. Si está activada la comprobación de fraudes, cada pedido de ventas especificado se comparará con los datos estáticos. Si los datos se encuentran en la dirección de facturación o de entrega del cliente, o si los datos se encuentran en la dirección de entrega de la línea de ventas, se sumarán las puntuaciones de todas las coincidencias únicas.  
-   Las **reglas dinámicas** se compone de variables y condiciones definidas para esas variables. Con las reglas dinámicas, ningún otro criterio definido en las reglas estáticas puede comprobarse. Instrucciones “AND/OR” más complejas se pueden usar para considerar varias condiciones para determinar si hay una coincidencia positiva con los criterios de la regla y el pedido de ventas que se envía. Por ejemplo, si un usuario desea poner en espera de revisión de fraudes todos los pedidos para clientes relacionados con un valor de grupo de clientes específico y que pidieron un producto específico, las condiciones para validar al cliente y para validar productos serían definidas en la página **Reglas** con la condición "AND". El pedido se pondría en espera por fraude solo si se cumplieran ambas condiciones y el valor de puntuación asignado a la regla pusiera la puntuación de fraude total del pedido por encima de la puntación de fraude mínima que se define en los parámetros del centro de llamadas.

Un usuario del centro de llamadas también puede configurar manualmente un pedido en la cola de retención por fraude. Si el usuario que introduce el pedido cree que el cliente que realiza el pedido puede ser sospechoso y desea que otra persona revise adicionalmente la validez del pedido antes de procesarlo, el usuario que introduce el pedido puede elegir la opción **Retención manual por fraude** del menú desplegable **Retenciones** en la página **Resumen de pedido de ventas** (ésta aparece después de que se llama a la función **Completar** pedido.) Se solicitará al usuario que escriba una nota para explicar con más detalle por qué cree que el pedido puede ser fraudulento para que el revisor tenga más contexto.

Todos los pedidos retenidos a través de retención de fraude manual o por cálculo sistemático de las puntuaciones de fraude aparecerán en la página **Retenciones de pedido** , donde el pedido se puede revisar y después cancelar o liberar a procesamiento.

> [!NOTE]
> El uso de varias reglas o de reglas excesivamente complejas producirá un rendimiento deficiente del sistema cuando se envíen pedidos de ventas. La característica de alerta por fraude no se ha optimizado para gestionar un volumen grande de entradas de datos estáticos de fraudes y muchas reglas activas. Es importante recordar que cada regla es evaluada durante la función de envío de la entrada de pedidos de ventas del centro de llamadas. Las reglas se evalúan con la cabecera del pedido de ventas y todas las líneas de pedido. Cuanto más reglas haya y más complejas sean las instrucciones de las reglas, más tardarán en procesarse. Si tiene un gran número de artículos de línea en el pedido, y un gran número de reglas activas y entradas de datos estáticos, este proceso sistemático de revisar y validar todos los datos y de calcular una puntuación de fraude puede tener un impacto severo en el rendimiento.  Las organizaciones que usan esta característica deben probar y confirmar siempre que el tiempo de procesamiento de envío de pedidos es aceptable antes de aplicar cambios a las reglas o los criterios de fraudes estáticos en el entorno de producción.

