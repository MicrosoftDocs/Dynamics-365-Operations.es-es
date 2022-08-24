---
title: Cambio de base en cálculos de impuestos ICMS-DIF para productos de proveedores de otros estados
description: Este artículo describe la configuración para los cálculos del tipo de impuesto ICMS-DIF cuando se recibe un documento fiscal en el estado brasileño de Rio Grande do Sul (RS) o São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
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
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218662"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Cambio de base (base dual) en cálculos de impuestos ICMS-DIF para productos de proveedores de otros estados

Este artículo describe la configuración para los cálculos del tipo de impuesto **ICMS-DIF** cuando se recibe un documento fiscal en el estado brasileño de Rio Grande do Sul (RS) o São Paulo (SP).

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
    - En el campo **Base marginal**, seleccione **Importe neto por línea**.
    - Defina el código de impuestos para que tenga un valor fiscal de **3**. De esta forma, la transacción de ajuste se creará automáticamente cuando el módulo **Libros fiscales** esté habilitado.
    - En la configuración del grupo de impuestos sobre las ventas, seleccione la opción **IVA de importación** para el código de impuesto sobre las ventas **ICMS-DIF**.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Usar el índice de impuestos delta en la configuración de los códigos de impuestos ICMS-DIF de base doble

Cuando se utilizan los ajustes descritos anteriormente, el código de impuesto sobre las ventas **ICMS-DIF** se calculará en la regla de base dual. Sin embargo, la tasa impositiva nominal pasa a ser del 18 por ciento, que difiere de la tasa del 6 por ciento en la regla básica simple. Esta diferencia provoca problemas de incoherencia en el documento fiscal y la declaración de impuestos. A partir de Microsoft Dynamics 365 Finance versión 10.0.29, puede habilitar la función **(Brasil) Configure la tasa impositiva delta en el código impositivo ICMS-DIF para el caso de base dual** en **Gestión de características** para eliminar la inconsistencia.

- Además de completar los pasos de la sección anterior, seleccione el código de impuesto sobre las ventas **ICMS 12** en el campo **Impuesto sobre las ventas sobre el impuesto sobre las ventas**.
- Establece la tasa de impuestos del código de impuesto sobre las ventas **ICMS-DIF** en el 18 por ciento. El campo **Porcentaje/Cantidad** mostrará la tasa impositiva nominal como 6 por ciento.

> [!NOTE]
> Los códigos de impuestos sobre las ventas **ICMS-DIF** e **ICMS 12** deben asignarse en el mismo grupo de impuestos sobre las ventas.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Cambio de base (base dual) en cálculos de impuestos ICMS-DIF para productos a consumidores que no pagan impuestos (DIFAL) en otros estados

Habilite la función **(Brasil) Cálculo de base dual para ICMS-DIFAL en transacciones de venta** en **Gestión de características** para apoyar el cambio de base ICMS-DIF en la comercialización a consumidores no contribuyentes de otro estado. El código de impuesto sobre las ventas ICMS-DIF de muestra entra en vigencia en las transacciones de órdenes de venta y facturas de texto sin formato.

Habilite la función **(Brasil) Cálculo de base dual para ICMS-DIFAL para casos de IPI** en **Gestión de características** para soportar escenarios en los que la comercialización a consumidores no contribuyentes de otro estado también sea responsable del Imposto sobre Productos Industrializados (IPI). El monto del impuesto del IPI código de impuesto a las ventas será reconocido y aplicado en la base imponible del ICMS-DIFAL.

- En la cabecera del pedido de cliente o factura de texto libre, en la ficha rápida **Información fiscal**, la opción **Usuario final** debe estar configurada en **Sí**.
- En la cabecera del pedido de compra o factura de proveedor, en la ficha rápida **Información fiscal**, la opción **Uso y consumo** debe estar configurada en **Sí**.
