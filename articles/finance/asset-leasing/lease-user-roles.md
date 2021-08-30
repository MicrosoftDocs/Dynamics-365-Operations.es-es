---
title: Asignar roles de usuario de arrendamiento
description: Este tema describe los roles de seguridad que se utilizan en el arrendamiento de activos. También explica cómo asignar usuarios a esos roles.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7a3443cf9fa5b14ac0b3c4560ed45874939aa50cd665f4db46290f5af04bf6ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771761"
---
# <a name="assign-lease-user-roles"></a>Asignar roles de usuario de arrendamiento

[!include [banner](../includes/banner.md)]

Este tema describe los roles de seguridad que se utilizan en el arrendamiento de activos. También explica cómo asignar usuarios a esos roles.

Tres roles de usuario diferencian el acceso en el arrendamiento de activos. Un rol es apropiado para mantener arrendamientos, otro es apropiado para ver arrendamientos y otro es apropiado para realizar las tareas de un empleado de la sección de arrendamientos. Cada rol tiene permisos específicos para todas las páginas de arrendamiento y cada uno permite a los usuarios ver, crear, editar o eliminar arrendamientos, de acuerdo con sus deberes laborales.

| Función           | Descripción |
|----------------|-------------|
| Mantener arrendamiento | Los usuarios en este rol pueden agregar, editar, eliminar y ver arrendamientos. Esta función está diseñada para usuarios diarios cuyas tareas incluyen la creación y registro de movimientos de diario mensuales y la adición de nuevos arrendamientos. Este rol da acceso a todas las funciones de arrendamiento de activos. |
| Ver arrendamiento     | Los usuarios con este rol solo pueden ver registros de arrendamiento, programas y ejecutar informes. No pueden crear nuevos arrendamientos, editar arrendamientos existentes ni crear movimientos de diario contra arrendamientos. El rol está diseñado para usuarios que solo tienen que ver los arrendamientos, las programaciones de arrendamientos y las transacciones que ocurren con esos arrendamientos. |
| Empleado administrativo de arrendamientos    | Los usuarios con este rol solo pueden crear nuevos arrendamientos. No pueden editar ni eliminar arrendamientos existentes, ver programaciones de arrendamientos ni registrar entradas de diario de arrendamientos. Este rol está diseñado para usuarios que trabajan en una capacidad de entrada de datos. |

Siga estos pasos para asignar usuarios a los roles que se utilizan en el arrendamiento de activos.

1. Vaya a **Administración del sistema \> Seguridad \> Asignar usuarios a roles**.
2. Seleccione el rol **Mantener arrendamiento**, **Empleado de sección de arrendamientos** o **Ver arrendamiento** y luego seleccione **Asignar/excluir usuarios manualmente**.
3. Seleccione el usuario para asignar al rol y luego seleccione **Asignar a rol**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
