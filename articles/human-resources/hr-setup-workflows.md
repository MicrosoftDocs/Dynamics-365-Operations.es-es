---
title: Utilizar flujos de trabajo para administrar la información sobre los empleados
description: Este artículo explica cómo puede utilizar la capacidad del flujo de trabajo para que Recursos Humanos administre la información sobre los empleados. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación que se inicia cuando los empleados cambian su registro.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b637186e8ab43378e9d7f0fd3b8e7d7415c21cc2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010493"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utilizar flujos de trabajo para administrar la información sobre los empleados

Este artículo explica cómo puede utilizar la capacidad del flujo de trabajo para que Recursos Humanos administre la información sobre los empleados. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación que se inicia cuando los empleados cambian su registro.

La capacidad del flujo de trabajo para Recursos Humanos proporciona numeroso flujos de trabajo para gestionar actividades de Recursos Humanos. Asimismo, hay numerosas opciones disponibles para que pueda modificar flujos de trabajo específicos y asociarlos a una jerarquía de informes. Los flujos de trabajo están disponibles para ayudar a gestionar cambios a varios tipos estándar de información sobre los empleados. Puede asociar un flujo de trabajo a un puesto. A continuación, si los empleados cambian su registro de empleado, se inicia un flujo de trabajo que requiere aprobación antes de que se guarde la nueva información. Los flujos de trabajo están predefinidos para los siguientes tipos de información para ayudarle a gestionar de manera eficiente los cambios y mantener preciosos los datos de sus empleados:

-   Números de identificación
-   Cursos
-   Formación
-   Imagen
-   Artículos prestados
-   Experiencia profesional
-   Experiencia en proyectos
-   Aptitudes
-   Puestos de confianza
-   Acciones de recursos humanos
-   Registro del curso

Cuando se contrata, transfiere o despide a empleados, el flujo de trabajo puede incluir un proceso de revisión. De esta manera, se puede revisar un documento o se puede definir una acción como parte del flujo de trabajo. Cuando se completa el proceso de revisión, se completa el documento o la acción, y el flujo de trabajo se mueve a un paso de aprobación final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Asociar un flujo de trabajo a una jerarquía de puestos
Puede asociar un flujo de trabajo con cualquier jerarquía que configure. Por ejemplo, si un puesto está asociado a una jerarquía de informes de matriz, puede configurar un flujo de trabajo que distribuye los gastos para un proyecto específico al cliente potencial del proyecto en lugar de al director del empleado asociado a ese puesto. Para crear un nuevo flujo de trabajo o modificar un flujo de trabajo existente, en la página **Flujo de trabajo de recursos humanos**, haga clic en **Nuevo**. Seleccione un flujo de trabajo en la lista para iniciar al diseñador de flujo de trabajo. Puede usar al diseñador para crear un nuevo flujo de trabajo o para cambiar los pasos de un flujo de trabajo existente. Al cambiar un flujo de trabajo existente, los cambios se guardan como una nueva versión. Por lo tanto, siempre puede volver a una versión anterior si es necesario.

## <a name="configure-a-human-resources-workflow"></a>Configurar un flujo de trabajo de las acciones de recursos humanos
Siga estos pasos para configurar un flujo de trabajo básico que se inicia cuando la solicitud de los empleados cambia a su identificación personal.

1.  En la página **Flujos de trabajo de recursos humanos**, haga clic en **Nuevo**.
2.  En la lista de flujos de trabajo disponibles, seleccione **Números de identificación**.
3.  Haga clic en **Ejecutar** para iniciar al diseñador de flujo de trabajo y, a continuación, introduzca su nombre de usuario y contraseña cuando se le solicite.
4.  Arrastre el elemento **Aprobar número de identificación** de la lista de elementos de flujo de trabajo al lienzo de diseñador.
5.  Conecte el elemento de aprobación para **Empezar** y **Finalizar**.
6.  Haga doble clic en **Aprobar elemento** y, a continuación, haga clic con el botón secundario y seleccione **Propiedades**.
7.  Siga estos pasos para agregar las instrucciones del elemento de trabajo:
    1.  Seleccione **Asignación** y, a continuación, seleccione **Jerarquía** en el tipo de asignación.
    2.  En la selección **Jerarquía**, seleccione **Jerarquía configurable**.
    3.  Agregue una condición de detención y cierre la página.

8.  Complete cualquier instrucción adicional (no debe haber advertencias adicionales).
9.  Haga clic en **Guardar y cerrar**. Active el nuevo flujo de trabajo cuando se abra el cuadro de diálogo, y seleccione **Activar**.
10. Vaya a **Recursos Humanos** &gt; **Puestos** &gt; **Tipos de jerarquías de puestos**
11. Seleccione **Matriz**.
12. Agregue el flujo de trabajo **Número de identificación de trabajador** a la lista.




