---
title: Función NULLDATETIME ER
description: Este tema proporciona información general sobre cómo usar la función NULLDATETIME de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 159abe09f158565fa9c38da530498329ff183fba
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563447"
---
# <a name="nulldatetime-er-function"></a><span data-ttu-id="52d44-103">Función NULLDATETIME ER</span><span class="sxs-lookup"><span data-stu-id="52d44-103">NULLDATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52d44-104">La función `NULLDATETIME` devuelve un valor *Fecha y hora* que representa el valor **nulo** de fecha / hora (1 de enero de 1900) en hora universal coordinada (Hora meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="52d44-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="52d44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52d44-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="52d44-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="52d44-106">Return values</span></span>

<span data-ttu-id="52d44-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="52d44-107">*DateTime*</span></span>

<span data-ttu-id="52d44-108">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="52d44-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="52d44-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52d44-109">Example</span></span>

<span data-ttu-id="52d44-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` devuelve el valor de la cadena **1900-01-01T00:00:00.0000000+00:00** cuando se llama durante un proceso iniciado por un usuario de la aplicación que tiene el valor de zona horaria **(GMT) Hora universal coordinada** en la sección **Preferencias de idioma y país / región**.</span><span class="sxs-lookup"><span data-stu-id="52d44-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52d44-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="52d44-111">Additional resources</span></span>

[<span data-ttu-id="52d44-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="52d44-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]