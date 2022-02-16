---
title: Validar las transacciones de la tienda para el cálculo de extractos
description: En este tema se describe la funcionalidad para validar transacciones de tienda en Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: f51b1f39aa212fe8587761721194db7791bec5bc
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087458"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Validar las transacciones de la tienda para el cálculo de extractos

[!include [banner](includes/banner.md)]

En este tema se describe la funcionalidad para validar transacciones de tienda en Microsoft Dynamics 365 Commerce. El proceso de validación identifica y marca las transacciones que causarán errores de registro, antes de que se seleccionen por el proceso de registro de extractos.

Cuando intenta registrar un extracto, se puede generar un error en el proceso de validación debido a datos incoherentes en las tablas de transacciones de Commerce. A continuación, se muestran algunos ejemplos de factores que pueden causar estas incoherencias:

- El total de la transacción de la tabla de encabezado no coincide con el total de la transacción de las líneas.
- El número de artículos que se especifica en la tabla de encabezado no coincide con el número de artículos de la tabla de transacciones.
- Los impuestos de la tabla de encabezado no coinciden con el importe de impuestos de las líneas. 

Si las transacciones incoherentes se seleccionan por el proceso de registro de extractos, las facturas de ventas y diarios de pagos que se crean pueden causar un error en el registro de extractos. El proceso **Validar transacciones de la tienda** evita estos problemas al garantizar que solo las transacciones que superan las reglas de validación de transacciones se pasen al proceso de cálculo de extractos de la transacción.

En la siguiente ilustración se muestran los procesos diarios periódicos para cargar transacciones, validar transacciones, y calcular y registrar extractos de transacciones, así como los procesos de fin de día para el cálculo y el registro de informes financieros.

