---
title: Asignación de ingresos
description: Este tema explica cómo utilizar la asignación de ingresos en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 2a1bdff364039c6bf0cdfbc11f0979398934c52c
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629450"
---
# <a name="revenue-allocation"></a>Asignación de ingresos

Este tema explica cómo configurar los parámetros de asignación de ingresos para una programación de facturación. Puede configurar o editar la asignación de ingresos cuando crea la programación de facturación. Cuando abre la página **Asignación de ingresos** para una programación de facturación activa o terminada, los campos son de solo lectura.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Especificar la asignación de ingresos para una programación de facturación

Para especificar la asignación de ingresos para una programación de facturación, siga estos pasos.

1. En la página de listas **Programas de facturación (todas/activas)**, seleccione una programación de facturación o una línea de programación de facturación.
2. En la pestaña **Asignación de ingresos** de la parte superior de la página, seleccione **Asignación de ingresos**.
3. En el campo **Tipo de disposición de varios elementos**, seleccione el tipo de disposición de elementos múltiples (MEA).
4. En el campo **Número de disposición de varios elementos**, especifique el número de MEA. Luego, en el campo **Cuenta de ingresos de contratos aplazados**, especifique la cuenta de ingresos de contratos aplazados.

    Si configura el campo **Tipo de disposición de varios elementos** como **Único**, se aplicarán los mismo valores de **Número de disposición de varios elementos** y **Cuenta de ingresos de contratos aplazados** a cada línea. Si configura el campo **Tipo de disposición de varios elementos** como **Varios**, puede especificar distintos valores de **Número de disposición de varios elementos** y **Cuenta de ingresos de contratos aplazados** a cada línea.
    
    Número de MEA solo se puede asignar a dos o más elementos. Una sola línea no puede tener su propio número de MEA.

5. Seleccione **Guardar**.

### <a name="fields"></a>Campos

La página **Disposición de varios elementos** contiene los siguientes campos.

