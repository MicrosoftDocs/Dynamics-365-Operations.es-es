---
title: Tipos de inventario mezclados al usar un perfil de administración de muelles
description: Para que un perfil de administración del muelle administre de manera efectiva la mezcla de inventario, se debe configurar primero una pausa en el encabezado de trabajo. Esta página explica cómo hacerlo.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477508"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>Los tipos de inventario se mezclan al usar un perfil de administración de muelles

## <a name="symptoms"></a>Síntomas

Está usando *directivas de consolidación de envíos*. Ha configurado un *perfil de gestión del muelle* para *perfil de ubicación*, pero cuando se crea el trabajo, los tipos de inventario se mezclan en la ubicación final.

## <a name="resolution"></a>Resolución

Los perfiles de gestión de muelles requieren que el trabajo se divida por adelantado. En otras palabras, el perfil de administración del muelle espera que un encabezado de trabajo no tenga múltiples ubicaciones de colocación.

Para que el perfil de administración del muelle administre de manera efectiva la mezcla de inventario, se debe configurar una pausa en el encabezado de trabajo.

En este ejemplo, nuestro perfil de gestión de muelles está configurado de manera que **Tipos de inventario que no deben mezclarse** se establece en *Identificación del envío*, y configuraremos un descanso de encabezado de trabajo para ello:

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Seleccione el **Tipo de orden de trabajo** para editar (por ejemplo, *Ordenes de compra*).
1. Seleccione la plantilla de trabajo para editar.
1. En el panel Acciones, seleccione **Editar consulta**.
1. Abra la pestaña **Clasificación** y agregue una fila con la siguiente configuración:
    - **Tabla** - *Transacciones laborales temporales*
    - **Tabla derivada** - *Transacciones laborales temporales*
    - **Campo** - *Identificación del envío*
1. Seleccione **Aceptar**.
1. Regresa a la página **Plantillas de trabajo**. En el panel de acciones, seleccione **Saltos de encabezado de trabajo**.
1. En el panel Acciones, seleccione **Editar**.
1. Seleccione la casilla de verificación asociada con el **Nombre del campo** *Identificación del envío*.
1. En el panel Acciones, seleccione **Guardar**.
