---
title: Configuración de precios
description: Este artículo describe las diversas configuraciones para la gestión de precios y descuentos en Microsoft Dynamics 365 Commerce headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 79130e0ef285d6bd5e544f2d6a6368c0393fa7fa
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474052"
---
# <a name="pricing-settings"></a>Configuración de precios

[!include [banner](../includes/banner.md)]

Este artículo describe las diversas configuraciones para la gestión de precios y descuentos en Microsoft Dynamics 365 Commerce headquarters. Esta configuración permite a las organizaciones definir el comportamiento de los precios en su solución de Commerce para satisfacer necesidades comerciales específicas.

## <a name="company-level-pricing-settings"></a>Configuración de precios a nivel de empresa

La mayoría de las configuraciones de precios son a nivel de empresa y se pueden encontrar en **Parámetros de Commerce \> Precios y descuentos** en Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Modelo de control de concurrencia de mejor precio o combinado

El ajuste **Modelo de control de concurrencia de mejor precio o combinado** determina cómo el motor de precios procesa múltiples descuentos en el modelo de descuento **mejor precio** o **combinado**. 

Si el parámetro se establece en **Mejor precio y compuesto dentro de la prioridad, nunca se compone entre prioridades**, todos los descuentos **combinados** que tienen la misma prioridad de precios se combinan. El resultado combinado compite con cualquier descuento de **mejor precio** que tenga la misma prioridad de precios, se aplica el mejor precio y se ignoran todos los descuentos que tienen una prioridad de precios más baja.

Si el parámetro se establece como **Mejor precio solo dentro de la prioridad, siempre se compone entre prioridades**, todos los descuentos **combinados** se tratan como descuentos de **mejor precio**. En una prioridad de precios, solo gana un único descuento. Si ese único descuento es un descuento de **mejor precio** o **combinado**, se combina con todos los descuentos de **mejor precio** o **combinados** que tengan una prioridad de precios más baja.

### <a name="discount-compound-behavior"></a>Comportamiento de descuento combinado

El ajuste **Comportamiento de descuento combinado** determina cómo el motor de precios calcula múltiples descuentos combinados.

Si el parámetro se establece en **Combinado**, se aplica un descuento sobre otro de forma acumulativa. Si está configurado como **Compuesto en el precio original**, todos los descuentos se tratan de forma independiente y se aplican al mismo precio original.

Por ejemplo, usted desea combinar descuentos del 10 por ciento y del 20 por ciento para un producto que tiene un precio original de 100 $. Si configura el parámetro **Comportamiento de descuento combinado** como **Combinado**, el precio final será 72 $ (100 $ &times; 90 % &times; 80 %). Si lo configura como **Compuesto en el precio original**, el precio final será 70 $ (100 $ – 10 $ – 20 $).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Habilitar la competencia entre el umbral exclusivo y otros descuentos periódicos

Si el parámetro **Habilitar la competencia entre el umbral exclusivo y otros descuentos periódicos** se establece en **Sí**, el motor de precios hace que los descuentos de umbral exclusivos compitan con descuentos exclusivos sin umbral. Se sigue aplicando la prioridad de precios. El comportamiento de descuentos de umbral de **mejor precio** y **combinado** se mantiene como está. En otras palabras, no compiten con los descuentos sin umbral.

### <a name="manual-line-discount-and-system-discount"></a>Descuento de línea manual y descuento del sistema

El parámetro **Descuento de línea manual y descuento del sistema** determina cómo el motor de precios aplica un descuento de línea manual y un descuento del sistema a la misma línea. El descuento de línea manual se puede combinar sobre el descuento del sistema o puede reemplazar el descuento del sistema. Cuando se combinan el descuento de línea manual y el descuento del sistema, la lógica de cálculo respeta el ajuste **Comportamiento de descuento combinado**. Un descuento total manual que se aplica a todo el pedido no respeta esa configuración.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Mantenga los artículos en la misma línea de ventas para redondear el precio con descuento

A veces, el importe de un descuento por cantidad no se puede dividir por igual entre la cantidad de calificación (por ejemplo, si el importe del descuento es 10 $ menos por tres unidades compradas). En estos casos, el parámetro **Mantenga los artículos en la misma línea de ventas para redondear el precio con descuento** determina cómo el motor de precios aplica y distribuye el importe del descuento. Si el parámetro se establece en **Sí**, el importe del descuento se aplica como un todo y no se divide. Si está configurado como **No**, el importe del descuento se divide entre la cantidad de calificación y se redondea. Por ejemplo, una cantidad de descuento de 10 $ de descuento para tres unidades se divide en 3,33 $ de descuento para una unidad, 3,33 $ de descuento para la segunda unidad y 3,34 $ de descuento para la tercera unidad.