| Campo | Description |
|---|---| 
| Tipo de disposición de varios elementos | <p>Seleccione el tipo de MEA para la transacción:</p><ul><li>**Varios** – Los elementos de línea en la transacción son parte del MEA, o existe más de una disposición.</li><li>**Ninguno** – La transacción es una transacción estándar que no tiene ninguna asignación de ingresos.</li><li>**Único** – Todos los elementos de la transacción forman parte de un solo MEA.</li></ul> |
| Número de disposición de varios elementos | <p>Número de MEA para la línea. Este campo solo está disponible cuando el campo **Tipo de disposición de varios elementos** está establecido en **Varios**.</p><p>Si este campo está en blanco y asigna un número de MEA, los campos **Origen de precio de venta individual** y **Precio de venta individual** se actualizan automáticamente en función de los valores de la página **Precio de venta individual de artículo**. Solo están disponibles los números de MEA que están asignados a otras líneas en el pedido de ventas.</p> |
| Cuenta de ingresos de contratos aplazados | Especifique la cuenta que se usará para los movimientos del diario cuando se cree una factura de contrato MEA. Este campo solo está disponible cuando se utiliza facturación periódica del contrato. |
| **Líneas** | |
| Número de variante | Número de variante del pedido de ventas. |
| Número de artículo | Número de artículo del pedido de ventas. |
| Frecuencia de facturación | Frecuencia de la asignación de ingresos: **Diaria**, **Mensual**, **Trimestral**, **Semestral** o **Anual**. |
| Quantity | Valor del pedido de ventas. |
| Valor contractual | Valor contractual. |
| Número de disposición de varios elementos | <p>Número de MEA para la línea. Este campo solo está disponible cuando el campo **Tipo de disposición de varios elementos** está establecido en **Varios**.</p><p>Si este campo está en blanco y asigna un número de MEA, los campos **Origen de precio de venta individual** y **Precio de venta individual** se actualizan automáticamente en función de los valores de la página **Precio de venta individual de artículo**. Solo están disponibles los números de MEA que están asignados a otras líneas en el pedido de ventas. Si estos valores no están configurados para el elemento, se utilizarán los valores de la página **Parámetros de asignación de ingresos de varios elementos**.</p> | 
| Origen de precio de venta individual | <p>Origen del precio de venta independiente:</p><ul><li>**Importe**: el precio de venta independiente es un importe que usted especifica que es mayor que 0 (cero). El importe se convierte entre las monedas funcional y de origen, según sea necesario.</li><li>**Precio de venta base**: el precio de venta independiente coincide con el precio de venta base del artículo.</li><li>**Precio de factura**: el precio de venta independiente coincide con el precio de factura del artículo.</li><li>**Porcentaje del artículo**: el precio de venta independiente se especifica como un valor porcentual y se calcula en función del precio del artículo. Si selecciona esta opción, especifique el porcentaje predeterminado.</li><li>**Importe residual asignado**: el origen del precio de venta independiente se calcula como *Valor total del contrato del artículo principal* o *Precio de venta independiente total de artículos secundarios*:</p><ul><li>El *Valor total del contrato del artículo primario* es el importe neto o facturado.</li><li>El *Precio de venta independiente total de artículos secundarios* es la suma del precio de venta independiente extendido o del contrato de todos los artículos secundarios, excepto el artículo secundario que utiliza este origen de precio de venta independiente.</li></ul><p>Si la cantidad calculada es un valor negativo, la cantidad se establece en 0 (cero).</p><p>**Nota:** esta opción se puede seleccionar solo para un artículo secundario en la división de ingresos.</p></li><li>**Ninguno**: el origen del precio de venta independiente se basa en los artículos secundarios. Esta opción se aplica a los artículos que se definen como artículos primarios en una plantilla de división de ingresos. Si la casilla **División de ingresos** está seleccionada, esta opción se selecciona automáticamente y la configuración no se puede cambiar.</li><li>**Porcentaje del precio de la factura primaria**: el origen del precio de venta independiente es un porcentaje del precio de factura del artículo primario. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos.</li><li>**Porcentaje del precio estándar primario**: el origen del precio de venta independiente es un porcentaje del precio estándar del artículo primario. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos. Cuando la opción para un artículo secundario se cambia de **Porcentaje del precio estándar principal** a **Porcentaje del precio de la factura primaria**, o de **Porcentaje del precio de la factura primaria** a **Porcentaje del precio estándar primario**, los valores calculados también se actualizan.</li></ul> |
| Precio de venta individual | <p>Precio de venta individual de la línea, en la divisa de la transacción.</p><p>El valor del campo **Importe** se ingresa o se calcula.</p> |
| Precio de venta individual del contrato | Precio de venta individual del contrato. |
| Ingresos restantes del contrato | Importe restante de ingresos del contrato. Este importe es la suma de todas las líneas para las que aún no se han creado facturas. |
| Ingresos del contrato total | Importe total de ingresos del contrato para la línea. Este importe es la suma de todas las líneas, independientemente de que se hayan creado facturas para ellas. |
| Cuenta de ingresos de contratos aplazados | <p>Especifique la cuenta que se usará para los movimientos del diario cuando se cree una factura de contrato MEA.</p><p>Este campo solo está disponible cuando se utiliza facturación periódica del contrato.</p> |
| Error | Errores que se hayan producido en la asignación de ingresos. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Utilice asignación de gastos en un pedido de ventas

Para utilizar la función de asignación de ingresos en un pedido de ventas, siga estos pasos.

1. En la página **Todos los pedidos de ventas**, cree un pedido de ventas que tenga artículos.
2. En la pestaña **Factura**, en **Asignación de ingresos**, seleccione **Asignación de ingresos**.
3. En el campo **Tipo de disposición de varios elementos**, seleccione el tipo de MEA.
4. En el campo **Número de disposición de varios elementos**, especifique el número de MEA.
5. Si el campo **Tipo de disposición de varios elementos** se establece en **Varios**, seleccione las líneas que desee y luego seleccione **Aplicar a seleccionados**.
6. Seleccione **Guardar**.

Si usa aplazamientos de ingresos y gastos, se crea automáticamente la programación de aplazamiento. Puedes verla en la página **Todas las programaciones de aplazamientos**.
