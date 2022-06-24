---
title: Ejemplos de informes de valor de inventario y lógica
description: Este artículo proporciona algunos ejemplos de resultados que se presentan en cada tipo de informe de valor de inventario. Los informes de valor de inventario proporcionan detalles sobre los importes y cantidades físicas y financieras de su inventario.
author: JennySong-SH
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: e6c6387be5204fde6ebc7a4983567801900974af
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877664"
---
# <a name="inventory-value-report-examples-and-logic"></a>Ejemplos de informes de valor de inventario y lógica

[!include [banner](../includes/banner.md)]

Los informes de valor de inventario proporcionan detalles sobre los importes y cantidades físicas y financieras de su inventario. Este artículo proporciona algunos ejemplos de resultados que se presentan en cada tipo de informe de valor de inventario.

Para obtener más información sobre cómo generar y utilizar cada tipo de informe de valor de inventario, consulte [Informes de valor de inventario](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Datos de muestra que se usan en estos ejemplos

Los ejemplos de este artículo se basan en los datos de muestra de transacciones de inventario que se describen en esta sección.

### <a name="storage-dimension-setup"></a>Configuración de la dimensión de almacenamiento

El sistema de ejemplo contiene la siguiente configuración de dimensiones de almacenamiento.

| Nombre | Activas | Inventario físico | Inventario financiero |
|---|---|---|---|
| Sitio | Sí | Sí | Sí |
| Almacén | Sí | Sí | No |

### <a name="inventory-model"></a>Modelo de inventario

Para el sistema de ejemplo, el modelo de inventario para los productos publicados es *FIFO*, y el campo **Precio de coste** para el modelo de inventario es *Incluir valor físico*.

### <a name="inventory-transactions"></a>Transacciones de inventario

El sistema de ejemplo contiene las siguientes transacciones de inventario para un producto publicado que tiene el número de artículo *B0001*.

| Referencia | Sitio | Almacén | Recepción | Problema | Fecha física | Fecha financiera | Cantidad | Importe de coste | Importe de coste físico |
|---|---|---|---|---|---|---|---|---|---|
| Pedido de compra | 1 | 11 | Comprado | | 15 de marzo | 15 de marzo | 10 | 1.000 | 1.000 |
| Pedido de compra | 2 | 21 | Comprado | | 15 de marzo | 15 de marzo | 10 | 2,000 | 2,000 |
| Pedido de compra | 1 | 11 | Recibida | | 15 de abril | | 5 | | 375 |
| Orden de transferencia | 1 | 11 | | Vendido | mayo de 2 | mayo de 2 | -5 | -458,33 | -458,33 |
| Orden de transferencia | 1 | 12 | Comprado | | mayo de 2 | mayo de 2 | 5 | 458.33 | 458.33 |
| Pedido de ventas | 1 | 12 | | Vendido | mayo de 3 | mayo de 3 | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Configuración de informes de valor de inventario

El sistema de ejemplo incluye una configuración de informes de valor de inventario que tiene los siguientes ajustes:

- **Intervalo:**  *Fecha de registro*
- **Inventario:** *Sí*
- **Calcular coste unitario promedio:** *Sí*
- **Cantidad total y valor:** *Sí*
- **Sitio, vista:** *Seleccionado*
- **ID de recurso, vista:** *Sí*
- **Nivel:** *Totales*

## <a name="inventory-value-report-example-1"></a>Ejemplo de informes de valor de inventario 1

La siguiente tabla e ilustraciones muestran los resultados cuando utiliza los datos de ejemplo y la configuración de informes que se describen anteriormente en este artículo.

| Tipo de recurso | Recurso | Sitio | Referencia | Inventario: Cantidad financiera | Inventario: Importe financiero | Inventario: Cantidad física registrada | Inventario: Importe físico registrado | Inventario: Cantidad | Inventario: Importe | Coste unitario promedio |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Saldo final | 9.00 | 908.33 | 5.00 | 375.00 | 14,00 | 1,283.33 | 91.67 |
| Material | B0001 | 2 | Saldo final | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Informe de valor de inventario estándar para el ejemplo 1

La siguiente ilustración muestra el informe de **Valor de inventario** estándar para el ejemplo 1. (Seleccione la ilustración para abrir una versión más grande).

[![Informe de valor de inventario para el ejemplo 1.](media/inventory-value-report-ex1-small.png "Informe de valor de inventario para el ejemplo 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Informe de almacenamiento de informes de valor de inventario para el ejemplo 1

La siguiente ilustración muestra el informe de **Almacenamiento de informes de valor de inventario** para el ejemplo 1. (Seleccione la ilustración para abrir una versión más grande).

[![Informe de almacenamiento de informes de valor de inventario para el ejemplo 1.](media/inventory-value-report-storage-ex1-small.png "Informe de almacenamiento de informes de valor de inventario para el ejemplo 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Ejemplo de informes de valor de inventario 2

La siguiente tabla e ilustraciones muestran los resultados cuando utiliza los datos de ejemplo que se describen anteriormente en este artículo, pero usted cambia el valor del campo **Nivel** a *Transacciones* en la configuración del informe, y establece el campo **Fecha de inicio** a *15 de marzo* cuando ejecuta el informe.

| Tipo de recurso | Recurso | Sitio | Fecha | Número | Referencia | Inventario: Cantidad financiera | Inventario: Importe financiero | Inventario: Cantidad física registrada | Inventario: Importe físico registrado | Inventario: Cantidad | Inventario: Importe |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 3/15/2021 | 00000126 | Pedido de compra | 0,00 | 0,00 | 10,00 | 1.000,00 | **10.00** | **1,000.00** |
| Material | B0001 | 1 | 3/15/2021 | 00000126 | Pedido de compra | 10,00 | 1.000,00 | -10,00 | -1.000,00 | **0.00** | **0.00** |
| Material | B0001 | 1 | 4/15/2021 | 00000128 | Pedido de compra | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Material | B0001 | 1 | 5/2/2021 | 000003 | Envío de pedidos de transferencia | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |
| Material | B0001 | 1 | 5/2/2021 | 000003 | Recepción de pedidos de transferencia | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 1 | 5/3/2021 | 000835 | Pedido de ventas | 0,00 | 0,00 | -1,00 | -91,67 | **-1.00** | **-91.67** |
| Material | B0001 | 1 | 5/3/2021 | 000835 | Pedido de ventas | -1,00 | -91,67 | 1.00 | 91.67 | **0.00** | **0.00** |
| Material | B0001 | 2 | 3/15/2021 | 00000127 | Pedido de compra | 0,00 | 0,00 | 10,00 | 2,000.00 | **10.00** | **2,000.00** |
| Material | B0001 | 2 | 3/15/2021 | 00000127 | Pedido de compra | 10,00 | 2,000.00 | -10,00 | -2.000,00 | **0.00** | **0.00** |
| Material | B0001 | 2 | 5/2/2021 | 000003 | Envío de pedidos de transferencia | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 2 | 5/2/2021 | 000003 | Recepción de pedidos de transferencia | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Informe de valor de inventario estándar para el ejemplo 2

La siguiente ilustración muestra el informe de **Valor de inventario** estándar para el ejemplo 2. (Seleccione la ilustración para abrir una versión más grande).

[![Informe de valor de inventario para el ejemplo 2.](media/inventory-value-report-ex2-small.png "Informe de valor de inventario para el ejemplo 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Informe de almacenamiento de informes de valor de inventario para el ejemplo 2

La siguiente ilustración muestra el informe de **Almacenamiento de informes de valor de inventario** para el ejemplo 2. (Seleccione la ilustración para abrir una versión más grande).

[![Informe de almacenamiento de informes de valor de inventario para el ejemplo 2.](media/inventory-value-report-storage-ex2-small.png "Informe de almacenamiento de informes de valor de inventario para el ejemplo 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Ejemplo de informes de valor de inventario 3

Recomendamos que ejecute informes de valor de inventario después del recálculo o cierre de inventario, para que tenga las transacciones y los importes que se ven afectados por el recálculo o cierre de inventario.

Las siguientes subsecciones muestran los informes de valor de inventario que se generan después de cerrar el inventario hasta el 30 de mayo.

### <a name="example-3-when-the-totals-level-is-used"></a>Ejemplo 3 cuando se usa el nivel de Totales

La siguiente tabla muestra los resultados cuando utiliza los datos de ejemplo y la configuración de informes que se describen anteriormente en este artículo. (En esa configuración de informe, el campo **Nivel** está configurado en *Totales*.)

| Tipo de recurso | Recurso | Sitio | Referencia | Inventario: Cantidad financiera | Inventario: Importe financiero | Inventario: Cantidad física registrada | Inventario: Importe físico registrado | Inventario: Cantidad | Inventario: Importe | Coste unitario promedio |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Saldo final | 9.00 | 900.00 | 5.00 | 375.00 | 14,00 | 1,275.00 | 91.07 |
| Material | B0001 | 2 | Saldo final | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Ejemplo 3 cuando se usa el nivel de Transacciones

La siguiente tabla muestra los resultados cuando usa los datos de ejemplo que se describen anteriormente en este artículo, pero usted cambia el valor del campo **Nivel** a *Transacciones* en la configuración del informe.

| Tipo de recurso | Recurso | Sitio | Fecha | Número | Referencia | Inventario: Cantidad financiera | Inventario: Importe financiero | Inventario: Cantidad física registrada | Inventario: Importe físico registrado | Inventario: Cantidad | Inventario: Importe |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 3/15/2021 | 00000126 | Pedido de compra | 0,00 | 0,00 | 10,00 | 1.000,00 | 10,00 | 1.000,00 |
| Material | B0001 | 1 | 3/15/2021 | 00000126 | Pedido de compra | 10,00 | 1.000,00 | -10,00 | -1.000,00 | 0,00 | 0,00 |
| Material | B0001 | 1 | 4/15/2021 | 00000128 | Pedido de compra | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Material | B0001 | 1 | 5/2/2021 | 000003 | Envío de pedidos de transferencia | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 1 | 5/2/2021 | 000003 | Recepción de pedidos de transferencia | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 1 | 5/3/2021 | 000835 | Pedido de ventas | 0,00 | 0,00 | -1,00 | -91,67 | -1,00 | -91,67 |
| Material | B0001 | 1 | 5/3/2021 | 000835 | Pedido de ventas | -1,00 | -91,67 | 1.00 | 91.67 | 0,00 | 0,00 |
| Material | B0001 | 1 | 5/31/2021 | 000835 | Pedido de ventas | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Material | B0001 | 1 | 5/31/2021 | 000003 | Envío de pedidos de transferencia | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Material | B0001 | 1 | 5/31/2021 | 000003 | Recepción de pedidos de transferencia | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 3/15/2021 | 00000127 | Pedido de compra | 0,00 | 0,00 | 10,00 | 2,000.00 | 10,00 | 2,000.00 |
| Material | B0001 | 2 | 3/15/2021 | 00000127 | Pedido de compra | 10,00 | 2,000.00 | -10,00 | -2.000,00 | 0,00 | 0,00 |
| Material | B0001 | 2 | 5/2/2021 | 000003 | Envío de pedidos de transferencia | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 2 | 5/2/2021 | 000003 | Recepción de pedidos de transferencia | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 2 | 5/31/2021 | 000003 | Envío de pedidos de transferencia | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 5/31/2021 | 000003 | Recepción de pedidos de transferencia | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
