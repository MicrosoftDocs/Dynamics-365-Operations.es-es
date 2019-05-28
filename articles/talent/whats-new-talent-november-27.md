---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (27 de noviembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 81ea0e4f4878d1967234c597504071ce464a22c5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519042"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-27-2018"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (27 de noviembre de 2018)

[!include [banner](includes/banner.md)]

**Compilación 8.1.2064**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.


## <a name="changes"></a>Cambios

### <a name="unable-to-create-a-note-in-case-management"></a>Incapaz de crear una nota en administración de casos

Un cambio se ha realizado para un problema que se produce al intentar editar o crear una nota en el registro de casos de la gestión de casos.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Palabra errónea en la ficha de análisis en el espacio de trabajo de la compensación 

Un cambio se ha efectuado para corregir la ortografía de “origen étnico” en el gráfico de análisis de compensación en el área de trabajo de compensación.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>El espacio de trabajo de Employee self-service no se muestra cuando no se ha asignado un usuario a un trabajador 

Se ha realizado un cambio cuando el área de trabajo de **Employee self-service** se selecciona como la página de inicio en el inicio para un usuario que no está asignado a un trabajador. En esta situación, el panel predeterminado se mostrará.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Error de la licencia y de ausencia: la referencia de objeto no está establecida en una instancia de un objeto

Se han realizado cambios en ausencias y bajas para corregir este error después de aprobar los registros de ausencias y bajas en el lista **Elementos de trabajo asignados a mí** .

### <a name="unable-to-recall-an-image-workflow"></a>Incapaz de volver a llamar a un flujo de trabajo de imagen

Tras recuperar un flujo de trabajo de la imagen, el flujo de trabajo se establecerá en "cancelado" y la solicitud existente se puede eliminar en el área de trabajo Employee Self-Service.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Los empleados o contratistas que se vuelven a contratar aparecen varias veces después de la finalización 

Con esta actualización, los empleados cesados que se vuelven a contratar solo se verán una vez en la lista de salidas. 

## <a name="known-issue"></a>Problema conocido

- **Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan. 
- **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
