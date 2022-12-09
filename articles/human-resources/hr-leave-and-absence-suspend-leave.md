---
title: Suspender un permiso
description: Puede suspender un permiso para un empleado en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805270"
---
# <a name="suspend-leave"></a>Suspender baja

>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede suspender un permiso para que un empleado deje de acumular permisos para los tipos de permiso seleccionados.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Suspender permisos y ausencias para un empleado

1. En el registro del empleado, seleccione **Baja**.

2. Seleccione **Suspender permiso**.

3. Seleccione **Nuevo**.

4. En el cuadro de diálogo **Suspender acumulación de permiso**, seleccione el **Tipo de permiso** junto con la **Fecha inicial** y **Fecha final** para la suspensión.

5. Opcionalmente, puede agregar un **Comentario** para la suspensión. 

Si las acumulaciones se procesan mientras se suspende el permiso del empleado, no se realizará ninguna acumulación para los tipos de permiso suspendido.

> [!NOTE]
> Las solicitudes de permiso de ausencia suspenderán las solicitudes de tiempo libre, pero las solicitudes de tiempo libre no suspenderán las solicitudes de permiso de ausencia.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Configurar tipos de bajas y ausencias](hr-leave-and-absence-types.md)
- [Acumular planes de permisos y ausencias](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
