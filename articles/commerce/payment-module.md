---
title: Módulo de pago
description: En este tema se trata el modulo de pago y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 894ac35973927c193d6e9c54e326daefb8a3f4a5
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055390"
---
# <a name="payment-module"></a>Módulo de pago

[!include [banner](includes/banner.md)]

En este tema se trata el modulo de pago y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El módulo de pago permite a los clientes pagar pedidos con tarjetas de crédito o débito. La integración de pagos para este módulo la proporciona el connector de pagos de Dynamics 365 para Adyen. Para obtener más información sobre cómo instalar y configurar el conector de pagos, consulte [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).

El módulo de pago aloja la información de pagos que se proporciona a través de Adyen en un marco en línea HTML (iframe). El módulo de pago interactúa con la Commerce Scale Unit para obtener la información de pagos de Adyen. Como parte de la interacción de la Commerce Scale Unit, el módulo de pago puede permitir que la información de la dirección de facturación se proporcione en el iframe o como un módulo independiente. En el tema Fabrikam, la dirección de facturación se muestra en un módulo independiente. Este enfoque permite una mayor flexibilidad de formato, ya que las líneas de dirección se pueden representar para que se parezcan a las líneas de la dirección de envío.

El módulo de pago también permite a los clientes registrados guardar su información de pago. La información de pago y la dirección de facturación se guardan y gestionan a través del conector de pago de Adyen.

El módulo de pago cubre cualquier gasto de pedido que aún no esté cubierto por puntos de fidelidad o una tarjeta regalo. Si el total de un pedido está totalmente cubierto por puntos de fidelidad o créditos de tarjetas regalo, el módulo de pago se ocultará y el cliente podrá realizar el pedido sin él.

El conector de pago de Adyen también admite la autenticación segura de clientes (SCA). Parte de la Directiva de servicios de pago 2.0 (PSD2.0) de la Unión Europea (UE) requiere que los compradores en línea estén autenticados fuera de su experiencia de compra en línea cuando utilicen un método de pago electrónico. Durante el flujo de finalización de compra, se redirige a los clientes a su sitio bancario. Una vez autenticados, se les redirige al flujo de finalización de compra de Commerce. Durante esta redirección, la información introducida por un en el flujo de finalización de compra (por ejemplo, la dirección de envío, las opciones de entrega, la información de la tarjeta regalo y la información de puntos de fidelidad) persistirá. Para poder activar esta característica, el conector de pago debe configurarse para SCA en la sede de Commerce. Para obtener más información, consulte [Autenticación segura de clientes mediante Adyen](adyen_redirect.md).

> [!NOTE]
> Para el conector de pago de Adyen, el módulo iframe del módulo de pago solo se puede procesar si agrega la URL de Adyen a la lista de permitidos del sitio. Para completar este paso, agregue **\*.adyen.com** a las directivas **child-src** , **connect-src** , **img-src** , **script-src** y **style-src** de la directiva de seguridad del contenido del sitio. Para obtener más información, consulte [Administrar la directiva de seguridad de contenido](manage-csp.md). 

La siguiente ilustración muestra un ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago en una página de finalización de compra.

![Ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago en una página de finalización de compra.](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Propiedades del módulo de pago

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto del encabezado | Un encabezado opcional para el módulo de pago. |
| Altura del iframe | Píxeles | La altura del iframe, en píxeles. La altura se puede ajustar según sea necesario. |
| Mostrar dirección de facturación | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero** , Adyen proporcionará la dirección de facturación dentro del iframe del módulo de pago. Si se configura en **Falso** , Adyen no proporcionará la dirección de facturación y un usuario de Commerce tendrá que configurar un módulo para mostrar la dirección de facturación en la página de finalización de compra. |
| Anulación de estilo de pago | Código de hojas de estilo en cascada (CSS) | Como el módulo de pago está alojado en un iframe, la capacidad de estilos es limitada. Puede lograr aplicar estilos con esta propiedad. Para reemplazar los estilos del sitio, debe pegar el código CSS como valor de esta propiedad. Los estilos y reemplazos de CSS del generador de sitios no se aplican a este módulo. |

## <a name="billing-address"></a>Dirección de facturación

El módulo de pago permite a los clientes proporcionar una dirección de facturación para su información de pago. También les permite usar su dirección de envío como dirección de facturación, para que el proceso de finalización de compra sea más fácil y rápido. Si la propiedad **Mostrar dirección de facturación** está establecida en **Falso** , el módulo de pago debe configurarse en la página de finalización de compra.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de pago a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de pago solo se puede agregar a un módulo de finalización de compra. Para obtener más información acerca de cómo configurar un módulo de pago para una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md)

[Autenticación segura de clientes mediante Adyen](adyen_redirect.md)
