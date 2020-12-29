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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e14c6a8aaff0a32a115117938d0e853bb34bb14
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684868"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="50702-103">Función GETCURRENTCOMPANY de ER</span><span class="sxs-lookup"><span data-stu-id="50702-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50702-104">La función `GETCURRENTCOMPANY` devuelve un valor *Cadena* que representa el código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente.</span><span class="sxs-lookup"><span data-stu-id="50702-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="50702-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50702-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="50702-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="50702-106">Return values</span></span>

<span data-ttu-id="50702-107">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="50702-107">*String*</span></span>

<span data-ttu-id="50702-108">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="50702-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="50702-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50702-109">Example</span></span>

<span data-ttu-id="50702-110">`GETCURRENTCOMPANY ()` devuelve **USMF** para un usuario que está registrado en la empresa **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="50702-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50702-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="50702-111">Additional resources</span></span>

[<span data-ttu-id="50702-112">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="50702-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
