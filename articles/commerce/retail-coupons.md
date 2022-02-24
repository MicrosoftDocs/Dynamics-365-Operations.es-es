---
title: Configurar vales para ventas minoristas
description: Este tema proporciona una visión general de los cupones y explica cómo configurarlos.
author: scott-tucker
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a07bed244152327047efd68cfacb329a722c0049
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415464"
---
# <a name="set-up-coupons-for-retail-sales"></a>Configurar vales para ventas minoristas

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Visión general de los vales

Los vales son códigos y códigos de barras que se usan para agregar descuentos a las transacciones. Cada vale puede tener varios códigos, y cada código puede tener sus propias fechas de vigencia.

Cada vale está relacionado con un descuento. Los grupos de precios asociados al descuento definen a los clientes que pueden utilizar un vale o los canales donde es válido un vale.

Esencialmente, los vales son una validación adicional a los descuentos. El vale proporciona los códigos y los códigos de barras obligatorios, así como los intervalos de fechas para dichos códigos. El vale también proporciona límites de uso opcionales y propiedades requeridas por el cliente. El descuento proporciona el conjunto de productos para los que es válido. Los grupos de precios para el descuento proporcionan el conjunto de clientes, canales o catálogos para los que el vale es válido.

Para crear un vale, cree el descuento y el vale por separado. A continuación los vincula seleccionando el descuento en la página de vales en Commerce.

> [!NOTE]
> Después de vincular un vale a un descuento, varios campos de la página de descuentos de Commerce se vuelven de solo lectura porque son administrados mediante la configuración del vale. Estos campos incluyen los campos para estado y los intervalos de fechas estándar.

### <a name="limited-use-coupons"></a>Vales de uso limitado

Los vales se pueden configurar como vales de uso limitado. El límite de uso puede definirse por cliente o canal, o como límite global. Este límite se aplica cuando el código o el código de barras se introducen o escanean en el PDV o durante la entrada de pedidos de ventas.

El límite se aplica por el código de vale. Por ejemplo, un cupón de un solo uso que tiene dos códigos de vale se puede utilizar dos veces: una vez por cada código de vale. Cada código de un vale se puede activar de forma independiente.

Los cupones se pueden usar en cualquier canal de venta; sin embargo, para pedidos de centros de llamadas, los cupones de uso limitado se pueden usar solo para aquellos pedidos de centros de llamadas donde la configuración **Orden de finalización** del centro de llamadas está habilitada. Si esto no está habilitado, solo se pueden usar cupones de tipo de uso no limitado en los pedidos del centro de atención telefónica.

> [!NOTE]
> Una vez que un código de vale ha llegado a su límite de uso, el sistema *no* cambia automáticamente el estado del código de vale a "Usado". Sin embargo, ese código de cupón ha alcanzado su límite de uso y no se puede usar. Si el estado de un código de vale se establece manualmente en algo distinto de **Activo**, entonces este código de vale no se puede utilizar en ningún canal.  

## <a name="managing-coupons"></a>Administrar vales

Debe crear el descuento y el vale por separado. A continuación los vincula seleccionando el descuento en la página de vales. Después de vincular un vale a un descuento, varios campos del descuento se vuelven de solo lectura porque son administrados mediante la configuración del vale. Estos campos incluyen los campos para estado y los intervalos de fechas estándar.

Esencialmente, los vales son ahora una validación adicional a los descuentos. El vale proporciona los códigos y los códigos de barras, así como los intervalos de fechas, los límites de uso y la propiedad exigida por el cliente. El descuento proporciona el conjunto de productos para los que es válido. Los grupos de precios del descuento proporcionan el conjunto de clientes, canales o catálogos para los que el vale es válido.

## <a name="system-setup-for-coupons"></a>Configuración del sistema para vales

Para poder configurar un vale, debe configurar el código de barras del vale y dos secuencias numéricas de vales.

1. En la página **Caracteres de máscara**, cree un nuevo carácter de máscara para el código de vale. Puede seleccionar cualquier carácter que no se haya utilizado.
2. En la página **Configuración de máscara de código de barras**, cree una nueva máscara de código de barras. Establezca el campo **Tipo** en **Vale**.
3. En la página **Configuración de código de barras**, cree un nuevo código de barras que utilice la máscara de código de barras que acaba de crear.
4. En la página **Secuencias numéricas** , cree dos nuevas secuencias numéricas. Una secuencia es para el identificador del código de vale y la otra para el número de vale. El identificador del código de vale es el identificador único de cada código de vale. El número de vale es el identificador único de un vale. Cada vale puede tener varios códigos y códigos de barras que activan el vale.

    > [!NOTE]
    > En ambas secuencias numéricas, debe establecer el campo **Ámbito** a **Empresa**. En la mayoría de los casos, debe generar automáticamente los dos números secuenciales.

5. En la página **Parámetros de Commerce**, en la pestaña **Códigos de barras**, seleccione el código de barras que ha creado anteriormente.
6. En la página **Parámetros compartidos de Commerce**, en la pestaña **Secuencias numéricas**, seleccione las secuencias numéricas que ha creado para el número de vale y el identificador del código de vale.
7. Ahora puede abrir la página **Vales** y crear vales nuevos.

## <a name="the-effect-of-partial-updates-on-coupons"></a>El efecto de las actualizaciones parciales en los vales

La funcionalidad de vales incluye varias características distintivas. Commerce Headquarters (HQ) y el canal se pueden actualizar parcialmente a través de los componentes. Por lo tanto, es importante que comprenda cómo las actualizaciones parciales afectan a la funcionalidad de los vales en conjunto.

- **La central se actualiza parcialmente, pero no se actualizan Commerce Scale Unit ni los PDV.** En una actualización de la central, se actualizan el vale y las páginas de descuento, y el motor de precios de Commerce también se actualiza. Si solo uno de estos dos componentes se actualiza, algunas páginas de Commerce no coincidirán los datos de cálculo de precio. Por lo tanto, cálculos de descuento o errores inesperados pueden producirse durante cálculos de descuento.
- **La central se actualiza, pero no se actualizan Commerce Scale Unit ni los PDV (N-1).** Dado que no todas las tiendas se pueden actualizar al mismo tiempo, recomendamos que actualice la central antes de actualizar las tiendas. En la situación N-1, la nueva funcionalidad relacionada con vales no estará disponible en las tiendas que todavía no se hayan actualizado. Por ejemplo, la funcionalidad de vales introduce líneas de “exclusión”. Si usa líneas de exclusión en un descuento, estas no se aplicarán en una tienda que esté ejecutando una versión anterior.
- **La central no se actualiza, pero se actualizan Commerce Scale Unit ni los PDV (N+1).** Dado que el motor de precios actualizado en el servidor de Commerce Scale Unit puede gestionar códigos de descuento antiguos durante los cálculos de precios, la actualización no debe tener ningún impacto funcional en este escenario.
