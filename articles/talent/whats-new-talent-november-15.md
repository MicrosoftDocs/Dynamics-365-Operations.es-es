---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (15 de noviembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a7598db1dc4c11864cf5f5a73d00672ceb66e8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462465"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-15-2018"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (15 de noviembre de 2018)

**Compilación 8.1.2045**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="other-changesfixes"></a>Otros cambios/correcciones

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Incapaz de cambiar el puesto actual del empleado por una vacante futura

Un cambio se ha realizado para habilitar las transferencias de puesto cuando el puesto sólo está disponible en el futuro. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>El puesto no muestra al crear un nuevo empleado

Un cambio se ha realizado para mostrar todas las vacantes que están disponibles para su asignación cuando se contratan nuevos empleados en Talent. Esto incluye puestos históricos o si los puestos se han fechado en el futuro. Los puestos ahora aparecerán correctamente según la fecha de inicio del empleo. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>La fecha final se muestra en función de la configuración del usuario

Un cambio se ha realizado en la última lista de los empleados del pasado para explicar cualquier desplazamiento horario de la zona horaria preferida de los empleados cuando se visualiza la fecha final.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Los enlaces de elementos de trabajo que se me asignan no contienen la información correcta

Con este cambio, la navegación a los detalles de los elementos de trabajo individuales en la lista mostrarán la información correcta para el elemento seleccionado. Este problema solo se producía con opciones de seguridad avanzadas.


## <a name="known-issue"></a>Problema conocido

- **Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan. 
- **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
