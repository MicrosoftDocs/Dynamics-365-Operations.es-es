---
title: "Métodos de pago en un centro de asistencia telefónica"
description: "En este tema se tratan los diferentes métodos de pago que puede utilizar en un centro de llamadas en Retail y Commerce."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 636d83ecc7732a164924352853603588cded0db4
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods-in-a-call-center"></a>Métodos de pago en un centro de asistencia telefónica

En este tema se tratan los diferentes métodos de pago que puede utilizar en un centro de llamadas en Retail y Commerce.

Los métodos de pago que se usan en otros canales en Retail y Commerce en Microsoft Dynamics AX, como efectivo, cheques, tarjetas de crédito y tarjetas regalo, también se pueden usar en centros de llamadas. Tras configurar un método de pago para un centro de llamadas, aparece como una de las opciones de la sección **Pagos** de la página **Pedido de ventas** para los usuarios del centro de llamadas. Además, puede configurar vales para ofrecer descuentos a los clientes que realizan un pedido en el centro de llamadas de la organización. Los vales pueden ser para un importe de descuento fijo o para un porcentaje del precio del artículo o el total del pedido. Por ejemplo, un vale basado en importe podría ofrecer a los clientes un descuento de 75,00 cuando el cliente gasta 750,00 o más. Puede crear distintos tipos de vales, configurar vales principales o secundarios, y copiar o anular un cupón. Utilice las opciones de la siguiente tabla para crear vales.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Atributo**             | En el campo **Tipo de canje **, especifique el tipo de canje previsto del vale como porcentaje y seleccione si el vale se puede usar como un vale de uso único, si se volverá a emitir o si es específico para un cliente.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Válido**                 | En los campos **Fecha inicial** y **Fecha final**, especifique las fechas para la primera y última fecha de validez del vale.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Reglas de inclusión o exclusión** | En los campos **Catálogos** y **Artículos**, seleccione si se incluyen o excluyen catálogos o artículos del vale. Si selecciona **Incluir** o **Excluir**, haga clic en **Configurar**, seleccione **Incluir o excluir catálogos** o **Incluir o excluir productos**y escriba información sobre el catálogo o el artículo. Si selecciona **Ninguno** en estos campos, se incluyen todos los catálogos o artículos en el vale.                                                                                                                                                                                                                          |
| **Varios**         | Si no se puede utilizar este vale junto con otros descuentos, active la casilla **Exclusivo**. A continuación, en el campo **Origen**, seleccione dónde se puede usar el vale. En este vale es un vale del fabricante, active la casilla **Vale de fabricante**.                                                                                                                                                                                                                                                                                                                                                                |
| **Vale futuro**         | Si este vale se asociará con otros vales como vale principal, active la casilla **Vale principal**. Si este vale debe asociarse como vale secundario con un vale existente, seleccione el vale principal en el campo **Id. de vale principal**. Por ejemplo, cree un vale para el próximo catálogo de primavera. Los demás vales que cree para el catálogo de primavera serán vales secundarios del vale del catálogo de primavera. Los vales secundarios podrían incluir un descuento del 20 % para nuevos pedidos del cliente, un descuento del 10 % en un artículo recién lanzado o un descuento de 95,00 en pedidos de 1.000,00 o más. |

Si envía un pago de tarjeta de crédito desde la página **Pedido de ventas** y recibe un mensaje que indica que la tarjeta no estaba autorizada, puede gestionar la autorización manualmente. Puede autorizar, rechazar o volver a enviar una transacción de tarjeta de crédito mediante la página **Administración de autorizaciones**. Utilice la página de parámetros de centro de llamadas para configurar opciones de procesamiento de pagos adicionales:

-   Las retenciones de cheques permiten al personal contable procesar pedidos que se han puesto en espera debido a que se utilizó un cheque como el método de pago y se superó el importe del umbral de retención de cheques. La retención se puede liberar manualmente o caduca automáticamente al final del período configurado.
-   Puede establecer umbrales por encima de los cuales las devoluciones emitidas mediante cheques y tarjetas de crédito deben aprobarse manualmente. Cualquier devolución que supere el importe de umbral se agrega a la cola de aprobación. Tras aprobar la devolución, el pedido de ventas de devolución puede ser facturado.



