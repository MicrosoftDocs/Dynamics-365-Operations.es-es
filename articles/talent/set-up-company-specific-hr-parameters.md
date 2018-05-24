---
title: "Configuración de los parámetros de recursos humanos específicos de la empresa"
description: "La configuración de algunos parámetros de Recursos Humanos (RR. HH.) se comparten entre empresas, mientras que la configuración de otros parámetros son específicos de la empresa. Este artículo explica cómo configurar parámetros de RR. HH. específicos de la empresa."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HRMParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e195f9976465a933ceaaeb0bd2cbec4f814bc5f8
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-company-specific-hr-parameters"></a>Configuración de los parámetros de recursos humanos específicos de la empresa

[!include [banner](includes/banner.md)]

La configuración de algunos parámetros de Recursos Humanos (RR. HH.) se comparten entre empresas, mientras que la configuración de otros parámetros son específicos de la empresa. Este artículo explica cómo configurar parámetros de RR. HH. específicos de la empresa.

Se usan dos páginas para definir los parámetros de recursos humanos. Para los parámetros que se comparten entre las empresas, se usa la página **Parámetros compartidos de recursos humanos**. Para los parámetros que son específicos de la empresa (es decir, los ajustes se aplican a una sola empresa), se usa la página **Parámetros de recursos humanos**. En la página **Parámetros de recursos humanos**, los ajustes se dividen en seis pestañas:

-   General
-   Contratación: esto no se incluye en Dynamics 365 for Talent
-   Compensación
-   Secuencias numéricas
-   Ley de Ausencia Familiar y Médica
-   Autoservicio para empleados

Cada pestaña contiene información que pertenece a una sola empresa. Los ajustes en la pestaña **General** definen el aspecto de la información acerca de ausencia, lesión y enfermedad, y los nuevos trabajadores. Los ajustes de esta pestaña también definen algunas entradas predeterminadas que aparecen mientras trabaja. Concretamente, esta pestaña permite seleccionar un color que aplicará a las transacciones de ausencia abiertas, especificar la hoja de estilo que se debe usar para los informes y habilitar la integración entre los cursos de aprendizaje y el registro de ausencias, y seleccionar el código de ausencia que se usa para controlar esta integración. También puede indicar cuánto tiempo se deben guardar los incidentes de lesión y enfermedad, y especificar el número de identificación predeterminado que se muestra al contratar a un nuevo trabajador. 

Los ajustes en la pestaña **Contratación** definen los tipos de documento que se usan para la correspondencia que se envía automáticamente a los candidatos, y el proyecto de contratación que se usa para las solicitudes no solicitadas (solicitudes que no son para un proyecto de contratación específico). El período definido para el vencimiento del proyecto de contratación determina los proyectos de contratación que se incluyen en el título **Proyectos en vencimiento** en el espacio de trabajo **Gestión de contratación**. El período definido para la advertencia del plazo de solicitud se usa para mostrar los proyectos de contratación que se están acercando al plazo de la solicitud en el mosaico **Se acerca el plazo de la solicitud** en el espacio de trabajo **Contratación**. 

Los ajustes en la pestaña **Compensación** definen si los usuarios deben confirmar que desean guardar la información de un plan fijo o de compensación variable. Si activa la casilla **Habilitar guardar la validación** , siempre que los usuarios cierran una página relacionada con la compensación, reciben un mensaje que les pregunta si desean guardar el registro. Algunas páginas en la gestión de compensación no permiten a los usuarios eliminar la información. Por tanto, al preguntar al usuario que verifique que desea guardar información, podría ser capaz de limitar el importe de información que se guarda pero, por otro lado, no se podrá eliminar posteriormente. Si la casilla **Habilitar guardar validación** se desactiva, los registros se guardan siempre inmediatamente, probablemente antes de que el usuario esté listo. Si se usa la gestión de rendimiento, la pestaña **Compensación** también le permite seleccionar un modelo de tasación para usarlo en lugar del modelo que está asignado a los planes de compensación al evaluar el rendimiento. 

### <a name="previously-released-functionality"></a>Funcionalidad anteriormente liberada
Los ajustes en la pestaña **Secuencia numérica** determina las secuencias que se usarán para asignar automáticamente identificadores a elementos de recursos humanos, como solicitudes, registros de ausencias, resultados de procesos de compensación, números de casos, cursos y programaciones de cursos. Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas** (haga clic en **Administración de la organización** &gt; **Secuencias numéricas** &gt; **Secuencias numéricas**).

### <a name="if-youre-using-dynamics-365-for-talent"></a>Si utiliza Dynamics 365 for Talent
Los ajustes en la pestaña **Secuencia numérica** determina las secuencias que se usarán para asignar automáticamente identificadores a elementos de recursos humanos, como solicitudes, registros de ausencias, resultados de procesos de compensación, números de casos, cursos y programaciones de cursos. Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas** (haga clic en **Administración del sistema** &gt; **Ficha Vínculos** &gt; **Secuencias numéricas** &gt; **Secuencias numéricas**). 

Los ajustes en la pestaña **FMLA** definen el número de horas que debe trabajar un empleado para que se puedan aplicar las prestaciones de FMLA, la duración del empleo que se requiere para la idoneidad y la fecha de inicio del empleo que se usa para determinar la duración del empleo. Los parámetros también definen el número de horas de FMLA al que tienen derecho los empleados y el calendario de ausencias de FMLA que se usa para calcular cuántas horas de FMLA han usado los empleados. La pestaña **FMLA** solo está disponible para las empresas en los Estados Unidos. 

**Nota:** el número de horas que se trabaja no puede superar 1.250, y la duración del empleo no puede superar 12 meses. Estos valores máximos están de acuerdo con la legislación federal en los Estados Unidos. Finalmente, los ajustes en la pestaña **Autoservicio del empleado** determinan la información que un director puede especificar en nombre de sus empleados.

<a name="additional-resources"></a>Recursos adicionales
--------

[Configurar parámetros de recursos humanos en entidades jurídicas](set-up-hr-parameters-across-legal-entities.md)




