---
title: Creación de pagos de proveedor mediante una propuesta de pago
description: Este tema proporciona una visión general de las opciones de propuesta de pago e incluye algunos ejemplos que muestran cómo funcionan las propuestas de pago.
author: abruer
manager: AnnBe
ms.date: 04/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 54c3d2b6ecae1481fd9b979e5d4ced217a67f5aa
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509197"
---
# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Creación de pagos de proveedor mediante una propuesta de pago

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general de las opciones de propuesta de pago e incluye algunos ejemplos que muestran cómo funcionan las propuestas de pago. Las propuestas de pago se usan a menudo para crear pagos de proveedor, ya que se puede usar la consulta para seleccionar rápidamente facturas de proveedor para realizar el pago, en función de los criterios como la fecha de vencimiento y el descuento por pronto pago. 

Las empresas a menudo usan propuestas de pago para crear pagos de proveedor, ya que se puede usar la consulta asociada a la propuesta de pago para seleccionar rápidamente facturas de proveedor para realizar el pago, en función de la fecha de vencimiento, el descuento por pronto pago y otros criterios. 

La consulta de la propuesta de pago contiene diferentes fichas, cada una con varias opciones para seleccionar facturas que pagar. La pestaña **Parámetro** incluye las opciones que usan la mayoría de las organizaciones. En la pestaña desplegable **Registros que incluir**, puede especificar qué facturas o proveedores incluir en el pago definiendo intervalos para diversas características. Por ejemplo, si desea pagar solo un intervalo específico de proveedores, puede definir un filtro para el intervalo de proveedores. Esta función a menudo se usa para seleccionar facturas para un método de pago determinado. Por ejemplo, si define un filtro donde **Método de pago** = **Cheque**, solo se seleccionan para pagarse las facturas que tengan esa forma de pago, siempre que también se cumplan otros criterios especificados en la consulta. La ficha **Parámetros avanzados** incluye opciones adicionales, algunas de las cuales pueden no ser relevantes para su organización. Por ejemplo, esta ficha contiene las opciones para pagar facturas de pagos centralizados.

## <a name="parameters"></a>Parámetros
-   **Seleccionar facturas por**: las facturas dentro del intervalo de fechas especificado por los campos **Fecha inicial** y **Fecha final** se pueden seleccionar por fecha de vencimiento, fecha de descuento por pronto pago o ambas. Si usa la fecha de descuento por pronto pago, el sistema busca primero facturas con una fecha de descuento por pronto pago entre la fecha inicial y la fecha final. El sistema a continuación determina si la factura puede optar al descuento por pronto pago mediante la fecha de la sesión para asegurarse de que la fecha de descuento por pronto pago no haya pasado ya.
-   **Fecha inicial** y **Fecha final**: las facturas que tienen una fecha de vencimiento o una de descuento por pronto pago dentro del intervalo de fechas se selecciona para su pago.
-   **Fecha de pago mínima**: especifique la fecha de pago mínima. Por ejemplo, los campos **Fecha inicial** y **Fecha final** especifican un intervalo desde el 1 de septiembre al 10 de septiembre, y la fecha de pago mínima es el 5 de septiembre. En este caso, todas las facturas que tienen fecha de vencimiento del 1 de septiembre al 5 de septiembre tienen una fecha de pago del 5 de septiembre. Sin embargo, todas las facturas que tienen una fecha de vencimiento del 5 de septiembre al 10 de septiembre tienen una fecha de pago igual a la fecha de vencimiento de cada factura.
-   **Límite del importe**: especifique el importe total máximo para todos los pagos.
-   **Crear pagos sin vista previa de factura**: si esta opción se establece en **Sí**, los pagos se crean inmediatamente en la página **Pagos de proveedor**. La página **Propuesta de pago** no se tiene en cuenta. Así pues, los pagos se crean más rápidamente. Los pagos se pueden modificar desde la página **Pagos de proveedor**. Alternativamente, puede volver a la página **Propuesta de pago** mediante el botón **Editar facturas para pago seleccionado**.

