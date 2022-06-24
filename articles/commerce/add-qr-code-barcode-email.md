---
title: Agregar un código QR o un código de barras a los correos electrónicos transaccionales y de recibos
description: Este artículo explica cómo insertar códigos QR y códigos de barras que representan id. de pedidos en correos electrónicos transaccionales y de recibos en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ffa0009c55b5322b209b19692952c2e0704f65c9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872893"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Agregar un código QR o un código de barras a los correos electrónicos transaccionales y de recibos

[!include [banner](includes/banner.md)]

Este artículo explica cómo insertar códigos QR y códigos de barras que representan id. de pedidos en correos electrónicos transaccionales y de recibos en Microsoft Dynamics 365 Commerce.

Puede incluir fácilmente códigos QR y códigos de barras en correos electrónicos transaccionales para ayudar a acelerar el proceso de búsqueda de pedidos en un entorno minorista. Para insertar códigos QR y códigos de barras en correos electrónicos, utilice una etiqueta HTML **\<img\>** que solicita un código QR o una imagen de código de barras de un servicio de generación y representación. Microsoft no proporciona este servicio. Sin embargo, existen muchos servicios gratuitos o económicos que pueden servir códigos QR o códigos de barras que se generan dinámicamente en función de un valor que se pasa en una cadena de consulta.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Agregar un código QR o un código de barras a un correo electrónico transaccional

Para insertar un código QR o un código de barras en un correo electrónico transaccional que se envía como parte de una compra de comercio electrónico, siga estos pasos.

1. Abra el HTML de origen para la plantilla de correo electrónico transaccional y agregue una etiqueta HTML **\<img\>** que apunte a su código QR o servicio de código de barras. He aquí un ejemplo.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    A continuación se ofrece una explicación del ejemplo anterior:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representa el dominio de su servicio de códigos QR o códigos de barras.
    - **data** representa el parámetro que utiliza el código QR o el servicio de código de barras para recibir el contenido que debe mostrarse como un código QR o código de barras.

        El valor **%salesid%** debe asignarse a este parámetro. En este ejemplo, observe que el valor también se usa como texto alternativo para la imagen.

    - **param1** y **param2** representan parámetros opcionales adicionales.

1. Vaya a **Comercio minorista y Commerce \> Configuración de la sede \> Parámetros \> Plantillas de correo electrónico de organización** y cargue el HTML actualizado en la plantilla de correo electrónico transaccional correspondiente.

> [!NOTE]
> Los parámetros pueden diferir entre los proveedores de servicios de códigos QR y códigos de barras. Por lo tanto, asegúrese de contactar con su proveedor de servicios para confirmar los parámetros a los que debe asignar valores.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Agregar un código QR o un código de barras a un correo electrónico de recibo 

Para insertar un código QR o un código de barras en un correo electrónico de recibo que se puede enviar después de realizar una compra en el punto de venta (PDV), siga estos pasos.

1. Abra el HTML de origen para la plantilla de correo electrónico de recibo y agregue una etiqueta HTML **\<img\>** que apunte a su código QR o servicio de código de barras. A continuación viene un ejemplo.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    A continuación se ofrece una explicación del ejemplo anterior:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representa el dominio de su servicio de códigos QR o códigos de barras.
    - **data** representa el parámetro que utiliza el código QR o el servicio de código de barras para recibir el contenido que debe mostrarse como un código QR o código de barras.

        El valor **%receiptid%** debe asignarse a este parámetro. En este ejemplo, observe que el valor también se usa como texto alternativo para la imagen.

    - **param1** y **param2** representan parámetros opcionales adicionales.

1. Vaya a **Comercio minorista y Commerce \> Configuración de la sede \> Parámetros \> Plantillas de correo electrónico de organización** y cargue el HTML actualizado en la plantilla de correo electrónico que tenga el id. de correo **emailrecpt**.

> [!NOTE]
> Los parámetros pueden diferir entre los proveedores de servicios de códigos QR y códigos de barras. Por lo tanto, asegúrese de contactar con su proveedor de servicios para confirmar los parámetros a los que debe asignar valores.

## <a name="additional-resources"></a>Recursos adicionales

[Enviar recibos por correo electrónico desde Modern PDV (MPOS)](email-receipts.md)

[Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md)
