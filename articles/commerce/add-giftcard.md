---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7fc35c67a2d9b641f03f11ed5d06913e10d8e25b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347512"
---
# <a name="gift-card-module"></a>Módulo de tarjeta de regalo

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de tarjetas de regalo se pueden usar para en módulos de pago para aceptar tarjetas de pago, un método de pago habitual utilizado en transacciones de comercio electrónico. El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex. Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen. Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md).

> [!NOTE]
> El soporte para canjear tarjetas de regalo SVS y Givex durante el proceso de pago está disponible en Dynamics 365 Commerce 10.0.11. 

Hay dos módulos de tarjetas de regalo disponibles:

- **Tarjeta regalo**: este módulo se puede utilizar en una página de pago para canjear una tarjeta de regalo como oferta. 
- **Comprobación del saldo de la tarjeta regalo**: este módulo se puede utilizar en cualquier página para comprobar el saldo de una tarjeta regalo. Este módulo está disponible en Commerce, versión 10.0.14 y posterior.

> [!NOTE]
> La compatibilidad con el módulo de verificación de saldo de la tarjeta de regalo está disponible en Dynamics 365 Commerce 10.0.14.

La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.

![Ejemplo de un módulo de tarjeta regalo.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propiedades del módulo

- **Mostrar campos adicionales**: esta propiedad define qué campos se deben mostrar para las tarjetas de regalo, además del número de la tarjeta regalo, que siempre se muestra de forma predeterminada. Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento. Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.

Valores admitidos:
-   PIN
-   Fecha de caducidad
-   PIN y fecha de vencimiento 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Configuración del sitio para módulos de tarjetas de regalo

En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**. Esta configuración admite tres valores:
- **Tarjeta de regalo de Dynamics 365**: cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365. Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.
- **Tarjetas de regalo SVS y Givex**: cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS. Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.
- **Tarjetas de regalo Dynamics 365, SVS y Givex**: cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS. Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.

> [!IMPORTANT]
> Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.11 y son necesarios solo si necesita soporte para tarjetas de regalo SVS o Givex. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Ampliar las tarjetas regalo internas para su uso en tiendas de comercio electrónico

De forma predeterminada, las tarjetas de regalo internas no están optimizadas para su uso en escaparates de comercio electrónico. Por lo tanto, antes de permitir que se utilicen tarjetas de regalo internas para el pago, debe configurarlas con extensiones que ayuden a hacerlas más seguras. Estas son las áreas de tarjetas de regalo que debe ampliar antes de permitir que las tarjetas de regalo internas se utilicen en producción:

- **Numero de tarjeta de regalo**: las secuencias de números se utilizan para generar números de tarjetas de regalo para tarjetas de regalo internas. Debido a que las secuencias de números se pueden predecir fácilmente, debe ampliar la generación de números de tarjetas regalo para que se utilicen cadenas aleatorias y criptográficamente seguras para los números de tarjetas regalo que se emiten.
- **GetBalance**: la API **GetBalance** se utiliza para buscar saldos de tarjetas de regalo. De forma predeterminada, esta API es pública. Si no se requiere un PIN para buscar saldos de tarjetas regalo, existe el riesgo de que los ataques por fuerza bruta puedan usar la API **GetBalance** para intentar buscar números de tarjetas de regalo que tengan saldo. Al implementar ambos requisitos de PIN para las tarjetas regalo y la limitación de API, se puede ayudar a mitigar el riesgo.
- **PIN** de forma predeterminada, las tarjetas regalo internas no admiten los PIN. Debe extender las tarjetas de regalo internas para que se requiera un PIN para buscar saldos. Esta funcionalidad también se puede usar para bloquear tarjetas de regalo después de intentos consecutivos incorrectos de introducir el PIN.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Habilitar pagos con tarjeta regalo para la finalización de compra de invitados

De forma predeterminada, los pagos con tarjeta regalo no están habilitados para la finalización de compra de invitados (anónima). Para habilitarlos, siga estos pasos.

1. En la sede central de Commerce, vaya a **Minorista y comercio \> Configuración de canales \> Configuración de PDV \> PDV \> Operaciones de PDV**.
1. Seleccione y mantenga presionado (o haga clic con el botón derecho) el encabezado de la cuadrícula y luego seleccione **Insertar columnas**.
1. En el cuadro de diálogo **Insertar columnas**, seleccione el cuadro de diálogo **AllowAnonymousAccess**.
1. Seleccione **Actualizar**.
1. Para operaciones **520** (Saldo de tarjeta regalo) y **214**, seleccione el valor **AllowAnonymousAccess** en **1**.
1. Seleccione **Guardar**.
1. Ejecute el trabajo de programador **1090** para sincronizar los cambios con la base de datos de canal. 

## <a name="add-a-gift-card-module-to-a-page"></a>Agregar un módulo de tarjeta regalo a una página

Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Compatibilidad para tarjetas de regalo externas](./dev-itpro/gift-card.md)

[Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