### <a name="apply-discounts-to-key-in-price-products"></a>Aplicar descuentos a productos con precio marcado

El parámetro **Aplicar descuentos a productos con precio marcado** determina si los descuentos se pueden aplicar junto con precios marcados que se ingresan en el punto de venta (POS). El parámetro **Especificar precio** en la configuración del producto determina si un producto admite el precio marcado y cómo.

### <a name="apply-discounts-to-price-overrides"></a>Aplicar descuentos a anulaciones de precios

El parámetro **Aplicar descuentos a anulaciones de precios** determina si se pueden aplicar descuentos junto con anulaciones de precios.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Distribuir descuentos para los descuentos menos caros

Para los descuentos combinados que usan el tipo de cálculo "menos caro", el ajuste **Distribuir descuentos para los descuentos menos caros** determina si el motor de precios distribuye el descuento entre líneas.

Si el parámetro se establece en **No**, el descuento se aplica solo a las líneas menos caras. Por ejemplo, para un descuento combinado "compre 2 y obtenga 1 gratis", el artículo menos costoso será gratis y los otros dos artículos se mantendrán a precio completo. En este caso, un cliente que devuelva ambos artículos a precio completo seguirá recibiendo el tercer artículo gratis. Este escenario podría causar una pérdida para el distribuidor.

Si el parámetro se establece en **Sí**, el motor de precios distribuye el descuento entre todas las líneas aplicables. Esta configuración puede ayudar a reducir la pérdida en las devoluciones.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Calcular precios y descuentos multicanal de forma manual

El parámetro **Calcular precios y descuentos multicanal de forma manual** controla si el motor de precios utiliza el cálculo de descuentos y precios diferidos para la aplicación PDV y el canal del centro de llamadas. Si el parámetro se establece en **Sí**, el motor de precios no calcula de inmediato los descuentos de varias líneas (como descuentos por cantidad, descuentos de umbral y descuentos combinados) cada vez que se crea o edita un pedido de ventas en la aplicación PDV o el canal del centro de llamadas.

> [!NOTE]
> En Commerce versión 10.0.30 y anteriores, el parámetro **Calcular precios y descuentos multicanal de forma manual** controla solo el canal del centro de llamadas. Un parámetro aparte **Calcular manualmente múltiples descuentos de artículos** en el perfil de funcionalidad controla el comportamiento de cálculo de precios de la aplicación PDV. En Commerce versión 10.0.31, las dos configuraciones se consolidan en una configuración a nivel de empresa.

### <a name="retention-period-in-days"></a>Período máximo de retención en días

El parámetro **Período máximo de retención en días** indica cuántos días después de la fecha de vencimiento (si se establece una fecha de vencimiento) o la fecha de desactivación (si no se establece una fecha de vencimiento) se debe eliminar sistemáticamente un descuento. Si el parámetro se establece en **0** (cero), no se produce ninguna eliminación automática.

> [!NOTE]
> En Commerce versión 10.0.30 y anteriores, esta configuración se llama **Número de días después de los cuales deben eliminarse los descuentos vencidos**.

### <a name="coupon-bar-code"></a>Código de barras de vale

