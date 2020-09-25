---
title: Moviendo mensaje
description: La media móvil es un método de gestión de costes perpetuo que se basa en el principio de promedio, en que los costes de emisiones de inventario no cambian cuando cambia el coste de compra. La diferencia se capitaliza y se basa en un cálculo proporcional. El importe restante se anota como gasto.
author: AndersGirke
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40cb135c285afb4466f36dbe637368829fec196f
ms.sourcegitcommit: 097e92f4da7ed9c33f8eb0a7e09969260c399446
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763618"
---
# <a name="moving-average"></a>Moviendo mensaje

[!include [banner](../includes/banner.md)]

La media móvil es un método de gestión de costes perpetuo que se basa en el principio de promedio, en que los costes de emisiones de inventario no cambian cuando cambia el coste de compra. La diferencia se capitaliza y se basa en un cálculo proporcional. El importe restante se anota como gasto.

Si usa la media móvil, no se admiten las liquidaciones ni el marcado de inventario. El cierre de inventario no afecta a los productos que tienen media móvil, como el grupo de modelos de inventario, y no genera liquidaciones entre transacciones.

A continuación se indican requisitos previos para usar el coste de media móvil como método de gestión de costes.

1. En la página **Grupos de modelos de artículo**, configure un grupo de modelos de artículos con **Media móvil** seleccionado en el campo **Modelo de inventario**.

    > [!NOTE]
    > De forma predeterminada, cuando se selecciona **Media móvil**, también se seleccionan los campos **Registrar inventario físico** y **Registrar inventario financiero**.

1. En la página **Publicar**, asigne cuentas a la **Diferencia de precio por media móvil**. La cuenta **Diferencia de precios para la media móvil** se usa cuando el coste se ha contabilizado proporcionalmente. Esto ocurre en los siguientes dos escenarios:
    - Hay una diferencia de coste entre un recibo de compra y la factura de compra porque hay una diferencia entre la cantidad de inventario original y la cantidad disponible actual.
    - Las transacciones llevan el inventario de negativo a cero y hay una diferencia entre el coste de transacción y el coste promedio móvil actual.

1. En la página **Registro**, asigne cuentas a las cuentas a las cuentas **Revalorización de costes para la media móvil** en la pestaña **Inventario**. Utiliza la cuenta **Revalorización de costes para la media móvil** cuando quiere ajustar el coste de la media móvil para un producto a un nuevo precio unitario.

1. En la página **Productos emitidos**, asigne el grupo de modelos de producto de media móvil al producto.

    > [!NOTE]
    > El proceso de cierre de inventario solo cierra el periodo contable. No afecta a los productos que tienen asignada la media móvil como grupo de modelos de producto.

## <a name="convert-to-the-moving-average-costing-method"></a>Conversión al método de gestión de costes de media móvil

Los productos se pueden convertir para usar el método de valoración de inventario de media móvil. Este tipo de conversión se realiza normalmente al final del año, una vez cerrado el último mes del año actual. Se realiza usando el modelo de gestión de costes actual del producto. Puede cambiar el método de gestión de costes de inventario de un método de gestión de costes basado en el coste medio o estándar a un método basado en la media móvil.

Si va a cambiar el método gestión de costes de un método de gestión de costes estándar a un método de media móvil, debe completar las siguientes tareas:

1. Realizar ajustes para poner las cantidades y los valores de inventario a 0 (cero).
1. Cuando el valor y la cantidad de inventario sean 0 (cero), cambie el grupo de modelos de producto a media móvil.
1. Realice ajustes para devolver las cantidades y los valores al inventario.

No puede cambiar el método de gestión de costes de inventario de un método de media móvil al método de orden de entrada (FIFO), de salida en orden inverso al de entrada (LIFO) o de media ponderada.

> [!NOTE]
> La conversión de coste estándar a media ponderada móvil es un proceso manual.

Los siguientes ejemplos ilustran el efecto de usar el método de gestión de costes de media móvil. Existen cuatro configuraciones:

- Pedido de compra y diferencia de coste anotada como gasto proporcionalmente
- Producto de media móvil y ajuste de inventario
- Media móvil con producción
- Media móvil con transacción antedatada

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Pedido de compra y diferencia de coste anotada como gasto proporcionalmente

Con la media móvil, el coste del producto viene determinado por el recibo de compra. Cuando se registra la factura de compra, si hay una diferencia de coste entre el recibo y la factura de compra, la diferencia se ajusta proporcionalmente a los productos actuales con existencias y el importe restante se anota como gasto.

En este ejemplo, un pedido de compra se crea y se recibe a un coste y la factura de compra se registra con otro coste.

1. Cree un pedido de compra para una cantidad de 2 y un precio unitario de 10,00.
1. Cree un recibo de compra del producto.
1. Cree un pedido de ventas para una cantidad de 1 y un precio unitario de 10,00.
1. Cree una factura de compra para una cantidad de 2 y un precio unitario de 12,00.

La diferencia en el precio unitario, 2,00, se registra en la cuenta Diferencia de precios para la media móvil cuando se registra la factura de compra. La razón es que los dos productos se adquirieron a un coste de 20,00. Uno de los productos se vendió por un precio unitario de 10,00. Se registró la factura de compra a un precio unitario de 12,00 con una cantidad de 2. El precio unitario del producto no se puede registrar en 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Producto de media móvil y ajuste de inventario

Si necesita ajustar el coste de media móvil de un producto, se permiten ajustes de inventario con la fecha actual. No se puede antedatar un ajuste de inventario para corregir el coste de media móvil de un producto. No se puede usar el coste en transacciones posteriores.

