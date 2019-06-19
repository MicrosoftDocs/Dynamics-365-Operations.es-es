---
title: Informe de declaración de ISR y procesos auxiliares para México
description: En México, todos los individuos o corporaciones deben presentar un informe de declaración mensual Impuesto sobre la renta (ISR). Este tema proporciona información acerca de la generación de este informe financiero.
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ISRConcept_MX, ISRConceptMainAccount_MX, ISRRateTable_MX
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 270644
ms.assetid: bcc395db-7c00-4151-9340-e83415cb0882
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b347eec8ccbf6ef366270fd2735bd2168435f09f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549497"
---
# <a name="isr-declaration-report-and-supporting-processes-for-mexico"></a>Informe de declaración de ISR y procesos auxiliares para México

[!include [banner](../includes/banner.md)]

En México, todos los individuos o corporaciones deben presentar un informe de declaración mensual Impuesto sobre la renta (ISR). Este tema proporciona información acerca de la generación de este informe financiero.

Debe presentar el informe de la declaración de IRS para cada mes el día diecisiete del siguiente mes o antes. El informe muestra los cálculos detallados de pagos provisionales de impuestos y se basa en los factores siguientes:

-   Categorías del concepto de ISR vinculadas a una o varias cuentas contables
-   Tabla de tipo de ISR anual
-   Coeficiente de la utilidad de ISR

Por ejemplo, los pagos de ISR provisionales para enero de 2014 se pagan y se presentan en febrero de 2014; los pagos de febrero se pagan y se presentan en marzo, etc. Los contribuyentes deben usar el año natural para archivar los impuestos. Al final del año, los contribuyentes también deben enviar la declaración anual, que muestra el cálculo final del impuesto.

## <a name="prerequisites"></a>Requisitos previos
Antes de generar el informe de ISR, puede usar Microsoft Dynamics 365 for Finance and Operations para configurar la categoría del concepto y para definir los índices de ISR que se deben aplicar en el informe. El informe de ISR se basa en las transacciones de diario generales.

### <a name="concepts"></a>Conceptos

Debe crear conceptos para identificar las distintas secciones del informe y vincular a continuación una o más cuentas principales para cada concepto. Puede vincular un intervalo o cuentas principales específicas, en función de la estructura del plan de cuentas. Cuando se vincula una cuenta principal, puede seleccionar **Débitos** para usar el importe del débito, **Crédito** para usar solo el importe de crédito o **Ambos**. El informe de ISR muestra el valor, en función del concepto que haya configurado. **Ejemplo**

|               |                                                          |
|---------------|----------------------------------------------------------|
| **Ingresos**   | Cuentas principales 4010001, 401002, 4010003, 4100001, 4100002 |
| **Inventario** | Cuentas principales 1155001, 1155002, 1155003                  |

### <a name="isr-rate-table"></a>Tabla de coeficientes de ISR

Puede crear o actualizar los índices de ISR que se usan para calcular el importe del pago de ISR provisional. Esta tabla está normalmente disponible en el sitio del gobierno. Identifica el año y el mes y, a continuación los importes mínimo y máximo, el importe fijo y el índice de ISR. En el informe de pago de ISR, el porcentaje de la tasa se usa para multiplicar el valor derivado después de que el importe mínimo se deduzca del importe fiscal resultante. **Ejemplo**

| Importe mínimo | Importe máximo | Importe fijo | Porcentaje de tasa que se aplicará en el importe mínimo |
|----------------|----------------|--------------|--------------------------------------------------|
| 0,00           | 496,07         | 0,00         | 1,92                                             |
| 496,08         | 4210,41       | 9,52         | 6,4                                              |
| 4210,42       | 7399,42       | 247,23       | 10,88                                            |
| 7399,43       | 8601,50       | 594,24       | 16                                               |
| 8601,51       | 10.298,35      | 786,55       | 17,92                                            |

Si el importe de utilidad fiscal que se obtiene durante el proceso de cálculo se encuentra entre 7399,43 y 8601,50, la tasa que se debe aplicar es del 16 por ciento.

## <a name="generating-the-provisional-isr-payment-report"></a>Generación del informe de pago de ISR provisional
Puede generar un informe de ISR detallado o el informe puede resumir cada cuenta principal que tenga los indicadores de débito y crédito. Para generar el informe, haga clic en **Impuestos** &gt; **Declaraciones** &gt; **Impuestos** &gt; **Informes de ISR**. Al generar el informe de ISR, debe especificar la información en los campos siguientes:

-   **Mes** y **Año**
-   **Coeficiente de utilidad**: especifique el valor que se usará como parte del cálculo de los impuestos de ISR para el período. En el informe de ISR, este coeficiente se multiplicará por el valor del concepto **Categoría de ingresos**.
-   **Tipo de informe**: seleccione uno de los siguientes valores:
    -   **Detalles**: los valores se agrupan por categoría de concepto y las cuentas principales que se vinculan a cada categoría. Cada registro del informe muestra la cuenta principal, el nombre de la cuenta principal, los números de asiento, el período para el que se genera el informe, el tipo de registro de las transacciones y el valor de las transacciones. El informe también indica si las transacciones son débitos o de créditos. Todos los campos de importe del informe se muestran en la divisa de la empresa.
    -   **Resumen**: los valores se agrupan por categoría de concepto y se calcula el valor global de cada categoría del concepto. Este informe muestra el importe mínimo, el importe fijo, la tasa de utilidad y los índices de ISR. Todos los campos de importe del informe se muestran en la divisa de la empresa.