El parámetro **Código de barras de vale** determina qué código de barras específico se utiliza para generar códigos de barras de vale. Los usuarios pueden seleccionar uno de los códigos de barras predefinidos que están configurados en la página **Configuración de código de barras**. Para obtener más información acerca de los códigos de barras y las máscaras de códigos de barras, consulte [Configurar códigos de barras](set-up-bar-codes.md) y [Configurar máscaras de código de barras](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>El código del vale debe aplicarse manualmente a las transacciones de devolución

El parámetro **El código del vale debe aplicarse manualmente a las transacciones de devolución** solo se aplica a las transacciones de devolución para las que no se proporciona un recibo de venta. Establezca el parámetro en **No** si los códigos de vale se deben aplicar automáticamente a la transacción. Configúrelo en **Sí** si los códigos de vale deben agregarse manualmente a la transacción.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Usar acuerdos de venta configurados para la organización

Para pedidos de empresa a empresa (B2B), si el parámetro **Usar acuerdos de venta configurados para la organización** se establece en **Sí**, el motor de precios utiliza los acuerdos de venta definidos para la organización en la jerarquía de clientes del usuario para determinar el precio basado en el contrato. Si el parámetro se establece en **No** o si la jerarquía de clientes no está definida, el motor de precios busca acuerdos de venta definidos para que el usuario determine el precio basado en el contrato. Para obtener más información acerca de las jerarquías de clientes para comercio electrónico B2B, consulte [Administrar socios comerciales B2B utilizando jerarquías de clientes](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Configuración de precios a nivel de canal

La siguiente configuración permite a las organizaciones controlar el comportamiento de los precios en canales de venta específicos.

### <a name="enable-order-price-control"></a>Habilitar control de precios de pedidos

El parámetro **Habilitar control de precios de pedidos** se encuentra en la ficha rápida **General** de la página **Configuración del centro de llamadas**. La configuración determina si el motor de precios impone una restricción en la operación de anulación de precios en el canal del centro de llamadas. Funciona en conjunto con el ajuste a nivel de producto **Permitir ajuste de precios**.

Si el control de precios de pedidos está desactivado, cualquier usuario del centro de llamadas puede realizar cambios de precios en las líneas de ventas en el canal del centro de llamadas, independientemente de si los productos correspondientes permiten el ajuste de precios.

Si el control de precios de pedidos está activado, solo los productos en los que está establecido el parámetro **Permitir ajuste de precio** se establece en **Sí** permitir anulaciones de precios en los pedidos de venta del canal del centro de llamadas, y se debe proporcionar un código de motivo en las líneas de ventas correspondientes. Un usuario del centro de llamadas puede cambiar el precio de venta solo hasta el valor de **Porcentaje de margen de beneficio de coste** que se define en **Retail y Commerce \> Configuración de canales \> Configuración del centro de llamadas \> Anular permisos**. Si una anulación de precios supera ese porcentaje, el usuario debe enviar una solicitud, que luego se procesa a través de un flujo de trabajo predefinido de Commerce para su revisión y aprobación. Para obtener más información sobre flujos de trabajo de Commerce, consulte [Visión general del sistema de flujos de trabajo](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Configuración de precios a nivel de producto

Las siguientes configuraciones imponen reglas de precios a nivel de producto y se pueden encontrar en la página **Configuración del producto** de una organización.

### <a name="allow-price-adjust"></a>Permitir ajuste de precios

Si el parámetro **Permitir ajuste de precio** se establece en **Sí**, se puede aplicar una anulación de precios al producto en los pedidos de venta del canal del centro de llamadas.

### <a name="key-in-price"></a>Especificar precio

El parámetro **Especificar precio** determina si es obligatorio un precio marcado cuando se agrega un producto a una transacción de venta en PDV. También define las restricciones de valor de precio correspondientes.

### <a name="zero-price-valid"></a>Precio cero válido

El parámetro **Precio cero válido** determina si los precios de venta predefinidos, calculados por el sistema o ajustados manualmente para un producto pueden ser 0 (cero). Establezca el parámetro en **Sí** si se permite un precio de cero. Este valor también se puede especificar al nivel de categoría desde la jerarquía de productos de Commerce.

### <a name="prevent-all-discounts"></a>Evite todos los descuentos

Al establecer el parámetro **Evite todos los descuentos** como **Sí**, evita que se apliquen todos los tipos de descuentos (incluidos los descuentos manuales) a un producto. Este valor también se puede especificar al nivel de categoría desde la jerarquía de productos de Commerce.

> [!NOTE]
> Este ajuste no limita la operación de la anulación de precio, ya que esa operación establece el precio base y no se trata como un descuento.

### <a name="prevent-manual-discounts"></a>Evitar los descuentos manuales

Al establecer el parámetro **Evitar los descuentos manuales** como **Sí**, evita que se apliquen descuentos manuales de la línea o la transacción a un producto. Todos los demás descuentos aún se pueden aplicar. Este valor también se puede especificar al nivel de categoría desde la jerarquía de productos de Commerce.

> [!NOTE]
> Este ajuste no limita la operación de la anulación de precio, ya que esa operación establece el precio base y no se trata como un descuento.

### <a name="prevent-retail-discounts"></a>Evitar descuentos comerciales

Si el parámetro **Evitar descuentos comerciales** se establece en **Sí**, no se pueden aplicar los descuentos **simples**, **por cantidad**, **por umbral**, **combinados** y **de envío** a un producto. Todos los demás descuentos (incluidos los descuentos manuales) se siguen pudiendo aplicar.

### <a name="prevent-tender-based-discounts"></a>Evitar descuentos basados en formas de pago

Si el parámetro **Evitar descuentos basados en formas de pago** se establece en **Sí**, no se podrá aplicar un descuento **basado en formas de pago** a un producto. Todos los demás descuentos (incluidos los descuentos manuales) se siguen pudiendo aplicar.

Los minoristas eligen a menudo excluir algunos productos, como artículos nuevos o artículos con demanda, de los descuentos basados en artículos (como descuentos simples o descuentos por cantidad). Sin embargo, pueden seguir aplicando descuentos basados en la forma de pago si un cliente paga mediante la forma de pago preferida. Para conseguir este resultado, los minoristas pueden establecer los parámetros **Evite todos los descuentos** y **Evitar descuentos basados en la forma de pago** como **No**, y los parámetros **Evitar los descuentos al por menor** y **Evitar los descuentos manuales** como **Sí**.

## <a name="deprecated-or-removed-settings"></a>Parámetros quitados o en desuso

La siguiente configuración de precios se eliminó o se planea eliminar de Dynamics 365 Commerce.

| Configuración | Motivo de la eliminación o del desuso | Estado de desuso o eliminación |
|---------|-----------------------------------|-------------------------------|
| Control de descuentos superpuestos | Proporcionamos esta configuración en los parámetros de Commerce para controlar cómo el motor de precios busca y determina la mejor combinación de descuento para aplicar. La opción **Mejor descuento** fuerza todas las posibles combinaciones de descuento durante el cálculo del precio. La opción **Mejor rendimiento** es una opción optimizada que utiliza un algoritmo heurístico avanzado y un método de clasificación de valor marginal para priorizar, evaluar y determinar la mejor combinación de descuentos de manera oportuna. La opción **Cálculo equilibrado** de la base de código funciona igual que **Mejor rendimiento**. Por lo tanto, es esencialmente una opción duplicada. Para ayudar a mejorar el rendimiento, el motor de precios se actualizó para que use solo **Mejor rendimiento** como opción estándar. Por tanto, esta configuración ya no es aplicable. | En desuso en la versión 10.0.21 y se eliminará en octubre de 2022. |
| Permitir que los ajustes de precios incrementen el precio del producto | Proporcionamos esta configuración para controlar si la función de ajuste de precios puede aumentar los precios del producto. Si el parámetro está desactivado, las organizaciones pueden utilizar la función de ajuste de precios solo para establecer el precio unitario de un producto, de forma que quede por debajo del precio base y el precio de venta del acuerdo comercial. Rechazamos esta configuración porque la función de ajuste de precios se actualizó para admitir ajustes bidireccionales (aumento o disminución) listos para usar. | En desuso en la versión 10.0.30 y se eliminará en octubre de 2023. |
| Habilitar informe de precios para tienda | Proporcionamos esta configuración para controlar si la función **Informe de precios** está disponible para su uso en la página de configuración de la tienda. Rechazamos esta configuración porque la página de configuración de la tienda se ha actualizado para proporcionar siempre **Informe de precios** como función estándar. | En desuso en la versión 10.0.31 y se eliminará en octubre de 2023. |
| Use la fecha de hoy para calcular los precios | El motor de precios de Dynamics 365 Supply Chain Management admite el cálculo de precios basado en la fecha de envío solicitada o la fecha de recepción solicitada, junto con la fecha actual. El motor de precios de Commerce solo admite el cálculo de precios que se basa en la fecha de hoy. Para los clientes que usan las capacidades de Supply Chain Management y Commerce, proporcionamos esta configuración y recomendamos que los clientes siempre la establezcan en **Sí** para que los dos motores de precios puedan trabajar juntos. Rechazamos esta configuración porque no cambia fundamentalmente el comportamiento del cálculo y, por tanto, es redundante. | En desuso en la versión 10.0.31 y se eliminará en octubre de 2023. |
| Precio máximo | Proporcionamos esta configuración en el perfil de funcionalidad para controlar si solo los productos que tienen un precio de venta inferior al precio máximo especificado se pueden vender a través de PDV en tiendas específicas. Rechazamos esta configuración debido al bajo uso de funciones. | En desuso en la versión 10.0.31 y se eliminará en octubre de 2023. |
| Aplicar descuentos a precio unitario | Esta configuración estaba destinada a controlar si los precios y los descuentos se redondean al nivel de precio unitario o al nivel de línea de ventas durante el cálculo de precios. La rechazamos porque no se consume en ninguna parte del código base actual. | En desuso en la versión 10.0.31 y se eliminará en octubre de 2023. |
| Calcular manualmente múltiples descuentos de artículos | Proporcionamos esta configuración para controlar si el motor de precios usa el cálculo de precios diferido para el canal de tienda minorista. Si el parámetro se establece en **Sí**, el motor de precios no calcula de inmediato los descuentos de varias líneas (como descuentos por cantidad, descuentos de umbral y descuentos combinados) cada vez que se crea o edita un pedido de ventas en la aplicación PDV. Decidimos consolidar esta configuración con una configuración similar en los parámetros de Commerce para hacer un control omnicanal. | En desuso en la versión 10.0.31 y se eliminará en octubre de 2023. |

Para obtener una lista completa de las funciones eliminadas o en desuso en Dynamics 365 Commerce, vea [Características eliminadas o en desuso en Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
