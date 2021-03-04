---
title: Función NUMSEQVALUE ER
description: En este tema se proporciona información sobre cómo usar la función NUMSEQVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b513d04bfeb3a37aa0b1703d0fdde040885a5159
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680599"
---
# <a name="numseqvalue-er-function"></a>Función NUMSEQVALUE de ER

[!include [banner](../includes/banner.md)]

La función `NUMSEQVALUE` devuelve un valor de tipo *Cadena* que representa el nuevo valor generado de una secuencia numérica, basado en la secuencia numérica especificada, el ámbito y el id. de ámbito. El id. de ámbito es igual al código de empresa suministrado por el contexto en el que se ejecuta el formato de informes electrónicos (ER).

## <a name="syntax-1"></a>Sintaxis 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Sintaxis 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argumentos

`number sequence code`: *Cadena*

Un valor de texto que representa el código de la secuencia numérica en la que se requiere un nuevo valor.

`number sequence record ID`: *Int64*

Un valor de tipo *Int64* que representa el id. de registro de un registro de la tabla NumberSequenceTable que contiene la definición de la secuencia numérica en la que se requiere un nuevo valor.

`scope type`: *Valor de enumeración*

Un valor de enumeración de **ERExpressionNumberSequenceScopeType** que define el ámbito de la secuencia numérica en la que se requiere un nuevo valor. Los tipos de ámbito disponibles son **Compartido**, **Entidad jurídica** y **Empresa**.

`scope ID`: *Cadena*

Valor de tipo *Cadena* que identifica el ámbito en función del tipo de ámbito especificado.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Para el ámbito de tipo **Compartido**, especifique una cadena vacía como identificador de ámbito.

Para los ámbitos de tipo **Empresa** y **Entidad jurídica**, especifique el código de empresa como identificador de ámbito. Si especifica una cadena vacía como el identificador de ámbito para estos tipos de ámbito, se usa el código de la empresa actual.

Cuando se utiliza la sintaxis 1, se solicita la secuencia numérica para el tipo de ámbito **Empresa** y el el código de empresa lo suministra el contexto en el que se ejecuta el formato de ER.

## <a name="example-1"></a>Ejemplo 1

En su formato de ER, usted define el origen de datos **AskNumSeq** del tipo *Parámetro de entrada del usuario*. Este origen de datos hace referencia a la tipo de datos extendido (EDT) **Descripción**. A continuación, define el origen de datos **NumSeq** del tipo *Campo calculado*. Este origen de datos contiene la expresión `NUMSEQVALUE (AskNumSeq)`. Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado de la secuencia numérica que se especificó en tiempo de ejecución al introducir su código en el cuadro de diálogo. Se solicita la secuencia numérica para el ámbito de tipo **Empresa**. El código de empresa lo suministra el contexto en el que se ejecuta el formato de ER.

## <a name="example-2"></a>Ejemplo 2

Los siguientes orígenes de datos se definen en la asignación del modelo:

- El origen de datos **LedgerParms** del tipo *Tabla*. Este origen de datos hace referencia a la tabla LedgerParameters.
- El origen de datos **NumSeq** del tipo de datos *Campo calculado*. Este origen de datos contiene la expresión `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado a partir de la secuencia numérica que se ha configurado en los parámetros de contabilidad general para la empresa que proporciona el contexto donde se ejecuta el formato de ER. Esta secuencia numérica identifica de forma exclusiva los diarios y actúa como número de lote que vincula las transacciones.

## <a name="example-3"></a>Ejemplo 3

Los siguientes orígenes de datos se definen en la asignación del modelo:

- El origen de datos **enumScope** del tipo *enumeración* de Microsoft Dynamics 365 Finance. Este origen de datos hace referencia a la enumeración **ERExpressionNumberSequenceScopeType**.
- El origen de datos **NumSeq** del tipo de datos *Campo calculado*. Este origen de datos contiene la expresión `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado a partir de la secuencia numérica **Gene\_1** que se ha configurado para la empresa que proporciona el contexto donde se ejecuta el formato de ER.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]