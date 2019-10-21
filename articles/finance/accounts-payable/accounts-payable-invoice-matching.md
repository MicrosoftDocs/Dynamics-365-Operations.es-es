---
title: Visión general de la conciliación de facturas de proveedores
description: La conciliación de facturas de proveedores es el proceso de conciliación de la factura de proveedor, el pedido de compra y la información de recepción de producto.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 27361
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b45c6f20bf5b6fb02379f71b5806c6c147789e73
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189761"
---
# <a name="accounts-payable-invoice-matching-overview"></a>Visión general de la conciliación de facturas de proveedores

[!include [banner](../includes/banner.md)]

La conciliación de facturas de proveedores es el proceso de conciliación de la factura de proveedor, el pedido de compra y la información de recepción de producto.

A la hora de conciliar documentos, las diferencias entre estos documentos se denominan "discrepancias coincidentes". Las discrepancias de conciliación se comparan con las tolerancias especificadas. Si una discrepancia de conciliación supera el porcentaje o el importe de tolerancia, se mostrarán iconos de desviación de conciliación en la página Factura de proveedor y en la página Historial de facturas y detalles de conciliación. 

Por ejemplo, ha especificado un pedido de compra con un artículo de línea para 1.000 baterías a un precio de 1,00 cada una. El pedido de compra se aprueba y se envía al proveedor. El proveedor envía 1.000 baterías y usted indica una recepción de producto para 1.000 baterías a un precio de 1,00 cada una. El coste de inventario de las baterías se actualizará con este precio. 

Llega una factura para 1.000 baterías a un precio de 1,10 cada una. La directiva de la entidad jurídica permite una tolerancia de precio unitario neto del 5 por ciento para esta categoría de artículo. Un precio de 1,05 sería aceptable, pero 1,10 no lo es. Al especificar la información de la factura, se identifica una discrepancia de conciliación de precios y se puede guardar la factura hasta que la discrepancia se resuelva.

Puede usar los siguientes tipos de conciliación de facturas de proveedores:

-   Conciliación de totales de factura: concilie los importes totales de la factura con los importes totales del pedido de compra. Este tipo de conciliación de la factura incluye el importe mínimo de detalle, por lo que puede usar esta opción para configurar los controles que minimizan el tiempo de personal necesario para revisar la información de conciliación de facturas.
-   Doble conciliación: concilie la información del precio de la factura con la información del precio del pedido de compra.
-   Triple conciliación: concilie la información del precio de la factura con la información del precio del pedido de compra. Concilie también la información de cantidad de la factura con la información de cantidad de las recepciones de producto seleccionadas para la factura.
-   Conciliación de gastos: concilie la información de gastos (importes) de la factura con la información de gastos (importes) del pedido de compra.

> [!NOTE]
> Otros formularios de validación de factura se pueden completar mediante las directivas de facturas de proveedor. 

La doble conciliación y la triple conciliación siempre concilian la información del precio por precio unitario. También puede configurar estas directivas de conciliación para que coincida con la información del precio por el total de precio.
-   Conciliación de precio unitario neto: concilie la información de precio para doble conciliación o triple conciliación comparando el precio unitario neto de cada línea de la factura con el precio unitario neto correspondiente del pedido de compra. El precio unitario neto se determina por la fórmula siguiente: importe neto de la línea/cantidad de la línea
-   Conciliación de totales de precio: concilie la información de precio para doble o triple conciliación comparando el importe neto (total de precio) de cada línea de la factura con el importe neto correspondiente del pedido de compra. El importe neto se determina por la fórmula siguiente: *(precio unitario \* cantidad de línea) + gastos de línea - descuentos de línea*. Al correlacionar los totales de precio por porcentaje, el sistema compara los valores utilizando la divisa de transacción. Al correlacionar los totales de precio por importe, el sistema compara los valores utilizando la divisa de contabilidad.

Normalmente, los cálculos de conciliación de facturas se realizan automáticamente al editar facturas de proveedor en la página Factura de proveedor. Como alternativa, la conciliación de facturas se puede realizar a pedido, según sea necesario. La conciliación de facturas bajo pedido se controla para la entidad jurídica mediante Actualizar estado de encabezado de factura automáticamente en la página Parámetros de proveedores en la ficha Validación de factura. También se pueden conciliar facturas como parte de un proceso de revisión de facturas. Puede ver los resultados de la conciliación de facturas en la página Factura de proveedor y las páginas de conciliación de facturas relacionadas.

## <a name="invoice-totals-matching"></a>Conciliación de totales de factura
Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable. Se comparan seis totales en la página Detalles de coincidencia de totales de factura, tal y como se muestra en la siguiente tabla. Si la tolerancia permisible para la conciliación de los totales de la factura es del 20%, el porcentaje de desviación del 100% para el importe de descuento total se considera una discrepancia de conciliación.

