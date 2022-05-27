---
title: Características de programación de facturación
description: Este tema explica las características de los programas de facturación, como los métodos de fijación de precios, los aumentos y descuentos, las fechas de alineación, el prorrateo, la facturación inversa y los grupos de artículos divididos.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ce323565a94e8e70d90a65b7a3143e984a1c159
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8700730"
---
# <a name="billing-schedule-features"></a>Características de programación de facturación

[!include [banner](../includes/banner.md)]

Este tema explica las características de los programas de facturación y las líneas de programación de facturación. Describe los diferentes métodos que se utilizan para la fijación de precios, cómo utilizar aumentos y descuentos, y cómo revertir un período de facturación. También incluye ejemplos de cálculos de prorrateo y grupos de artículos divididos.

## <a name="pricing-methods"></a>Métodos de precios

Puede utilizar uno de los siguientes métodos de fijación de precios para calcular el precio unitario de un artículo:

* Plano
* Estándar
* Nivel
* Nivel plano

### <a name="flat-pricing"></a>Precio único

Cuando se utiliza el método de fijación de precio único, el precio unitario de un artículo de línea de programación de facturación de la página **Todas las programaciones de facturación** se puede editar a cualquier valor que desee. El valor del **Unidad de precio** siempre es **1**. Por lo tanto, los valores de **Precio unitario** e **Importe neto** para un artículo son los mismos.

### <a name="standard-pricing-without-a-trade-agreement"></a>Precio estándar (sin acuerdo comercial)

Cuando se usa el método de fijación de precios estándar sin un acuerdo comercial, configure el precio unitario para un elemento de línea de la programación de facturación seleccionando **Gestión de la información del producto** en la página **Liberar detalles del producto**. El precio unitario se muestra en la sección **Precio base de venta**. Se calcula como *Precio* &divide; *Cantidad de precio*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Precio estándar (con acuerdo comercial)

Los siguientes ejemplos muestran los cálculos de precios estándar cuando existe un acuerdo comercial. Puede crear acuerdos comerciales desde la página **Liberar detalles del producto**.

Ambos ejemplos usan un artículo que tiene los siguientes rangos de precios.

| Cantidad desde | Cantidad hasta | U de M | Precio | Unidad de precio |
|---|---|---|---|---|
| 0 | 100 | Cada uno | 1.50 | 1 |
| 100 | 200 | Cada uno | 1.25 | 1 |
| 200 | 999999 | Cada uno | 1.00 | 1 |

**Ejemplo 1**

La cantidad de la factura es 250 y se utiliza el método de precios estándar. Debido a que la cantidad está en el rango de cantidad de precio 200–999 999, el precio unitario es 1,00. 

El importe neto se calcula de la siguiente manera:

*Importe neto* = (*Cantidad* &times; *Precio*) &divide; *Precio unitario* = (250 &times; 1,00)&divide; 1 = 250

**Ejemplo 2**

La cantidad de la factura es 100 y se utiliza el método de precios estándar. Debido a que la cantidad de la factura está en el rango de cantidad de precio 0-100, el precio unitario es 1,50.

> [!NOTE]
> La cantidad de la factura está en el rango de 0-100 en lugar del rango de 100-200 porque, en el comportamiento de coincidencia de cantidad estándar, una cantidad coincide si es *mayor o igual a* la cantidad "desde" y *menor que* la cantidad "hasta".

El importe neto se calcula de la siguiente manera:

*Importe neto* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Precios por niveles

En el siguiente ejemplo, un artículo tiene los siguientes rangos de precios.

| Cantidad desde | Cantidad hasta | U de M | Precio | Unidad de precio |
|---|---|---|---|---|
| 0 | 100 | Cada uno | 1.50 | 10 |
| 100 | 200 | Cada uno | 1.25 | 10 |
| 200 | 999999 | Cada uno | 1.00 | 10 |

Si la cantidad de la factura es 250 y se utiliza el método de precios por niveles, los precios de los artículos se calculan de la siguiente manera, en función de los tramos de precios:

- **Primeros 100 elementos:** 100 &times; 1,50 = 150,00
- **Segundos 100 elementos:** 100 &times; 1,25 = 125,00
- **Artículos restantes:** 50 &times; 1,00 = 50,00

El importe neto se calcula de la siguiente manera:

*Importe neto* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

Después de calcular el importe neto, el precio unitario se calcula dividiendo el importe neto por la cantidad:

*Precio unitario* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Precios únicos por niveles

En el siguiente ejemplo, un artículo tiene los siguientes rangos de precios.

| Cantidad desde | Cantidad hasta | U de M | Importe de nivel plano | Unidad de precio |
|---|---|---|---|---|
| 0 | 50 | Cada uno | 100.00 | 50 |
| 50 | 200 | Cada uno | 150.00 | 200 |