En este ejemplo, se ajusta el coste de media móvil para un producto.

1. Seleccione el producto para el que desee ajustar el coste de media móvil. 

 > [!NOTE]
 > La página **Revalorización para el valor promedio móvil** examina el inventario disponible para un producto. El producto seleccionado tiene una cantidad registrada de 1, un valor registrado de 12,00, un coste unitario registrado de 12,00 y un coste unitario de 12,00.
    
1. Actualice el campo **Coste unitario** a 16,00. El sistema calcula los campos restantes.
1. El ajuste se registró.

> [!NOTE]
> Solo puede ajustar el coste de media móvil con la fecha actual.

En la página **Liquidaciones para el asiento** puede ver un ajuste de 4,00 registrado en la cuenta Revalorización de costes para la media móvil.

## <a name="moving-average-with-production"></a>Media móvil con producción

La media móvil admite los productos producidos. Si pretende usar la media móvil en un entorno de producción, seleccione **Utilizar precio de coste estimado** en la página **Parámetros de control de producción**. Esto significa que se usa el precio de coste que se calcula durante la estimación en lugar del precio de coste de cálculo de L. MAT real.

## <a name="moving-average-with-a-backdated-transaction"></a>Media móvil con transacción antedatada

El coste de media móvil actual se asigna a las transacciones antedatadas y la cantidad física del producto se actualiza, pero el coste de media móvil del producto no se ve afectado. En este ejemplo de media móvil, se registra una transacción antedatada para un producto de media móvil.

1. Cree un ajuste de inventario para el producto de media móvil para una cantidad de 1 y un coste de 20,00.
1. El historial de transacciones de inventario para el producto tendría el aspecto siguiente:
    - Una transacción de inventario de 1, un coste de 16,00, la fecha de registro 15 de enero y la fecha de transacción 15 de enero.
    - Un ajuste de inventario de 1, un coste de 20,00, la fecha de registro 1 de enero y la fecha de transacción 15 de enero.
1. Registre el ajuste.

En la página **Transacciones de inventario** puede ver que 4,00 está anotado como gasto como media móvil actual del producto, 16,00. Puede registrar en el pasado, pero se debe anotar como gasto la diferencia de coste, por lo que el coste de media móvil no se ve afectado.

## <a name="negative-inventory-balances"></a>Saldos de inventario negativos

Las transacciones se manejan de manera diferente dependiendo de si la nueva cantidad disponible después de la transacción es negativa, cero o positiva.

### <a name="new-balance-is-negative-or-zero"></a>El nuevo saldo es negativo o cero

Si la nueva cantidad disponible es negativa o cero, la transacción se calcula según los costes promedio actuales. Si hay una diferencia entre el precio de compra y los costes promedio actuales, se registra en **Diferencia de precio por media móvil**.

### <a name="new-balance-is-positive"></a>El nuevo saldo es positivo

Si la nueva cantidad disponible es positiva después de la transacción, la transacción se divide en dos partes y se calcula de manera diferente, como se resume en la siguiente tabla.

| Pieza | Descripción |
|---|---|
| Cantidad de negativa a cero | El inventario utiliza el coste promedio móvil actual del artículo en lugar del coste de transacción para esa parte de la cantidad recibida que aumenta el saldo disponible de negativo a cero. La diferencia entre el coste de la transacción y el coste medio móvil se registra en **Diferencia de precio por media móvil**. |
| Cantidad de cero a negativa | El inventario utiliza el coste de la transacción para esa parte de la cantidad recibida que aumenta el saldo disponible de cero a positivo.                                                  |

## <a name="inventory-value-report"></a>Informe del valor del inventario

En este ejemplo de media móvil, se imprime el informe valor de inventario para admitir el cálculo de media móvil actual de un producto. El informe Valor de inventario permite imprimir las transacciones en orden cronológico, junto con el coste de admitir el cálculo del coste de media móvil de un producto. El informe muestra el coste de media móvil del producto. En el cuadro de diálogo **Informes de valor de inventario**, un intervalo de fechas le permite seleccionar el tipo de orden: por **Hora de la transacción** o por **Fecha de registro**. Normalmente, el informe se imprime con la opción **Fecha de registro**. La opción **Hora de transacción** es la fecha real en que se informa de la transacción y el coste de media móvil del producto se actualiza. Puede imprimir el informe Valor de inventario mediante la opción de orden **Hora de la transacción** si desea ver el cálculo del coste de media móvil a lo largo del tiempo. En la tabla siguiente se muestran las transacciones para el producto para el que se imprime el informe si usa la opción de orden **Hora de la transacción**.

| Hora de la transacción | Fecha         | Tipo de transacción           | La cantidad | Importe | Coste unitario promedio |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 de octubre    | Saldo inicial          | 0        | 0,00   | 0,00              |
| 8 de octubre        | 28 de septiembre | Recibo antedatado          | 1        | 16,00  | 16,00             |
| 3 de octubre        | 3 de octubre    | Recibo de compra           | 2        | 20,00  | 12,00             |
| 5 de octubre        | 5 de octubre    | Pedido de ventas                | -1       | -10,00 | 13,00             |
| 7 de octubre        | 7 de octubre    | Factura de compra           |          | 2,00   | 14,00             |
| 8 de octubre        | 8 de octubre    | Revalorización de la media móvil |          | 4.00   | 16.00             |
|                  | 31 de octubre   | Total                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> No se puede conciliar el libro mayor con el inventario mediante la opción de orden **Hora de la transacción**. El informe se debe imprimir mediante la opción **Fecha de registro**.
