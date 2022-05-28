---
title: Contratar a empleados existentes a través de la contratación
description: A veces las vacantes se pueden ocupar por candidatos que ya son empleados de la organización.
author: twheeloc
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 07dae424f32281a39c3887437ac7976fb3beb8d3
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734934"
---
# <a name="hire-existing-employees-through-recruitment"></a>Contratar a empleados existentes a través de la contratación

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> La funcionalidad de contratación en este tema se denominará Proyectos de contratación y se centra en los solicitantes, las solicitudes y los proyectos de contratación.  


A veces, las vacantes se pueden ocupar por candidatos que ya son empleados de la organización. Este procedimiento le muestra los pasos para contratar a un empleado existente a través del proceso de contratación. En este procedimiento, ya hay configurado un proyecto de contratación, y un empleado existente ha enviado ya una solicitud para el proyecto de contratación. Para crear este procedimiento se utiliza la empresa de datos de prueba **USMF**.

1. Vaya a **Recursos humanos \> Contratación \> Solicitudes \> Solicitudes**.
2. En la lista, localice la solicitud del empleado que quiere contratar. Por ejemplo, seleccione **00002 John Emory**.
3. Seleccione **Estado de solicitud**.

    El estado de la solicitud indica el punto del proceso de contratación en el que se encuentra la solicitud. Cada paso es opcional. Normalmente, una solicitud pasaría por diferentes estados en el siguiente orden: **recibido**, **confirmado** y **entrevistado**. Después del proceso de entrevista, se tomará una decisión de contratación.

4. Seleccione **Cambiar puesto**.
5. Seleccione el puesto para el que va a contratar al empleado.
6. En el campo **Fecha de inicio de la nueva asignación**, escriba la fecha en la que el empleado empezará a trabajar en el puesto nuevo.
7. En el campo **Fecha de finalización de asignación**, escriba la fecha en la que el empleado dejará de trabajar en su puesto actual.

    La fecha de inicio para el nuevo puesto y la fecha de finalización del puesto anterior se pueden superponer. Esta superposición puede suceder si una persona está realizando tareas en ambos puestos durante un período de transición.

8. Opcional: seleccione un código de motivo. Por ejemplo: seleccione **Reorganización**.
9. Seleccione **Cambiar puesto**.

    Ahora, también puede cambiar la compensación. Si no lo hace, puede cambiarla más tarde seleccionando **Plan fijo** en la pestaña **Compensación** de la página **Trabajador**.

    Tras seleccionar **Cambiar puesto**, el estado de la solicitud se actualizará a **Empleado**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