La siguiente tabla muestra las facturas y los precios unitarios para las diferentes cantidades que se compran. Primero se calcula el importe neto y luego se calcula el precio unitario.

| Factura | Cantidad comprada | Precio unitario | Importe neto |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Escalaciones y descuentos

Una *escalación* es un aumento de precio para un período de facturación futuro para el que aún no se ha creado la factura. Un *desceunto* es una reducción de precio para un período de facturación futuro para el que aún no se ha creado la factura.

En la facturación de Suscripción, las escalaciones y los descuentos no se pueden aplicar retroactivamente a una programación de facturación. Por ejemplo, no se puede aplicar un escalamiento a una programación de facturación de hace tres meses y procesarlo. En otras palabras, no puede aplicar un aumento de precio que ocurrió hace tres meses.

Puede aplicar una escalación o un descuento a una programación de facturación o a una línea de la programación de facturación en uno de los siguientes lugares:

- La página de listas **Programas de facturación (todas/activas)**
- Una programación de facturación específica
- Una línea de programación de facturación específica

### <a name="apply-an-escalation-or-discount"></a>Aplicar una escalación o descuento

Para aplicar una escalación o un descuento a una programación de facturación, siga estos pasos.

1. Seleccione una programación de facturación o una línea de la programación de facturación.
2. Seleccione **Escalación y descuento**, ya sea en la pestaña **Escalación y descuento** o en la línea de programación de facturación.
3. Si se utiliza un índice de precios al consumidor para calcular el aumento o el descuento, seleccione un valor en el campo **Cálculo del índice de precios al consumidor**.
4. Seleccione **Nuevo** para agregar una escalación o una línea de descuento.
5. Para obtener un descuento, seleccione la casilla **Descuento**. Para una escalación, deje sin marcar la casilla **Descuento**.
6. Seleccione los campos **Fecha de inicio** y **Frecuencia**.
7. Para artículos aplazados que utilizan la función de ingresos no facturados, configure el campo **Fecha de finalización**.
8. Seleccione el campo **Porcentaje**, **Importe** o **Programación del índice de precios al consumidor**.
9. Seleccione el campo **Fecha de finalización**.
10. Seleccione **Aceptar**.
11. Repita los pasos del 4 al 10 para cada escalamiento adicional o línea de descuento que necesite.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Campos en la página de líneas de programación de facturación

La página **Líneas de programación de facturación** contiene los siguientes campos.

| Campo | Description |
|---|---|
| Número de artículo | El número de artículo para la línea de programación de facturación. Este campo está disponible solo cuando la página se abre desde un elemento de línea de la programación de facturación. |
| Cálculo de índices de precios al consumidor | <p>Seleccione el método que se utiliza para calcular la escalación del índice de precios al consumidor:</p><ul><li>**Índice de precios al consumidor anterior**: utilice el valor anterior del índice de precios al consumidor para el cálculo de la escalación.</li><li>**Índice de precios al consumidor base**: utilice el valor base del índice de precios al consumidor para el cálculo de la escalación.</li></ul> |
| Cuadrícula **Líneas** | |
| Descuento | <p>Establezca la casilla de verificación para especificar si el cambio en el importe es una escalación o un descuento:</p><ul><li>**Seleccionado**: el cambio aplica un descuento a la programación de facturación o a la línea de programación de facturación.</li><li>**Borrado**: el cambio aplica una escalación a una programación de facturación o una línea de programación.</li></ul><p>La configuración de esta casilla no se puede cambiar para artículos que usan la función de ingresos no facturados. Además, los descuentos no se pueden aplicar a artículos que utilizan la división de ingresos.</p> |
| Fecha inicial | Seleccione la fecha de inicio de la escalación o el descuento. |
| Frecuencia | Seleccione la frecuencia de la escalación o descuento: **Ninguna**, **Mensual**, **Trimestral**, **Semestral** o **Anual**. |
| Porcentaje | Especifique el porcentaje de la escalación o el descuento. |
| Importe | Especifique la cantidad de escalación o descuento. |
| Programación de índices de precios al consumidor | Seleccione la programación del índice de precios al consumidor que se utiliza para los cálculos. |
| Fecha final | <p>Seleccione la fecha de finalización de la escalación o el descuento.</p><p>**Nota:** este campo es obligatorio para los artículos que utilizan la función de ingresos no facturados.</p> |
| Número de programación de aplazamientos | <p>Número de programación de aplazamiento.</p><p>Este campo está disponible solo cuando la página se abre desde una línea de la programación de facturación.</p> |
| Número de lote de diario | <p>El número de lote del diario.</p><p>Este campo está disponible solo cuando la página se abre desde una línea de la programación de facturación.</p> |
| Importe de descuento total | <p>La suma de los importes de descuento para todas las líneas de la cuadrícula.</p><p>Este campo está disponible solo cuando la página se abre desde una línea de la programación de facturación.</p> |
| Importe actual de ingresos no facturados a corto plazo | <p>El importe actual de ingresos no facturados a corto plazo.</p><p>Esta cantidad aparece cuando se selecciona un método de aplazamiento a corto plazo en la página **Parámetros de facturación de contratos periódicos**, y las cuentas para el elemento de línea se configuran en la página **Configuración de ingresos no facturados**.</p> |
| Importe actual de ingresos no facturados a largo plazo | <p>El importe actual de ingresos no facturados a largo plazo.</p><p>Esta cantidad aparece cuando se selecciona un método de aplazamiento a corto plazo en la página **Parámetros de facturación de contratos periódicos**, y las cuentas para el elemento de línea se configuran en la página **Configuración de ingresos no facturados**.</p> |

