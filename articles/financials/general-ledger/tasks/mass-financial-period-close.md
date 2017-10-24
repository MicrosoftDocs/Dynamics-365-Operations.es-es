--- 
title: "Cierre masivo de período financiero"
description: "Este procedimiento muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d7151cbcd02f9312ca6b0de5e27231a0b0dc9d6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="mass-financial-period-close"></a>Cierre masivo de período financiero

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo. Además, la tarea mostrará cómo restringir el registro del grupo de usuarios a módulos específicos.

1. Vaya a Contabilidad general > Cierre de período > Calendarios del libro mayor.
    * Tenga en cuenta que la lista de entidades jurídicas presentadas depende del calendario fiscal seleccionado en la página. Solo se mostrarán las entidades jurídicas que usan el calendario fiscal seleccionado.  
2. Haga clic en Editar.
3. Seleccione el período para el que desee modificar el estado.
4. Seleccione las entidades legales para las que desee actualizar el estado.
    * Puede seleccionar rápidamente todas las entidades jurídicas seleccionando la marca de verificación en la parte superior izquierda de la cuadrícula.  
5. Seleccione Actualizar acceso al módulo para definir el acceso de registro a un módulo seleccionado.
    * El estado del módulo también puede actualizarse uno por uno editando los registros de la cuadrícula. El botón es útil si desea actualizar rápidamente múltiples registros de la entidad jurídica.  
6. En el módulo Aplicación, seleccione el módulo del que desea actualizar el estado. Haga clic en Seleccionar.
7. En el nivel Acceso, seleccione Todos, Ninguno o un grupo de usuarios específico. Haga clic en Seleccionar.
    * Todo indica que todos los usuarios con acceso de edición al módulo pueden registrar si el período está abierto. Ninguno indica que los usuarios no pueden registrar en el módulo si el período está abierto. Un grupo de usuarios específico indica que solo los usuarios del grupo pueden registrar en el módulo si el período está abierto.  
8. Haga clic en Actualizar.
9. Seleccione otro período para actualizar el estado.
10. Seleccione las entidades legales para las que desea actualizar el estado del período.
11. Seleccione Actualizar estado del período y establezca el estado En espera, Abierto o Cerrado de forma permanente.
    * Abierto indica el período en el que se puede registrar, siempre que el usuario tenga acceso. En espera significa que el período no se pueden registrar, pero el período se puede volver a abrir. Cerrado de forma permanente significa que el período está cerrado y no se puede abrir nunca. No se pueden registrar ajustes. No se recomienda establecer un período como Cerrado de forma permanente hasta que se completen todos los ajustes y las auditorías.  
12. Haga clic en Actualizar.


