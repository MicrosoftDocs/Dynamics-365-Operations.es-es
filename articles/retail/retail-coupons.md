---
title: Crear vales para ventas minoristas
description: "Este tema proporciona una visión general de los vales comerciales y explica cómo configurarlos."
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7e05361bf865e44ba6073198fba94d7102b1ed19
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="create-coupons-for-retail-sales"></a>Crear vales para ventas minoristas

[!include[banner](includes/banner.md)]


## <a name="overview-of-coupons"></a>Visión general de los vales

Los vales son códigos y códigos de barras que se usan para agregar descuentos al por menor a las transacciones. Cada vale puede tener varios códigos, y cada código puede tener sus propias fechas de vigencia. 

Cada vale está relacionado con un descuento minorista. Los grupos de precios asociados al descuento definen a los clientes que pueden utilizar un vale o los canales donde es válido un vale. 

Esencialmente, los vales son una validación adicional a los descuentos minoristas. El vale proporciona los códigos y los códigos de barras obligatorios, así como los intervalos de fechas para dichos códigos. El vale también proporciona límites de uso opcionales y propiedades requeridas por el cliente. El descuento proporciona el conjunto de productos para los que es válido. Los grupos de precios para el descuento proporcionan el conjunto de clientes, canales o catálogos para los que el vale es válido.

Para crear un vale, cree el descuento y el vale por separado. A continuación vincúlelos seleccionando el descuento en la página de vales en Microsoft Dynamics 365 for Retail. 

> [!NOTE]
> Después de que un vale se vincula a un descuento, varios campos en la página de descuentos en Microsoft Dynamics 365 for Retail se vuelven de sólo lectura, ya que son administrados mediante la configuración del vale. Estos campos incluyen los campos para estado y los intervalos de fechas estándar.

### <a name="limited-use-coupons"></a>Vales de uso limitado

Los vales se pueden configurar como vales de uso limitado. El límite de uso puede definirse por cliente o canal, o como límite global. Este límite se aplica cuando el código o el código de barras se introducen o escanean en el PDV o durante la entrada de pedidos de ventas. Un vale se registra como usado cuando se completa un pedido que tiene el vale asociado a él.

El límite se aplica por el código de vale. Por ejemplo, un cupón de un solo uso que tiene dos códigos de vale se puede utilizar dos veces: una vez por cada código de vale. Cada código de un vale se puede activar de forma independiente.

## <a name="managing-coupons"></a>Administrar vales

Debe crear el descuento y el vale por separado. A continuación los vincula seleccionando el descuento en la página de vales. Después de vincular un vale a un descuento, varios campos del descuento se vuelven de solo lectura porque son administrados mediante la configuración del vale. Estos campos incluyen los campos para estado y los intervalos de fechas estándar.  

Esencialmente, los vales son ahora una validación adicional a los descuentos minoristas. El vale proporciona los códigos y los códigos de barras, así como los intervalos de fechas, los límites de uso y la propiedad exigida por el cliente. El descuento proporciona el conjunto de productos para los que es válido. Los grupos de precios del descuento proporcionan el conjunto de clientes, canales o catálogos para los que el vale es válido.

## <a name="system-setup-for-coupons"></a>Configuración del sistema para vales 

Para poder configurar un vale, debe configurar el código de barras del vale y dos secuencias numéricas de vales. 

1.  En la página **Caracteres de máscara**, cree un nuevo carácter de máscara para el código de vale. Puede seleccionar cualquier carácter que no se haya utilizado.
2.  En la página **Configuración de máscara de código de barras**, cree una nueva máscara de código de barras. Establezca el campo **Tipo** en **Vale**.
3.  En la página **Configuración de código de barras**, cree un nuevo código de barras que utilice la máscara de código de barras que acaba de crear.
4.  En la página **Secuencias numéricas** , cree dos nuevas secuencias numéricas. Una secuencia es para el identificador del código de vale y la otra para el número de vale. El identificador del código de vale es el identificador único de cada código de vale. El número de vale es el identificador único de un vale. Cada vale puede tener varios códigos y códigos de barras que activan el vale.

    > [!NOTE]
    > En ambas secuencias numéricas, debe establecer el campo **Ámbito** a **Empresa**. En la mayoría de los casos, debe generar automáticamente los dos números secuenciales.

5.  En la página **Parámetros compartidos comerciales** , en la ficha **Códigos de barras**, seleccione el código de barras que ha creado anteriormente.
6.  En la página **Parámetros de ventas al por menor**, en la ficha **Secuencias numéricas** , seleccione las secuencias numéricas que ha creado para el número de vale y el identificador del código de vale.
7.  Ahora puede abrir la página **Vales** y crear vales nuevos.

## <a name="the-effect-of-partial-updates-on-coupons"></a>El efecto de las actualizaciones parciales en los vales

La funcionalidad de vales incluye varias características distintivas de Dynamics 365 for Retail. Microsoft Dynamics 365 for Retail Headquarters (HQ) y el canal se pueden actualizar parcialmente a través de los componentes. Por lo tanto, es importante que comprenda cómo las actualizaciones parciales afectan a la funcionalidad de los vales en conjunto.

- **La central se actualiza parcialmente, pero no se actualizan el servidor de venta al por menor ni los PDV.** En una actualización de la central, se actualizan el vale y las páginas de descuento, y el motor de precios minoristas también se actualiza. Si solo uno de estos dos componentes se actualiza, algunas páginas de Retail no coincidirán los datos de cálculo de precio. Por lo tanto, cálculos de descuento o errores inesperados pueden producirse durante cálculos de descuento.
- **La central está actualizada, pero ni el servidor de Retail ni los PDV están actualizados (N-1).** Dado que no todas las tiendas se pueden actualizar al mismo tiempo, recomendamos que actualice la central antes de actualizar las tiendas. En la situación N-1, la nueva funcionalidad relacionada con vales no estará disponible en las tiendas que todavía no se hayan actualizado. Por ejemplo, la funcionalidad de vales introduce líneas de “exclusión”. Si usa líneas de exclusión en un descuento, estas no se aplicarán en una tienda que esté ejecutando una versión anterior.
- **La central no está actualizada, pero el servidor de Retail y los PDV sí (N+1).** Dado que el motor de precios actualizado en el servidor de Retail puede gestionar códigos de descuento antiguos durante los cálculos de precios, la actualización no debe tener ningún impacto funcional en este escenario.