## <a name="advanced-options"></a>Opciones avanzadas
- **Comprobar saldo de proveedor**: si esta opción se establece en **Sí**, el sistema comprueba que un proveedor no tenga saldo de débito antes de pagar ninguna factura. Si un proveedor tiene un saldo de débito, no se creará ningún pago. Por ejemplo, el proveedor puede tener notas de abono o pagos registrados pero que no se han liquidado aún. En estos casos, no se debe pagar al proveedor. En su lugar, las notas de abono o los pagos se deben liquidar con las facturas pendientes.
- **Eliminar los pagos negativos**: esta opción funciona de forma diferente en función de si los pagos se realizan para facturas individuales o para la suma de las facturas que cumplen los criterios de pago. Este comportamiento se define en la forma de pago.
- **Pago para cada factura**: si la opción **Eliminar los pagos negativos** está establecida en **Sí**, y hay una factura y un pago sin liquidar para un proveedor, solo se selecciona la factura para su pago. El pago existente no se liquida con la factura. Si la opción **Eliminar los pagos negativos** está establecida en **No** y hay una factura y un pago sin liquidar, se seleccionan para su pago la factura y el pago. Se crea un pago para el pago y una devolución (pago negativo) para el pago.
- **Pago para la suma de facturas**: si la opción **Eliminar los pagos negativos** está establecida en **Sí** y hay una factura y un pago sin liquidar para un proveedor, la factura y el pago sin liquidar se seleccionan para su pago, y los importes se agregan para producir el importe total de pago. La única excepción es cuando la suma resulta en una devolución. En este caso, no se selecciona ni la factura ni el pago. Si la opción **Eliminar los pagos negativos** está definida en **No** y hay una factura y un pago sin liquidar, la factura y el pago se seleccionan para su pago, y los importes se agregan para producir el importe total de pago.
- **Imprimir solo informe**: defina esta opción en **Sí** para ver los resultados de la propuesta de pago en un informe, pero sin crear ningún pago.
- **Incluir facturas de proveedor de otras entidades jurídicas**: si su organización tiene un proceso centralizado para el pago y la propuesta de pago debe incluir facturas de otras entidades jurídicas incluidas en los criterios de búsqueda, establezca esta opción en **Sí**.
- **Proponer pagos de proveedor independientes por entidad jurídica**: si esta opción está establecida en **Sí**, se crea un pago aparte para cada entidad jurídica por proveedor. El proveedor en el pago es el proveedor de la factura de cada entidad jurídica. Si la opción está definida en **No** y el mismo proveedor tiene facturas que pagar en varias entidades jurídicas, se crea un pago para el importe total de las facturas seleccionadas. El proveedor en el pago es el proveedor en la entidad jurídica actual. Si la cuenta de proveedor no existe en la entidad jurídica actual, se usa la cuenta de proveedor de la primera factura que se debe pagar.
- **Divisa de pago**: este campo especifica la divisa en la que se crean todos los pagos. Si no se ha definido ninguna divisa, cada factura se paga en la divisa de la factura.
- **Día de pago**: especifique el día de la semana en el que se debe efectuar el pago. Este campo solo se usa si el método de pago se configura para sumar las facturas por pagar en un día concreto de la semana.
- **Tipo de cuenta de contrapartida** y **Cuenta de contrapartida**: establezca estos campos para definir un tipo de cuenta específico (como **Libro mayor** o **Banco**) y una cuenta de contrapartida (como una cuenta bancaria concreta). El método de pago para la factura define el tipo de cuenta de contrapartida predeterminada como cuenta de contrapartida, si bien puede usar estos campos para reemplazar los valores predeterminados.
- **Fecha de pago total**: Se utiliza únicamente cuando el campo **Periodo** de la forma de pago se establece en **Total**. Si se ha definido una fecha, todos los pagos se crean con esta fecha. El campo **Fecha de pago mínima** no se tiene en cuenta.
- **Filtros adicionales**: en la ficha desplegable **Registros que incluir** puede definir más intervalos como criterios. Por ejemplo, si desea pagar solo a un intervalo específico de proveedores, puede definir un filtro para el intervalo de proveedores. Esta función a menudo se usa para seleccionar facturas para un método de pago determinado. Por ejemplo, si define un filtro donde **Método de pago** = **Cheque**, solo se seleccionan para pagarse las facturas que tengan esa forma de pago, siempre que también se cumplan otros criterios especificados en la consulta.

## <a name="scenarios"></a>Situaciones

| Proveedor | Factura | Fecha de factura | Importe de factura | Fecha de vencimiento | Fecha del descuento por pronto pago | Importe de descuento por pronto pago |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 de junio      | 500,00         | 15 de julio  | 29 de junio            | 10,00                |
| 3050   | 1002    | 20 de junio      | 600,00         | 20 de julio  | 4 de julio             | 12,00                |
| 3075   | 1003    | 15 de junio      | 250,00         | 29 de junio  |                    | 0,00                 |
| 3100   | 1004    | 17 de junio      | 100,00         | 17 de julio  | 1 de julio             | 1,00                 |