## <a name="proration-examples"></a>Ejemplos de prorrateo

Los cálculos de prorrateo se pueden basar en el número de días o en el número de meses. El método que se utiliza para el cálculo del prorrateo se establece en la página **Parámetros de facturación de contratos periódicos**. El método de prorrateo afecta la forma en que se calculan los importes para una programación de facturación en las siguientes situaciones:

- Creación inicial
- Aplicación de una escalación o descuento
- Finalización
- Colocación o eliminación de una retención
- Adición de soporte o renovación

El método de prorrateo también afecta los cálculos en el informe de ingresos periódicos mensuales (MRR).

### <a name="example-1"></a>Ejemplo 1

El importe anual de un calendario de facturación es de 5000 $. La fecha de inicio es el 12 de agosto de 2019 y la fecha de finalización es el 22 de diciembre de 2019. La frecuencia de facturación es anual. El importe prorrateado se calcula de las siguientes formas, según se utilice el método de cálculo diario o mensual:

- **Diariamente**

    - *Número de días* = *Fecha de finalización* – *Fecha de inicio* + 1 = 133 días
    - *Número de días en el año* = 11 de agosto de 2020 – 12 de agosto de 2019 + 1 = 366 días
    - *Cantidad prorrateada* = 5000 &times; (133 &divide; 366) = 1816,94

- **Mensual**

    - *Parte del mes de inicio* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Meses intermedios* = 3
    - *Porción de fin de mes* = 22 &divide; 31
    - Cantidad prorrateada = 5000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>Ejemplo 2

El importe anual de un calendario de facturación es de 12 000 $. La fecha de inicio es el 1 de agosto de 2019 y la fecha de finalización es el 31 de diciembre de 2019. La frecuencia de facturación es anual. El importe prorrateado se calcula de las siguientes formas, según el método de cálculo:

- **Diariamente**

    - *Número de días* = *Fecha de finalización* – *Fecha de inicio* + 1 = 153 días
    - *Número de días en el año* = 31 de julio de 2020 – 1 de agosto de 2019 + 1 = 366 días
    - *Cantidad prorrateada* = 12 000 &times; (153 &divide; 366) = 5016,39

- **Mensualmente (mes completo)**

    - *Número de meses* = 5
    - *Meses totales* = 12
    - *Cantidad prorrateada* = (12 000 &times; 5) &divide; 12 = 5000

## <a name="reversing-a-period-billing"></a>Revertir la facturación de un período

Para este ejemplo, una programación de facturación tiene solo una línea:

- La facturación se realiza mensualmente durante 12 meses, de enero a diciembre.
- Se han creado facturas para todos los períodos hasta abril.

Desea revertir la factura del período de facturación de abril.

Si aún no se ha creado una factura de venta para el período de facturación de abril, puede eliminar el pedido de venta. En este caso, se eliminaría el estado **Facturado** del detalle. Sin embargo, debido a que se ha creado una factura para el período de facturación, el estado **Facturado** del detalle no se puede borrar. Por lo tanto, para revertir la facturación de abril, debe crear una nota de crédito compensatoria para la línea.

1. En la página **Todas las programaciones de facturación**, cree una línea de programación para el mismo artículo.
2. Cambie el valor **Cantidad** del artículo al opuesto de la cantidad original.
3. Seleccione el campo **Frecuencia de facturación** a **Una vez**.
4. Actualice las fechas de inicio y finalización para que coincidan con las fechas de la línea de detalle de facturación para la que desea crear una nota de crédito. Para este ejemplo, establezca la fecha de inicio en el 1 de abril de 2019 y la fecha de finalización en el 30 de abril de 2019.
5. Guarde los cambios.
6. Abra la página **Generar factura** y cree el pedido de ventas que tiene la nota de crédito para el período especificado.
7. Opcional: registre la factura.

