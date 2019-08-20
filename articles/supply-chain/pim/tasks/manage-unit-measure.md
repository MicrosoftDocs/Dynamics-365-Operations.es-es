---
title: Gestionar la unidad de medida
description: Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.
author: sorenva
manager: AnnBe
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 042a7495d55fb9d884771972cfc18e5ddb25330d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844330"
---
# <a name="manage-unit-of-measure"></a>Gestionar la unidad de medida

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas. Puede revisar este procedimiento con datos de demostración, o bien, utilizar sus propios datos.

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Mantenimiento de productos emitidos**.
2. Haga clic en **Unidades**.

## <a name="create-a-unit-of-measure"></a>Creación de una unidad de medida
1. Haga clic en **Nuevo**.
2. En el campo **Unidad**, escriba un valor. Especifique el identificador o el símbolo que usar al hacer referencia a la unidad de medida.  
3. En el campo **Descripción**, escriba un valor. Especifique un nombre descriptivo para la unidad de medida en el idioma del sistema.  
4. En el campo **Clase de unidad**, seleccione una opción. La clase de unidad define a qué agrupación lógica de medida, como área, masa o cantidad, pertenece la unidad de medida.  
5. En el campo **Precisión decimal**, especifique un número. Especifique el número de decimales a los que se redondea la unidad de medida convertida cuando se completa un cálculo para la unidad de medida.  
6. Haga clic en **Guardar**.

## <a name="define-unit-translations"></a>Definición de conversiones de unidades
1. En el **panel de acciones**, haga clic en **Textos de la unidad**.
2. Haga clic en **Nuevo**. Use el texto de unidad para crear una traducción del identificador o de un símbolo que represente a la unidad de medida para su uso en documentos externos en los idiomas específicos del cliente o del proveedor.  
3. En el campo **Idioma**, especifique o seleccione un valor.
4. En el campo **Texto**, escriba un valor.
5. Haga clic en **Guardar**.
6. Cierre la página.
7. En el **panel de acciones**, haga clic en **Descripciones de unidades convertidas**.
8. Haga clic en **Nuevo**. Defina descripciones en idiomas específicos para la unidad de medida.  
9. En el campo **Idioma**, especifique o seleccione un valor.
10. En el campo **Descripción**, escriba un valor.
11. Haga clic en **Guardar**.
12. Cierre la página.

## <a name="define-unit-conversion-rules"></a>Definición de reglas de conversión de unidades
1. En el **panel de acciones**, haga clic en **Conversiones de unidades**. Defina reglas para convertir la unidad de medida a y de otras unidades de medida en la clase de unidad seleccionada.  
2. Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
3. En el campo **Factor**, escriba un número. Factor de conversión entre la unidad de origen y la de destino. Por ejemplo, el factor de conversión de centímetros a metros es 100 porque hay 100 centímetros en un metro.  
4. En el campo **Hasta unidad**, especifique o seleccione un valor.
5. En el campo **Redondeo**, seleccione una opción. Defina cómo se debe redondear el valor convertido.  
6. Haga clic en **Aceptar**.
7. Cierre la página.

