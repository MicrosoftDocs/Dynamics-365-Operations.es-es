---
title: Calcular las facturas de TDS utilizando el formulario de pedido de compra y el formulario de pedido de ventas
description: Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en varios tipos de facturas.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d0e6cce8f7a90cd1624e64023a1b51fd02d12152f874e13ce2e5d22af16fe173
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782852"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Calcular las facturas de TDS utilizando el formulario de pedido de compra y el formulario de pedido de ventas

[!include [banner](../includes/banner.md)]

Este tema enumera los pasos para calcular el impuesto deducido en el origen (TDS) en varios tipos de facturas utilizando las páginas de **Pedido de compra**, **Diario de compra**, **Pedido marco** y **Pedido de ventas**.

1. Cree un pedido de compra, un diario de compra, un pedido marco de compra o un pedido de ventas utilizando la página que aparece. Especifique los detalles necesarios.

2. Seleccione la pestaña **Configuración** para ver la naturaleza del evaluado del proveedor o cliente. Esta información se enumera en el campo **Naturaleza del evaluado**, en el el grupo de campo **Grupo de retención de impuestos**.

3. En el campo **Grupo TDS**, consulte o modifique el grupo TDS predeterminado definido para el proveedor o cliente.

   > [!NOTE]
   > El campo **Grupo TCS** no está disponible cuando selecciona un grupo TDS en el campo **Grupo TDS**. TDS se calcula solo si se ha seleccionado la casilla **Calcular retención de impuestos** para el proveedor o cliente en las páginas **Todos los proveedores** o **Todos los clientes**.  

4. Cree líneas de artículos en la pestaña **Líneas** e introduzca los detalles requeridos.

5. Seleccione la pestaña **Configuración** (nivel de línea) para ver o cambiar el grupo TDS definido en el nivel de encabezado. El grupo TDS se muestra en el campo **Grupo TDS**, que está en el grupo de campo **Grupo de retención de impuestos**.

6. Seleccione la pestaña **Información de impuestos** y seleccione direcciones alternativas que estén configuradas para el nombre de la empresa que se muestra en este campo. El nombre de la empresa se muestra en el campo **Nombre**, que está en el grupo de campo **Información de la empresa**. 

   El TAN del nombre de la empresa seleccionada se muestra en el campo **Número de cuenta de impuestos** (**TAN**), en el grupo de campo **Retención de impuestos**. 

7. Seleccione **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**. Consulte los siguientes campos en el panel superior de la página **Transacciones de retención temporal de impuestos**.

   - **Retención** **de** **importe** **total** **de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.

   - **Valor**: el porcentaje total utilizado para calcular TDS para la transacción. El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS adjuntos al grupo TDS.

   - **Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.

   - **TDS**: si se selecciona, se adjunta un grupo de TDS a la transacción.

Los campos en las pestañas **Información general**, **General** y **Ajuste** en la página **Transacciones de retención temporal de impuestos** muestra la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.

8. Seleccione **Umbral** para abrir la página **Umbral**. Consulte el límite de umbral definido para el componente de impuestos de TDS adjunto a un código de impuestos de TDS específico en esta página.

9. Seleccione **Diseñador de fórmulas** para abrir la página **Diseñador de fórmulas**. Consulte la fórmula definida para un código de impuestos TDS específico en esta página. 

10. Registre la factura. La cantidad de TDS calculada en las facturas de compra se registra en la cuenta de proveedores y la cantidad de TDS calculada en las facturas de venta se contabiliza en la cuenta de clientes que se define para cada código de impuestos de TDS en el grupo de TDS. Las cuentas de proveedores o de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.

11. Seleccione el botón **Consulta** y el botón **> Factura > Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**. Puede ver el porcentaje total utilizado para calcular TDS para la transacción en el campo **Valor**.

Los campos en las pestañas **Descripción general**, **General** e **Importe** en la página **Transacciones de retención de impuestos** muestran la información de TDS calculada para la transacción. Consulte la información de cálculo de TDS para cada código de impuestos de TDS adjunto al grupo de TDS.
