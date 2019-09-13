---
title: Cierre masivo de período financiero
description: En este tema se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 398a62e575010501291af3016553fc72fbc891de
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914639"
---
# <a name="mass-financial-period-close"></a>Cierre masivo de período financiero

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo. Además, la tarea mostrará cómo restringir el registro del grupo de usuarios a módulos específicos.

1. En el panel de navegación, vaya a **Módulos > Contabilidad general > Cierre de período > Calendarios del libro mayor**. Tenga en cuenta que la lista de entidades jurídicas presentadas depende del calendario fiscal seleccionado en la página. Solo se mostrarán las entidades jurídicas que usan el calendario fiscal seleccionado.
2. Seleccione **Editar**.
3. Seleccione el período para el que desee modificar el estado.
4. Seleccione las entidades legales para las que desee actualizar el estado. Puede seleccionar rápidamente todas las entidades jurídicas seleccionando la marca de verificación en la parte superior izquierda de la cuadrícula.  
5. Seleccione **Actualizar acceso al módulo** para definir el acceso de registro a un módulo seleccionado. El estado del módulo también puede actualizarse uno por uno editando los registros de la cuadrícula. El botón es útil si desea actualizar rápidamente múltiples registros de la entidad jurídica.  
6. En el módulo **Aplicación**, seleccione el módulo del que desea actualizar el estado. Haga clic en **Seleccionar**.
7. En el nivel **Acceso**, seleccione **Todos**, **Ninguno** o un grupo de usuarios específico. Haga clic en **Seleccionar**. Todo indica que todos los usuarios con acceso de edición al módulo pueden registrar si el período está abierto. Ninguno indica que los usuarios no pueden registrar en el módulo si el período está abierto. Un grupo de usuarios específico indica que solo los usuarios del grupo pueden registrar en el módulo si el período está abierto.  
8. Seleccione **Actualizar**.
9. Seleccione otro período para actualizar el estado.
10. Seleccione las entidades legales para las que desea actualizar el estado del período.
11. Seleccione **Actualizar estado del período** y establezca el estado **En espera**, **Abierto** o **Cerrado de forma permanente**. **Abierto** indica el período en el que se puede registrar, siempre que el usuario tenga acceso. **En espera** significa que el período no se puede registrar, pero se puede volver a abrir. **Cerrado de forma permanente** significa que el período está cerrado y no se puede abrir nunca. No se pueden registrar ajustes. No se recomienda establecer un período como **Cerrado de forma permanente** hasta que se completen todos los ajustes y las auditorías.  
12. Seleccione **Actualizar**.

