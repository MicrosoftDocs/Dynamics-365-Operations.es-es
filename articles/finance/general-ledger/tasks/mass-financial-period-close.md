---
title: Cierre masivo de período financiero
description: En este artículo se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo.
author: aprilolson
ms.date: 11/16/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a85d512842b27f2d74507be16a8f2819f483e0d
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779836"
---
# <a name="mass-financial-period-close"></a>Cierre masivo de período financiero

[!include [banner](../../includes/banner.md)]

En este artículo se muestra cómo configurar un período en espera o cerrar de forma permanente un período o más de una entidad jurídica al mismo tiempo. Además, la tarea mostrará cómo restringir el registro del grupo de usuarios a módulos específicos.

1. En el panel de navegación, vaya a **Contabilidad general > Cierre de período > Calendarios del libro mayor**. 

>[!NOTE]
> La lista de entidades jurídicas presentadas depende del calendario fiscal seleccionado en la página. Solo se mostrarán las entidades jurídicas que usan el calendario fiscal seleccionado.

2. Seleccione **Editar**.
3. Seleccione el período para el que desee modificar el estado.
4. Seleccione las entidades legales para las que desee actualizar el estado. Puede seleccionar rápidamente todas las entidades jurídicas seleccionando la marca de verificación en la parte superior izquierda de la cuadrícula.  
5. Seleccione **Actualizar acceso al módulo** para definir el acceso de registro a un módulo seleccionado. El estado del módulo también puede actualizarse uno por uno editando los registros de la cuadrícula. El botón es útil si desea actualizar rápidamente múltiples registros de la entidad jurídica.  
6. En el módulo **Aplicación**, seleccione el módulo del que desea actualizar el estado. Haga clic en **Seleccionar**.
7. En el nivel **Acceso**, seleccione **Todos**, **Ninguno** o un grupo de usuarios específico. Haga clic en **Seleccionar**.  
- **Todos**: todos los usuarios con acceso de edición al módulo pueden registrar si el período está abierto. 
- **Ninguno**: los usuarios no pueden registrar en el módulo si el período está abierto. Un grupo de usuarios específico indica que solo los usuarios del grupo pueden registrar en el módulo si el período está abierto.  
8. Seleccione **Actualizar**. 
9. Seleccione otro período para actualizar el estado.
10. Seleccione las entidades legales para las que desea actualizar el estado del período.
11. Seleccione **Actualizar estado del período** y establezca el estado **En espera**, **Abierto** o **Cerrado de forma permanente**. **Abierto** indica el período en el que se puede registrar, siempre que el usuario tenga acceso. **En espera** significa que el período no se puede registrar, pero se puede volver a abrir. **Cerrado de forma permanente** significa que el período está cerrado y no se puede abrir nunca. No se pueden registrar ajustes. No se recomienda establecer un período como **Cerrado de forma permanente** hasta que se completen todos los ajustes y las auditorías.  
12. Seleccione **Actualizar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
