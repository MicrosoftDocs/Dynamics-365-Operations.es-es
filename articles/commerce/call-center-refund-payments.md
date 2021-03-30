---
title: Procesamiento de reembolso de pagos en centros de llamadas
description: Este tema explica cómo se generan los reembolsos de pagos a través de los centros de llamadas cuando se crean devoluciones o cuando se cancelan pedidos o líneas de pedido.
author: hhainesms
manager: annbe
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fd49835a24dc6ec429ac4b01f363f1be937628ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214744"
---
# <a name="refund-payment-processing-in-call-centers"></a>Procesamiento de reembolso de pagos en centros de llamadas

Este tema explica cómo se generan los reembolsos de pagos a través de los centros de llamadas cuando se crean devoluciones o cuando se cancelan pedidos o líneas de pedido.

Un usuario que crea un pedido de devolución para un cliente como usuario de un centro de llamadas en la sede central de Microsoft Dynamics 365 Commerce utiliza la página **Pedido de devolución** para crear la autorización inicial de devolución de materiales (RMA). La RMA define los productos que el cliente desea devolver o cambiar y crea un pedido de ventas de devolución vinculado que tiene un tipo de orden pedido de **Pedido devuelto**. Este pedido devuelto vinculado se utiliza para rastrear la publicación del inventario devuelto y cualquier nota de crédito o reembolso de pago que se registre.

Si la opción **Habilitar finalización del pedido** está configurada en **Sí** para el canal del centro de llamadas, el usuario del centro de llamadas que crea el RMA debe ejecutar el flujo de procesamiento de finalización de pedidos seleccionando **Completar** en la página **Pedido de devolución**. La función **Completar** proporciona un resumen de devolución calculado que describe el importe del reembolso adeudado. Además, cuando está configurado correctamente, crea sistemáticamente una línea de pago de reembolso contra el pedido devuelto.

La lógica del centro de llamadas determina el método de pago para la línea de pago de reembolso, según el método de pago que se utilizó para el pedido original. Si el pedido de devolución que se crea no está vinculado a un pedido original, se aplica un método de pago predeterminado que se toma de un parámetro del sistema.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Cómo un centro de llamadas determina qué método de pago aplicar a un pedido de devolución

El centro de llamadas utiliza el método de pago del pedido original para determinar el método de pago que se debe aplicar a un pedido de devolución. Así es como funciona este proceso para los siguientes métodos de pago originales:

- **Normal** (efectivo) o **Cheque**: cuando un pedido de devolución que se crea hace referencia a un pedido original que se pagó usando el tipo de pago normal (efectivo) o por cheque, la aplicación del centro de llamadas hace referencia a las configuraciones de la página **Métodos de reembolso del centro de llamadas**. Esta página permite a las organizaciones definir, por la divisa del pedido, cómo se emiten los reembolsos a los clientes por pedidos que originalmente se pagaron mediante el tipo de pago normal o por cheque. La página **Métodos de reembolso del centro de llamadas** también permite a las organizaciones seleccionar si se envía al cliente un cheque de reembolso generado por el sistema o si se crea un crédito en la cuenta del cliente contra el saldo interno de la cuenta del cliente. En estos escenarios, la lógica del centro de llamadas hace referencia a la divisa del pedido de devolución y luego usa el valor **Método de pago minorista** para esa divisa, para crear una línea de pago de reembolso el pedido de ventas de devolución. Posteriormente, se vincula a la divisa un diario de pagos de clientes (AR) que utiliza el método de pago AR asignado.

    La siguiente ilustración muestra la configuración de un escenario en el que un cliente devuelve productos de un pedido de ventas que está vinculado a la divisa USD y que originalmente se pagó mediante el tipo de pago normal o por cheque. En este escenario, se emitirá un reembolso al cliente a través de un cheque de reembolso generado por el sistema. El método de pago AR **REF-CHK** se ha configurado como un tipo de pago con cheque de reembolso.

    ![Configuración de los métodos de reembolso del centro de llamadas para pagos originales normales y por cheque](media/callcenterrefundmethods.png)

