---
title: "Flujos de trabajo de uso para gestionar la información de empleado"
description: "Este tema explica cómo puede usar la capacidad del flujo de trabajo para Recursos Humanos administrar la información de empleado. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación iniciada cuando los empleados cambian su registro."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Flujos de trabajo de uso para gestionar la información de empleado

Este tema explica cómo puede usar la capacidad del flujo de trabajo para Recursos Humanos administrar la información de empleado. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación iniciada cuando los empleados cambian su registro.

La capacidad del flujo de trabajo para los recursos humanos proporciona los flujos de trabajo numerosos gestionar actividades de recursos humanos. Además, las opciones que están disponibles para poder modificar flujos de trabajo específicos y asociarlos con una jerarquía de informes. Los flujos de trabajo están disponibles ayudar a gestionar cambios a varios tipos estándar de información de empleado. Puede asociar un flujo de trabajo a un puesto. A continuación, si los empleados cambian su registro de empleado, se inicia un flujo de trabajo que requiere aprobación antes de que se guarde la nueva información. Los flujos de trabajo están predefinidas para los siguientes tipos de información para ayudarle a gestionar eficientemente cambios y a mantener datos de sus empleados precisos:

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

Al contratar, se transfieren, o se finalizan a los empleados, el flujo de trabajo puede incluir un proceso de revisión. De esta manera, un documento puede revisar o los términos de una acción se pueden definir como parte del flujo de trabajo. Cuando el proceso de revisión se complete, el documento o la acción se complete, y el flujo de trabajo a un paso de aprobación final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Asociar un flujo de trabajo con una jerarquía de puestos
Puede asociar un flujo de trabajo con cualquier jerarquía que configure. Por ejemplo, si un puesto está asociado a una jerarquía de informes de matriz, es posible que configurar un flujo de trabajo que distribuye los gastos para un proyecto específico al cliente potencial del proyecto en lugar del director del empleado que está asociado a ese puesto. Para crear un nuevo flujo de trabajo o modificar un flujo de trabajo existente, en ** flujo de trabajo de recursos humanos ** la página, haga clic en ** ** nuevo. Seleccione un flujo de trabajo en la lista para iniciar al diseñador de flujo de trabajo. Puede usar al diseñador para crear un nuevo flujo de trabajo o para cambiar los pasos de un flujo de trabajo existente. Al cambiar un flujo de trabajo existente, los cambios se guardan como nueva versión. Por lo tanto, puede volver a siempre una versión anterior si es necesario.

## <a name="configure-a-human-resources-workflow"></a>Configuración de un flujo de trabajo de recursos humanos
Para configurar un flujo de trabajo básico iniciada cuando la solicitud de los empleados cambia a su identificación personal, siga estos pasos.

1.  En ** flujos de trabajo de recursos humanos ** la página, haga clic en ** ** nuevo.
2.  En la lista de flujos de trabajo disponible, seleccione ** los números de identificación **.
3.  Haga clic en ejecución ** ** para iniciar al diseñador de flujo de trabajo y, a continuación para especificar su nombre de usuario y contraseña cuando el sistema le solicite que.
4.  Arrastre ** apruebe el número de identificación ** el artículo de la lista de elementos de flujo de trabajo al lienzo de diseñador.
5.  Conectar inicio del elemento de aprobación ** ** y ** ** final.
6.  El doble clic ** apruebe el artículo ** y, a continuación haga clic con el botón secundario, seleccione y ** las propiedades **.
7.  Siga estos pasos para agregar instrucciones del elemento de trabajo:
    1.  Seleccione ** ** asignación y, a continuación ** jerarquía ** sujetos al tipo de asignación.
    2.  En ** jerarquía ** selección, seleccione ** jerarquía configurable **.
    3.  Agregar condición de detención, y cierre la página.

8.  Complete las instrucciones adicional (ninguna adicionales advertencias deben existir).
9.  Haga clic en **Guardar y cerrar**. Active el nuevo flujo de trabajo cuando abre el cuadro de diálogo, y seleccione ** crear activos **.
10. ** Van recursos humanos ** &gt; ** puestos ** &gt; ** los tipos de jerarquía de puestos **.
11. Seleccione ** ** matriz.
12. Agregar ** número de identificación del trabajador ** el flujo de trabajo a la lista.



