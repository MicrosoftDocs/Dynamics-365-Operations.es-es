---
title: Información general de Dynamics 365 Payment Connector para Adyen
description: Este artículo proporciona una descripción general Microsoft Dynamics 365 Payment Connector para Adyen.
author: rassadi
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.openlocfilehash: 6c819e8cf9f5dcb7895ac2633decf0a925c08f2d
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785002"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Información general de Dynamics 365 Payment Connector para Adyen

[!include [banner](../includes/banner.md)]

Este artículo proporciona una descripción general de Microsoft Dynamics 365 Payment Connector para Adyen e incluye una lista completa de características y funciones compatibles. Los artículos relacionados cubren el registro de Adyen, la configuración del conector, las preguntas frecuentes y la guía de solución de problemas para algunos problemas comunes.

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Conector de pago | Una extensión que facilita la comunicación entre Microsoft Dynamics 365 Commerce (y componentes asociados) y un servicio de pago. El conector que se describe en este artículo se implementó usando el kit de desarrollo de software (SDK) de pagos estándar. |
| Tarjeta presente | Se refiere a las transacciones de pago en las que una tarjeta física se muestra y se usa en un conector del terminal de pago del punto de venta de Dynamics 365. |
| Tarjeta no presente | Se refiere a las transacciones de pago en las que no hay una tarjeta física presente, como escenarios de comercio electrónico o del centro de llamadas. En estos escenarios, la información relacionada con el pago se especifica manualmente en sitio web de comercio electrónico, en un flujo del centro de llamadas o en el punto de venta o terminal de pago. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Características, funcionalidades, versiones y terminales admitidos

El Dynamics 365 Payment Connector para Adyen listo para utilizar utiliza el SDK de pagos estándar. Por lo tanto, no tiene capacidades especiales que no estén disponibles para otros conectores de pago.

### <a name="supported-versions"></a>Versiones admitidas

#### <a name="microsoft-dynamics-365-supported-versions"></a>Versiones admitidas de Microsoft Dynamics 365
El Dynamics 365 Payment Connector para Adyen original y listo para usar es compatible con Microsoft Dynamics 365 Finance versión 8.1.3 (enero de 2019) o posterior, y con Microsoft Dynamics 365 Retail versión 8.1.3 o posterior. Sin embargo, los terceros siguen pudiendo desarrollar otros conectores de pago para Adyen para versiones anteriores de Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Versiones de firmware de Adyen compatibles

La lista siguiente describe las versiones mínimas y máximas de firmware de Adyen que son compatibles con cada versión de Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Dynamics 365 Retail POS versión 10.0.25
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Dynamics 365 Retail POS versión 10.0.26
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Dynamics 365 Retail POS versión 10.0.27
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Dynamics 365 Retail POS versión 10.0.28
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Dynamics 365 Retail POS versión 10.0.29
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Dynamics 365 Retail POS versión 10.0.30
| Versión de firmware de Adyen mínima | Versión de firmware de Adyen máxima |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Adyen puede publicar actualizaciones de versiones secundarias después de que Microsoft haya probado la versión principal. Siempre que se admita una versión principal, está bien tener actualizaciones de versiones secundarias dentro de la misma versión principal. Estas actualizaciones normalmente son correcciones muy específicas y no cumplen con el listón para realizar una nueva prueba completa, siempre que se haya probado previamente la misma versión de firmware principal. Las actualizaciones no deben exceder la versión máxima de firmware de Adyen que se indica en la documentación. 
>
> La migración de una versión de firmware de Adyen anterior a la versión 53 a la versión 53 requiere PDV KB **4577957** para actualizaciones mensuales de Commerce, de las versiones 10.0.11 a 10.0.14. Si una de esas versiones está en uso y no incluye la revisión, la actualización posterior del terminal de pago solo permitirá pagos a través de NFC. La aplicación de la revisión al PDV resuelve este problema. Si la versión del PDV es anterior a la versión 10.0.11, presente una solicitud de soporte indicando que una solución para KB **4577957** es necesaria para un MPOS fuera de servicio.
> 
> Para las versiones de firmware de Adyen de 59p7 a 62p9, la operación **cobro en efectivo de tarjeta regalo** solicita introducir dos veces el PIN en escenarios donde la tarjeta regalo se introduce manualmente. Este problema no se reproduce cuando se desliza la tarjeta regalo. Adyen está investigando la situación. 

