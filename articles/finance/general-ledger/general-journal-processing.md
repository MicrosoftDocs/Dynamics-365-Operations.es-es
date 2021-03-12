---
title: Procesamiento de diarios generales
description: Este tema describe las capacidades en Microsoft Dynamics 365 Finance que pueden facilitar el proceso del diario general y que también puede ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno.
author: ShylaThompson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd854b2188b07830e5641ccdd4bb02804a07b55c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975642"
---
# <a name="general-journal-processing"></a>Procesamiento de diarios generales

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades que pueden facilitar el proceso del diario general y que también puede ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno.  

## <a name="journal-names"></a>Nombres de diarios

Una de las áreas más importantes para configurar es los nombres de diario. Conviene definir los nombres de diario específicos para cada propósito, como empresas vinculadas, ajuste de acumulación y corrección de error. Puede ajustar cada nombre de diario para que la entrada de datos para cada propósito sea sencilla y segura. 

En la página **Nombres de diario**, puede configurar los siguientes elementos:

-   **Aprobación de flujo de trabajo:** para mejorar el control interno, defina los flujos de trabajo de diarios que establecen los límites de los pasos para su revisión y aprobación, en función de criterios como importe de débito total. Debe configurar los flujos de trabajo para los diarios generales en la página **Flujos de trabajo de contabilidad general**.
-   **Valores predeterminados:** seleccione valores predeterminados para cuentas de contrapartida, divisa y dimensiones financieras.
-   **Control del diario:** puede configurar las restricciones en la empresa y el tipo de cuenta, y también los valores de segmento. 

**Ejemplos**

Un nombre de diario también se puede usar solo para ajustes. En este caso, puede especificar que solo el tipo de cuenta **Libro mayor** es válido en todas las empresas. 

[![Tipos de cuenta de control de diarios](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Un nombre de diario solo se puede usar para un segmento específico o para un intervalo para las cuentas principales. 

[![Segmento de control de diarios](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

La opción **Inversión automática** solo está disponible en los diarios generales. Por ejemplo, tiene un ajuste de acumulación donde el documento real aún no se ha procesado, como se muestra en la siguiente ilustración.
[![Inversión del diario general](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

El complemento de Microsoft Excel para el movimiento del diario proporciona un nivel adicional de automatización y hace que la entrada de datos sea más fácil. La acción **Líneas abiertas en Excel** está disponible en las páginas del **Diario general** y **Asiento del diario** . 

En la página **Diarios periódicos**, puede configurar los diarios periódicos para automatizar el proceso de diario. 

Puede usar plantillas de asientos en cualquier momento. En la página **Diarios generales**, las acciones **Guardar** y **Seleccionar la plantilla de asientos** se encuentran en la página **Asiento del diario**, en **Funciones** para las líneas de asientos.

## <a name="related-setup"></a>Configuración relacionada
La configuración siguiente no es específica para los diarios generales, pero ayudará a asegurarse de que la entrada de datos sea correcta y fácil.

### <a name="main-account"></a>Cuenta principal

La configuración de la cuenta principal ofrece muchas opciones para el proceso del diario general:

-   **Requisito de DC/CR:** use esta opción si una cuenta principal está limitada a las transacciones de débito o crédito. Se comprueba la configuración cuando se valida o se registra un diario.

-   **Cuenta de contrapartida predeterminada**
-   **Suspendida:** suspenda una cuenta principal para la entrada de datos en todas las empresas o para una empresa o entidad jurídica específicas.
-   **No permitir entrada manual:** evitar que los usuarios especifiquen manualmente un valor para la cuenta en los diarios.
-   **Validar divisa o predeterminada**
-   **Anulación de la entidad jurídica:** esta configuración es específica a la empresa o a entidad jurídica definidas:
    -   **Validar impuestos o predeterminados**
    -   **Dimensión predeterminada**: **Valor no fijo** o **Valor fijo**. **Valor fijo** le ayudará a asegurarse de que todos los registros para esta cuenta principal usan siempre un valor de dimensión que está configurado como **Fijo**.
-   **Validación del registro**
    -   **Validación de usuario:** esta opción controla qué usuarios pueden registrar en una cuenta principal.
    -   **Validación de tipo de registro:** esta opción controla qué tipos de registro se premiten en una cuenta principal.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Estructuras contables y estructuras de reglas avanzadas

Las estructuras contables y las estructuras de reglas avanzadas son muy importantes para asegurarse de que los datos necesarios para los informes financieros y el seguimiento del rendimiento se capturen durante el proceso del diario general y la documentación. Las estructuras contables y las estructuras de reglas avanzadas le permiten adaptar la experiencia de entrada de datos. Puede permitir la entrada de datos solo para las dimensiones financieras que son relevantes en cada situación, y también puede exigir el requisito de que los datos obligatorios y correctos se capturen siempre.

Para obtener más información, consulte los siguientes temas:
- [Planificar su plan de cuentas](plan-chart-of-accounts.md) 
- [Crear reglas avanzadas para diarios](tasks/create-advanced-rules-journals.md)
- [Creación de un movimiento de diario mediante una plantilla](tasks/create-journal-entry-template.md)
- [Crear y validar diarios](tasks/create-validate-journals.md)
- [Registrar diarios periódicos](tasks/post-periodic-journals.md)
- [Procesar diario de asignaciones contables](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Simular registro
Puede encontrar **Simular registro** en el menú **Validar** para la mayoría de los diarios. Cuando se valida un diario mediante la función **Validar**, el sistema prueba el diario para detectar condiciones de error específicas. Si utiliza la función **Simular registro**, el sistema ejecuta todos los mismos procesos que se ejecutan a durante el registro sin registrar realmente el diario. A continuación puede revisar los mensajes de registro que se muestran, corregir todos los errores que encuentre y abrir el menú **Registrar** para registrar el diario. 

**Simular el registro** no está disponible para el procesamiento por lotes. Sin embargo, hay un código disponible para simular el registro en lote y los desarrolladores pueden ampliar el código para agregar dicha funcionalidad.  

## <a name="journal-unlock"></a>Desbloquear el diario
Un botón está disponible en la página del diario para desbloquear los diarios con un estado de "bloqueado por el sistema" establecido en Sí. Este desbloqueo lo puede realizar un administrador del sistema que haya analizado y ejecutado trabajo por lotes y confirmado que este diario ya está siendo procesado activamente por un trabajo por lotes. Este botón solo habilita la función denominada **Botón de desbloqueo de diario** en la página **Administración de características**. 

## <a name="workflow-recall"></a>Recuperación del flujo de trabajo 
La capacidad de recuperar un diario en un flujo de trabajo que tiene un estado de “irrecuperable” se habilita usando el botón **Flujo de trabajo** en un diario y en la página **Historial de flujo de trabajo**. Esto se habilita mediante la característica denominada **Restablecer el estado del flujo de trabajo para los diarios** en la página **Administración de características**.

## <a name="delete-journal-lines"></a>Eliminar líneas de diario
La capacidad de eliminar todas las líneas del diario se habilita rápidamente en un diario en **Funciones** > **Eliminar las líneas de diario**. Para habilitar esta característica, en **Administración de características**, seleccione **Eliminar otimizaciones de rendimiento del diario**.
