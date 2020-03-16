---
title: Función CONVERTCURRENCY de ER
description: En este tema se proporciona información sobre cómo usar la función CONVERTCURRENCY de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d0c168e07252f7c423271bc808f3fca3834077f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041524"
---
# <a name="CONVERTCURRENCY">Función CONVERTCURRENCY de ER</a>

[!include [banner](../includes/banner.md)]

La función `CONVERTCURRENCY` devuelve un valor *Real* que representa el resultado de convertir el importe monetario especificado de la divisa de origen especificada a la divisa de destino especificada con la configuración de la empresa especificada en la fecha especificada.

## <a name="syntax"></a>Sintaxis

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argumentos

`amount`: *Entero* o *Real*

Un valor numérico que representa la cantidad monetaria que debe convertirse.

`source currency`: *Cadena*

El código de la divisa de origen.

`target currency`: *Cadena*

El código de divisa objetivo.

`date`: *Fecha*

Un valor *Fecha* que representa la fecha que se utiliza para determinar el tipo de cambio para la conversión.

`company`: *Cadena*

Un valor *Cadena* que representa el código de una empresa que proporciona la configuración que se utiliza para la conversión.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="example"></a>Ejemplo

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` devuelve el equivalente de un euro en dólares estadounidenses en la fecha de la sesión actual, en función de la configuración para la empresa de **DEMF**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)