### <a name="supported-payment-terminals"></a>Terminales de pago admitidos
El Dynamics 365 Payment Connector para Adyen aprovecha el [API de terminal de pago de Adyen](https://www.adyen.com/blog/introducing-the-terminal-api) independiente de dispositivos. Es compatible con todos los terminales de pago compatibles con esta interfaz de programación de aplicaciones (API). Para obtener una lista completa de los terminales de pago admitidos, visite la página [Terminales PDV de Adyen](https://www.adyen.com/pos-payments/terminals).

El siguiente video describe las capacidades del terminal de pago Android Adyen Castles SE1.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bKeM]

### <a name="supported-payment-instruments"></a>Instrumentos de pago admitidos

#### <a name="supported-debit-and-credit-cards"></a>Tarjetas de débito y crédito admitidas

| Marca | Variante | Tarjeta presente | Comercio electrónico | Centro de llamadas |
|---|---|:-:|:-:|:-:|
| MasterCard | Crédito | ✔ | ✔ | ✔ |
| MasterCard | Débito | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Crédito | ✔ | ✔ | ✔ |
| VISA | Débito | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | VISA Checkout | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | VISA Aravia Card | ✔ | ✔ | ✔ |
| AMEX | Crédito | ✔ | ✔ | ✔ |
| AMEX | Débito | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX Small Business | ✔ | ✔ | ✔ |
| Discover | Estándar | ✔ | ✔ | ✔ |
| Discover | Android Pay | ✔ |  |  |
| Discover | Apple Pay | ✔ |  |  |
| Discover | Samsung Pay | ✔ |  |  |
| Diners   | Estándar | ✔ | ✔ | ✔ |
| Dineromail | Estándar | ✔ | ✔ | ✔ |
| JCB | Estándar | ✔ | ✔ | ✔ |
| Union Pay\* | Estándar | ✔ |  |  |
| Interac Debit\* | Estándar | ✔ |  |  |

\*Adyen no proporciona tokens de tarjetas periódicos de Interac y Union Pay, por lo que no se pueden admitir para transacciones sin tarjeta presente.

