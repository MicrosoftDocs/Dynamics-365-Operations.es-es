---
title: Códigos de referencia de error del módulo de finalización de la compra
description: Este artículo describe los códigos de referencia de error del módulo de pago que se muestran en los mensajes de error para el usuario en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 952cb932522b4e0bb91be985e4f8974cb6cd8bc0
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728255"
---
# <a name="checkout-module-error-reference-codes"></a>Códigos de referencia de error del módulo de finalización de la compra

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artículo describe los códigos de error del módulo de pago que se muestran en los mensajes de error para el usuario en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ha introducido referencias de error estandarizadas que se pueden incluir en los errores de pago del canal en línea que se presentan a los clientes en línea. En la versión 10.0.31 y posteriores de Commerce, los mensajes de error en el módulo de pago incluyen códigos de error y no muestran información innecesaria al cliente en línea. Los códigos de error se refieren a errores que se detallan en este artículo.

Según el error que se encuentre, la tabla de este artículo incluye los siguientes detalles:

- Una descripción de la condición que causó el error o detalles adicionales
- Información a tener en cuenta en el entorno o configuraciones del conector de pago
- Información a la que se puede hacer referencia en un caso de soporte, si se requiere asistencia adicional

## <a name="prerequisites"></a>Requisitos previos

Para habilitar los códigos de referencia de errores del módulo de finalización de compra que se enumeran a continuación, en el creador de sitios para su sitio, vaya a **Configuración del sitio \> Extensiones** y, en la sección **Carro y finalización de compra**, seleccione **Habilitar mensajes de visualización de errores de canales en línea mejorados**. 

## <a name="checkout-module-error-reference-codes"></a>Códigos de referencia de error del módulo de finalización de la compra

Utilice la siguiente tabla para obtener más detalles sobre las referencias de códigos de error proporcionadas por los clientes o experimentadas en la tienda en línea. Desplácese hacia la derecha para ver la columna **Descripción del error**.

| Código de error | Código de error relacionado con la dinámica | Error de descripción |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | No se pudo autorizar el pago. Falta el ID de tipo de tarjeta en **TokenizedPaymentCard** o el ID de tipo de tarjeta proporcionado no es compatible. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Denegado. No se pudo autorizar el pago. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | No se pudo autorizar el pago. Se requiere información adicional del cliente. |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Parece que hubo un problema. No pudimos obtener el resultado de aceptación del pago con tarjeta. Inténtelo de nuevo o póngase en contacto con el administrador del sistema. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | No se puede realizar el pago porque faltan propiedades de pago de comerciante. Póngase en contacto con el administrador del sistema. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | No se pudo recuperar el servicio de licitación para la operación. Verifique la configuración de su método de pago para el tipo de pago seleccionado. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | Ya se aplicó un pago de cuenta de cliente y solo se permite aplicar un pago por transacción. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountLimitSignDifferentFromAmountDue | El límite de la cuenta del cliente difiere del monto adeudado. Pruebe con un método de pago diferente o póngase en contacto con el servicio de atención al cliente para obtener ayuda. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | El pago de la cuenta del cliente excede el total adeudado por los artículos enumerados. Vuelva a intentarlo más tarde o póngase en contacto con el servicio de atención al cliente para obtener ayuda. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | El pago de la cuenta del cliente requiere su propia cuenta o una cuenta de facturación coincidente en una línea de forma de pago. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | No se puede procesar un pago de cuenta de cliente en este momento; se ha superado el valor de límite de planta. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | No se permite que este cliente pague a cuenta. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Parece que hubo un problema. No se pudo cancelar el pago. Inténtelo de nuevo. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Error al procesar el pago. Vuelva a intentarlo más tarde. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | El importe del pago de fidelización supera lo permitido para la tarjeta de fidelización utilizada en esta transacción. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | El importe de devolución de fidelización supera lo permitido para la tarjeta de fidelización utilizada en esta transacción. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | No se encontró el número de tarjeta de fidelización. Active el número de tarjeta de fidelización o especifique un número de tarjeta diferente y vuelva a intentarlo. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | El número de tarjeta de fidelización no está disponible. Especifique un número de tarjeta diferente y luego vuelva a intentarlo. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Esta tarjeta de fidelización no es apta para canjear puntos de fidelización para esta transacción. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | El número de la tarjeta de regalo encontró un error. Pruebe con una tarjeta de regalo diferente o póngase en contacto con el servicio de atención al cliente para obtener ayuda. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | El importe supera el saldo en la tarjeta regalo. Especifique un importe diferente y luego vuelva a intentarlo. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | La transacción no puede contener más de una línea de pago de fidelización. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | Falta información en la información de pago o es incorrecta. Verifique la información de pago y vuelve a intentarlo. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | El pedido no se puede procesar en estos momentos. Vuelva a intentarlo más tarde. |
| CCR025     | Tiempo de espera de front-end para la API de finalización de compra | Se agotó el tiempo de espera de la operación frontal. Confirmar si el pedido ha sido procesado en Dynamics 365 Commerce headquarters. |
| CCR026     | Monto original autorizado modificado | El monto del pedido ha cambiado del monto de la autorización original procesada con la pasarela de pago. Esto puede deberse a la expiración programada de un cupón, promoción o venta. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Error al procesar un pago. La referencia proporcionada a la API del carrito tiene una referencia diferente a la esperada (observando posibles inconsistencias durante el proceso de pago). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | El método de pago intentado ha encontrado un error. Póngase en contacto con el soporte para revisar la configuración de su cuenta o inténtelo de nuevo con un método de pago diferente. |

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](dev-itpro/payments-retail.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)
