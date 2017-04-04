---
title: Procesamiento de diarios generales
description: "Este describen los artículos capacidad en Microsoft Dynamics 365 para las operaciones que pueden ayudar a crear procesar general del diario más sencilla, y que también pueden ayudar a garantizar que se captura los datos correctos y el control interno no se compromete."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 50cd203025be8857de943e458fc32315e494fb7a
ms.lasthandoff: 03/31/2017


---

# <a name="general-journal-processing"></a>Procesamiento de diarios generales

Este artículo describe las capacidades en Microsoft Dynamics AX que pueden facilitar el proceso del diario general y que también puede ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno.  

Nombres de diarios

Una de las partes más importantes a configurar es nombres de diario. Conviene definir nombres de diario específicos para cada propósito, como empresas vinculadas, ajuste de la acumulación, y corrección de errores. Puede ajustar cada nombre de diario para que la entrada de datos para cada propósito y fácil segura. 

En la página **Nombres de diario**, puede configurar los siguientes elementos:

-   **Aprobación de flujo de trabajo:** para mejorar el control interno, defina los flujos de trabajo de diarios que establecen los límites de los pasos para su revisión y aprobación, en función de criterios como importe de débito total. Se flujos de trabajo de la configuración de los diarios generales en ** flujos de trabajo de Contabilidad general ** la página.
-   **Valores predeterminados:** seleccione valores predeterminados para cuentas de contrapartida, divisa y dimensiones financieras.
-   **Control del diario:** puede configurar las restricciones en la empresa y el tipo de cuenta, y también los valores de segmento. 

**Ejemplos**

Un nombre de diario también se puede usar solo para ajustes. En este caso, puede especificar que solo el tipo de cuenta **Libro mayor** es válido en todas las empresas. [tipos de cuenta![control![Journal] (. /media/journal-control-account-types1.png])(. /media/journal-control-account-types1.png)

Un nombre de diario solo se puede usar para un segmento específico o para un intervalo para las cuentas principales. [segmento de control de![Journal] (. /media/journal-control-segment1.png])(. /media/journal-control-segment1.png)

La opción **Inversión automática** solo está disponible en los diarios generales. Por ejemplo, tiene un ajuste de acumulación donde el documento real aún no se ha procesado, como se muestra en la siguiente ilustración.
[diario general![de inversión] (. /media/general-journal-reversing1.png])(. /media/general-journal-reversing1.png) 

El complemento de Microsoft Excel para la entrada del diario proporciona una capa adicional de automatización y crea la entrada de datos más fácil. La acción **Líneas abiertas en Excel **está disponible en las páginas del **Diario general** y **Asiento del diario** . 

En la página **Diarios periódicos**, puede configurar los diarios periódicos para automatizar el proceso de diario. 

Puede usar plantillas de asientos en cualquier momento. ** En los diarios generales ** la página, ** Guardar ** y ** plantilla de asientos ** seleccione las acciones se encuentran en ** asiento de diario ** la página, en ** las funciones ** para las líneas de asiento.

## <a name="related-setup"></a>Configuración relacionada
La configuración siguiente no es específica para los diarios generales, pero ayudará a garantizar que la entrada de datos sea correcta y fácil.

### <a name="main-account"></a>Cuenta principal

La configuración de la cuenta principal ofrece muchas opciones para el proceso del diario general:

-   **Requisito de DC/CR:** use esta opción si una cuenta principal está limitada a las transacciones de débito o crédito. Se comprueba la configuración cuando se valida o se registra un diario.
-   **Cuenta de contrapartida predeterminada**
-   **Suspendida:** suspenda una cuenta principal para la entrada de datos en todas las empresas o para una empresa o entidad jurídica específicas.
-   **No permitir entrada manual:** evitar que los usuarios especifiquen manualmente un valor para la cuenta en los diarios.
-   **Validar divisa o predeterminada**
-   **Anulación de la entidad jurídica:** esta configuración es específica a la empresa o a entidad jurídica definidas:
    -   **Validar impuestos o predeterminados**
    -   **Dimensión predeterminada**: **Valor no fijo** o **Valor fijo**. **Valor fijo** ayudará a garantizar que todos los registros para esta cuenta principal usan siempre un valor de dimensión que está configurado como **Fijo**.
-   **Validación del registro**
    -   **Validación de usuario:** esta opción controla qué usuarios pueden registrar en una cuenta principal.
    -   **Validación de tipo de registro:** esta opción controla qué tipos de registro se premiten en una cuenta principal.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Estructuras contables y estructuras de reglas avanzadas

Las estructuras contables y las estructuras de reglas avanzadas son muy importantes para garantizar que los datos necesarios para los informes financieros y el seguimiento del rendimiento se capture durante el proceso del diario general y la documentación. Las estructuras contables y las estructuras de reglas avanzadas le permiten adaptar la experiencia de entrada de datos. Puede permitir la entrada de datos solo para las dimensiones financieras que son relevantes en cada situación, y también puede exigir el requisito de que los datos necesarios y correctos se capturen siempre.

Para obtener más información, consulte [planificado: Plan contable plan-chart-of-accounts.md] (). 


