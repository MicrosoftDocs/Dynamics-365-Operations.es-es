---
title: "Directivas de triple conciliación"
description: "Este artículo proporciona ejemplos de triple conciliación."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b9f66a9a907cf01046c78677a3f1d55f112fa8c7
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="three-way-matching-policies"></a>Directivas de triple conciliación

[!include[banner](../includes/banner.md)]


Este artículo proporciona ejemplos de triple conciliación.

<a name="example-three-way-matching-for-items"></a>Ejemplo: Triple conciliación para artículos
-------------------------------------

**Resumen**: Ken es controlador en las sedes corporativas de una entidad jurídica llamada Fabrikam. Ken decide que todas las facturas de proveedor basadas en pedidos de compra deben coincidir con las líneas de pedido de compra (doble conciliación). Para las compras de los artículos que se usarán como activos fijos, las facturas se deben coincidir con las líneas de pedido de compra y las líneas de recepción de producto (triple conciliación).

Fabrikam funciona con las entidades jurídicas y los empleados varias en todas las partes del mundo. Mientras el volumen de transacciones aumenta, las discrepancias entre los recibos y las facturas también se actualizando. Esto resulta en los activos que se han cancelado. Las facturas de los proveedores se vayan a pagadas, pero el proceso no incluye la identificación de discrepancias cuando se reciben menos artículos que se han ordenados, o cuando los artículos no se reciben en absoluto. El gasto también aumentará dado que los empleados aún necesitan las herramientas y otros materiales hacer que sus trabajos. Ken desea asegurarse de que los proveedores se envían los productos que se han que y los artículos se vayan a reciben por los empleados de Fabrikam. Por lo tanto, Ken requiere doble y la triple conciliación para todas las entidades jurídicas de la organización. Las ayudas de conciliación de facturas a garantizar que los problemas con los artículos que se hayan desaparecido o recibido puedan seguidos y cumplir. 

Las directivas de conciliación de facturas en este personas de la ayuda de ejemplo de los roles siguientes cumplen estos objetivos:

-   Ken es el controlador de la empresa de Fabrikam. Este puede ayudar a las personas de su organización a identificar y a sortear problemas con pedir, recepción, y pagar artículos (las mercancías y servicios) de los proveedores.
-   Phyllis y april son directores de contabilidad del departamento de los proveedores de la división de Estados Unidos de Fabrikam. Pueden aplicar la directiva corporativa y asegurarse de que las facturas se hayan pagado solo después de que las facturas se asocian al pedido de compra y las recepciones de bienes y servicios, según proceda.
-   Tony es el director de producción para la división de Estados Unidos de Fabrikam. Él y otros personales de producción pueden asegurarse de que los artículos estén recibidos como se pidieron de proveedores, y explicados de modo que personal tengan lo que deben tener para llevar a cabo sus trabajos.

### <a name="prerequisites"></a>Requisitos previos

-   Ken establece la directiva de conciliación en el nivel de entidad jurídica en Triple conciliación.
-   Ken establece la actualización automática de la alternancia de estado de coincidencia del encabezado en la entidad jurídica en Sí.
-   Ken establece el campo Conciliar totales de precios para la entidad jurídica en Porcentaje, y especifica 15% como porcentaje de tolerancia.
-   Ken establece la directiva de conciliación en el nivel de artículo para el artículo 1500 - Máquina de CNC Milicron en Triple conciliación. Este artículo es un artículo del activo que se usa para la producción en Fabrikam. Las facturas para este artículo se asocian a las líneas de pedido de compra para los precios y con las recepciones de producto para las cantidades.
-   Tony especifica un pedido para cinco máquinas de CNC Milicron. Alicia, vendedor del pedido de compra en Fabrikam, emite un pedido de compra en una entidad jurídica denominada Contoso para suministrar artículos.

    | Número de artículo                 | Cantidad | Precio unitario | Importe neto | Código de gastos        | Valor de gastos |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 - Máquina de CNC Milicron | 5        | 8.000,00   | 40.000,00  | Envío y dirección | 3.000,00      |

-   Arnie, vendedor de clientes en Contoso, revise los envíos para la semana. Arnie selecciona transacciones de envío a la factura Fabrikam para la entrega de las máquinas de CNC Milicron. Arnie incluye un gasto para enviar y guiar. Fabrikam tendrá en cuenta el gasto formar parte del coste del activo.

### <a name="scenario"></a>Escenario

