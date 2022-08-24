---
title: Configurar códigos de barras
description: Este artículo describe cómo usar códigos de barras en Dynamics 365 Commerce.
author: josaw1
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.industry: Retail
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
ms.openlocfilehash: 5771ada4a9bba92fb32155ae425f08d6429b46e6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271806"
---
# <a name="set-up-bar-codes"></a>Configurar códigos de barras

[!include [banner](includes/banner.md)]

Este artículo describe cómo usar códigos de barras en Dynamics 365 Commerce.

Puede usar códigos de barras para comprar y vender productos, realizar un seguimiento de las variantes del producto y configurar los clientes y empleados. También puede usar códigos de barras para emitir y endosar cupones, tarjetas de regalo y notas de crédito. Puede configurar productos para que tengan códigos de barras estándar o códigos de barras internos personalizados. Los productos pueden tener más de un código de barras. Por ejemplo, un producto puede tener varios códigos de barras si procede de distintos fabricantes o si tiene variaciones de tamaño, estilo o color. Los códigos de barras pueden incluir el peso o el precio del producto. Las máscaras de código de barras son plantillas que se usan para crear códigos de barras.

> [!NOTE]
> Si asigna un código de barras único a cada combinación de variantes, puede digitalizar el código de barras en la caja registradora para que el programa determine la variante del producto que se vende. También puede recopilar y consultar estadísticas sobre las venta por variante. Se puede asignar un número único a cada grupo de tamaños, colores y estilos que identifique a este grupo en el código de barras. Commerce usa la máscara de código de barras para generar automáticamente códigos de barras para cada combinación de variantes. Esta funcionalidad puede ser útil si existen muchos tamaños, colores y estilos, ya que el número de combinaciones aumenta significativamente con cada código de variante que se agrega. Si no se usa esta funcionalidad, es necesario asignar códigos de barras manualmente a cada combinación que represente una variante de producto.

Los códigos de barras se crean manual o automáticamente. Para crear códigos de barras, realice las siguientes tareas en el orden en el que aparecen.

1. [Configuración de los caracteres de máscara de código de barras](set-up-bar-code-masks.md).
2. [Configuración de máscaras de código de barras](set-up-bar-code-masks.md).
3. Configure códigos de barras.
4. [Crear códigos de barras para productos](../supply-chain/pim/tasks/create-bar-code-product.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configuración de máscaras de código de barras](set-up-bar-code-masks.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
