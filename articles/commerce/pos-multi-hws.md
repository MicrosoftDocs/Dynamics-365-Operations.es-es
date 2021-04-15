---
title: Terminales de pago dedicados y avisos para una impresora y un cajón de efectivo
description: Este tema proporciona información sobre la capacidad de tener un terminal de pago dedicado y solicita al usuario que seleccione un cajón de efectivo y una impresora de recibos.
author: rubendel
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ad75430c606f959b17c887531fb62bd37caec624
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804316"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Terminales de pago dedicados y avisos para una impresora y un cajón de efectivo

[!include [banner](includes/banner.md)]

Este tema proporciona información sobre la capacidad de tener un terminal de pago dedicado y solicita al usuario que seleccione un cajón de efectivo y una impresora de recibos.

## <a name="overview"></a>Información general

Los minoristas modernos están buscando formas de racionalizar la experiencia de pago en la tienda. Las tendencias recientes hacia el pago sin papel a través de pagos electrónicos no solo ayudan a que la experiencia de compra sea más fluida, sino que también reducen la necesidad de tener un complemento completo de dispositivos periféricos disponibles para cada asociado de la tienda.

Microsoft Dynamics 365 Commerce admite estas tendencias al habilitar un escenario en el que un dispositivo de punto de venta (PDV) tiene un terminal de pago dedicado asignado todo el tiempo, pero no tiene su propia impresora de recibos o cajón de efectivo. Cuando los asociados deben imprimir un recibo o recibir un pago en efectivo, se les solicita que seleccionen una estación de hardware donde estén configurados esos dispositivos.

## <a name="key-terms"></a>Términos clave

| Condición | Descripción |
|---|---|
| Inscribir | La entidad que se utiliza para configurar una instancia de un registro PDV. |
| Dispositivo | Una representación de la instancia física de un registro de TPV y la aplicación de PDV moderno que se le asigna. |
| Estación de hardware dedicada | La lógica de negocio de la estación de hardware incorporada en los PDV modernos para Windows y PDV modernos para Android. |
| Puerto de apertura cajón (d/k) | Un método tradicional para conectar un cajón de efectivo a una impresora de recibos. |
| Periféricos de red | Soporte incorporado para terminales de pago con capacidad de red, impresoras de recibos y cajones de efectivo. |

## <a name="supported-pos-clients-and-devices"></a>Clientes y dispositivos PDV compatibles

La funcionalidad que se describe en este tema es compatible con Modern POS para Windows y Modern POS para clientes PDV Android.

Esta funcionalidad admite terminales de pago con capacidad de red e impresoras de recibos. Puede proporcionar asistencia para el cajón de efectivo conectando el cajón de efectivo a la impresora de recibos habilitada para red a través del puerto d/k.

El soporte inmediato para esta funcionalidad lo proporciona el [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). Sin embargo, otros conectores de pago pueden ser compatibles a través del kit de desarrollo de software (SDK) de Commerce para pagos. Las impresoras de recibos compatibles incluyen impresoras de recibos habilitadas para red de Star Micronics y Epson.

Para configurar las impresoras de recibos de Star Micronics, use la Utilidad de impresoras de Star Micronics para configurar el dispositivo de modo que pueda usarse en la red. Esta utilidad también proporcionará la dirección IP del dispositivo.

Para configurar impresoras de recibos Epson, use la utilidad Epson ePOS-Print para configurar el dispositivo para usar protocolos de red.

