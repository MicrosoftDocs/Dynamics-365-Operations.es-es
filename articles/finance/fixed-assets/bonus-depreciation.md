---
title: Depreciación de bonificación
description: Este artículo proporciona una visión general de la funcionalidad de depreciación de bonificación.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: kfend
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 801747f06d16e70cd04b727787f0bfa6b6baefc0
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711156"
---
# <a name="bonus-depreciation"></a>Depreciación de bonificación

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general de la funcionalidad de depreciación de bonificación.

Para la depreciación de bonificación puede aceptar importes de depreciación adicionales o de bonificación durante el primer año que el activo entra en servicio y se deprecia. La amortización de la bonificación se debe realizar antes de cualquier otro cálculo de depreciación. Por lo tanto, es preferible usar la depreciación de bonificación con libros donde la función de Registrar en la contabilidad general está deshabilitada. Puede usar la opción de **Suprimir transacciones no registradas en la contabilidad general** para eliminar las transacciones históricas para los libros que no registran en la contabilidad general. A continuación puede alojar la depreciación de bonificación más adelante en el ciclo de vida del activo eliminando las transacciones de depreciación previamente registradas. 

Puede calcular la amortización de bonificación mediante el proceso de propuesta, o bien crear transacciones de amortización de bonificación manuales. No se pueden crear transacciones de depreciación de bonificación si existen transacciones de depreciación o transacciones de ajuste de depreciación para ese libro de activos.

Cuando usa el proceso de propuesta para calcular la amortización de bonificación, todas las transacciones de bonificación existentes se incluyen en el cálculo de esa base. El cálculo también incluye las depreciaciones de bonificaciones anteriores que haya introducido manualmente para el activo. 

Si se toma más de una amortización de bonificación para un activo, se tendrá en cuenta la prioridad. Cada bonificación reduce la base del activo para la siguiente bonificación. No se tiene en cuenta el valor residual en la base del activo para los cálculos de amortización de bonificación, y la convención de amortización no se aplica a la amortización de bonificación. 

Actualmente en los Estados Unidos, algunas propiedades reúnen los requisitos como propiedad del grupo 179. Mediante la deducción del grupo 179, puede recuperar todo o parte del coste de algunas propiedades, hasta un límite. Puede recuperar el coste deduciéndolo en el año en el que la propiedad se pone en servicio.

## <a name="example"></a>Ejemplo
Las siguientes depreciaciones de bonificación se asocian a un libro de activos:

-   **Grupo 179:** 1.000,00, Prioridad 1
-   **Zona de libertad:** 30 por ciento, Prioridad 2

El coste de adquisición de activos es de 5.000,00. Al calcular la amortización de bonificación, el primer importe de amortización es 1.000,00 para la amortización del grupo 179. 

El siguiente importe de amortización de bonificación para la amortización de la zona de libertad, se calcula de la siguiente manera: 

Coste de adquisición: 1.000 (amortización del grupo 179) x 30% = 1.200 

Si el importe de amortización de bonificación es superior al coste de adquisición restante, el importe de amortización de bonificación es el cálculo de amortización de bonificación o el coste de adquisición restante, cualquiera que sea inferior. 

Si el coste de adquisición restante es 0 (cero) o menos, las transacciones de depreciación de bonificación no se generan. 

Cuando la amortización de bonificación se calcula mediante el proceso de propuesta, se crea una transacción de amortización de bonificación para todos los registros de amortización de bonificación asociados al libro amortización de activos. 

Puede crear un número ilimitado de registros de amortización de bonificación. Cuando haya asignado dichos registros al libro del grupo de activos, se aplican al libro de activos. 

La amortización de bonificación se inserta como un porcentaje o un importe fijo. Al registrar las propuestas de amortización, las transacciones de amortización de bonificación se registran en el libro como transacciones independientes de las transacciones de amortización.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
