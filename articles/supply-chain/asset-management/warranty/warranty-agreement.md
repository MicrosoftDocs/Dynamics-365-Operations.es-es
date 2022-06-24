---
title: Contratos de garantía
description: En este artículo se explican los contratos de garantía en Administración de activos.
author: johanhoffmann
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 32e5ba8bf87d7bcd30e7f1493540317764d347ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864038"
---
# <a name="warranty-agreements"></a>Contratos de garantía

[!include [banner](../../includes/banner.md)]

 


En gestión de activos, puede configurar los términos de garantía que se pueden conectar a un activo o un tipo de activo. Los términos de garantía se crean para un período específico. La garantía se puede configurar para proporcionar cobertura total o alcance parcial, y puede configurar condiciones relacionadas con las horas, los gastos, y artículos.

El primer paso consiste en crear los acuerdos de la garantía de proveedor que tiene en el equipo. A continuación adjunta los acuerdos de la garantía a los activos o a tipos de activos. Los acuerdos de la garantía de proveedor solo se usan con fines informativos. Si la garantía de proveedor se configura en un activo, puede consultar el período de cobertura de la garantía en el activo.

## <a name="create-a-warranty-agreement"></a>Crear un acuerdo de garantía

Un acuerdo de la garantía puede incluir varias líneas del acuerdo para cubrir la garantía para las horas de trabajo, gastos, y artículos.

1. Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Garantía**.
2. Seleccione **Nuevo** para crear un producto.
3. En el campo **Garantía**, especifique un identificador de la garantía. 
4. En el campo **Nombre**, escriba una descripción.

    En la ficha desplegable **Detalles**, el campo **Activos** se muestra el número de activos activos que usan el acuerdo de la garantía.

5. En la ficha desplegable **Líneas de garantía**, siga estos pasos para agregar líneas que deben incluirse en un acuerdo de garantía:

    1. Seleccione **Agregar línea** para agregar una nueva condición a la garantía. Se especifica automáticamente un número de línea secuencial en el campo **Línea**.
    2. En el campo **Período**, seleccione el tipo de período de garantía.
    3. Escriba un número en el campo **Intervalo**. Este campo define el número de períodos para los que la garantía debe ser válida.
    4. En el campo **Porcentaje**, especifique el porcentaje de cobertura para la línea de la garantía. El porcentaje indica cuánto está cubierta por la empresa.

![Página de garantía.](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]