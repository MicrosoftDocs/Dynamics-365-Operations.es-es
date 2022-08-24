---
title: Función ALLITEMSQUERY ER
description: En este artículo se proporciona información sobre cómo usar la función ALLITEMSQUERY de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e350dfbe800ddc3e7b1f388fb951d091a283f4e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285317"
---
# <a name="allitemsquery-er-function"></a>Función ALLITEMSQUERY ER

[!include [banner](../includes/banner.md)]

La función `ALLITEMSQUERY` se ejecuta como consulta SQL combinada. Devuelve un valor aplanado nuevo de *Lista de registros* que consiste en una lista de registros que representa todos los elementos que coinciden con la ruta especificada.

## <a name="syntax"></a>Sintaxis

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argumentos

`path`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*. Debe contener al menos una relación.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La ruta especificada se debe definir como ruta válida de un origen de datos a un elemento de origen de datos del tipo de datos de la *Lista de registro*. También debe contener al menos una relación. Elementos de datos como la *Cadena* de ruta y la *Fecha* deberían activar un error en el tiempo de diseño del generador de expresiones de informes electrónicos (ER).

Cuando esta función se aplica a las fuentes de datos del tipo de datos *Lista de registros* que se refieren a un objeto de aplicación al que se puede llamar directamente mediante SQL (por ejemplo, una tabla, entidad o consulta), se ejecuta como una consulta SQL unida. De lo contrario, se ejecuta en la memoria como función [ALLITEMS](er-functions-list-allitems.md).

## <a name="example"></a>Ejemplo

Defina los siguientes orígenes de datos en la asignación de su modelo:

- Una fuente de datos **CustInv** del tipo *Tabla de registros* que hace referencia a la tabla CustInvoiceTable
- Una fuente de datos **FilteredInv** del tipo *Campo calculado* que contiene la expresión `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- Una **JourLines** del tipo *Campo calculado* que contiene la expresión `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

Cuando ejecute la asignación del modelo para llamar al origen de datos **JourLines**, se ejecuta la siguiente instrucción SQL:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
