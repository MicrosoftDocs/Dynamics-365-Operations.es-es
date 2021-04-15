---
title: Función GETCURRENTCOMPANY de ER
description: Este tema proporciona información general sobre cómo usar la función GETCURRENTCOMPANY de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 87bef4aa11c01b42af19f7dc20ca8731b9fb4111
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752848"
---
# <a name="getcurrentcompany-er-function"></a>Función GETCURRENTCOMPANY de ER

[!include [banner](../includes/banner.md)]

La función `GETCURRENTCOMPANY` devuelve un valor *Cadena* que representa el código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente.

## <a name="syntax"></a>Sintaxis

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`GETCURRENTCOMPANY ()` devuelve **USMF** para un usuario que está registrado en la empresa **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]