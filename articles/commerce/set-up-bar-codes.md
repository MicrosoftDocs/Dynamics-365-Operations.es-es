---
title: Configurar códigos de barras
description: Este artículo describe cómo usar códigos de barras en Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 52801e0d09b1d7da50719966700ca45275d702f7
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057287"
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
4. Cree códigos de barras para productos.

## <a name="additional-resources"></a>Recursos adicionales

[Configuración de máscaras de código de barras](set-up-bar-code-masks.md)
