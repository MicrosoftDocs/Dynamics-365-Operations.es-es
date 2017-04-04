---
title: Budget planning justification documents
description: "Los documentos de justificación proporcionan una narrativa para las que se aplican un presupuesto para explicar por qué un presupuesto específico es necesario."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Budget planning justification documents

Los documentos de justificación proporcionan una narrativa para las que se aplican un presupuesto para explicar por qué un presupuesto específico es necesario. 

Una plantilla del plan del presupuesto crea el director de presupuestos en Microsoft Word y asignada al proceso de planificación actual del presupuesto. Presupueste los propietarios continuación puede abrir la plantilla y tener datos rellenar automáticamente en la palabra basada en la solicitud de presupuesto. Entonces podrán agregar texto adicional o datos antes de guardado y de adjuntar el documento personalizado de justificación a su plan del presupuesto.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Complemento de instalación de la oficina de Microsoft Dynamics for Microsoft Word

1.  Abra un nuevo documento de Microsoft Word.
2.  Haga clic en ** Insert ** en la cinta de opciones, y haga clic en ** ** almacén.
3.  Busca el complemento de la oficina de Microsoft Dynamics y clic ** agregue **.
4.  En Word, en el panel derecho, haga clic ** agregar información del servidor **.
5.  Escriba o pegue la dirección URL del servidor y haga clic en ** éste **.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definir la plantilla de justificación en Microsoft Word

1.  Haga clic en diseño ** ** en el complemento de la oficina de Microsoft Dynamics después de que haya iniciado sesión.
2.  Para obtener información de encabezado, utilice ** agregue los campos ** el botón.
3.  Seleccione el origen de datos de la entidad de BudgetPlanJustification, y haga clic en Siguiente ** **. ** Nota: ** Son necesarios para esta entidad los documentos de la justificación. Otras entidades pueden ser utilizadas pero la carga de nuevo en Microsoft Dynamics 365 para las operaciones fallará si esta entidad no se incluye.
4.  Agregue el BudgetPlanName, el BudgetPlanPreparer, el ResponsibilityCenter, y las etiquetas y los valores de DocumentNumber en el documento de Word. ** Nota: ** Puede usar sus propias etiquetas personalizadas, en lugar de las etiquetas estándar, si es necesario.
5.  Haga clic en ** hecho ** para completar la sección de cabecera.
6.  Para el detalle de nivel de línea de los importes del plan del presupuesto, haga clic ** agregue la tabla **.
7.  Una vez más seleccionar el origen de datos de la entidad de BudgetPlanJustification, y haga clic en Siguiente ** **.
8.  Agregue campos para EffectiveDate, ScenarioName, AccountDisplayValue, y AccountingCurrencyExpenseAmount. ** Nota: ** Si los comentarios están disponibles agregar dentro de las líneas individuales del plan del presupuesto, la se pueden agregar a la tabla aquí.
9.  Agregue la instrucción adicional de proporcionar al usuario final, y realizar cualquier formato necesario diseñar o al documento.
10. Guarde el documento a su equipo local y cerrar el archivo antes de continuar.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Configurar el proceso de planificación presupuestaria para usar la plantilla de la justificación

1.  En Microsoft Dynamics 365 para las operaciones, vaya ** presupuestaria ** &gt; ** la configuración ** &gt; ** presupuesto planificado ** &gt; ** las plantillas de documento de la justificación **.
2.  Haga clic en ** nuevo ** exploración y en el documento de Microsoft Word recién creado.
3.  Especifique un nombre para mostrar y una descripción de la plantilla. Click **OK**.
4.  Vaya a la gestión presupuestaria ** ** &gt; ** la configuración ** &gt; ** presupuesto ** ** planificado ** &gt; ** proceso de planificación presupuestaria **.
5.  Seleccione el proceso en la plantilla de justificación debe ser utilizada, y haga clic en ** ** edición.
6.  En ** plantilla de documento de la justificación ** campo, seleccione la plantilla y Guardar adecuadas.

##### <a name="edit-and-save-personalized-justification-documents"></a>La edición y Guardar personalizaron documentos de justificación

1.  En Dynamics 365 para las operaciones, cree un nuevo plan de presupuesto o abra un plan existente de presupuesto.
2.  En ** justificación ** el menú desplegable, seleccione ** crear nueva justificación **.
3.  Después de rellenar en los detalles, seleccione para cargar el documento personalizado ** justificación ** de menú desplegable.