- **Tarjeta de crédito**: cuando un pedido de devolución que se crea hace referencia a un pedido original que se pagó con una tarjeta de crédito, la lógica del centro de llamadas para los pagos de reembolso aplica la misma tarjeta de crédito original al pedido de devolución.
- **Tarjeta de fidelidad**: cuando un pedido de devolución que se crea hace referencia a un pedido original que se pagó con una tarjeta de fidelidad, la lógica del centro de llamadas para los pagos de reembolso aplica el reembolso a la misma tarjeta de fidelidad.
- **Tarjeta de regalo** (interna): cuando un pedido de devolución que se crea hace referencia a un pedido original que se pagó con una tarjeta regalo emitida desde Dynamics 365 Commerce (funcionalidad de tarjeta de regalo interna), la lógica del centro de llamadas para pagos de reembolso aplica el reembolso al mismo número de tarjeta de regalo original.
- **Tarjeta de regalo** (externa): cuando un pedido de devolución que se crea hace referencia a un pedido original que se pagó con una tarjeta de regalo externa de terceros, la lógica del centro de llamadas para los pagos de reembolso aplica el método de pago de devolución predeterminado que se define en la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**.

Si el tipo de pago del pedido original se desconoce por algún motivo, o si se utilizaron varios métodos de pago para pagar el pedido original, la lógica del centro de llamadas aplica el método de pago de devolución predeterminado que se define en la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**.

La siguiente ilustración muestra el campo **Método de pago** en la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**.

![Campo Método de pago en la pestaña RMA/Devolución de la página Parámetros del centro de llamadas](media/callcenterrefundparameters.png)

> [!NOTE]
> Las reglas de procesamiento de reembolsos que se describen anteriormente también se aplican a los pedidos o líneas de pedidos que un usuario del centro de llamadas cancela en la sede central de Commerce. Si la cancelación de un pedido o unas líneas de pedido específicas ocasiona sobrepagos, se utilizarán las mismas reglas para generar líneas de pago de reembolso.

Normalmente, un pedido de devolución pasa por un proceso estándar, donde el inventario se recibe (o desecha), se contabiliza un albarán contra el pedido de devolución y luego se ejecuta un proceso de contabilización de facturas para el pedido de devolución de ventas. El pedido de devolución de ventas se vincula y se genera sistemáticamente como parte del proceso de creación del pedido de devolución. En escenarios típicos, los reembolsos de pago no se emiten a los clientes hasta que se registra la factura del pedido de devolución de ventas.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Qué sucede cuando se registra una factura en un pedido de devolución de ventas

Los escenarios siguientes explican lo que sucede cuando se registra una factura en un pedido de devolución de ventas:

- Si el pago del reembolso en el pedido de devolución es para una tarjeta de crédito, se invoca una lógica adicional cuando se registra la factura. Esta lógica requiere que el procesador de pagos reembolse el pago a la tarjeta de crédito del cliente. También se crea un vale de pago de reembolso del cliente y se registra sistemáticamente en la cuenta del cliente. Este diario de pagos se liquidará contra el vale de la nota de crédito del pedido de devolución.
- Si el pago de reembolso que se debe emitir es para el tipo de pago con cheque, se crea un vale de pago del cliente que utiliza el método de pago AR, y debe contabilizarse o imprimirse manualmente antes de que el vale de pago pueda contabilizarse en la cuenta del cliente. Para procesar el cheque de reembolso, los usuarios pueden usar la página **Diario de pagos del cliente** en Clientes, o la página especializada **Procesamiento de cheques de reembolso** en página en Retail y Commerce.
- Si el pago del reembolso que debe emitirse es por el tipo de pago interno con tarjeta de regalo o tarjeta de fidelidad, cuando se factura el pedido de devolución, se crea el vale de pago del reembolso y se contabiliza en la cuenta del cliente. Este paso de facturación también devuelve el importe del reembolso al saldo de la tarjeta de regalo o al saldo de puntos de fidelidad del cliente para el que se realiza un seguimiento interno.
- Si un método de pago que utiliza la función **Cliente** (por ejemplo, una cuenta de cliente) está vinculado al pedido de ventas de devolución, las validaciones del límite de crédito se ignoran cuando se procesa el pago. No se crea ni se contabiliza ningún vale de pago en este contexto. Cuando se utiliza un tipo de pago de cliente en un pedido de devolución, el vale de nota de crédito que crea el proceso de contabilización de facturas sirve como vale de crédito del cliente e indica un reembolso al saldo de AR del cliente.

