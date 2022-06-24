---
title: Procesar devoluciones no vinculadas con Dynamics 365 Commerce Payment Connector para Adyen
description: Este artículo describe cómo funcionan las devoluciones no vinculadas cuando se usa Microsoft Dynamics 365 Payment Connector para Adyen.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 634b30de7adbfb0c316fe14456581ea8eb89d070
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885206"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Procesar devoluciones no vinculadas con Dynamics 365 Commerce Payment Connector para Adyen

[!include [banner](../includes/banner.md)]

Este artículo describe cómo funcionan las devoluciones no vinculadas cuando se usa [Microsoft Dynamics 365 Payment Connector para Adyen](adyen-connector.md). También revisa la capacidad de procesar una devolución con un nuevo método de pago en el punto de venta (PDV) o en el centro de llamadas.

Dynamics 365 Payment Connector para Adyen admite la capacidad de procesar devoluciones mediante un método de pago diferente al que se utilizó para la transacción original. Aunque le recomendamos que utilice [devoluciones vinculadas](linked-refunds.md) para procesar una devolución con el método de pago original que se proporcionó, en algunos escenarios se requieren devoluciones en un método diferente. Por ejemplo, la tarjeta que se usó para el pago original ahora podría estar caducada o haberse perdido, o podría haberla cancelado el usuario.

## <a name="prerequisites"></a>Requisitos previos

Se deben completar los siguientes requisitos previos antes de que Dynamics 365 Payment Connector para Adyen pueda procesar devoluciones no vinculadas:

- Configurar [métodos de pago](../payment-methods.md).
- Configurar [pagos omnicanal](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Configuración adicional

Dynamics 365 Payment Connector para Adyen ofrece una implementación del componente estándar de cada escenario de devolución compatible que se describe en la siguiente sección. Los clientes que no utilizan la implementación lista para usar de Dynamics 365 Payment Connector para Adyen deben configurar el conector que admita la creación de tokens de tarjetas de crédito.

## <a name="supported-refund-scenarios"></a>Escenarios de devoluciones admitidas

Dynamics 365 Commerce admite devoluciones de transacciones que se aprobaron y confirmaron anteriormente. Las devoluciones pueden consistir en una devolución completa o en una devolución parcial de la transacción. Las devoluciones no pueden exceder el importe total de la autorización de pago original. Las devoluciones no vinculadas solo se admiten en PDV y centro de llamadas.

## <a name="enable-unlinked-refunds-functionality"></a>Habilitar la función de devoluciones no vinculadas

Para habilitar la función de devoluciones no vinculadas en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce**.
1. En la pestaña **Pagos de omnicanal**, establezca la opción **Usar pagos omnicanal** en **Sí**.

### <a name="supported-payment-method-variants"></a>Variantes del método de pago admitidas

Las siguientes variantes de métodos de pago admiten devoluciones no vinculadas listas para usar:

- Tarjetas
- Cartera

No todas las variantes de métodos de pago admiten devoluciones no vinculadas. La siguiente tabla proporciona una lista de métodos de pago comunes y muestra la capacidad de soporte de cada método para devoluciones vinculadas y no vinculadas.

| Método de pago        | Devolución vinculada | Devolución no vinculada |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Sí           | Sí             |
| amexconsumer          | Sí           | Sí             |
| amexcorporate         | Sí           | Sí             |
| amexdebit             | Sí           | Sí             |
| amexprepaid           | Sí           | Sí             |
| amexprepaidreloadable | Sí           | Sí             |
| amexsmallbusiness     | Sí           | Sí             |
| discover              | Sí           | Sí             |
| maestro               | Sí           | Sí             |
| maestrouk             | Sí           | Sí             |
| mc                    | Sí           | Sí             |
| mcalphabankbonus      | Sí           | Sí             |
| mcprepaidanonymous    | Sí           | Sí             |
| visa                  | Sí           | Sí             |
| visaalphabankbonus    | Sí           | Sí             |
| visacheckout          | Sí           | Sí             |
| visadankort           | Sí           | Sí             |
| visahipotecario       | Sí           | Sí             |
| visasaraivacard       | Sí           | Sí             |
| vpay                  | Sí           | Sí             |
| givex                 | **No**        | Sí             |
| svs                   | **No**        | Sí             |
| cup                   | Sí           | Sí             |
| diners                | Sí           | Sí             |
| interac               | **No**        | Sí             |
| jcb                   | Sí           | Sí             |
| jcb_applepay          | Sí           | Sí             |
| unionpay              | Sí           | Sí             |

### <a name="process-an-unlinked-refund-in-pos"></a>Procesar una devolución no vinculada en PDV

Un cliente devuelve un artículo a un cajero de PDV dentro del periodo permitido para devoluciones y tiene un recibo válido. Durante la tramitación de la devolución, el cuadro de diálogo **Devolución de pago** incluye una opción de **Elegir un método de pago**. El cajero puede seleccionar un método de pago entre los métodos de pago admitidos para devoluciones (tarjetas y efectivo).

### <a name="process-an-unlinked-refund-in-call-center"></a>Procesar una devolución no vinculada en un centro de llamadas

Cuando se procesa una devolución no vinculada contra un pedido en el centro de llamadas, un empleado del centro de llamadas selecciona un método de pago que difiere del método de origen. A continuación, se solicita al empleado que obtenga un número de identificación personal (PIN) anulado por el administrador. Se requiere el PIN antes de que se pueda procesar el método de pago diferente para la devolución.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Configurar un PIN de anulación de administrador para el centro de llamadas

Para configurar un PIN de anulación de administrador para el centro de llamadas en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración del canal \> Configuración del centro de llamadas** o busque "Anular permisos".
1. Seleccione el rol para el que desea conceder los permisos de procesamiento de devoluciones no vinculadas.
1. En la ficha desplegable **Devoluciones**, configure la opción **Permitir pago alternativo** a **Sí**.

## <a name="additional-resources"></a>Recursos adicionales

[Dynamics 365 Payment Connector para Adyen](adyen-connector.md)

[Reembolsos vinculados de transacciones previamente aprobadas y confirmadas](linked-refunds.md)
