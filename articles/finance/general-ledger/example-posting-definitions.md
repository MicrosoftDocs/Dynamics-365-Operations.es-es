---
title: Ejemplos de definición de contabilización
description: Este artículo proporciona ejemplos que demuestran cómo se usan las definiciones de contabilización se usan para reservas de gastos de pedidos de compra y para apropiaciones presupuestarias.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dbbc727120f5292a3ad94711cf79138b35593bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235146"
---
# <a name="posting-definition-examples"></a>Ejemplos de definición de contabilización

[!include [banner](../includes/banner.md)]

Este artículo proporciona ejemplos que demuestran cómo se usan las definiciones de contabilización se usan para reservas de gastos de pedidos de compra y para apropiaciones presupuestarias.

Antes de leer este tema, es necesario que esté familiarizado con las definiciones de contabilización y las definiciones de contabilización de transacciones. Para obtener información, vea [Definiciones de contabilización](posting-definitions.md). Los ejemplos siguientes se pueden configurar en la página **Definiciones de contabilización**. Cada uno de los ejemplos contiene estas secciones:

-   Definición de contabilización: criterios de coincidencia
-   Definición de contabilización: entradas generadas
-   Transacciones con las cuentas, los valores de dimensión y los importes
-   Asientos contables generados a partir de la definición de contabilización

Cuando se produce una coincidencia entre las cuentas y los valores de la dimensión en el panel **Criterios de coincidencia** de la definición de contabilización y las cuentas y los valores de dimensión de la transacción, se generan asientos contables basados en el panel **Entradas generadas** de la definición de contabilización. 
> [!NOTE]
> Para asociar una definición de contabilización a un tipo de transacción específico, use la página **Definiciones de contabilización de transacciones**. Tras asociar una definición de contabilización con un tipo de transacción y seleccionar **Usar definiciones de contabilización** en la página **Parámetros de contabilidad general**, todas las transacciones del tipo de transacción seleccionado deben usar definiciones de contabilización.

## <a name="example-purchase-order-encumbrances"></a>Ejemplo: reserva de gastos de pedidos de compra
Cuando se permite el proceso de reserva de gasto al seleccionar **Habilitar proceso de reserva de gasto** en la página **Parámetros de Contabilidad general**, se deben usar definiciones de contabilización para registrar las reservas de gasto en la contabilidad general para las cuentas que se deban reservar. En la mayoría de los casos, todas las cuentas de gastos se reservan en el balance de situación. 

Las definiciones de contabilización para reservas de gastos se configuran para el módulo **Compras** en la página **Definiciones de contabilización**. A continuación, en el área **Compras** de la página **Definiciones de contabilización de transacciones**, puede seleccionar el tipo de transacción **Pedido de compra** para asociar la definición de contabilización a los pedidos de compra. 

Todas las transacciones de asiento para las reservas de gasto de pedidos de compra deben compensarse (es decir, los débitos deben igualar a los créditos) en cada dimensión de un asiento.

### <a name="posting-definition--match-criteria"></a>Definición de contabilización: criterios de coincidencia

| Estructura contable       | Número de cuenta coincidente | Prioridad |
|-------------------------|----------------------|----------|
| Estructura contable: pérdidas y ganancias | \*                   | 1        |

<em>Un valor en blanco en el campo **Número de cuenta coincidente</em>* implica que todas las cuentas coincidentes de la estructura contable definida forman parte de la regla coincidente.

### <a name="posting-definition--generated-entries"></a>Definición de contabilización: entradas generadas

| Estructura contable | Número de cuenta generado                    | Crédito o débito generado |
|-------------------|---------------------------------------------|------------------------|
| Saldo           | 300143 (Cuenta de reserva de gasto)             | Igual                   |
| Saldo           | 300144 (Reserva de cuenta de reserva de gasto) | Equilibrar              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transacciones con las cuentas, los valores de dimensión y los importes

