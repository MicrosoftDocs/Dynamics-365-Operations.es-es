---
title: Preparar el mantenimiento de los costes estándar de artículos fabricados
description: Este tema decribe los pasos para prepararse para el mantenimiento de costes de artículos fabricados.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8d42f61bcd44e89f0563c8f7450a1cdd6fd0e3ce
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679146"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Preparar el mantenimiento de los costes estándar de artículos fabricados

[!include [banner](../includes/banner.md)]

Este tema decribe los pasos para prepararse para el mantenimiento de costes de artículos fabricados. Los pasos para los artículos fabricados varían ligeramente de los pasos de los artículos adquiridos.

Las directivas que se asignan a los artículos fabricados pueden afectar a los cálculos de coste de los artículos fabricados principales. Para prepararse para mantener los costes de artículos fabricados, siga estos pasos.

1. Asigne un grupo de modelos de artículos al artículo fabricado. 

   El grupo de modelos de artículos identifica el uso de esos costes estándar.

2. Asigne un grupo de artículos al artículo fabricado. 

   El grupo de artículos contiene cuentas contables que se aplican al artículo fabricado. Las cuentas contables de un artículo fabricado que tiene un modelo de inventario de coste estándar incluyen varias desviaciones de producción, la desviación de cambio de coste y la revalorización del coste de inventario.

3. Asigne la unidad de medida de inventario al artículo. 

   Los costes del artículo siempre se expresan en la unidad de medida de inventario del artículo.

4. No asigne un grupo de costes al artículo fabricado a menos que el artículo se trate como un artículo comprado.

5. Asigne un grupo de cálculo de lista de materiales (L. MAT) al artículo fabricado. 

   El grupo de cálculo de L. MAT del artículo define las condiciones de advertencia que se aplican. De esa manera, cuando se realiza un cálculo de L. MAT, pueden generarse mensajes de advertencia sobre los posibles orígenes de errores de cálculo. Por ejemplo, un mensaje de advertencia puede identificar cuándo no existen una L. MAT o ruta activas. El grupo de cálculos de L. MAT contiene una directiva de detención de la expansión que indica cuándo un artículo fabricado debe tratarse como un artículo comprado.

6. Si el artículo fabricado tiene costes constantes, asigne una cantidad de pedido estándar a este. 

   La cantidad de pedido estándar es un tamaño del lote de contabilidad para la amortización de costes constantes. Los ejemplos de costes constantes incluyen horas de configuración en las operaciones de enrutamiento y una cantidad de componentes constante en la L. MAT.

7. Defina la L. MAT para el artículo fabricado. 

   Es posible definir una o más versiones de la L. MAT. Compruebe que las versiones deseadas se marcaron como aprobadas y están activas, y que tengan las fechas de vigencia deseadas. La versión de la L. MAT puede ser para toda la empresa o específica para un sitio.

8. Defina la ruta para el artículo fabricado. 

   Es posible definir una o más versiones de la ruta. Compruebe que las versiones deseadas se marcaron como aprobadas y están activas, y que tengan las fechas de vigencia deseadas. La versión de la ruta debe ser específica para un sitio.

Si desea utilizar la información de enrutamiento para la gestión de costes necesitará pasos preparativos adicionales. Por ejemplo, las categorías de coste asignadas a las operaciones de enrutamiento deben ser correctas y estar completas.

## <a name="related-topics"></a>Temas relacionados

[Amortizar los costes constantes para un artículo fabricado](amortize-constant-costs-manufactured-item.md)

[Configurar productos que pueden fabricarse o suministrarse](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]