## <a name="advance-credit"></a>Adelantar crédito

Cuando un usuario procesa pedidos de devolución como usuario de un centro de llamadas donde la opción **Habilitar la finalización del pedido** está configurada en **Sí**, puede ocurrir una excepción al proceso descrito anteriormente para la contabilización del pago de reembolso si el usuario del centro de llamadas que está creando el pedido de devolución establece la opción **Crédito anticipado** en **Sí** en la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**. En este caso, el reembolso del pago se produce inmediatamente después de que el pedido de devolución se envía correctamente utilizando la función **Enviar** de la página **Resumen de devolución**. El sistema crea inmediatamente un vale de prepago del cliente de prepago por el valor de devolución, aunque el propio pedido de ventas de devolución aún no se haya facturado. Este enfoque se puede utilizar en situaciones en las que una organización debe emitir reembolsos a los clientes por adelantado debido a problemas de servicio al cliente, y no desea exigir que se reciba el inventario devuelto antes de emitir los reembolsos.

## <a name="replacement-orders"></a>Pedidos de reemplazo

Cuando se emite un pedido de devolución, la función **Pedido de reemplazo** se puede utilizar para generar un nuevo pedido de ventas para el cliente. Este enfoque se puede utilizar en escenarios de intercambio. La función **Pedido de reemplazo** crea otro pedido de ventas para los nuevos artículos que deben enviarse, pero un vínculo de referencia cruzada en la pestaña **RMA/Devolución** de **Parámetros del centro de llamadas** vincula el pedido de reemplazo, el RMA y el pedido de ventas devuelto.

Cuando se procesan los pagos de un pedido de reemplazo, las organizaciones tienen dos opciones:

- Reembolsar al cliente por el pedido de reemplazo, según el método de pago original, y luego cobrar un pago separado por el pedido de reemplazo. No se requiere configuración adicional para utilizar esta opción.
- Seleccione la opción **Aplicar crédito** en **Sí** en la pestaña **RMA/Reemplazo** de la página **Parámetros de centro de llamadas**. En este caso, se aplica sistemáticamente un método de pago del cliente tanto al pedido de devolución como al pedido de reemplazo. Esta opción puede ayudar a evitar que se emita un pago de reembolso externo. También ayuda a evitar cualquier procesamiento de pago en la transacción. Puede ser útil en situaciones en las que se está procesando un intercambio entre iguales y la organización prefiere utilizar el vale de crédito que se genera cuando se factura el pedido de devolución para pagar la factura que se genera con el pedido de reemplazo. Cuando la opción **Aplicar crédito** está configurada en **Sí**, la organización debe liquidar manualmente la nota de crédito contra la factura del pedido de reemplazo después de que se hayan generado ambos documentos financieros.

El valor **Sí** de la opción **Aplicar crédito** es aplicable solo cuando el pedido de devolución esté vinculado a un pedido de reemplazo. En este caso, el método de pago del cliente que se utilizará para pagar sistemáticamente la devolución y el pedido de cambio lo define el campo **Aplicar método de pago de créditos** de la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**. Solo se puede seleccionar en este campo un pago del tipo de pago de la función **Cliente**.

