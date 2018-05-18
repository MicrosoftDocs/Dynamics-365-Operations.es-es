---
title: Procesamiento de diarios generales
description: "Este artículo describe las capacidades en Microsoft Dynamics 365 for Finance and Operations que pueden facilitar el proceso del diario general y que también pueden ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb46613f805999753c2ab73ffb91a6fdae04c68e
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="general-journal-processing"></a>Procesamiento de diarios generales

[!include [banner](../includes/banner.md)]

Este artículo describe las capacidades en Microsoft Dynamics 365 for Finance and Operations que pueden facilitar el proceso del diario general y que también pueden ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno.  

Nombres de diarios

Una de las áreas más importantes para configurar es los nombres de diario. Conviene definir los nombres de diario específicos para cada propósito, como empresas vinculadas, ajuste de acumulación y corrección de error. Puede ajustar cada nombre de diario para que la entrada de datos para cada propósito sea sencilla y segura. 

En la página **Nombres de diario**, puede configurar los siguientes elementos:

-   **Aprobación de flujo de trabajo:** para mejorar el control interno, defina los flujos de trabajo de diarios que establecen los límites de los pasos para su revisión y aprobación, en función de criterios como importe de débito total. Debe configurar los flujos de trabajo para los diarios generales en la página **Flujos de trabajo de contabilidad general**.
-   **Valores predeterminados:** seleccione valores predeterminados para cuentas de contrapartida, divisa y dimensiones financieras.
-   **Control del diario:** puede configurar las restricciones en la empresa y el tipo de cuenta, y también los valores de segmento. 

**Ejemplos**

Un nombre de diario también se puede usar solo para ajustes. En este caso, puede especificar que solo el tipo de cuenta **Libro mayor** es válido en todas las empresas. [![Tipos de cuenta de control de diarios](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Un nombre de diario solo se puede usar para un segmento específico o para un intervalo para las cuentas principales. [![Segmento de control de diarios](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

La opción **Inversión automática** solo está disponible en los diarios generales. Por ejemplo, tiene un ajuste de acumulación donde el documento real aún no se ha procesado, como se muestra en la siguiente ilustración.
[![Inversión del diario general](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

El complemento de Microsoft Excel para el movimiento del diario proporciona un nivel adicional de automatización y hace que la entrada de datos sea más fácil. La acción **Líneas abiertas en Excel** está disponible en las páginas del **Diario general** y **Asiento del diario** . 

En la página **Diarios periódicos**, puede configurar los diarios periódicos para automatizar el proceso de diario. 

Puede usar plantillas de asientos en cualquier momento. En la página **Diarios generales**, las acciones **Guardar** y **Seleccionar la plantilla de asientos** se encuentran en la página **Asiento del diario**, en **Funciones** para las líneas de asientos.

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

Para obtener más información, consulte los siguientes temas:
- [Planificación: plan de cuentas](plan-chart-of-accounts.md). 
- [Crear reglas avanzadas para diarios](tasks/create-advanced-rules-journals.md)
- [Crear un movimiento de diario mediante una plantilla](tasks/create-journal-entry-template.md)
- [Crear y validar diarios](tasks/create-validate-journals.md)
- [Registrar diarios periódicos](tasks/post-periodic-journals.md)
- [Procesar diario de asignaciones contables](tasks/process-ledger-allocation-journal.md)



