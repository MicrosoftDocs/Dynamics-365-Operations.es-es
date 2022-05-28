---
title: Configuración, autorización y captura de tarjetas de crédito
description: Este artículo proporciona información general de la autorización de la tarjeta de crédito en Microsoft Dynamics 365 Finance. Incluye información acerca de cómo configurar un servicio de pago, agregar una tarjeta de crédito a un pedido de ventas y anular una autorización.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d363b8a909855d3495d78b8721e467d3f78ebbd6
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714016"
---
# <a name="credit-card-setup-authorization-and-capture"></a>Configuración, autorización y captura de tarjetas de crédito

[!include [banner](../includes/banner.md)]

Este artículo proporciona información general de la autorización de la tarjeta de crédito en Microsoft Dynamics 365 Finance. Incluye información acerca de cómo configurar un servicio de pago, agregar una tarjeta de crédito a un pedido de ventas y anular una autorización.

## <a name="setting-up-the-credit-card-payment-service"></a>Configuración del servicio de pago con tarjeta de crédito

Para usar tarjetas de crédito debe configurar y activar un servicio de pago en la página Servicios de pago. Un servicio de pago actúa como puente entre su entidad jurídica y el banco que procesa los gastos de tarjeta de crédito del cliente. Debe trabajar con un proveedor de tarjetas de crédito incluido en el campo Conector de pago y configurar una cuenta con dicho proveedor. A continuación debe configurar las demás opciones de la página Servicios de pago, configurar los tipos de tarjeta de crédito para American Express, Discover y Mastercard en la página Tipos de tarjetas de crédito, y activar el proveedor como proveedor predeterminado. También debe seguir estos pasos para completar su configuración:
-   En la página Parámetros de clientes, especifique los parámetros para usar autorizaciones de tarjeta de crédito.
-   Configure las condiciones de pago para la tarjeta en la página Condiciones de pago. En el campo Tipo de pago, seleccione Tarjeta de crédito.
-   En la página Tarjetas de crédito del cliente, especifique los datos de tarjeta de crédito de los clientes.

## <a name="adding-a-new-credit-card"></a>Adición de una nueva tarjeta de crédito
Puede crear nuevos registros de tarjeta de crédito nuevos en la página Clientes a través de Cliente, Configuración, Tarjeta de crédito. También puede crear registros de tarjeta de crédito al especificar pedidos de ventas en la página Pedido de ventas, mediante Gestionar, Cliente, Tarjeta de crédito, Registro.

## <a name="adding-a-credit-card-to-a-sales-order"></a>Adición de una tarjeta de crédito a un pedido de ventas

Puede agregar una tarjeta de crédito a un pedido de ventas seleccionando una tarjeta de crédito en la búsqueda de tarjetas de crédito en la ficha desplegable Precio y descuentos de la página Pedido de ventas. Para iniciar el proceso de autorización, en el panel de acciones, en la ficha Gestionar, seleccione Tarjeta de crédito y Autorizar.

## <a name="authorizing-a-credit-card"></a>Autorización de una tarjeta de crédito

Cuando se autoriza una tarjeta de crédito, se verifica el número de la tarjeta y la identidad de su titular, y se confirma además el saldo de crédito disponible. Opcionalmente, se verifican el valor de verificación de tarjetas y la dirección del titular. A continuación, se carga el importe de la factura en la cuenta del cliente, descontándolo del saldo de crédito disponible. El servicio de pago envía información acerca de la aprobación o rechazo de la tarjeta de crédito. Cuando se factura el pedido de ventas, se carga (captura) el importe de la factura en la tarjeta de crédito.

### <a name="card-verification-value"></a>Código de seguridad de la tarjeta

Puede requerir el valor de la verificación de la tarjeta, en ocasiones llamado "código de seguridad". Para American Express, es un valor de cuatro dígitos. En Discover, MasterCard y Visa, es un valor de tres dígitos.

### <a name="address-verification"></a>Comprobación de dirección

La información de verificación de la dirección se envía siempre al proveedor de pagos. Puede decidir la cantidad de información requerida para aceptar una transacción. Asegúrese de confirmar con su proveedor si acepta esta información. Estas son las opciones para verificación de direcciones:
-   **Aceptar siempre la transacción**: se acepta la transacción, independientemente de los resultados de la comprobación de la dirección.
-   **Titular de la cuenta**: se compara el nombre del titular de la tarjeta de crédito en la transacción con la información de la empresa de la tarjeta de crédito.
-   **Dirección de facturación**: se compara el nombre y la dirección de facturación del titular para la transacción con la información de empresa de la tarjeta de crédito.
-   **Código postal de facturación**: se compara el nombre, la dirección de facturación y el código postal del titular para la transacción con la información de empresa de la tarjeta de crédito.

## <a name="data-support"></a>Soporte de datos
Para cada tipo de tarjeta de crédito se que admita, puede especificar el nivel de soporte de datos. El nivel controla la cantidad de información sobre una transacción que se transfiere al servicio de pago. Asegúrese de confirmar con su proveedor si puede proporcionar esta información. Estas son las opciones para el nivel de aceptación de datos:
-   **Nivel 1**: se transfiere la fecha de transacción, el importe de la transacción y una descripción.
-   **Nivel 2**: se transfiere toda la información de nivel 1, más el envío y las direcciones mercantiles, así como la información fiscal.
-   **Nivel 3**: se transfiere toda la información del nivel 2, más información de la línea de pedido.

## <a name="partial-payments"></a>Pagos parciales
Si se envía parte de un pedido, el importe del pedido parcial se captura, y se cierra la autorización, obtenida para el importe del pedido en su totalidad. A continuación, se envía una nueva autorización para el importe restante del pedido que no se ha enviado.

## <a name="voiding-an-authorization"></a>Anulación de una autorización 
Para anular una autorización de tarjeta de crédito puede cambiar el método de pago a otro método que no sea del tipo Tarjeta de crédito.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
