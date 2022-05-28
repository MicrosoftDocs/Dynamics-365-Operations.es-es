---
title: Cambio de base en cálculos de impuestos ICMS-DIF para productos de proveedores de otros estados
description: Este tema describe la configuración para los cálculos del tipo de impuesto ICMS-DIF cuando se recibe un documento fiscal en el estado brasileño de Rio Grande do Sul (RS) o São Paulo (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 63e3cbaaf77456b55f08ea91831ba9d49cb57185
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689167"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Cambio de base en cálculos de impuestos ICMS-DIF para productos de proveedores de otros estados

Este tema describe la configuración para los cálculos del tipo de impuesto **ICMS-DIF** cuando se recibe un documento fiscal en el estado brasileño de Rio Grande do Sul (RS) o São Paulo (SP).

De acuerdo con la definición en la ley estatal, el Imposto sobre Circulação de Mercadorias e Serviços (ICMS) que se recauda debe seguir esta regla:

*ICMS a cobrar* = ([(*Importe de la operación* – *ICMS desde el origen*) ÷ (1 – *% de ICMS interno*)] × *% de ICMS interno*) – *Importe de ICMS del origen*

## <a name="example"></a>Ejemplo

Una empresa brasileña en el estado de RS recibe un documento fiscal para una compra de un proveedor en el estado de SP. La empresa debe cobrar la diferencia porcentual de ICMS entre el estado RS (18 por ciento) y el estado SP (12 por ciento). Sin embargo, la base debe calcularse de acuerdo con la regla anterior.

- **Importe de la operación:** 1000 reales brasileños (1000 R$)
- **ICMS interestatal:** 120 R$
- **Porcentaje de ICMS en el estado RS:** 18 por ciento
- **ICMS para recaudar en el estado RS:** (\[(1000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = 73,17 R$ 

## <a name="resolution"></a>Resolución

Para calcular el ICMS diferencial (ICMS-DIF) de acuerdo con las reglas del estado RS, debe configurar códigos de impuestos sobre las ventas y un grupo de impuestos sobre las ventas de la siguiente manera:

1. Cree un código de impuestos sobre las ventas para recibir el ICMS del 12 por ciento (para el otro estado). Este código se utiliza para registrar el importe del impuesto a cobrar del proveedor.
2. Cree un código de impuesto sobre las ventas para recaudar el ICMS-DIF. Este código de impuestos sobre las ventas debe tener un porcentaje del 18 por ciento (para su propio estado) para definir la diferencia entre el 18 por ciento y el 12 por ciento. Establezca el tipo de impuesto en **ICMS-DIF**. Este código de impuesto sobre las ventas debe definirse de la siguiente manera en los parámetros de cálculo:

    - En el campo **Origen**, seleccione **Porcentaje del importe bruto**.
    - En el campo **Base marginal**, seleccione **Importe neto por línea** o **Importe neto del saldo de la factura**.
    - Defina el código de impuestos para que tenga un valor fiscal de **3**. De esta forma, la transacción de ajuste se creará automáticamente cuando el módulo **Libros fiscales** esté habilitado.
    - En la configuración del grupo de impuestos sobre las ventas, seleccione la opción **IVA de importación** para el código de impuesto sobre las ventas **ICMS-DIF**.
