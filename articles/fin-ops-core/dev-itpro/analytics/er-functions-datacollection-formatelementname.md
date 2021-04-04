---
title: Función FORMATELEMENTNAME ER
description: Este tema proporciona información general sobre cómo usar la función FORMATELEMENTNAME de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 1e2ee2faa2784f34d540c113622cee2090f24cef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561311"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="717ef-103">Función FORMATELEMENTNAME ER</span><span class="sxs-lookup"><span data-stu-id="717ef-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="717ef-104">La función `FORMATELEMENTNAME` devuelve un valor *Cadena* que representa el nombre del elemento del formato de informe electrónico ER actual.</span><span class="sxs-lookup"><span data-stu-id="717ef-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="717ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="717ef-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="717ef-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="717ef-106">Return values</span></span>

<span data-ttu-id="717ef-107">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="717ef-107">*String*</span></span>

<span data-ttu-id="717ef-108">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="717ef-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="717ef-109">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="717ef-109">Usage notes</span></span>

<span data-ttu-id="717ef-110">Esta función puede llamarse en expresiones ER configuradas para las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** de un componente de formato ER del grupo **Texto** que reside en el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="717ef-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="717ef-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="717ef-111">Example</span></span>

<span data-ttu-id="717ef-112">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="717ef-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="717ef-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="717ef-113">Additional resources</span></span>

[<span data-ttu-id="717ef-114">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="717ef-114">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]