1.  Sammy, trabajador en el departamento de recepción de Fabrikam, recibe la cantidad total de máquinas que se envían de Contoso. Éste especifica una cantidad de 5 en una recepción de producto. Dado que el pedido de compra se ha recibido completamente, el estado del pedido de compra cambia a Recibido.
2.  April, el coordinador de proveedores en Fabrikam, especifique y comprueba la factura que se produce por Contoso. Comprueba la siguiente información:
    -   Para los artículos que requieren triple conciliación, la cantidad de la línea de factura coincide con la cantidad que se ha recibido. La cantidad recibida se indica en la recepción de producto que se asigna a la factura.
    -   Para los artículos que requieren doble o triple conciliación, los precios en la línea de factura se encuentran dentro de las tolerancias que se definen en Microsoft Dynamics 365 for Operations. Esto incluye los siguientes tipos de conciliación de precio:
        -   Conciliación de precio neto unitario – el precio unitario neto de la línea de factura coincide con el precio unitario neto de la línea de pedido de compra, dentro del porcentaje de tolerancia. En este ejemplo, la tolerancia de precio unitario neto es el +8%.
        -   Conciliación de totales de precios: la desviación entre el importe neto de las líneas de facturas y el importe neto de las líneas de pedidos de compra deben estar dentro de los porcentajes de tolerancia permitidos. En este ejemplo, los totales de precio coincidentes tolerancia son los +15%.

La factura de papel de Contoso contiene la siguiente información.

| Artículo                        | La cantidad | Precio unitario | Importe neto |
|-----------------------------|----------|------------|------------|
| 1500 - Máquina de CNC Milicron | 5        | 8.100,00   | 40.500,00  |
| Envío y manipulación       |          |            | 4.000,00   |
| Impuesto                         |          |            | 0,00       |
| Total                       |          |            | 44.500,00  |

En Microsoft Dynamics 365 for Operations, la línea de factura incluye la información siguiente.

| código de artículo                 | Cantidad | Precio unitario | Importe neto de línea | Directiva de conciliación    | Cantidad de recepciones de producto para asignar | Conciliación de precios | Conciliación total de precios |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 - Máquina de CNC Milicron | 5        | 8.100,00   | 40.500,00       | Triple conciliación | Aprobada                         | Aprobada      | Aprobada            |

Puesto que esta línea se aprobará el proceso de conciliación de facturas, la factura se pueda registrar.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>Ejemplo: Triple conciliación para combinaciones de artículo y proveedor
Resumen: Ken es el controlador en las jefaturas corporativas de una entidad jurídica denominada Fabrikam. Ken decide que todas las facturas basadas en pedidos de compra deben coincidir con las líneas de pedido de compra (doble conciliación). Cassie es la contable en la división de Fabrikam en Malasia. Ella especifica que los artículos seleccionados que se piden de determinados proveedores en Malasia deben coincidir con las líneas de pedido de compra y las líneas de recepción de producto (triple conciliación). También puede anular la directiva de conciliación a un nivel superior de conciliación para los pedidos de compra. 

El volumen y los importes son pequeños, y ha habido problemas con la entrega de algunos proveedores en Malasia. Por estas razones, Cassie establece el nivel de comprobación para ciertas combinaciones de artículo y proveedor que se adquieren en Malasia en la triple conciliación. 

Las directivas de conciliación de facturas en este personas de la ayuda de ejemplo de los roles siguientes cumplen estos objetivos:
-   Ken es el controlador de la empresa de Fabrikam. Este puede ayudar a las personas de su organización a identificar y a sortear problemas con pedir, recepción, y pagar artículos (las mercancías y servicios) de los proveedores.
-   Cassie es la contable en la división de Fabrikam en Malasia. Puede aplicar la directiva corporativa y asegurarse de que las facturas se hayan pagado solo después de que se asocien a las líneas de pedido de compra y recepciones de producto que representan el envío de bienes y servicios, según proceda. Ella también puede aumentar el nivel de comprobación a la triple conciliación para los artículos específicos para controlar los costes operativos.

### <a name="prerequisites"></a>Requisitos previos

