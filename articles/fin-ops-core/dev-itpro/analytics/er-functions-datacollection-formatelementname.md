---
title: Función FORMATELEMENTNAME ER
description: En este artículo se proporciona información sobre cómo usar la función FORMATELEMENTNAME de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 0a733c3c70cede6395b3d7454d82ce4d999e7e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851991"
---
# <a name="formatelementname-er-function"></a>Función FORMATELEMENTNAME ER

[!include [banner](../includes/banner.md)]

La función `FORMATELEMENTNAME` devuelve un valor *Cadena* que representa el nombre del elemento del formato de informe electrónico ER actual.

## <a name="syntax"></a>Sintaxis

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función puede llamarse en expresiones ER configuradas para las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** de un componente de formato ER del grupo **Texto** que reside en el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.

## <a name="example"></a>Ejemplo

Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de recopilación de datos](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]