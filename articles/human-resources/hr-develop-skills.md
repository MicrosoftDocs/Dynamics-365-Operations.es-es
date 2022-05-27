---
title: Configurar aptitudes
description: Puede realizar un seguimiento de las aptitudes de su trabajador en Dynamics 365 Human Resources. También puede especificar las aptitudes necesarias para un puesto concreto.
author: twheeloc
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7c853ad71aecd7f5d214c02da97f7956ff2391df
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695967"
---
# <a name="configure-skills"></a>Configurar aptitudes

> [!IMPORTANT]
> La funcionalidad mencionada en este tema está disponible actualmente para los clientes de Recursos Humanos en la infraestructura de Finanzas.  


Puede realizar un seguimiento de las aptitudes de su trabajador en Dynamics 365 Human Resources. También puede especificar las aptitudes necesarias para un puesto concreto.

Estos son ejemplos de aptitudes de las que se puede hacer un seguimiento:

- Supervisión: capacidad para supervisar el trabajo de los demás.
- Liderazgo: capacidad para dirigir empleados y dominios de empresa.
- Planificación: capacidad para anticipar las cosas, formar instrucciones de visiones de futuro y ponerlas en práctica.
- HTML: capacidad de escribir código HTML.

Si aún no ha configurado tipos de aptitudes y modelos de calificación, deberá agregar algunos antes de crear habilidades.

Las siguientes personas pueden ingresar aptitudes para un trabajador:

- Los trabajadores pueden introducir aptitudes por sí mismos en el autoservicio para empleados. Estas habilidades requieren la aprobación del gerente.
- Los gerentes pueden introducir aptitudes para sus trabajadores. Puede crear un flujo de trabajo que apruebe automáticamente estas aptitudes.

## <a name="create-a-skill-type"></a>Crear un tipo de aptitud

Los tipos de aptitudes son categorías a las que pertenecen las aptitudes individuales, como Administración o Ventas.

1. En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.

2. En **Configuración de competencias**, seleccione **Tipos de aptitudes**.

3. Seleccione **Nuevo**.

4. Complete los siguientes campos:

   - **Tipo de aptitud**: escriba un nombre para el tipo de aptitud.
   - **Descripción**: escriba una descripción para el tipo de aptitud.

5. Seleccione **Guardar**.

## <a name="create-a-rating-model"></a>Crear un modelo de evaluación

Los modelos de evaluación ayudan a evaluar el nivel de aptitud real de una persona, el nivel que deben trabajar para lograr o el nivel de aptitud necesario para un puesto. Cada nivel del modelo de clasificación tiene asignado un factor.

1. En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.

2. En **Configuración de competencias**, seleccione **Modelos de clasificación**.

3. Seleccione **Nuevo**.

4. Complete los siguientes campos:

   - **Clasificación**: introduzca un nombre para el modelo de clasificación, como **Aptitudes**.
   - **Descripción**: introduzca una descripción para el modelo de calificación, como **Calificaciones de aptitud**.

5. En la sección **Niveles** sección, seleccione **Nuevo**. Para cada nivel que desee agregar, complete los siguientes campos:

   - **Nivel**: escriba un nombre para el nivel.
   - **Descripción**: escriba una descripción del nivel.
   - **Factor**: introduzca un valor de factor de 0 a 9. Los factores le ayudan a normalizar las puntuaciones de aptitudes que utilizan distintos modelos de evaluación. Cada nivel debe tener un factor único. Los niveles con valores más altos de factor conllevan más peso en un modelo de evaluación.

   Continúe agregando niveles según sea necesario. Puede escribir hasta 10 niveles para cada modelo de evaluación.

6. Seleccione **Guardar**.

## <a name="create-a-skill"></a>Crear una aptitud

Antes de poder asignar una aptitud, crear una búsqueda de asignación de aptitudes o un perfil de aptitudes, debe especificar información sobre las aptitudes en la página **Aptitudes**. Para cada aptitud, puede seleccionar un tipo de aptitud y un modelo de evaluación.

1. En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.

2. En **Configuración de competencias**, seleccione **Aptitudes**.

3. Seleccione **Nuevo**.

4. Complete los siguientes campos:

   - **Aptitud**: escriba un nombre para la aptitud.
   - **Descripción**: escriba una descripción para la aptitud.
   - **Valoración**: seleccione el modelo de valoración que quiere usar para esta aptitud.
   - **Tipo de aptitud**: seccione de la lista de tipos de aptitudes.

5. Seleccione **Guardar**.

## <a name="see-also"></a>Consulte también

[Introducir aptitudes](hr-develop-enter-skills.md)<br>
[Asignar aptitudes](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
