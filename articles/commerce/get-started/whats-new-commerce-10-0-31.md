---
title: Versión preliminar de Dynamics 365 Commerce 10.0.31 (febrero de 2023)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 05ccd9794ffeba6a09d6fec0a57ffad2b59707ad
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709865"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Versión preliminar de Dynamics 365 Commerce 10.0.31 (febrero de 2023)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Commerce versión de vista previa 10.0.31. Esta versión tiene el número de compilación 10.0.1406 y está disponible con la siguiente programación:

- **Versión preliminar:** octubre de 2022
- **Disponibilidad general de la versión (actualización automática):** enero de 2023
- **Disponibilidad general de la versión (actualización automática):** febrero de 2023

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Códigos de error | Commerce ha introducido referencias de error estandarizadas para incluir en los errores de pago del canal en línea que se presentan a los compradores en línea.| [Códigos de error del módulo de finalización de la compra](../checkout-module-error-codes.md)  | Activado de forma predeterminada |
| Pagos | [Habilitar Apple Pay con el Conector de pago de Dynamics 365 para Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | Los clientes de comercio electrónico pueden usar Apple Pay en el carrito y en las páginas de pago cuando usan dispositivos o navegadores compatibles. | Participación de desarrolladores |
| Pagos  |  Commerce agregó la capacidad de limitar la forma en que los usuarios interactúan con tokens de pago recurrentes en la interfaz de usuario de Commerce headquarters. Formas de pago, como la página **Orden de venta del centro de llamadas**, ya no muestra el token de pago recurrente utilizado previamente por un cliente para su uso en una nueva transacción. Solo una entrada determinada de "tarjeta en archivo" en la pantalla **Pagos de clientes** de Commerce, o con un acuerdo con un cliente mientras paga a través de una orden de venta, se presentará a los usuarios del centro de llamadas o de Commerce headquarters al procesar un pago para una nueva transacción. | [Limitar el uso del símbolo (token) de pago](../dev-itpro/limit-token-usage.md)  |  Administración de características<p>*Restringir el uso de token de pago al contexto de pedido*  |
| PDV | [Crear pedidos de compra desde PDV](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Se mejoró la operación de inventario entrante en la aplicación de punto de venta (PDV) para permitir a los usuarios crear, editar y confirmar solicitudes de órdenes de compra. |  Administración de características<p>*Capacidad de crear una solicitud de pedido de compra en el PDV*   |



## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Commerce 10.0.31 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.31 de aplicaciones de finanzas y operaciones (febrero de 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.31, inicie sesión en Microsoft Dynamics Lifecycle Services y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022](/dynamics365-release-plan/2022wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-commerce-features"></a>Funciones de Commerce eliminadas y obsoletas

El artículo [Funciones eliminadas o obsoletas en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) describe las características que se han eliminado o están obsoletas para Commerce.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes de su eliminación.


Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
