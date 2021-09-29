---
title: Retrasar el cálculo del precio exacto y el descuento para mejorar el rendimiento
description: Este tema describe la capacidad de cálculo de precio diferido que está disponible en el punto de venta (PDV) y centro de llamadas de Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8c4264c3a4c71e6aab0e1ef8d7d8cfffad065a46
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488372"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Retrasar el cálculo del precio exacto y el descuento para mejorar el rendimiento

[!include [banner](includes/banner.md)]

Este tema describe la capacidad de cálculo de precio diferido que está disponible en el punto de venta (PDV) y centro de llamadas de Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce admite la creación de descuentos multilínea que se aplican cuando se combinan varias líneas de venta de un pedido de venta o presupuesto de venta. Estos descuentos incluyen descuentos por combinación y coincidencia, por umbral y por cantidad.

Siempre que se agrega una nueva línea a un pedido, el motor de precios de Commerce evalúa todo el carrito para determinar si se puede aplicar alguno de estos descuentos de varias líneas. Debido a este nuevo cálculo, la adición de nuevas líneas puede afectar el rendimiento a medida que crece un pedido de ventas.

Sin embargo, las empresas con negocios de empresa a empresa (B2B) y algunas empresas con negocios de empresa a consumidor (B2C) suelen tener pedidos de gran tamaño. Por lo tanto, puede llevar mucho tiempo esperar a que el motor de precios vuelva a calcular después de agregar cada artículo al carrito. Además, para pedidos grandes, generalmente no es muy importante que el precio exacto y el descuento se muestren cada vez que se agrega un artículo al carrito. Es más importante que los usuarios puedan agregar elementos rápidamente. La capacidad de retrasar el cálculo exacto del precio y el descuento hasta que un usuario lo solicite o se finalice un pedido puede mejorar significativamente el rendimiento. También puede reducir el tiempo necesario para terminar de realizar un pedido.

La capacidad de retrasar el cálculo exacto del precio y el descuento ha estado disponible en los PDV desde hace mucho tiempo. A partir de la versión 10.0.22 de Commerce, también está disponible para el centro de llamadas.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Habilitar el cálculo de descuento y precio retrasado para PDV

Para habilitar el cálculo de descuento y precio retrasado para PDV, siga estos pasos.

1. En la sede de Commerce, vaya al perfil de funcionalidad que está asociado con la tienda física.
1. En la ficha desplegable **Importe**, habilite la configuración **Calcular manualmente los descuentos de varios artículos**.
1. Abra el diseñador de diseño de pantalla para los registros donde se debe habilitar el cálculo retrasado.
1. Agregue un botón para la operación **Calcular total** a la cuadrícula de botones deseada.
1. Ejecute las tareas **1070** y **1090**.

Ahora, cuando se agregan artículos a una transacción, los descuentos de varias líneas no se calculan a menos que el cajero seleccione el botón **Calcular total**. Después de seleccionar **Calcular total** para una transacción, los descuentos multilínea siempre se calcularán para ella. El cajero no tendrá que volver a seleccionar el botón, incluso si se agregan artículos adicionales al carrito. El sistema no permitirá que el cajero capture el pago hasta seleccionar **Calcular total**.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Habilitar el cálculo de descuento y precio retrasado para centro de llamadas

Para habilitar el cálculo de descuento y precio retrasado para centro de llamadas, siga estos pasos.

1. En la sede central de Commerce, vaya a **Espacios de trabajo \> Administración de características**.
1. Habilite la característica **Evitar el cálculo de precios no intencionado para pedidos comerciales**. Esta característica es un requisito previo para la capacidad de cálculo de descuento y precio retrasado.

    > [!NOTE]
    > Para nuevas implementaciones, la función **Evitar el cálculo de precios no intencionado para pedidos comerciales** está habilitada de forma predeterminada.

1. Vaya a **Parámetros de Commerce \> Precios y descuentos**.
1. En la sección **Diversos**, habilite la configuración **Calcular manualmente precios y descuentos de varias líneas**.

Ahora, cuando se crea o edita un pedido de ventas o un presupuesto de venta en el centro de llamadas, el precio exacto y el cálculo del descuento se retrasarán. El motor de precios considerará solo la línea de ventas que se está agregando o editando e ignorará todas las demás líneas de ventas. El importe neto de un artículo incluye el cálculo del precio y los descuentos simples (porcentaje de descuento o importe de descuento de un artículo individual). Sin embargo, no se aplicarán descuentos por combinación y coincidencia, umbral y cantidad. Los usuarios del centro de llamadas que deseen ver el precio exacto, incluidos todos los descuentos, pueden seleccionar uno de estos tres botones: **Recalcular**, **Totales** o **Completar**.

> [!NOTE]
> Para los pedidos del centro de llamadas, el sistema muestra un mensaje de advertencia para recordar al usuario que debe seleccionar el botón **Recalcular**, **Totales** o **Completar** para realizar el cálculo exacto del precio y el descuento. Para pedidos donde el botón **Completar** está disponible, no hay forma de que el usuario del centro de llamadas omita el precio exacto y el cálculo del descuento, porque debe seleccionar **Completar** para completar la captura del pedido. Para pedidos donde el botón **Completar** no está disponible, no hay ninguna acción que indique la finalización de la captura del pedido. Por lo tanto, el usuario del centro de llamadas es responsable de seleccionar **Recalcular** o **Totales** antes de completar la captura del pedido.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
