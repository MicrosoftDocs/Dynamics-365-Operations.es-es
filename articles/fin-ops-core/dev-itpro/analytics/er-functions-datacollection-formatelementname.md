---
title: Función FORMATELEMENTNAME ER
description: Este tema proporciona información general sobre cómo usar la función FORMATELEMENTNAME de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d66fed3815188fa7e31735e3523376ae4ea1cf46
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917681"
---
# <span data-ttu-id="8b674-103"><a name="FORMATELEMENTNAME">Función FORMATELEMENTNAME ER</a></span><span class="sxs-lookup"><span data-stu-id="8b674-103"><a name="FORMATELEMENTNAME">FORMATELEMENTNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b674-104">La función `FORMATELEMENTNAME` devuelve un valor *Cadena* que representa el nombre del elemento del formato de informe electrónico ER actual.</span><span class="sxs-lookup"><span data-stu-id="8b674-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b674-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b674-105">Syntax</span></span>

```
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="8b674-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8b674-106">Return values</span></span>

<span data-ttu-id="8b674-107">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8b674-107">*String*</span></span>

<span data-ttu-id="8b674-108">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="8b674-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8b674-109">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8b674-109">Usage notes</span></span>

<span data-ttu-id="8b674-110">Esta función puede llamarse en expresiones ER configuradas para las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** de un componente de formato ER del grupo **Texto** que reside en el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="8b674-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="8b674-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b674-111">Example</span></span>

<span data-ttu-id="8b674-112">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="8b674-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b674-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8b674-113">Additional resources</span></span>

[<span data-ttu-id="8b674-114">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="8b674-114">Data collection functions</span></span>](er-functions-category-data-collection.md)
