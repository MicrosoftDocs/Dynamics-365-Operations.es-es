---
title: Función GETCURRENTCOMPANY de ER
description: Este tema proporciona información general sobre cómo usar la función GETCURRENTCOMPANY de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: fcb5ef2f218a85bab25f830db583343504c46e98
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567553"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="aecad-103">Función GETCURRENTCOMPANY de ER</span><span class="sxs-lookup"><span data-stu-id="aecad-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aecad-104">La función `GETCURRENTCOMPANY` devuelve un valor *Cadena* que representa el código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente.</span><span class="sxs-lookup"><span data-stu-id="aecad-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="aecad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aecad-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="aecad-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="aecad-106">Return values</span></span>

<span data-ttu-id="aecad-107">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="aecad-107">*String*</span></span>

<span data-ttu-id="aecad-108">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="aecad-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="aecad-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aecad-109">Example</span></span>

<span data-ttu-id="aecad-110">`GETCURRENTCOMPANY ()` devuelve **USMF** para un usuario que está registrado en la empresa **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="aecad-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aecad-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aecad-111">Additional resources</span></span>

[<span data-ttu-id="aecad-112">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="aecad-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]