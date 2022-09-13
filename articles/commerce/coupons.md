---
title: Vales
description: Este artículo proporciona una visión general de las capacidades relacionadas con vales de Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 2594848948b141015adfaa4ec27e2c2b4cc4dcd2
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410779"
---
# <a name="coupons"></a>Vales

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artículo proporciona una visión general de las capacidades relacionadas con vales de Microsoft Dynamics 365 Commerce.

Los vales son códigos y códigos de barras que se usan para agregar descuentos a las transacciones. Los minoristas distribuyen vales a clientes potenciales o existentes para ayudarlos a mejorar el reconocimiento de su marca, impulsar la conversión, retener su base de clientes, impulsar las ventas y, finalmente, aumentar los ingresos. Los vales se han convertido en una de las herramientas de marketing más populares y son una nueva norma en las ventas de comercio electrónico.

En Dynamics 365 Commerce, los vales están vinculados a descuentos y se consideran una validación adicional además de los descuentos. Cada vale está relacionado con un descuento y el descuento vinculado define el conjunto de productos para los que es válido el vale.

Los grupos de precios que están asociados con un descuento definen las condiciones elegibles para las que se puede usar un vale. Esas condiciones incluyen grupos de clientes y canales de venta. Los vales también proporcionan propiedades de **Límite de uso** y **Cliente requerido** que se pueden utilizar para configurar restricciones de uso opcionales.

Cada vale puede tener varios códigos de vale y códigos de barras de vale, y cada código puede tener sus propios intervalo de fechas de vigencia y estado. Si el estado de un código se establece en **Inactivo**, el código no se puede utilizar en ningún canal.

## <a name="set-up-a-coupon"></a>Configurar un vale

Para poder configurar un vale, debe configurar el código de barras del vale y dos secuencias numéricas de vales.

Para configurar un vale en Commerce headquarters, siga estos pasos.

1. Vaya a **Retail y Commerce \> Gestión de inventarios \> Códigos de barras y etiquetas \> Caracteres de máscara**.
1. Seleccione **Agregar** para crear un carácter de máscara del tipo **Código del vale**. En el campo **Carácter** puede seleccionar cualquier carácter no utilizado.
1. Vaya a **Retail y Commerce \> Gestión de inventarios \> Códigos de barras y etiquetas \> Configuración de máscara de código de barras**.
1. Seleccione **Nuevo** para crear una máscara de código de barras del tipo **Vale**.
1. Vaya a **Retail y Commerce \> Gestión de inventarios \> Códigos de barras y etiquetas \> Configuración de código de barras**.
1. Seleccione **Nuevo** para crear un código de barras que utilice la máscara de código de barras que acaba de crear.
1. Vaya a **Administración de la organización \> Secuencias numéricas**.
1. Cree dos secuencias numéricas:

    1. Una secuencia para la referencia de **Número de vale**. Esta secuencia define el identificador único del vale.
    1. Una secuencia para la referencia de **Id. de código de vale**. Esta secuencia define el identificador único de cada código para un vale.

    En ambas secuencias numéricas, debe establecer el campo **Ámbito** a **Empresa**. En la mayoría de los casos, se deben generar automáticamente ambas secuencias numéricas.

1. Vaya a **Parámetros de Commerce \> Precios y descuentos \> Vales**.
1. Establezca el campo **Máscara de código de barras de vale** con el código de barras que creó anteriormente.
1. Vaya a **Parámetros de comercio \> Secuencias numéricas**.
1. Seleccione las secuencias numéricas que creó anteriormente para las referencias **Número de vale** e **Id. de código de vale**.

Para configurar un vale, debe crear el descuento y el vale por separado, y luego vincularlos seleccionando el descuento en el campo **Descuento** de la configuración del vale. Después de vincular un vale a un descuento, los campos **Estado**, **Fecha efectiva** y **Fecha de vencimiento** del descuento vinculado se vuelven de solo lectura, porque los valores están determinados por el estado del vale y el período de validez. Cuando el estado de un vale se establece en **Activo**, el estado del descuento vinculado se actualiza automáticamente a **Habilitado**. Del mismo modo, cuando el estado de un vale se establece en **Inactivo**, el estado del descuento vinculado se actualiza automáticamente a **Deshabilitado**.

## <a name="use-a-coupon"></a>Utilizar un vale

Para agregar un vale a una transacción de venta en el punto de venta (PDV) de Commerce, puede utilizar un código de vale o código de barras de vale. Para usar un código de vale, seleccione la operación **Agregar código de vale** y, a continuación, introduzca el código. Para utilizar un código de barras de vale, puede escanear el código de barras utilizando un dispositivo de escaneado o introducirlo usando el teclado numérico en la pantalla **Transacción**.

Los minoristas a veces quieren que los cajeros puedan ofrecer descuentos de cantidad fija a los clientes por razones de apaciguamiento o debido a defectos del producto, pero no quieren imprimir códigos de vale y distribuirlos a los cajeros. En este caso, puede configurar la opción **Aplicar sin código de vale** para el vale como **Sí**. Los cajeros de PDV pueden usar la función **Aplicar vale** de la operación **Ver descuentos disponibles** para agregar un vale a una transacción sin ingresar manualmente el código. Si existen varios códigos de vale para un vale, el sistema selecciona automáticamente el primer código activo y lo aplica a la transacción.

Para agregar un vale a un pedido de ventas del centro de llamadas, un usuario del centro de llamadas debe seleccionar **Vales** en la pestaña **Administrar** del Panel de acciones en la página de pedidos de ventas.

Para agregar un vale a un pedido de comercio electrónico, el comprador puede ingresar el código de vale en el campo **código promocional** del carrito de la compra.

Después de agregar un vale a un pedido de ventas, el motor de precios desencadena inmediatamente el recálculo de todo el pedido, independientemente de si el cálculo diferido está habilitado.

> [!NOTE]
> En Commerce versión 10.0.30 y anteriores, después de que los usuarios del centro de llamadas agreguen un vale a un pedido de ventas del centro de llamadas, deben seleccionar **Recalcular** en el grupo **Calcular** de la pestaña **Vender** del Panel de acciones para aplicar el descuento asociado con ese vale.

## <a name="coupon-usage-limit"></a>Límite de uso de vales

Los vales se pueden configurar para uso limitado. El límite de uso puede definirse por cliente, por canal o globalmente. El límite de uso se aplica por el código de vale en un vale. Por ejemplo, un vale de un solo uso que tiene dos códigos de vale se puede utilizar dos veces: una vez por cada código de vale.

Los vales se pueden utilizar en todos los canales de venta. Sin embargo, para el centro de llamadas, los vales de uso limitado solo se pueden aplicar cuando el parámetro **Habilitar finalización de pedidos** para el canal del centro de llamadas está habilitado. Si el parámetro **Habilitar finalización de pedidos** está deshabilitado, solo se pueden aplicar vales de uso no limitado.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
