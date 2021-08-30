---
title: Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B
description: Este tema describe cómo configurar el método de pago de la cuenta del cliente para los sitios de comercio electrónico de empresa a empresa (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 628f3b3b2d86154190dfdcc82b8b391c2facce103f607519514c65b5fba26653
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738062"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar el método de pago de la cuenta del cliente para los sitios de comercio electrónico de empresa a empresa (B2B).

Los minoristas pueden aceptar distintos tipos de pago a cambio de los productos y los servicios que venden en un canal de comercio electrónico. Al configurar el sistema, se deben configurar en Microsoft Dynamics 365 Commerce todos los tipos de pago que acepte un minorista. El método de pago de la cuenta del cliente (o "a cuenta") debe ser compatible con los sitios de comercio electrónico B2B. 

## <a name="prerequisites"></a>Requisitos previos

1. Agregue el método de pago de la cuenta del cliente en la sede central de Commerce.
2. Asocie el método de pago de la cuenta del cliente al canal de comercio electrónico.
3. Asegúrese de que **Permitir a cuenta** está habilitado para el cliente en **Retail y Commerce \> Clientes \> Todos los clientes \> Valores predeterminados de pago** en la sede de Commerce. Asegúrese también de que los parámetros **Límite de crédito** se establezcan de forma adecuada para el cliente en **Retail y Commerce \> Clientes \> Todos los clientes \> Crédito y cobros** en la sede central de Commerce. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce 

Para habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Configuración del sitio \> Extensiones**.
1. Establezca la propiedad **Habilitar pagos de cuenta de cliente** en **Habilitado para clientes de B2B**. 
1. Seleccione **Guardar y publicar**.

> [!NOTE]
> La nueva configuración de sitio solo surtirá efecto cuando se haya actualizado el archivo app.settings.json. Para obtener más información, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Habilite el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B

Para habilitar el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B, siga estos pasos.

1. En el generador de sitios de Commerce, busque y edite la página de pago o el fragmento que contiene el módulo de pago para el sitio de comercio electrónico B2B.
1. En la entrada **Contenedor de la sección de finalización de compra**, seleccione **Agregar módulo** y, a continuación, agregue un módulo **Pago de cuenta de cliente**.
1. Coloque el módulo **Pago de cuenta de cliente** seleccionando los puntos suspensivos (**...**) y seleccionando a continuación **Subir** o **Bajar** según sea necesario.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirmar que el método de pago de la cuenta del cliente se haya habilitado y publicado

Para confirmar que el método de pago de la cuenta del cliente se ha habilitado y publicado, siga estos pasos.

1. Inicie sesión en el sitio de comercio electrónico.
1. Agregue un producto al carro.
1. Vaya a la página de finalización de compra. Verá el nuevo método de pago de **Cuenta de cliente**.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Crear jerarquías de modelado de organización para organizaciones B2B](org-model.md)

[Administrar usuarios socios comerciales en sitios de comercio electrónico B2B](manage-b2b-users.md)

[Establecer límites de cantidad de productos para sitios de comercio electrónico B2B](quantity-limits.md)

[Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]