![En la siguiente ilustración se muestran los procesos diarios periódicos para cargar transacciones, validar transacciones, y calcular y registrar extractos de transacciones, así como los procesos de fin de día para el cálculo y el registro de informes financieros.](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Reglas de validación de transacciones de la tienda

El proceso por lotes **Validar transacciones de la tienda** comprueba la coherencia de las tablas de transacción de comercio, en función de las siguientes reglas de validación.

> [!NOTE]
> Las reglas de validación continuarán agregándose en versiones posteriores.

### <a name="transaction-header-validation-rules"></a>Reglas de validación de encabezado de transacción

En la siguiente tabla se muestran las reglas de validación de encabezado de transacción que se comparan con el encabezado de las transacciones minoristas antes de que esas transacciones se pasen al registro de informes.

| Regla | Descripción |
|-------|-------------|
| Fecha de negocio | Esta regla valida que la fecha comercial de la transacción está asociada a un período fiscal abierto en el libro mayor. |
| Redondeo de divisas | Esta regla valida que los importes de las transacciones se redondeen de acuerdo con la regla de redondeo de divisas. |
| Cuenta de cliente | Esta regla valida que el cliente que se utiliza en la transacción existe en la base de datos. |
| Importe de descuento | Esta regla valida que el importe del descuento del encabezado es igual a la suma de los importes de descuentos de las líneas. |
| Estado de registro del documento fiscal (Brasil) | Esta regla valida que el documento fiscal se pueda registrar correctamente. |
| Importe bruto | Esta regla valida que el importe bruto del encabezado de la transacción coincide con el importe neto, incluidos los impuestos, de las líneas de transacción además de los cargos. |
| Neto | Esta regla valida que el importe neto del encabezado de la transacción coincide con el importe neto, excluidos los impuestos, de las líneas de transacción además de los cargos. |
| Neto + impuestos | Esta regla valida que el importe bruto del encabezado de la transacción coincide con el importe neto, excluidos los impuestos, de las líneas de transacción además de los impuestos y cargos. |
| Número de artículos | Esta regla valida que el número de artículos que se especifica en el encabezado de la transacción coincide con la suma de las cantidades en las líneas de la transacción. |
| Importe del pago | Esta regla valida que el importe del pago del encabezado de la transacción coincide con la suma de todas las transacciones de pago. |
| Cálculo de exención de impuestos | Esta regla valida que la suma del importe calculado y el importe de impuestos exentos de las líneas de cargo es igual al importe calculado original. |
| Precios con impuestos incluidos | Esta regla valida que la marca **El impuesto está incluido en el precio** es coherente en el encabezado de la transacción y las transacciones de impuestos. |
| Transacción no vacía | Esta regla valida que la transacción contiene líneas y que al menos una línea no está anulada. |
| Sobrepago o pago insuficiente | Esta regla valida que la diferencia entre el importe bruto y el importe de pago no es superior a la configuración máxima de sobrepago o pago insuficiente. |

### <a name="transaction-line-validation-rules"></a>Reglas de validación de línea de transacción

En la siguiente tabla se muestran las reglas de validación de línea de transacción que se comparan con los detalles de línea de las transacciones minoristas antes de que esas transacciones se pasen al registro de informes.

| Regla | Descripción |
|-------|-------------|
| Código de barras | Esta regla valida que todos los códigos de barras de artículos que se utilizan en las líneas de transacción existen en la base de datos. |
| Líneas de cargo | Esta regla valida que la suma del importe calculado y el importe de impuestos exentos de las líneas de cargo es igual al importe calculado original. |
| Devoluciones de tarjeta regalo | Esta regla valida que no hay devoluciones de tarjetas regalo en la transacción. |
| Variante de artículo | Esta regla valida que todos los artículos y todas las variantes que se utilizan en las líneas de transacción existen en la base de datos. |
| Descuento de línea | Esta regla valida que el importe del descuento de línea coincide con la suma de las transacciones de descuentos. |
| Impuesto de línea | Esta regla valida que el importe del impuesto de línea coincide con la suma de las transacciones de impuestos. |
| Precio negativo | Esta regla valida que no se usan precios negativos en las líneas de transacción. |
| Controlado por el número de serie | Esta regla valida que el número de serie está presente en la línea de transacción para artículos controlados por el número de serie. |
| Dimensión de número de serie | Esta regla valida que no se proporcione ningún número de serie si la dimensión del número de serie del artículo está inactiva. |
| Contradicción de signo | Esta regla valida que el signo de la cantidad y el signo del importe neto son los mismos en todas las líneas de transacción. |
| Exento de impuestos | Esta regla valida que la suma del precio de artículo de línea y el importe de impuestos exentos es igual al precio original. |
| Asignación de grupos de impuestos | Esta regla valida que la combinación del grupo de impuestos y el grupo de impuestos de artículos produce una intersección de impuestos válida. |
| Conversiones de unidad de medida | Esta regla valida que la unidad de medida de todas las líneas tiene una conversión válida para la unidad de medida del inventario. |

## <a name="enable-the-store-transaction-validation-process"></a>Habilitar el proceso de validación de transacciones de tienda

Configure el trabajo **Validar transacciones de la tienda** para ejecuciones periódicas en la sede central de Commerce (**Retail y Commerce \> TI de Retail y Commerce \> Registro de PDV**). El trabajo por lotes se programa en función de la jerarquía organizativa de la tienda. Le recomendamos que configure este proceso por lotes para que se ejecute con la misma frecuencia que sus trabajos por lotes **trabajo P** y **Cálculo de extractos transaccionales**.

## <a name="results-of-the-validation-process"></a>Resultados del proceso de validación

Los resultados del proceso por lotes **Validar transacciones de la tienda** se pueden ver en cada transacción de tienda. El campo **Estado de validación** del registro de la transacción se establece en **Correcto**, **Error** o **Ninguno**. El campo **Hora de la última validación** muestra la fecha de la última ejecución de validación.

En la siguiente tabla se describe cada estado de validación.

| Estado de validación | Descripción |
|-------------------|-------------|
| Correcto | Se superaron todas las reglas de validación habilitadas. |
| Error | Una regla de validación habilitada ha identificado un error. Puede ver más detalles sobre el error seleccionando **Errores de validación** en el panel de acciones. |
| Ninguno | El tipo de transacción no requiere que se apliquen reglas de validación. |

![Página de transacciones de tienda que muestra el campo Estado de validación y el botón Errores de validación.](./media/valid-checker-validation-status-errors.png)

Solo las transacciones que tienen un estado de validación **Correcto** se incorporarán a los extractos transaccionales. Para ver transacciones que tienen un estado de **Error**, revise el mosaico **Errores de validación de pago al contado sin entrega a domicilio** en el espacio de trabajo **Operaciones financieras de tienda**.

![Iconos en el espacio de trabajo Operaciones financieras de tienda.](./media/valid-checker-cash-carry-validation-failures.png)

Para obtener más información sobre cómo corregir errores de validación de pago al contado sin entrega a domicilio, consulte [Editar y auditar transacciones de gestión del efectivo y pago al contado sin entrega a domicilio](edit-cash-trans.md).

## <a name="additional-resources"></a>Recursos adicionales

[Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
