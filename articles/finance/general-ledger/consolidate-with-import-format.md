---
title: Formato de importación para consolidación
description: Este tema proporciona información detallada sobre el formato de importación que se usa al consolidar datos financieros de varias entidades legales.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6d25ebfedfe748dfa262c1d4b0671539e6150a0f9f05dfca42e87f23486fbb19
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746425"
---
# <a name="import-format-for-consolidation"></a>Formato de importación para consolidación

[!include [banner](../includes/banner.md)]

Este tema proporciona información detallada sobre el formato de importación que se usa al consolidar datos financieros de varias entidades legales. El formato de importación debe guardarse como archivo de texto (.txt).

## <a name="import-format"></a>Formato de importación

La siguiente tabla enumera el formato de importación que debe utilizar cuando realiza una consolidación durante una importación.

| Tabla de registro | Formato | Notas |
|--------------|---------|-------|
| 1            | 170150, Fondo de comercio, 4 | <ul><li>Tabla de registro</li><li>El id. de la cuenta principal de origen</li><li>La línea de cuenta principal</li><li>El tipos de cuenta principal</li></ul> |
| 2            | 110130, 01/01/2015, 1, USD, 0,0,80699.39,0,1 | <ul><li>El id. de la cuenta principal</li><li>La fecha de transacción</li><li>El tipo de período fiscal (**0** = Apertura, **1** = En funcionamiento y **2** = Cierre)</li><li>La divisa de la transacción</li><li>Débito o crédito (**0** = Débito y **1** = Crédito)</li><li>La capa de registro</li><li>Importes de transacciones</li><li>Cantidad</li><li>El RecID local (valor int64 ambiguo y único para la transacción)</li></ul> |
| 3            | USMF0000009, 01/01/2017, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>El número de entrada (número de transacción del encabezado del presupuesto)</li><li>La fecha predeterminada del encabezado del presupuesto</li><li>El id. del modelo de presupuesto</li><li>Tipo de presupuesto (**1** - Presupuesto original, **2** - Transferencia, **3** - Revisión, **4** - Reserva de gasto, **5** - Previa reserva de gasto, **6** - Presupuesto transferible, **7** - Proyecto, **8** - Activos fijos, **9** - Previsión de la demanda, **10** - Previsión de suministro, **11** - Prorrateos, **12** - Presupuesto preliminar.)</li><li>La fecha de la línea</li><li>El id. de cuenta principal de la línea</li><li>El código de divisa para la línea</li><li>El importe de la línea, en la divisa de la transacción</li><li>El valor entero de enumeración para el tipo de presupuesto de la línea (gastos o ingresos)</li></ul> |
| 4            | DEMF | RecordCompany es la entidad jurídica de origen. |
| 5            | 110130, 01/01/2015, 1, USD, 0,0,80699.39,0,1 | <ul><li>Id. de la cuenta principal</li><li>Fecha movimiento</li><li>Tipo de período fiscal (0 Apertura, 1 En funcionamiento y 2 Cierre)</li><li>Divisa de la transacción</li><li>Débito o crédito (0 para Débito y 1 para Crédito)</li><li>Capa de registro</li><li>Importe de la transacción</li><li>Cantidad</li><li>El RecID local (valor int64 ambiguo y único para la transacción)</li></ul>  |
| 6            | BusinessUnit, 1 Departamento, 2 | Los atributos de dimensión financiera que se definen en el orden del segmento.<p>Puede usar la página **Exportar** para verificar cómo se definen los atributos.</p> |
| 7            | 002,1,658 | <ul><li>El valor de la dimensión financiera</li><li>La dimensión financiera, como el índice que se proporciona en RecordDimensions</li><li>Un id. de registro único y ambiguo que está asociado con el id. de registro único de RecordTrans o RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Valores de dimensión asociados con la transacción de RecordBudget</li><li>La dimensión financiera, como el índice que se proporciona en RecordDimensions</li><li>Un id. de registro de línea ambiguo que está alineado con el orden de las líneas de transacción en el archivo</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