Para obtener más información sobre cómo configurar periféricos de red, consulte [Resumen de soporte de periféricos de red](https://go.microsoft.com/fwlink/?linkid=2129965).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Configurar un terminal de pago dedicado y un aviso para una impresora y un cajón de efectivo

### <a name="set-up-hardware-profiles"></a>Configuración de perfiles de hardware

Debe tener dos tipos de perfil de hardware. El primero se asigna al registro. El segundo se asigna a una estación de hardware a nivel de tienda y se usa para agrupar lógicamente impresoras de recibos de red y cajones de efectivo.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Configurar un perfil de hardware para el registro

Para configurar el perfil de hardware asignado al registro, siga estos pasos.

1. En Dynamics 365 Commerce, busque **Perfil de hardware**.
2. Seleccione **Nuevo**.
3. Asigne un número de perfil de hardware y luego introduzca una descripción. Este perfil de hardware se asignará al propio registro. Por lo tanto, será suficiente una descripción como **Dedicado con respaldo**.
4. En las fichas desplegables para diferentes tipos de dispositivos, configure los siguientes tipos de dispositivos.

    | Dispositivo | Tipo | Nombre del dispositivo | Más detalles |
    |---|---|---|---|
    | Impresora | Reserva | *Alguna* | El nombre de dispositivo distingue entre mayúsculas y minúsculas. El **Id. de perfil de recibo** debería ser el mismo que el **Id. de perfil de recibo** que se asigna a la impresora de red que está configurada en el perfil de hardware asignado a la estación de hardware en el nivel del canal. |
    | Caja registradora | Reserva | *Alguna* | El nombre de dispositivo distingue entre mayúsculas y minúsculas. Establezca la opción **Usar de forma compartida** en **Sí**. |
    | Servicio EFT | Adyen | No aplicable | Para obtener información sobre cómo configurar el conector Adyen en su primer uso, consulte [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). Otros conectores de pago pueden ser compatibles a través del [kit de desarrollo de software (SDK) de Commerce para pagos](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/end-to-end-payment-extension). |
    | Terminal para introducción de PIN | Red | **MicrosoftAdyenDeviceV001** | Ninguno. |

5. En Dynamics 365 Commerce, busque **Registros**.
6. Seleccione un registro seleccionando el número de registro y luego seleccione **Editar**.
7. Asigne el perfil de hardware que acaba de crear al registro que debe usar un terminal de pago dedicado. El dispositivo que está asignado a este registro debe usar la aplicación PDV moderno para aplicación Windows o PDV moderno para Android.
8. Seleccione **Guardar**.
9. En el panel Acciones, en la pestaña **Registros**, seleccione **Configurar direcciones IP**.
10. En la ficha desplegable **Teclado de PIN**, introduzca la dirección IP del terminal de pago. Para obtener información sobre cómo obtener la dirección IP del terminal de pago mediante el conector Adyen, consulte [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3).
11. Seleccione **Guardar**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Configure un perfil de hardware para la impresora de recibos y el cajón de efectivo

Para configurar el perfil de hardware que se utiliza para agrupar la impresora de recibos de red y el cajón de efectivo, siga estos pasos.

1. En Dynamics 365 Commerce, busque **Perfil de hardware**.
2. Seleccione **Nuevo**.
3. Asigne un número de perfil de hardware y luego introduzca una descripción. Este perfil de hardware se usará para agrupar la impresora de recibos y el cajón de efectivo. Por lo tanto, será suficiente una descripción como **Impresora de red y cajón de efectivo**.
4. En las fichas desplegables para diferentes tipos de dispositivos, configure los siguientes tipos de dispositivos.

    | Dispositivo | Tipo | Descripción | Más detalles |
    |---|---|---|---|
    | Impresora | Red | **Epson** o **Star** | El nombre de dispositivo distingue entre mayúsculas y minúsculas. El **Id. de perfil de recibo** debería ser el mismo que el **Id. de perfil de recibo** que se asigna a la impresora que está configurada en el perfil de hardware asignado al registro. |
    | Caja registradora | Red | **Epson** o **Star** | El nombre de dispositivo distingue entre mayúsculas y minúsculas. Establezca la opción **Usar de forma compartida** en **Sí**. |

5. Seleccione **Guardar**.

### <a name="set-up-hardware-stations"></a>Configurar estaciones de hardware

Debes tener dos estaciones de hardware. El primero se asignará al registro. El segundo se seleccionará según sea necesario, siempre que se deba imprimir un recibo o se deba abrir un cajón de efectivo.

#### <a name="register-a-hardware-station"></a>Registrar una estación de hardware

1. En Dynamics 365 Commerce, busque **Todas las tiendas**.
2. Seleccione una tienda seleccionando sus valores de **Id. de canal minorista** y luego seleccione **Editar**.
3. En la ficha desplegable **Estaciones de hardware**, seleccione **Agregar**.
4. Establezca el campo **Tipo de estación de hardware** en **Dedicado**.
5. introduzca una descripción, pero no establezca ningún otro valor para esta estación de hardware. Esta estación de hardware se utilizará para el registro en todo momento. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Configurar una estación de hardware para la impresora de recibos y el cajón de efectivo

1. En Dynamics 365 Commerce, busque **Todas las tiendas**.
2. Seleccione una tienda seleccionando sus valores de **Id. de canal minorista** y luego seleccione **Editar**.
3. En la ficha desplegable **Estaciones de hardware**, seleccione **Agregar**.
4. Establezca el campo **Tipo de estación de hardware** en **Dedicado**.
5. Escribir una descripción. Esta estación de hardware se usará para la impresora de recibos y el cajón de efectivo.
6. En el campo **Perfil de hardware**, seleccione el perfil de hardware que creó anteriormente para la impresora de recibos y el cajón de efectivo.
7. Seleccione **Guardar**.
8. Mientras la estación de hardware para la impresora de recibos y el cajón de efectivo todavía está seleccionada, seleccione **Configurar direcciones IP**.
9. Obtenga la dirección IP de la impresora e ingrésela como la dirección IP para la impresora de recibos y el cajón de efectivo.
10. Seleccione **Guardar**.
11. Busque **Programaciones de distribución**.
12. Seleccione la programación de distribución **1090** y luego seleccione **Ejecutar ahora**.
13. Seleccione la programación de distribución **1070** y luego seleccione **Ejecutar ahora**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Configure el sistema para solicitar la selección de la impresora de recibos y el cajón de efectivo según sea necesario

1. En un cliente PDV compatible, cierre el turno actual, si hay un turno abierto.
2. Inicie sesión y luego seleccione **Operaciones de cajón que no son de cajón**.
3. Utilice la operación **Administrar estaciones de hardware** para activar una estación de hardware.
4. Seleccione la estación de hardware que creó para el registro para ponerla activa.
5. Cierre sesión del PDV y, vuelva a iniciar sesión y abra un turno.

El terminal de pago asignado al perfil de hardware ahora siempre estará activo y se le preguntará si se requiere una impresora de recibos o un cajón de efectivo.

Muchos comerciantes que solicitaron esta característica están interesados en reducir el desperdicio al proporcionar recibos por correo electrónico y alentar los pagos electrónicos. Dependiendo de la configuración del PDV, los asociados de la tienda deben seleccionar una impresora de recibos o un cajón de efectivo solo cuando un cliente desea un recibo físico o desea pagar en efectivo.

Se solicita a los asociados de la tienda que seleccionen una estación de hardware solo una vez por transacción, a menos que se deba imprimir un recibo y se use efectivo para el pago, pero el perfil de hardware que se seleccionó originalmente no incluye ambos dispositivos. En ese caso, se le solicitará nuevamente al asociado de la tienda que seleccione una estación de hardware que pueda usarse para completar la transacción.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar una aplicación de POS Hybrid en Android y en iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp)
- [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)
- [Resumen de soporte técnico de periféricos de red](https://go.microsoft.com/fwlink/?linkid=2129965)


[!INCLUDE[footer-include](../includes/footer-banner.md)]