| Campo Total    | Total de la factura real | Total de la factura previsto | Porcentaje de la desviación | Estado de conciliación |
|----------------|----------------------|------------------------|---------------------|--------------|
| Saldo        | 495,00               | 495,00                 | 0%                  | Aprobada       |
| Descuento total | 0,00                 | 9,90                   | 100 %                | Error       |
| Cargos        | 64,90                | 64,90                  | 0%                  | Aprobada       |
| Impuestos      | 139,98               | 137,50                 | 2%                  | Aprobada       |
| Redondear      | 0,00                 | 0,00                   | 0%                  | Aprobada       |
| Importe de factura | 699,88               | 687,50                 | 2%                  | Aprobada       |

La conciliación de totales de factura se controla para la entidad jurídica mediante la opción Conciliar totales de factura en la página Parámetros de proveedores. La conciliación se realiza en los totales previstos de la factura y los totales de factura reales. Los totales previstos de factura se calculan en función de los precios, gastos e información de impuestos de los pedidos de compra y las cantidades de la factura.

## <a name="two-way-price-totals-matching"></a>Doble conciliación de totales de precio
Use la doble conciliación para asegurarse de que la desviación entre la información sobre precios del pedido de compra y la factura se encuentra dentro de las tolerancias aceptables. Puede comparar la información sobre precios del importe neto de cada línea de factura, y todas las líneas de factura pendientes y registradas anteriormente, con el importe neto de la línea del pedido de compra correspondiente. A esto se le llama "conciliación de totales de precio". 

La conciliación de totales de precios se puede basar en un porcentaje, un importe o un porcentaje y un importe. 

Si se especifica un porcentaje de tolerancia de totales de precio de compra, se comparan cinco campos, como se muestra en la siguiente tabla. Dado que el porcentaje de tolerancia de totales de precio de compra es del 10%, el porcentaje de desviación del total de precio del 50% representa una discrepancia en la conciliación.

| Estado de conciliación | Importe neto de factura | Importe neto previsto | Porcentaje total de precio de compra sin conciliar (importe de desviación) | Porcentaje total de precio de compra sin conciliar (porcentaje de desviación) | Porcentaje de tolerancia total de precio de compra |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Aprobada       | 105,00             | 100,00              | 5,00                                             | 5%                                                              | 10%                                    |
| Error       | 150,00             | 100,00              | 50,00                                            | 50 %                                                             | 10%                                    |

Si se especifica un importe de tolerancia de totales de precio de compra, se comparan cinco campos, como se muestra en la siguiente tabla. Dado que el importe de tolerancia de totales de precio de compra es del 100,00, el importe de desviación del total de precio del 105,00 representa una discrepancia en la conciliación.

| Estado de conciliación | Importe neto de factura | Importe neto previsto | Porcentaje total de precio de compra sin conciliar (importe de desviación) | Total de precio de compra sin conciliar en la divisa de contabilidad (importe de desviación) | Tolerancia total de precio de compra |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Aprobada       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Error       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Si la conciliación de totales de precio se configura con una tolerancia de porcentaje y un importe de tolerancia, referidos a veces como "importe que no se debe superar", ambas tolerancias se consideran al evaluar si una línea tiene una discrepancia en la conciliación. Si el porcentaje o el importe supera la tolerancia, como se muestra en las líneas 150,00 y 205,00 de la siguiente tabla, la línea tiene una discrepancia en la conciliación.

| Estado de conciliación | Importe neto de factura | Importe neto previsto | Porcentaje total de precio de compra sin conciliar (porcentaje de desviación) | Porcentaje de tolerancia total de precio de compra | Total de precio de compra sin conciliar en la divisa de contabilidad (importe de desviación) | Tolerancia total de precio de compra |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Aprobada       | 105,00             | 100,00              | 5%                                                              | 10%                                    | 5,00                                                                    | 100,00                         |
| Error       | 150,00             | 100,00              | 50 %                                                             | 10%                                    | 50,00                                                                   | 100,00                         |
| Error       | 205,00             | 100,00              | 105%                                                            | 10%                                    | 105,00                                                                  | 100,00                         |

La conciliación de doble conciliación se controla para la entidad jurídica mediante el campo Directiva de conciliación de líneas de la página Parámetros de proveedores. En función de la selección en el campo Permitir anulación de directiva de conciliación, puede seleccionar la doble conciliación para un proveedor específico, un artículo o una combinación de artículo y proveedor en la página Directiva de conciliación, y para un pedido de compra específico en la página Pedido de compra.

La conciliación de totales de precios se controla para la entidad jurídica mediante la opción Conciliar totales de precios en la página Parámetros de proveedores. El porcentaje de tolerancia de totales de precio de compra y el importe de la tolerancia (importe que no se debe superar) también se especifican en esa página.

