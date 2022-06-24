---
title: Configurar un producto para comprarlo gratis
description: Este artículo describe cómo configurar un producto para que se pueda comprar gratis en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bd7e4f7a7873e471f1aee94f15e7932e8d9eecd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890364"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Configurar un producto para comprarlo gratis

[!include [banner](includes/banner.md)]


Este artículo describe cómo configurar un producto para que se pueda comprar gratis en Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Configurar el producto

Para vender un producto gratis en Dynamics 365 Commerce, debe establecer su precio en 0 (cero). Además, debe activar la configuración **Precio cero válido**.

Para configurar el **Precio cero válido** en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Productos emitidos por categoría**.
1. Vaya al producto que desea vender de forma gratuita. 
1. En la sección **Commerce** de la página del producto, establezca la opción **Precio cero válido** como **Sí**.

La siguiente ilustración muestra un ejemplo de un producto donde la opción **Precio cero válido** está configurada en **Sí**.

![Ejemplo de un producto en el que la opción Precio cero válido está establecida en Sí.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Configurar el perfil de funcionalidad de la tienda en línea

Antes de que se puedan procesar las transacciones gratuitas, debe configurar la opción **Permitir la compra sin pagos** del perfil de funcionalidad para su tienda en línea para que se permitan transacciones que no vayan acompañadas de pagos. Para obtener información sobre cómo crear perfiles de funcionalidad, consulte [Crear un perfil de funcionalidad en línea](online-functionality-profile.md).

Para configurar la opción **Permitir la compra sin pagos** en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de tienda en línea**.
1. En la página del perfil de funcionalidad de su tienda, en **Verificar**, configure la opción **Permitir la compra sin pagos** en **Sí**.

La siguiente ilustración muestra un ejemplo de un perfil de tienda en línea donde la opción **Permitir la compra sin pagos** está configurada como **Sí**.

![Ejemplo de un perfil de tienda en línea donde la opción Permitir la compra sin pagos está configurada como Sí.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Recursos adicionales

[Administración de precios de venta comerciales](price-management.md)

[Crear un perfil de funcionalidad en línea](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
