---
title: "Visión general de la actualización del libro de amortización"
description: "En versiones anteriores, había dos conceptos de la evaluación para los activos fijos - modelos de valor y libros de amortización. En la versión 1611 de Microsoft Dynamics 365 for Operations, la función del modelo de valor y la del libro de amortización se han combinado en un solo concepto que se conoce como libro. Este tema proporciona algunas cosas a tener en cuenta para la actualización."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Visión general de la actualización del libro de amortización

En versiones anteriores, había dos conceptos de la evaluación para los activos fijos - modelos de valor y libros de amortización. En la versión 1611 de Microsoft Dynamics 365 for Operations, la función del modelo de valor y la del libro de amortización se han combinado en un solo concepto que se conoce como libro. Este tema proporciona algunas cosas a tener en cuenta para la actualización. 

El proceso de actualización moverá la configuración existente y todas las transacciones existentes a la estructura del nuevo libro. Los modelos de valor se mantendrán como hasta ahora, como un libro que registra en la contabilidad general. Los libros de amortización se moverán a un libro que tiene la opción **Registrar en la contabilidad general** establecida como **No**. Los nombres del diario del libro amortización se mueven a un nombre de diario de contabilidad general con la capa de registro establecida ** Ninguno **. Las transacciones del libro de amortización se mover a las transacciones de activos fijos. 

Antes de ejecutar la actualización de datos, debe comprender las dos opciones disponibles para actualizar las líneas del diario del libro de depreciación a los asientos de la transacción, y la secuencia numérica que se usará para la serie de asientos. 

Opción 1:  **secuencia numérica definida por el sistema** - Esta es la opción predeterminada para optimizar el rendimiento de la actualización. La actualización no utilizará el marco de las secuencias numéricas, pero por el contrario, debe asignar los asientos con un enfoque establecido. Una vez finalizada la actualización, la nueva secuencia numérica se creará con ** siguiente número establecido correctamente ** basado en las transacciones actualizadas. De forma predeterminada, la secuencia numérica usada tendrá el formato de FADBUpgr\#\#\#\#\#\#\#\#\# . Existen algunos parámetros disponibles para ajustar el formato al utilizar este planteamiento:

-   ** Código de secuencia numérica – ** el código para identificar la secuencia numérica. Este código de secuencia numérica no puede existir ya que se creará en la actualización.
    -   Nombre constante: **NumberSequenceDefaultCode**
    -   Valor predeterminado: "FADBUpgr"
-   **Prefijo** – El valor de cadena constante que se utilizará como prefijo para los números de asiento.
    -   Nombre constante: **NumberSequenceDefaultParameterPrefix**
    -   Valor predeterminado: "FADBUpgr"
-   **Longitud alfanumérica** – La longitud del segmento alfanumérico de la secuencia numérica.
    -   Nombre constante: ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Valor predeterminado: 9
-   **Número de inicio** - El primer número que se utilizará en la secuencia numérica.
    -   Nombre constante: ** NumberSequenceDefaultParameterStartNumber **
    -   Valor predeterminado: 1

Opción 2: ** La secuencia numérica definido por el usuario existente ** - esta opción le permitirá que defina la secuencia numérica que se utilizará para la actualización. Considere el uso de esta opción si necesita la configuración avanzada de la secuencia numérica. Para usar una secuencia numérica, debe modificar la clase ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans de actualización con la siguiente información:

-   **Código de secuencia numérica**: El código de la secuencia numérica.
    -   Nombre constante: ** NumberSequenceExistingCode **
    -   Valor predeterminado: No hay valor predeterminado, debe actualizarse al código de secuencia numérica.
-   **Secuencia numérica compartida**: Un valor booleano para identificar el ámbito de la secuencia numérica. Use “verdadero” para las secuencias numéricas compartidas en todas las empresas, y "falso" para el ámbito específico de una empresa. Cuando el uso “falso”, la secuencia numérica con el nombre especificado debe existir en cada empresa que contiene transacciones del libro depreciación. Las secuencias numéricas compartidas existen en cada parte que contenga transacciones del libro depreciación.
    -   Nombre constante: ** NumberSequenceExistingIsShared **
    -   Valor predeterminado: verdadero

Los parámetros se encuentran al principio de la clase de ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

* Especifique un enfoque preferible de 
allocation* de los asientos * verdadera, si desea usar un code* 
de la secuencia numérica existente * falso, si piensa usar la secuencia numérica definida por el sistema (predeterminado) * const NumberSequenceUseExistingCode booleano = falso;  

* Si se usa el enfoque de definidos por la secuencia numérica, especifique los parámetros del número sequence.*
* una nueva secuencia numérica se creará con estos parameters.* str NumberSequenceDefaultCode de const = “;” FADBUpgr str NumberSequenceDefaultParameterPrefix de const = “;” FADBUpgr const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

* Si se usa el enfoque de la secuencia numérica existente, especifique la secuencia numérica existente code.* 
* la asignación de asiento irá fila-por- fila para el número sequences.* existente str NumberSequenceExistingCode de const = ''; * Especifique el ámbito de 
code* de la secuencia numérica existente * verdadera, si la secuencia numérica especificada es shared* 
* falso, si la secuencia numérica especificada es per-company* 
* la secuencia numérica predeterminada definida por el sistema se utilizará si un código de secuencia numérica con el ámbito especificado no es found.* const boolean NumberSequenceExistingIsShared = verdadero; 

Volver a crear el proyecto que contiene la clase después de que se hayan modificado las constantes. 

Al usar el enfoque generado por el sistema de la secuencia numérica (la opción 1), la actualización utilizará el procesamiento establecer- basado para asignar los números de asiento como se especifica en los parámetros de la secuencia de comandos de actualización. También creará una nueva secuencia numérica con parámetros especificados después de la asignación. 

Al usar el enfoque de la secuencia numérica existente definida por el usuario (opción 2), la actualización de datos comprueba si la secuencia numérica con el ámbito especificado existe en la base de datos para cada parte y empresa con transacciones del libro de depreciación. Si existe, la actualización utilizará el procesamiento de la fila-por- fila para asignar los números de asiento según lo especificó la secuencia numérica mediante el marco de la secuencia numérica. Si la secuencia numérica no existe con el ámbito especificado la actualización, utilizará el método predeterminado definido de la secuencia numérica para asignar los números de asiento, y creará una nueva secuencia numérica con parámetros predeterminados especificados después de la asignación.

Con cualquiera de los enfoques, la secuencia de comandos de actualización de datos también utilizará la secuencia numérica del campo **Serie de asientos** en los nuevos nombres de diario de contabilidad general creados para los nombres anteriores del diario del libro amortización.