## <a name="two-way-net-unit-price-matching"></a>Doble conciliación de precio unitario
Use la doble conciliación para asegurarse de que la desviación entre la información sobre precios del pedido de compra y la factura se encuentra dentro de las tolerancias aceptables. Puede comparar la información sobre precios del precio unitario neto de cada artículo en la factura. A esto se le llama "conciliación de precio unitario neto". 

Se comparan nueve importes de línea en la página Detalles de coincidencia de factura, tal y como se muestra en la siguiente tabla. Si la tolerancia de precios permisible de la conciliación de precio neto es del 10%, la desviación de 22,61% para el precio unitario neto se considera una discrepancia en la conciliación.

| Campo Línea                    | Valor de la factura | Valor de pedido de compra | Porcentaje de la desviación | Estado de conciliación |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Precio unitario                    | 55,40         | 55,38                | 0%                  | Aprobada       |
| Unidad de precio                    | 1,00          | 1,00                 | 0%                  | Aprobada       |
| Gastos en compras          | 50,00         | 0,00                 | 100 %                | Error       |
| Descuento                      | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Porcentaje de descuento              | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Descuento multilínea            | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Porcentaje de descuento multilínea | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Importe neto                    | 271,60        | 221,52               | 22,61%              | Error       |
| Precio unitario neto                | 67,9000       | 55,3800              | 22,61%              | Error       |

La conciliación de doble conciliación se controla para la entidad jurídica mediante el campo Directiva de conciliación de líneas de la página Parámetros de proveedores. En función de la selección en el campo Permitir anulación de directiva de conciliación, puede seleccionar la doble conciliación para un proveedor específico, un artículo o una combinación de artículo y proveedor en la página Directiva de conciliación, y para un pedido de compra específico en la página Pedido de compra. 

La conciliación de precio unitario neto se controla para la entidad jurídica mediante el campo Habilitar validación de conciliación de facturas en la página Parámetros de proveedores. Los porcentajes de tolerancia de precio neto unitario se pueden configurar para artículos, grupos de artículos, proveedores, grupos de proveedores, combinaciones de artículos y proveedores o entidad jurídica usando la página Tolerancias de precios.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>Doble conciliación de totales de precio y conciliación de precio unitario neto
Puede usar la conciliación de totales de precio y la conciliación de precio unitario neto juntas. Este ejemplo asume la configuración siguiente:

-   La tolerancia de precio unitario neto para el artículo Unidad USB es del 10%.
-   La tolerancia de conciliación de totales de precio para la entidad jurídica es del 15% o 500,00.

El pedido de compra contiene la siguiente línea.

| Número de artículo | Cantidad | Precio unitario | Importe neto |
|-------------|----------|------------|------------|
| Unidad USB   | 1.000    | 10,00      | 10.000,00  |

Se especifican tres facturas, como se muestra en la siguiente tabla. Hay una discrepancia de conciliación de factura para la factura 3 porque la desviación de 1.880,00 supera el importe de tolerancia de totales de precio de compra de 500,00. Para la conciliación de totales de precio, el importe neto de factura incluye todas las facturas registradas anteriormente además de la factura con la que está trabajando actualmente.

| Número de artículo          | Cantidad | Precio unitario | Importe neto | Conciliación de precios | Conciliación total de precios |
|----------------------|----------|------------|------------|-------------|-------------------|
| Factura 1: Unidad USB | 800      | 10,80      | 8.640,00   | Aprobada      | Aprobada            |
| Factura 2: Unidad USB | 100      | 10,80      | 1.080,00   | Aprobada      | Aprobada            |
| Factura 3: Unidad USB | 200      | 10,80      | 2.160,00   | Aprobada      | Error            |
| Total                |          |            | 11.880,00  |             |                   |

## <a name="three-way-matching"></a>Triple conciliación

Use la triple conciliación para asegurarse de que la desviación entre la información sobre precios del pedido de compra y la factura se encuentra dentro de las tolerancias aceptables, y para asegurarse de que la cantidad de la factura coincide con la cantidad de las recepciones de producto correspondientes.

Los mismos importes de línea se comparan en la página Detalles de coincidencia de factura como en la doble conciliación. Además, la cantidad de la factura coincide con las cantidades de recepción de producto que se han recibido. Si la cantidad de la factura difiere de la cantidad de recepción de producto conciliada, hay un error de conciliación de cantidad.