#### <a name="supported-gift-cards"></a>Tarjetas regalo admitidas
| Esquema | Tarjeta presente | Tarjeta no presente |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Para respaldar estos esquemas de tarjetas regalo externas a través de Dynamics 365 Payment Connector para Adyen, debe completar pasos adicionales. Para obtener más información, consulte [Compatibilidad para tarjetas regalo externas](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Carteras admitidas

| Esquema | Tarjeta presente | Tarjeta no presente |
|---|---|---|
| Alipay | Se agregará soporte en una versión futura. | N.º |
| WeChat | Se agregará soporte en una versión futura. | N.º |

#### <a name="supported-card-present-input-methods"></a>Métodos de entrada de tarjeta presente admitidos
| Método de entrada | Compatible | Notas |
|---|:-:|---|
| Introducir | ✔ | |
| Pasar | ✔ | |
| Tocar | ✔ | |
| Entrada manual a través de la interfaz de usuario del PDV. |  | Actualmente no admitida |
| Entrada manual a través de terminal de pago. | ✔ | Admite la entrada manual de tarjetas de crédito, débito y regalo con entrada de PIN. | 


#### <a name="supported-card-present-countries"></a>Países que admiten la presencia de tarjeta

Los siguientes países tienen componentes de Commerce disponibles y soporte de tarjeta presente de Adyen. Para la disponibilidad internacional actual de Commerce, visite la [Página de disponibilidad internacional](/dynamics365/get-started/availability).

| País | Compatible |
| --- | :-: |
| Australia | ✔ |
| Austria | ✔ |
| Bélgica | ✔ |
| Canadá | ✔ |
| República Checa | ✔ |
| Dinamarca | ✔ |
| Estonia | ✔ |
| Finlandia | ✔ |
| Francia | ✔ |
| Alemania | ✔ |
| RAE de Hong Kong | ✔ |
| Hungría | ✔ |
| Islandia | ✔ |
| Irlanda | ✔ |
| Italia | ✔ |
| Japón | Versión de actualización futura |
| Letonia | ✔ |
| Lituania | ✔ |
| Malasia | ✔ |
| Países Bajos | ✔ |
| Nueva Zelanda | ✔ |
| Noruega | ✔ |
| Polonia | ✔ |
| Singapur | ✔ |
| Suiza | ✔ |
| España | ✔ |
| Suecia | ✔ |
| Suiza | ✔ |
| Reino Unido | ✔ |
| Estados Unidos | ✔ |
| Brasil | Versión de actualización futura |

#### <a name="supported-card-not-present-countries"></a>Países que admiten la ausencia de tarjeta

Los siguientes países son compatibles con Adyen para transacciones sin tarjeta presente. [Póngase en contacto con Adyen](https://www.adyen.com/contact/sales) para obtener detalles sobre el soporte para un país específico. Para la disponibilidad internacional actual de Commerce, visite la [Página de disponibilidad internacional](/dynamics365/get-started/availability).

| País | 
| --- |
| Argentina |
| Armenia |
| Australia |
| Austria |
| Baréin |
| Bélgica |
| Brasil |
| Bulgaria |
| Canadá |
| Chile |
| China |
| Colombia |
| Croacia |
| Chipre |
| República Checa  |
| Dinamarca |
| Egipto |
| Estonia |
| Finlandia |
| Francia |
| Georgia |
| Alemania |
| Gibraltar |
| Grecia |
| Guernsey |
| RAE de Hong Kong |
| Hungría |
| Islandia |
| India |
| Indonesia |
| Irlanda |
| Isla de Man |
| Israel |
| Italia |
| Japón |
| Jersey |
| Corea |
| Kuwait |
| Letonia |
| Lituania |
| Luxemburgo |
| Malasia |
| Malta |
| México |
| Marruecos |
| Países Bajos |
| Nueva Zelanda |
| Noruega |
| Perú |
| Polonia |
| Portugal |
| Catar |
| Rumanía |
| Arabia Saudí |
| Serbia |
| Singapur |
| Eslovaquia |
| Eslovenia |
| Sudáfrica |
| España |
| Suecia |
| Suiza |
| Taiwán |
| Tanzania |
| Tailandia |
| Turquía |
| Emiratos Árabes Unidos (EAU) |
| Reino Unido |
| Estados Unidos de América, incluido Puerto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Características de pago compatibles con Dynamics 365

La siguiente tabla muestra el conjunto de características que admite Dynamics 365 Payment Connector para Adyen. Estas características usan mejoras que se introdujeron en el SDK de pagos y algunos componentes en diciembre de 2018. No son exclusivas de Dynamics 365 Payment Connector para Adyen. Para obtener más información sobre cómo adoptar estas mejoras para un conector de pago diferente, consulte [Crear integración de pago de un extremo a otro para un terminal de pago](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Esquema | Tarjeta presente | Tarjeta no presente |
|---|:-:|:-:|
| [Cobrar en efectivo saldo de tarjeta regalo](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Duplicar protección de pagos](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Tokenización omnicanal | ✔ | ✔ |
| Reembolsos vinculados | ✔<br>(A partir de 10.0.1) | ✔<br>(A partir de 10.0.1) |
| [Guardar pagos en línea](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(A partir de 10.0.2) | 
| [Tarjetas regalo externas para centro de llamadas y comercio electrónico](./gift-card.md) | ✔<br>(A partir de 10.0.10) | 
| [Redirección de pago de SCA](../adyen_redirect.md) | | ✔<br>(A partir de 10.0.12) |
| [Terminales de pago dedicados y avisos para una impresora y un cajón de efectivo](../pos-multi-hws.md) | ✔<br>(A partir de 10.0.12) | |
| [Soporte de propinas a nivel de SDK a través del conector Adyen](tipping.md) | ✔<br>(A partir de 10.0.14) | |
| [Captura incremental para facturación administrativa](incremental-capture.md) |  | ✔<br>(A partir de 10.0.18) |
| [Pagos de cartera](../wallets.md) |  | ✔<br>(A partir de 10.0.20) |
| [Google Pay con Adyen](google-pay-adyen.md) |  | ✔<br>(A partir de 10.0.27) |

## <a name="next-steps"></a>Pasos siguientes

Para obtener información sobre cómo registrarse en Dynamics 365 Payment Connector para Adyen y configurarlo, consulte [Configuración de Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md)

[Preguntas frecuentes sobre Dynamics 365 Payment Connector para Adyen](adyen-connector-faq.md)

[Solucionar problemas de Dynamics 365 Payment Connector para Adyen](adyen-connector-troubleshoot.md)

[Preguntas frecuentes sobre pagos](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
