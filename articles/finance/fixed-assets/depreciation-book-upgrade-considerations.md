---
title: Información general de la actualización del libro amortización
description: Este artículo describe la funcionalidad del libreo actual en Activos fijos. Esta función se basa en la función del modelo de valor que estaba disponible en versiones anteriores, pero también incluye todas las funciones que se proporcionaron anteriormente únicamente en libros de depreciación.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 784ec32ae886ef7ea9342b085f893eeeec761961
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855502"
---
# <a name="depreciation-book-upgrade-overview"></a>Información general de la actualización del libro amortización

[!include [banner](../includes/banner.md)]

Este artículo describe la funcionalidad del libreo actual en Activos fijos. Esta función se basa en la función del modelo de valor que estaba disponible en versiones anteriores, pero también incluye todas las funciones que se proporcionaron anteriormente únicamente en libros de depreciación. La función de modelo de valor y la funcionalidad de libro de depreciación se han combinado en un solo concepto que se conoce como libro. La funcionalidad del libro le permite utilizar un único conjunto de páginas, consultas e informes para todos los procesos de activos fijos de su organización. Este artículo proporciona algunos asuntos que debe considerar antes de actualizar. 

El proceso de actualización moverá la configuración existente y todas las transacciones existentes a la estructura del nuevo libro. Los modelos de valor se mantendrán como hasta ahora, como un libro que registra en la contabilidad general. Los libros de amortización se moverán a un libro que tiene la opción Registrar en la contabilidad general establecida como No. Los nombres del diario del libro de depreciación se moverán a un nombre de diario de la contabilidad general con la capa de registro establecida a Ninguno. Las transacciones del libro de depreciación se moverán a transacción de activo fijo.

Antes de ejecutar la actualización de datos, debe comprender las dos opciones disponibles para actualizar las líneas del diario del libro de depreciación a los asientos de la transacción, y la secuencia numérica que se usará para la serie de asientos.

Opción 1:  **secuencia numérica definida por el sistema** - Esta es la opción predeterminada para optimizar el rendimiento de la actualización. La actualización no utilizará el marco de las secuencias numéricas, pero por el contrario, debe asignar los asientos con un enfoque establecido. Una vez finalizada la actualización, se creará la nueva secuencia numérica con el **Conjunto del siguiente número** basado correctamente en las transacciones actualizadas. De forma predeterminada, la secuencia numérica usada tendrá el formato de FADBUpgr\#\#\#\#\#\#\#\#\# . Existen algunos parámetros disponibles para ajustar el formato al utilizar este planteamiento:

-   **Código de secuencia numérica**: el código para identificar la secuencia numérica. Este código de secuencia numérica no puede existir ya que se creará en la actualización.
    -   Nombre constante: **NumberSequenceDefaultCode**
    -   Valor predeterminado: "FADBUpgr"
-   **Prefijo** – El valor de cadena constante que se utilizará como prefijo para los números de asiento.
    -   Nombre constante: **NumberSequenceDefaultParameterPrefix**
    -   Valor predeterminado: "FADBUpgr"
-   **Longitud alfanumérica** – La longitud del segmento alfanumérico de la secuencia numérica.
    -   Nombre de constante: **NumberSequenceDefaultParameterAlpanumericLength**
    -   Valor predeterminado: 9
-   **Número de inicio** - El primer número que se utilizará en la secuencia numérica.
    -   Nombre de constante: **NumberSequenceDefaultParameterStartNumber**
    -   Valor predeterminado: 1

Opción 2: **Secuencia numérica definida por el usuario existente**: esta opción le permitirá definir la secuencia numérica que se utilizará para la actualización. Considere el uso de esta opción si necesita la configuración avanzada de la secuencia numérica. Para usar una secuencia numérica, debe modificar la clase ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans de la actualización con la siguiente información:

-   **Código de secuencia numérica**: El código de la secuencia numérica.
    -   Nombre de constante: **NumberSequenceExistingCode**
    -   Valor predeterminado: No hay valor predeterminado, debe actualizarse al código de secuencia numérica.
-   **Secuencia numérica compartida**: Un valor booleano para identificar el ámbito de la secuencia numérica. Use “verdadero” para las secuencias numéricas compartidas en todas las empresas, y "falso" para el ámbito específico de una empresa. Cuando use “falso”, la secuencia numérica con el nombre especificado debe existir en cada empresa que contenga transacciones del libro de depreciación. Las secuencias numéricas compartidas existen en cada parte que contenga transacciones del libro depreciación.
    -   Nombre de constante: **NumberSequenceExistingIsShared**
    -   Valor predeterminado: verdadero

Los parámetros se encuentran al principio de la clase ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*// Especifique un enfoque preferible de la asignación de los asientos* 
 *// verdadero, si desea usar un código de secuencia numérica existente* 
 *// falso, si piensa usar la secuencia numérica definida por el sistema (el valor predeterminado)* const boolean NumberSequenceUseExistingCode = falso;  

*// Si se usa el enfoque de la secuencia numérica definida por el sistema, especifique los parámetros para la secuencia numérica.*
 *// Se creará una nueva secuencia numérica con estos parámetros.* str NumberSequenceDefaultCode de const = “;” FADBUpgr str NumberSequenceDefaultParameterPrefix de const = “;” FADBUpgr const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Si se usa el enfoque de la secuencia numérica existente, especifique el código de secuencia numérica existente* 
 *// La asignación de asiento irá fila por fila para las secuencias numéricas existentes.* const str NumberSequenceExistingCode = ''; *// Especifique el ámbito del código de secuencia numérica existente* 
 *// verdadero, si se comparte la secuencia numérica especificada* 
 *// falso, si la secuencia numérica especificada es por empresa* 
 *// La secuencia numérica predeterminada definida por el sistema se usará si no se encuentra un código de secuencia numérica con el ámbito especificado.* const boolean NumberSequenceExistingIsShared = verdadero; 

Volver a crear el proyecto que contiene la clase después de que se hayan modificado las constantes. 

Al usar el enfoque de la secuencia numérica generado por el sistema (opción 1), la actualización utilizará el procesamiento establecido para asignar los números de asiento como se especifica en los parámetros de la secuencia de comandos de actualización. También creará una nueva secuencia numérica con parámetros especificados después de la asignación. 

Al usar el enfoque de la secuencia numérica existente definida por el usuario (opción 2), la actualización de datos comprueba si la secuencia numérica con el ámbito especificado existe en la base de datos para cada parte y empresa con transacciones del libro de depreciación. Si existe, la actualización utilizará el procesamiento de fila por fila para asignar los números de asiento según lo especificó la secuencia numérica mediante el marco de la secuencia numérica. Si la secuencia numérica no existe con el ámbito especificado, la actualización utilizará el enfoque predeterminado de la secuencia numérica definido por el sistema para asignar los números de asiento, y creará una nueva secuencia numérica con parámetros predeterminados especificados después de la asignación.

Con cualquiera de los enfoques, la secuencia de comandos de actualización de datos también utilizará la secuencia numérica del campo **Serie de asientos** en los nuevos nombres de diario de contabilidad general creados para los nombres anteriores del diario del libro amortización.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