> [!NOTE]
> Para un pedido de devolución que no tiene un pedido de reemplazo vinculado, una configuración de **Sí** para la opción **Aplicar crédito** no tendrá ningún efecto en la lógica de pago del pedido de devolución, porque esta opción se aplica solo a los pedidos de reemplazo.

![Campo Método de pago de aplicación de créditos en la pestaña RMA/Devolución de la página Parámetros del centro de llamadas](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Si los usuarios que crean pedidos de reemplazo planean utilizar la opción **Aplicar crédito**, no deben ejecutar la función **Completar** en el pedido de devolución antes de establecer la opción **Aplicar crédito** en **Sí**. Después de ejecutada la función **Completar**, el pago del reembolso se calcula y se aplica al pedido de ventas de devolución. Cualquier intento de configurar la opción **Aplicar crédito** en **Sí** después de que ya se haya calculado y aplicado un pago de reembolso, no desencadenará un nuevo cálculo del pago de reembolso, y el método de pago seleccionado en el campo **Aplicar método de pago de créditos** no se aplicará. Si la opción **Aplicar crédito** debe usarse en este contexto, el usuario debe eliminar la orden de reemplazo y el RMA, y luego comenzar de nuevo y crear un nuevo RMA. Esta vez, el usuario debe asegurarse de que la opción **Aplicar crédito** esté configurada en **Sí** antes de ejecutarse la función **Completar**.

## <a name="payment-overrides-for-call-center-returns"></a>Anulaciones de pagos para devoluciones del centro de llamadas

Aunque la lógica del centro de llamadas determina sistemáticamente el método de pago del reembolso de la manera que se describe anteriormente en este tema, los usuarios a veces pueden querer anular dichos pagos. Por ejemplo, un usuario puede editar o eliminar líneas de pago de reembolso existentes y aplicar nuevas líneas de pago. Los pagos de reembolso calculados por el sistema solo pueden cambiarlos usuarios que tengan los permisos de anulación correctos. Estos permisos se pueden configurar en la página **Anular permisos** de Retail y Commerce. Para anular el pago de un reembolso, el usuario debe estar vinculado a un rol de seguridad en el que la opción **Permitir pago alternativo** esté configurada en **Sí** en la página **Anular permisos**.

![Permitir una opción de pago alternativa en la página Anular permisos](media/overridepermissions.png)

Alternativamente, una organización puede establecer la opción **Permitir anulación de pagos** en **Sí**, en la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**. En este caso, se debe seleccionar un código de anulación de seguridad en el campo **Código de anulación de seguridad**. El código de anulación de seguridad es un código alfanumérico que debe administrarse externamente, porque los usuarios no pueden verlo en la sede de Commerce una vez configurado. El código de anulación de seguridad solo deben conocerlo unas pocas personas clave y de confianza en una organización. Cuando la opción **Permitir anulación de pago** está configurada en **Sí**, si algún usuario que no tiene los permisos de rol correctos intenta cambiar el método de pago en un pedido de devolución, tendrá la opción de introducir el código de anulación de seguridad. Si no lo saben, o si un gerente o supervisor no pueden introducirlo en la página, no podrán anular el método de pago de devolución.

> [!NOTE]
> Si el código de anulación de seguridad se pierde u olvida, la organización tendrá que restablecerlo definiendo un nuevo código de anulación de seguridad en el campo **Código de anulación de seguridad** de la pestaña **RMA/Devolución** de la página **Parámetros del centro de llamadas**.

![Parámetros de anulación de pago en la pestaña RMA/Devolución de la página Parámetros del centro de llamadas](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Antes de que las organizaciones intenten anular los pagos de reembolsos que utilizan tipos de pago con tarjeta de crédito, deben verificar que su procesador de tarjetas de crédito permita devoluciones no vinculadas. Muchos procesadores requieren que los reembolsos se registren en la tarjeta original. Cualquier intento de emitir un reembolso a una tarjeta que no tenga capturas previas podrá provocar errores de contabilidad en el procesador.

## <a name="additional-resources"></a>Recursos adicionales

[Métodos de pago en centros de llamadas](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]