Las cuentas y los valores de dimensión proceden bien de las distribuciones contables especificadas para una línea de pedido de compra o bien de las cuentas y las dimensiones que se generan automáticamente en función de la configuración predeterminada de proveedores, artículos, categorías y plantillas de dimensión.

| Cuenta + dimensiones           | Débito  | Crédito | Comentario |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Training | 250,00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Asientos contables generados a partir de la definición de contabilización

Los asientos contables generados se crean para registrar las reservas de gasto.

| Cuenta + dimensiones           | Débito  | Crédito | Comentario |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-Training | 250,00 |        |         |
| 300144-OU\_1-OU\_3566-Training |        | 250,00 |         |

En este ejemplo, cualquier cuenta que sea parte de la cuenta de estructura contable: pérdidas y ganancias coincide con los criterios de definición de contabilización. Por lo tanto, cuando se evalúa 606500-OU\_1-OU\_3566-Training, se crean entradas generadas para las cuentas definidas en el panel **Entradas generadas** de la definición de contabilización.

## <a name="example-budget-appropriations"></a>Ejemplo: apropiaciones presupuestarias
Si habilita la apropiación presupuestaria seleccionando **Habilitar apropiación presupuestaria** en la página **Parámetros de Contabilidad general**, las definiciones de contabilización se deben usar para registrar las entradas de registro presupuestario en la contabilidad general. Si hay una configuración de control presupuestario activa y en funcionamiento, las definiciones de contabilización y las definiciones de contabilización de transacciones se pueden usar para admitir el registro de entradas para apropiaciones, revisiones, transferencias, proyectos, activos fijos y previsiones de demanda y suministro en la contabilidad general. 

Para configurar una definición de contabilización para las entradas del registro presupuestario que tienen el tipo presupuestario **Presupuesto original** y las apropiaciones habilitadas, seleccione el módulo **Presupuesto** en la página **Definiciones de contabilización**. A continuación, en el área **Presupuesto** de la página **Definiciones de contabilización de transacciones**, puede usar códigos presupuestarios para asociar la definición de contabilización a las entradas de registro presupuestario con el tipo de presupuesto **Presupuesto original**. 

Si se han habilitado las apropiaciones presupuestarias y las definiciones de contabilización, se registran las entradas del registro presupuestario para el control presupuestario y la contabilidad general.

### <a name="posting-definition--match-criteria"></a>Definición de contabilización: criterios de coincidencia

| Estructura contable       | Número de cuenta coincidente | Prioridad |
|-------------------------|----------------------|----------|
| Estructura contable: pérdidas y ganancias | \*                   | 1        |

<em>Un valor en blanco en el campo **Número de cuenta coincidente</em>* implica que todas las cuentas coincidentes de la estructura contable definida forman parte de la regla coincidente.

### <a name="posting-definition--generated-entries"></a>Definición de contabilización: entradas generadas

| Estructura contable | Número de cuenta generado              | Crédito o débito generado |
|-------------------|---------------------------------------|------------------------|
| Estructura contable | 300145 (Cuenta de ingresos estimados) | Igual                   |
| Estructura contable | 300146 (Cuenta de apropiación)     | Equilibrar              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transacciones con las cuentas, los valores de dimensión y los importes

Las cuentas, los valores de dimensión y los importes del asiento contable de presupuesto se especifican en la página **Entrada de registro de presupuesto**.

| Cuenta + dimensiones           | Débito | Crédito | Comentario |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Training |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Asientos contables generados a partir de la definición de contabilización

Los asientos contables generados se crean para registrar el presupuesto original de cada dimensión.

| Cuenta + dimensiones           | Débito  | Crédito | Comentario |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Training |        | 250,00 |         |
| 300146-OU\_1-OU\_3566-Training | 250,00 |        |         |

En este ejemplo, cualquier cuenta que sea parte de la cuenta de estructura contable: pérdidas y ganancias coincide con los criterios de definición de contabilización. Por lo tanto, si se evalúa 606400-OU\_1-OU\_3566-Training, se crean los asientos contables generados.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]