Cuando revise las líneas de la programación de facturación, notará que la nueva línea tiene un enlace a la nota de crédito. La línea original seguirá teniendo un enlace a la factura original de abril.

## <a name="split-item-group-examples"></a>Ejemplos de grupos de artículos divididos

Para este ejemplo, se ha implementado la siguiente configuración:

- En la página **Parámetros de facturación de contratos periódicos**, está seleccionado **Dividir por grupo de artículos** y el campo **Tipo de programación único** se establece en **Cliente**.
- Se han creado tres grupos de artículos: **PREFIX**, **DATAHUB** y **SPP**.
- El cliente US-001 tiene varios programas de facturación en los que el grupo de artículos es PREFIX o DATAHUB.
- El cliente US-002 tiene varios programas de facturación en los que el grupo de artículos es PREFIX o SPP.

| Número de programación de facturación | Cliente | Grupo de artículos |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

El cliente US-001 compra un artículo de renovación que pertenece al grupo de artículos PREFIX. Esta transacción es un nuevo pedido de ventas.

| N.º de pedido de ventas | Cliente | Artículo principal | Artículo de renovación | Grupo de artículos de renovación | Número de programación de facturación |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

Cuando se registra la factura del pedido de ventas, el artículo de renovación se agrega a la programación de facturación existente (SCH001) para el cliente. Esta programación de facturación utiliza el grupo de artículos PREFIX. Todos los artículos de renovación que pertenecen al mismo grupo de artículos se colocan en la misma programación de facturación.

**Encabezado**
 
| Número de programación de facturación | Cliente | Grupo de artículos |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Línea**

| Número de programación de facturación | Cliente | Grupo de artículos |
|---|---|---|
| SCH001 | US-001 | D0002 |

El cliente US-001 compra ahora un artículo de renovación que pertenece al grupo de artículos SPP. Esta transacción es un nuevo pedido de ventas.

| N.º de pedido de ventas | Cliente | Artículo principal | Artículo de renovación | Grupo de artículos de renovación | Número de programación de facturación |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

Actualmente, el cliente US-001 no tiene una programación de facturación que use el grupo de artículos SPP. Por lo tanto, se crea una nueva programación de facturación.

**Encabezado**

| Número de programación de facturación| Cliente | Grupo de artículos |
|---|---|---|
| SCH005 | US-001 | SPP |

**Línea**

| Número de programación de facturación | Cliente | Grupo de artículos |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Múltiples programaciones de facturación para el mismo usuario final y cliente

Para este ejemplo, se ha implementado la siguiente configuración:

- En la página **Parámetros de facturación de contratos periódicos**, está seleccionado **Dividir por grupo de artículos** y el campo **Tipo de programación único** se establece en **Usuario final**.
- En la página **Usuarios finales**, se configura la siguiente relación de cliente y usuario final.

    | Cuenta de cliente | Cuenta de usuario final |
    |---|---|
    | US-001 | US-221 |

Se crean múltiples programaciones de facturación para la combinación de cliente y usuario final. Como está seleccionado **Dividir por grupo de artículos** en la página **Parámetros de facturación de contratos periódicos**, se pueden crear múltiples programaciones de facturación para la misma relación de cliente y usuario final.

| Número de programación de facturación | Cliente | Cuenta de usuario final | Grupo de artículos de encabezado |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

En la página **Configuración del artículo**, puede crear relaciones de artículos de soporte y renovación.

| Código de artículo | Relación de artículos | Artículo de soporte | Artículo de renovación | Grupo de artículos de renovación |
|---|---|---|---|---|
| Tabla | D001 | ITEM27 | D007 | IG1 |
| Tabla | D002 | ITEM28 | D005 | IG2 |
| Tabla | D003 | ITEM29 | D006 | IG3 |

Ahora va a crear un pedido de ventas para el cliente US-001. Este pedido de ventas tiene artículos de la página **Configuración del artículo**. Cuando cree el pedido de cliente, abra la página **Proceso de soporte y renovación** y establezca el campo **Cuenta de usuario final** y cualquier otra información requerida para el artículo de renovación.

Cuando se crea y contabiliza la factura de la transacción, se crean diferentes programaciones de facturación para la combinación de cliente/usuario final y grupo de artículos. Se puede asignar más de una línea del mismo pedido de ventas a la misma programación de facturación.

| N.º de pedido de ventas | Cliente | Cuenta de usuario final | Artículo principal | Artículo de soporte | Artículo de renovación | Número de programación de facturación |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
