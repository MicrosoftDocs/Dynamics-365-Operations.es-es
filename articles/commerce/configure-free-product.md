---
title: Configurar un producto para comprarlo gratis
description: Este artículo describe cómo configurar un producto para que se pueda comprar gratis en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88370085de047a5e0be773dde218770cfa242d14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280374"
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