El 1 de julio, April paga a los proveedores. Usa una propuesta de pago para completar esta tarea de forma más eficaz.

### <a name="option-1-by-cash-discount"></a>Opción 1: con descuento por pronto pago

April selecciona  **Descuento por pronto pago** como tipo de propuesta. Especifica un intervalo de fechas del 26 de junio al 10 de julio. Las facturas siguientes se incluyen en la propuesta:

-   1002, porque la fecha de descuento de 4 de julio está en el intervalo de fechas de pago.
-   1004, porque la fecha de descuento de 1 de julio está en el intervalo de fechas de pago.

Las siguientes facturas no se incluyen en la propuesta:

-   1001, porque ya ha vencido la fecha de descuento del 29 de junio, por lo que esta factura dejará de ser apta para un descuento por pronto pago.
-   1003, porque esta factura no tiene fecha de descuento.

### <a name="option-2-by-due-date"></a>Opción 2: Por fecha de vencimiento

April selecciona **Por fecha de vencimiento** como tipo de propuesta. Especifica un intervalo de fechas del 26 de junio al 10 de julio. Las facturas siguientes se incluyen en la propuesta:

-   1003, porque la fecha de vencimiento de 29 de junio está en el intervalo de fechas de pago.

Las siguientes facturas no se incluyen en la propuesta:

-   1001, porque la fecha de vencimiento de 15 de julio está fuera del intervalo de fechas de pago.
-   1002, porque la fecha de vencimiento de 20 de julio está fuera del intervalo de fechas de pago.
-   1004, porque la fecha de vencimiento de 17 de julio está fuera del intervalo de fechas de pago.

### <a name="option-3-by-due-date-and-cash-discount"></a>Opción 3: Por fecha de vencimiento y descuento por pronto pago

April selecciona **Fecha de vencimiento y descuento por pronto pago** como tipo de propuesta. Especifica un intervalo de fechas del 26 de junio al 10 de julio. Las facturas siguientes se incluyen en la propuesta:

-   1003, porque la fecha de vencimiento de 29 de junio está en el intervalo de fechas de pago.
-   1002, porque la fecha de descuento de 4 de julio está en el intervalo de fechas de pago.
-   1004, porque la fecha de descuento de 1 de julio está en el intervalo de fechas de pago.

Las siguientes facturas no se incluyen en la propuesta:

-   1001, porque ya ha vencido la fecha de descuento del 29 de junio, por lo que esta factura dejará de ser apta para descuento por pronto pago y la fecha de vencimiento del 15 de julio también queda fuera del intervalo de fechas.

## <a name="country-specific-considerations"></a>Consideraciones específicas del país
### <a name="norway"></a>Noruega

#### <a name="dimension-control"></a>Control de dimensión

El control de dimensión permite controlar la agrupación de líneas generadas por la propuesta de pago y establecer las dimensiones predeterminadas en función de las dimensiones financieras utilizadas para las facturas aplicadas. En el contexto noruego, para cada forma de pago hay una ficha de la dimensión financiera donde puede activar el control de dimensión así como habilitar la agrupación para cada dimensión. Las posibles opciones son:

-   El campo de **Control de dimensión** está deshabilitado. La propuesta de pago se comporta como para otro país cualquiera.
-   El campo de **Control de dimensión** se activa sin definir más las dimensiones. La propuesta de pago se creará sin tener en cuenta las dimensiones. La transacción creada no hereda ninguna dimensión de la entrada aplicada.
-   El campo de **Control de dimensión** se activa y se habilitan más dimensiones. Ahora puede definir cómo se copiarán las dimensiones en el diario. Por ejemplo: • Active la casilla de verificación de **BusinessUnit** para crear una propuesta de pago por unidad de negocio para el método de pago, • Active la casilla de verificación de **CostCenter** para crear una propuesta de pago por centro de coste para el método de pago.

> [[!NOTE]
> Si selecciona más de una dimensión, en la tercera opción se creará una propuesta de pago para la combinación de dimensiones.

#### <a name="bank-account-selection"></a>Selección de cuenta bancaria

Puede definir una cuenta estándar de pago a débito por método de pago independientemente del contexto del país. Esto se definirá en las líneas de pago generadas por una propuesta. Con la función de la cuenta bancaria, puede definir varias cuentas bancarias de débito gestionadas por la dimensión y la divisa o una combinación de las anteriores para usar cuentas bancarias de débito diferentes, en función de cada combinación. Puede configurar estas combinaciones en la página de **Métodos de pago** mediante el botón  **Cuentas bancarias** disponible para cada forma de pago con **Tipo de cuenta de registro** = **Banco**.



