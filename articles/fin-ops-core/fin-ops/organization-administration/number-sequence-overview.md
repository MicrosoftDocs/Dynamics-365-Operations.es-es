---
title: Visión general de las secuencias numéricas
description: Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores.
author: MargoC
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4de5cc79b5c1e38e10bb6a382b279459a64a03c7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559393"
---
# <a name="number-sequences-overview"></a>Visión general de las secuencias numéricas

[!include [banner](../includes/banner.md)]

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores. El registro de datos maestros o de transacciones que necesita un identificador se denomina *referencia*.

Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia. Se recomienda usar las páginas en **Administración de la organización** para configurar secuencias numéricas. Si se requiere una configuración de módulo específica, puede usar la página de parámetros en un módulo para especificar secuencias numéricas para sus referencias. Por ejemplo, en **Clientes** y **Proveedores**, puede configurar también grupos de secuencias numéricas para asignar secuencias numéricas específicas a proveedores o clientes concretos.

Al configurar una secuencia numérica, debe especificar un ámbito, que defina qué organización usa la secuencia numérica. El ámbito puede ser **Compartido**, **Empresa**, **Entidad jurídica** o **Unidad operativa**. Los ámbitos **Entidad jurídica** y **Empresa** también se pueden combinar con **Período de calendario fiscal** para crear secuencias numéricas más específicas incluso.

Los formatos de secuencia numérica constan de segmentos. Las secuencias numéricas con un ámbito distinto a **Compartido** pueden contener segmentos que correspondan al ámbito. Por ejemplo, una secuencia numérica con un ámbito **Entidad jurídica** puede contener un segmento de entidad jurídica. Al incluir un segmento de ámbito en el formato de secuencia numérica, puede identificar el ámbito de un registro concreto mirando su número.

Además de los segmentos correspondientes a ámbitos, los formatos de secuencia numérica pueden contener segmentos **Constante** y **Alfanumérico**. Un segmento **Constante** contiene un conjunto de letras, números o símbolos que no cambian. Un segmento **Alfanumérico** contiene un conjunto de letras o números que aumentan cada vez que se usa un número. Use un signo de número (\#) para representar el incremento de números y un ampersand (&) para representar un incremento de letras. Por ejemplo, el formato \#\#\#\#\#\_2017 crea la secuencia 00001\_2017, 00002\_2017, etc.

## <a name="number-sequence-examples"></a>Ejemplos de secuencia numérica

En los siguientes ejemplos se muestra cómo usar segmentos para crear formatos de secuencia numérica. En concreto, en los ejemplos se muestran los efectos del uso de segmentos de ámbito.

### <a name="expense-report-numbers"></a>Números de informes de gastos

En el siguiente ejemplo, los números de informe de gastos se configuran para la entidad jurídica titulada **CS**.

- **Área:** Viajes y gastos
- **Referencia:** Número de informe de gastos
- **Ámbito:** Entidad jurídica
- **Entidad jurídica:** CS

| Segmentos  | Tipo de segmento | Valor     |
|-----------|--------------|-----------|
| Segmento 1 | Entidad jurídica | CS        |
| Segmento 2 | Constante     | -GASTO- |
| Segmento 3 | Alfanumérico | \#\#\#\#  |

**Ejemplo del número con formato**: CS-EXPENSE-0039

Puede configurar un formato de secuencia numérica similar para otras entidades jurídicas. Por ejemplo, para una entidad jurídica que se denomina **RW**, si cambia únicamente el valor del segmento de la entidad jurídica, el número con formato es RW-EXPENSE-0039. También puede cambiar el formato de secuencia numérica completo para otras entidades jurídicas. Por ejemplo, puede omitir el segmento de ámbito de entidad jurídica para crear un número con formato como Exp-0001.

### <a name="sales-order-numbers"></a>Números de pedidos de ventas

En el siguiente ejemplo, los números de pedidos de ventas se configuran para el id. de empresa **CEU**.

- **Área:** Ventas
- **Referencia:** Pedido de ventas
- **Ámbito:** Empresa
- **Empresa:** CEU

| Segmentos  | Tipo de segmento | Valor    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | SO-      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Ejemplo de número con formato**: SO-0029

Aunque no se incluye un segmento de ámbito en el formato, la numeración se reinicia para cada id. de empresa. Si usa el mismo formato para todos los id. de empresa, se usan los mismos números en cada empresa. Por ejemplo, el número de pedido de ventas SO-0029 se usa en cada empresa. También puede cambiar el formato de secuencia numérica completo para otros id. de empresa.

### <a name="purchase-requisition-numbers"></a>Números de solicitudes de compra

En el siguiente ejemplo, los números de solicitudes de compra son para toda la organización.

- **Área:** Compras
- **Referencia:** Solicitud de compra
- **Ámbito:** Compartido

| Segmentos  | Tipo de segmento | Valor    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | Sol      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Ejemplo de número con formato**: Req0052

Debido a que el ámbito es **Compartido**, se usa el formato de secuencia numérica en la organización. No puede configurar diferentes formatos de secuencia numérica para diferentes partes de la organización.

## <a name="performance-considerations-for-number-sequences"></a>Consideraciones de rendimiento para secuencias numéricas

Tenga en cuenta la siguiente información acerca de la manera en que la configuración de las secuencias numéricas puede afectar al rendimiento del sistema para poder configurar secuencias numéricas.

### <a name="continuous-and-non-continuous-number-sequences"></a>Secuencias numéricas continuas y no continuas

Las secuencias numéricas pueden ser continuas o no continuas. Una secuencia numérica continua no omite ningún número aunque los números no se pueden usar secuencialmente. Los números de una secuencia numérica no continua se usan secuencialmente pero la secuencia numérica puede omitir números. Por ejemplo, si un usuario cancela una transacción, se genera un número, aunque no se usa. En una secuencia numérica continua, dicho número se recicla posteriormente. En una secuencia numérica no continua, no se usa el número.

Las secuencias numéricas continuas se necesitan normalmente para documentos externos, como pedidos de compra, pedidos de ventas y facturas. Sin embargo, las secuencias numéricas continuas pueden afectar de manera adversa los tiempos de respuesta del sistema porque el sistema debe solicitar un número de la base de datos cada vez que se crea un registro o documento nuevo.

Si usa una secuencia numérica no continua, puede habilitar **Asignación previa** en la ficha desplegable **Rendimiento** de la página **Secuencias numéricas**. Al especificar una cantidad de números para preasignación, el sistema selecciona dichos números y los almacena en memoria. Los nuevos números se solicitan de la base de datos solo después de que se haya usado la cantidad preasignada.

A menos que haya una norma legal para usar secuencias numéricas continuas, se recomienda usar las secuencias numéricas no continuas para un mejor rendimiento.

### <a name="automatic-cleanup-of-number-sequences"></a>Limpieza automática de secuencias numéricas

En caso de fallo eléctrico, un error de aplicación u otro error inesperado, el sistema no podrá reciclar números de manera automática para las secuencias numéricas continuas. Puede ejecutar el proceso de limpieza manualmente o automáticamente para recuperar los números perdidos.

Valore detenidamente el uso del servidor al planificar el proceso de limpieza. Es recomendable que realice la limpieza como un trabajo por lotes durante las horas de menor demanda.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]