| Campo Línea                    | Valor de la factura | Valor de pedido de compra | Porcentaje de la desviación | Estado de conciliación |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Precio unitario                    | 55,40         | 55,38                | 0%                  | Aprobada       |
| Unidad de precio                    | 1,00          | 1,00                 | 0%                  | Aprobada       |
| Gastos en compras          | 50,00         | 0,00                 | 100 %                | Error       |
| Descuento                      | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Porcentaje de descuento              | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Descuento multilínea            | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Porcentaje de descuento multilínea | 0,00          | 0,00                 | 0%                  | Aprobada       |
| Importe neto                    | 271,60        | 221,52               | 22,61%              | Error       |
| Precio unitario neto                | 67,9000       | 55,3800              | 22,61%              | Error       |

| Campo Línea                     | Valor de la factura | Estado de conciliación |
|--------------------------------|---------------|--------------|
| Cantidad de la factura               | 4,00          |              |
| Recepciones de producto asignadas totales | 0,00          | Error       |

La triple conciliación se controla para la entidad jurídica mediante el campo Directiva de conciliación de líneas de la página Parámetros de proveedores. En función de la selección en el campo Permitir anulación de directiva de conciliación, puede seleccionar la triple conciliación para un proveedor específico, un artículo o una combinación de artículo y proveedor en la página Directiva de conciliación, y para un pedido de compra específico en la página Pedido de compra.

## <a name="charges-matching"></a>Conciliación de gastos varios
Puede usar la conciliación de gastos para asegurarse de que los importes de gastos no se desvían de los importes previstos en más de un porcentaje de desviación aceptable. Los importes totales de cada código de gastos que se aplican a la factura y al pedido de compra se comparan en la página Comparar valores de gastos varios - Factura: página, como se muestra en la siguiente tabla. Si la tolerancia permisible para el código de gastos es del 25%, el porcentaje de desviación del 99.999.999.999,99% para el código de gastos de licencia se considera una discrepancia de conciliación.

> [!NOTE] 
> Un porcentaje de desviación de 99.999.999.999,99% significa que el importe previsto basado en el pedido de compra es cero y el importe real de la factura es un valor positivo. 

| Estado de conciliación de gastos | Código de gastos de factura | Valor calculado total real | Valor calculado total previsto | Importe de desviación | Porcentaje de la desviación | Porcentaje de tolerancia |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Error               | Licencia              | 25                            | 0                               | 25              | 99.999.999.999,99%  | 25%                  |
| Aprobada               | Flete              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| Error               | Urgente             | 4                             | 2                               | 2               | 100 %                | 25%                  |

La conciliación de gastos de factura se controla para la entidad jurídica mediante la opción Conciliar gastos en la página Parámetros de proveedores. Puede configurar los porcentajes de tolerancia de desviación para los gastos en la página Tolerancias de gastos.

> [!NOTE]
> La conciliación de gastos se realiza solo en los códigos de gastos para los que se haya seleccionado la opción Comparar pedido de compra y valores de factura en la página Código de gastos.

## <a name="related-functionality"></a>Funcionalidad relacionada
Las facturas de proveedor a menudo se basan en los recepciones de producto que representan envíos reales, en lugar de basarse en pedidos de compra. Algunas veces, los importes facturados no coinciden con los importes de los pedidos de compra, y otras veces las cantidades enviadas no coinciden con las cantidades facturadas. También puede ayudar a gestionar la información de las siguientes formas:
-   Cree una factura de proveedor en función de las recepciones de producto. Las recepciones de producto se sugieren automáticamente para las facturas, y puede seleccionar qué recepciones de producto usar. También pueden seleccionar artículos de línea de recepciones de producto específicos de varios pedidos de compra, en caso necesario.
-   Ver y aprobar diferencias de cantidad entre la cantidad facturada en la factura y la cantidad recibida en la recepción de producto. Si existe una diferencia, se podrá guardar la factura y vincularla más adelante con otra recepción de producto o modificar la cantidad facturada para que coincida con la cantidad recibida.
-   Especifique importes de factura que no se han incluido en el pedido de compra original, de modo que la información de la factura coincida con la factura recibida del proveedor. Se pueden comparar los gastos varios de pedidos de compra con gastos varios para las facturas. En caso necesario, se pueden agregar gastos a las facturas y asignarlos a líneas de factura.
-   Vea y apruebe discrepancias de conciliación de precios entre el precio unitario neto de la factura y el precio unitario neto del pedido de compra. Se pueden configurar porcentajes de tolerancia de precios para la entidad jurídica, los proveedores y los artículos. Si el precio de la línea de factura del proveedor no se encuentra dentro de la tolerancia de precios aceptable, se puede guardar la factura hasta que se apruebe para el registro o bien hasta que se reciba una corrección por parte del proveedor.

Para obtener más información, consulte [Directivas de triple conciliación](three-way-matching-policies.md) y [Validación de conciliación de facturas de proveedores de instalación](tasks/set-up-accounts-payable-invoice-matching-validation.md). 