-   Ken establece la directiva de conciliación en el nivel de entidad jurídica en Doble conciliación.
-   Ken establece el campo Conciliar totales de precios para la entidad jurídica en Porcentaje, y especifica 10% como porcentaje de tolerancia.
-   Ken establece el porcentaje de tolerancia de precios por unidad para todos los artículos al 2%.
-   Cassie establece la directiva de conciliación en el nivel de la combinación de artículo y proveedor para el artículo PH2500: equipo y proveedor Contoso en Triple conciliación.
-   Alicia, responsable del pedido de compra en Fabrikam en la división de Malasia, emite pedidos de compra a Contoso para suministrar tres artículos, tal y como se muestra en la siguiente tabla. Al crear el pedido de compra, anula la directiva de conciliación para que el mouse inalámbrico sea de triple conciliación en lugar de doble conciliación.

    | Número de artículo           | Cantidad | Precio unitario | Importe neto | Directiva de conciliación (entrada predeterminada) | Directiva de conciliación (en la línea de pedido de compra) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | Equipo: PH2500     | 2        | 2.500,00   | 5.000,00   | Triple conciliación              | Triple conciliación                           |
    | MM01: mouse inalámbrico | 2        | 40,00      | 80,00      | Doble conciliación                | Triple conciliación                           |
    | Unidad USB             | 200      | 10,00      | 2.000,00   | Doble conciliación                | Doble conciliación                             |

### <a name="scenario"></a>Situación

1.  Llegan los artículos. Se interrumpe a Sammy, trabajador en el departamento de recepción de Fabrikam en la división de Malasia, y no registra la recepción del producto inmediatamente.
2.  April, el coordinador de proveedores en Fabrikam, especifique y comprueba la factura que se produce por Contoso. Comprueba la siguiente información:
    -   Para los artículos que requieren triple conciliación, la cantidad de la línea de factura coincide con la cantidad que se ha recibido. La cantidad recibida se indica en la recepción de producto que se asigna a la factura.
    -   Para los artículos que requieren doble o triple conciliación, los precios en la línea de factura se encuentran dentro de las tolerancias que se definen en Microsoft Dynamics 365 for Operations. Esto incluye los siguientes tipos de conciliación de precio:
        -   Conciliación de precio neto unitario – el precio unitario neto de la línea de factura coincide con el precio unitario neto de la línea de pedido de compra, dentro del porcentaje de tolerancia. En este ejemplo, la tolerancia de precio unitario neto es el +2%.
        -   Conciliación de totales de precios: la desviación entre el importe neto de las líneas de facturas y el importe neto de las líneas de pedidos de compra deben estar dentro de los porcentajes de tolerancia permitidos. En este ejemplo, los totales de precio coincidentes tolerancia son los +10%.

La factura de papel de Contoso contiene la siguiente información.

| Artículo                  | La cantidad | Precio unitario | Importe neto |
|-----------------------|----------|------------|------------|
| Equipo: PH2500     | 2        | 2.500,00   | 5.000,00   |
| MM01: mouse inalámbrico | 2        | 41,00      | 82,00      |
| Unidad USB             | 200      | 10,05      | 2.010,00   |
| Factura total         |          |            | 7.092,00   |

En Microsoft Dynamics 365 for Operations, la línea de factura incluye la información siguiente.

| código de artículo           | Cantidad | Precio unitario | Importe neto de línea | Directiva de conciliación    | Cantidad de recepciones de producto para asignar | Conciliación de precios | Conciliación total de precios |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| Equipo: PH2500     | 2        | 2.500,00   | 5.000,00        | Triple conciliación | Error                         | Aprobada      | Aprobada            |
| MM01: mouse inalámbrico | 2        | 41,00      | 82,00           | Triple conciliación | Error                         | Error      | Aprobada            |
| Unidad USB             | 200      | 10,05      | 2010,00         | Doble conciliación   |                                | Aprobada      | Aprobada            |

Tenga en cuenta los siguientes elementos:
-   Para el artículo PH2500: línea de equipo, la columna Cantidad de recepciones de producto para asignar tiene un icono de advertencia porque la línea de factura no coincide con una recepción de producto.
-   Para la línea MM01: mouse inalámbrico, la columna Cantidad de recepciones de producto para asignar tiene un icono de advertencia porque la línea de factura no coincide con una recepción de producto. La columna Conciliación de precio unitario tiene un icono de advertencia porque se supera la tolerancia del 2% de precio unitario neto.
-   Para la línea Unidad USB, la columna Cantidad de recepciones de producto para asignar está en blanco porque la doble conciliación no coincide con la línea de factura y las cantidades de la línea de recepción de producto.

Si es necesaria la aprobación para que las facturas se registren con discrepancias de conciliación de facturas, se debe activar Aprobar registro con discrepancias en la página Detalles de coincidencia de factura antes de poder registrar la factura con errores de conciliación de precio y de cantidad. Si la aprobación no es necesaria, el proceso de la factura puede continuar si no hay otros errores de registro.


Para obtener más información, consulte [Conciliación de facturas de proveedores](accounts-payable-invoice-matching.md).




