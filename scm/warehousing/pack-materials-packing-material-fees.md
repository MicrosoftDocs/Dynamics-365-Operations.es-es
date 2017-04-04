---
title: Materiales y cuotas de embalaje
description: "Las cuotas de material de embalaje se pagan en algunos intervalos para una empresa de reciclaje. Se debe pagar un importe por unidad de peso para cada material del que consta una unidad de embalaje. Las cuotas de material de embalaje se calculan y se notifican, pero no se registra ninguna transacción contable ya que las cuentas no se contemplan como impuestos que se deban pagar a una autoridad."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 7c0bc5b5d86956336012096c11d0d7621abab1f9
ms.lasthandoff: 03/31/2017


---

# <a name="packing-materials-and-fees"></a>Materiales y cuotas de embalaje

Las cuotas de material de embalaje se pagan en algunos intervalos para una empresa de reciclaje. Se debe pagar un importe por unidad de peso para cada material del que consta una unidad de embalaje. Las cuotas de material de embalaje se calculan y se notifican, pero no se registra ninguna transacción contable ya que las cuentas no se contemplan como impuestos que se deban pagar a una autoridad.

Las cuotas y pesos de material de embalaje se calculan para las líneas de pedido de compra y de ventas.

Puede definir una o más unidades de embalaje para un artículo, un grupo de embalaje de artículos o para todos los artículos. Una unidad de embalaje consta de materiales de embalaje y sus pesos, además del número de artículos que se incluyen en la unidad de embalaje. Se asigna un código de material de embalaje a cada tipo de material de embalaje definido. De acuerdo con el código de material de embalaje, puede especificar un precio de un período concreto. La cuota de material de embalaje se calcula en función de esta información.

| **Nota **                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aunque la empresa no pague las cuentas de material de embalaje, podrá utilizar las funciones para calcular las estadísticas para los pesos de material de embalaje. |

## <a name="setup-requirements-for-packing-material-fees"></a>Requisitos de configuración para las cuotas de los material de embalaje
Antes de calcular las cuotas o pesos de material de embalaje, o ambos, cree los siguientes datos base:

-   Grupos de embalaje: cree grupos de embalaje para asignar a los artículos.
-   Códigos de material de embalaje: cree códigos de material de embalaje para cada tipo de material de embalaje definido.
-   Unidades de embalaje: especifique una unidad de embalaje para un artículo, un grupo de embalaje o para todos los artículos. Para cada unidad de embalaje, defina los materiales de embalaje que se van a incluir, asigne los pesos y, en el campo Factor de la unidad de embalaje, introduzca el factor de conversión de la unidad del inventario.
-   Cuotas de material de embalaje: especifique las cuotas de material de embalaje por código de material de embalaje. Para cada tipo de material, defina el período de validez, el precio por material, la divisa y la unidad.

## <a name="packing-units-on-sales-order-lines"></a>Unidades de embalaje en las líneas de pedido de ventas
Al crear una línea de pedidos de ventas, se realiza una comprobación para ver si se han especificado las unidades de embalaje para el artículo. Si se han especificado unidades de embalaje, el sistema actualiza la línea de pedido de ventas con la unidad de embalaje especificada y la cantidad de unidades de embalaje. La cantidad de unidades de embalaje se calcula en función de la cantidad pedida dividida entre el número de artículos en la unidad de embalaje seleccionada. Si no se ha especificado ninguna unidad de embalaje, puede especificar de manera manual una unidad de embalaje y una cantidad de artículos de embalaje en la línea de pedido de ventas. También es posible cambiar la unidad de embalaje y la cantidad de unidades de embalaje al registrar la línea de pedido de ventas. Esto es relevante si la línea de pedido de ventas sólo se entrega o factura parcialmente. Las transacciones de material de embalaje se crean al facturar pedidos de ventas. Las transacciones de material de embalaje contienen los pesos del material de embalaje para la línea de ventas. También puede modificar las transacciones tras su facturación y, a continuación, crear nuevas transacciones.

## <a name="packing-units-on-purchase-order-lines"></a>Unidades de embalaje en las líneas de pedido de compra
El sistema no crea transacciones de materiales de embalaje para una línea de pedido de compra. Las transacciones para las líneas de pedido de compra facturadas se crean manualmente en la página **Transacciones de material de embalaje**.

## <a name="set-up-customer-packagingmaterialfee-license-numbers"></a>Configurar los números de licencia de packagingmaterialfee del cliente
Si los clientes pagan las cuotas de material de embalaje, especifique los números de licencia de cuota de material de embalaje de los clientes en la página **Clientes**. Si se ha asignado un número de licencia a un cliente, las cuotas de material de embalaje se calculan automáticamente al facturar los pedidos de ventas. Tras la facturación, se desactiva la casilla de verificación **Calcular cuota** de la página **Transacciones de material de embalaje**, ya que no necesita calcular e imprimir un informe. Puede imprimir los pesos del material de embalaje en la factura e informar a los clientes de que paguen las cuotas. 

Si la empresa paga las cuotas del material de embalaje, no especifique los números de licencia del cliente. Tras la facturación, la casilla **Calcular cuota** se activará en la página **Transacciones de material de embalaje**. Esto indica que las cuotas se calculan cuando se crea el informe. Puede imprimir los pesos en la factura e indicar que la empresa paga las cuotas.

## <a name="print-packaging-material-weights-on-invoices"></a>Imprimir pesos de material de embalaje en las facturas
Puede imprimir los pesos de material de embalaje en la factura e indicar quién paga las cuotas de material de embalaje. Los pesos se resumen por código de embalaje.
 



