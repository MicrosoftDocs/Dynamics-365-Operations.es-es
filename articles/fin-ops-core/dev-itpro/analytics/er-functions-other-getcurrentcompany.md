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
ms.openlocfilehash: a0b4c93a4705cd0e382b9b6c7af1d199beeceabe
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916002"
---
# <span data-ttu-id="86712-103"><a name="GETCURRENTCOMPANY">Función GETCURRENTCOMPANY de ER</a></span><span class="sxs-lookup"><span data-stu-id="86712-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="86712-104">La función `GETCURRENTCOMPANY` devuelve un valor *Cadena* que representa el código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente.</span><span class="sxs-lookup"><span data-stu-id="86712-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="86712-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86712-105">Syntax</span></span>

```
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="86712-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="86712-106">Return values</span></span>

<span data-ttu-id="86712-107">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="86712-107">*String*</span></span>

<span data-ttu-id="86712-108">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="86712-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="86712-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86712-109">Example</span></span>

<span data-ttu-id="86712-110">`GETCURRENTCOMPANY ()` devuelve **USMF** para un usuario que está registrado en la empresa **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="86712-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="86712-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="86712-111">Additional resources</span></span>

[<span data-ttu-id="86712-112">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="86712-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
