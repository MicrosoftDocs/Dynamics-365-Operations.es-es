---
title: Función GETCURRENTCOMPANY de ER
description: Este tema proporciona información general sobre cómo usar la función GETCURRENTCOMPANY de informes electrónicos (ER).
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
ms.openlocfilehash: d91caff1a1b89e060a16833e53f3647208ed3826
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041432"
---
# <a name="GETCURRENTCOMPANY">Función GETCURRENTCOMPANY de ER</a>

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
