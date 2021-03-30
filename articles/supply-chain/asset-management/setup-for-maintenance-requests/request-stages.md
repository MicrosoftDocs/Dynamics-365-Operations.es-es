---
title: Estados de ciclo de vida de solicitud de mantenimiento
description: Este tema describe cómo configurar los estados de ciclo de vida de la solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9022d866bf0da08a72ba9169587f87c1b77527a6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217230"
---
# <a name="maintenance-request-lifecycle-states"></a>Estados de ciclo de vida de solicitud de mantenimiento

[!include [banner](../../includes/banner.md)]

 


Los estados de ciclo de vida de solicitud de mantenimiento definen las etapas por las que puede pasar una solicitud. Los ejemplos incluyen **Creada**, **Activa** y **Finalizada**. Cuando una solicitud de mantenimiento se convierte en una orden de trabajo, el estado del ciclo de vida de la solicitud de mantenimiento se debe actualizar a **Finalizada** o **Cerrada** para indicar que la solicitud de mantenimiento ya no está activa. En la página de lista **Todas las solicitudes de mantenimiento**, puede ver todas las solicitudes de mantenimiento, independientemente de su estado de ciclo de vida.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Configurar estados de ciclo de vida de solicitud de mantenimiento

1. Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Estados de ciclo de vida**.
2. Seleccione **Nuevo** para crear un estado de ciclo de vida de solicitud de mantenimiento.
3. En el campo **Estado de ciclo de vida**, especifique un identificador para el estado de ciclo de vida.
4. Escriba un nombre en el campo **Nombre**.

    En el FastTab **Detalles**, el campo **Modelos de ciclo de vida** muestra el número de modelos de ciclo de vida de solicitud de mantenimiento que utilizan este estado de ciclo de vida.

5. En el FastTab **General**, establezca la opción **Activa** en **Sí** si una solicitud de mantenimiento está activa cuando se encuentra en este estado de ciclo de vida.
6. Establezca la opción **Establecer el final real** en **Sí** si se deben introducir una fecha y hora finales reales automáticamente en una solicitud de mantenimiento que se encuentre en este estado de ciclo de vida.
7. Establezca la opción **Crear orden de trabajo** en **Sí** si se puede crear una orden de trabajo a partir de una solicitud de mantenimiento que se encuentre en este estado de ciclo de vida.
8. Establezca la opción **Eliminar** en **Sí** si una solicitud de mantenimiento se puede eliminar siempre que se encuentre en este estado de ciclo de vida.
9. En la ficha desplegable **Actualizar**, las opciones **Entrante** y **Saliente** de la sección **Activo** son relevantes si utiliza la reparación de depósito. Establezca la opción adecuada en **Sí** si el estado del ciclo de vida de los activos seleccionados en una solicitud de mantenimiento debe actualizarse automáticamente a **Entrante** o **Saliente** cuando el estado del ciclo de vida de la solicitud de mantenimiento de esa solicitud de mantenimiento se establece en **Entrante** o **Saliente**.

La ilustración siguiente muestra un ejemplo de la página **Estados de ciclo de vida de solicitud de mantenimiento**.

![Página de estados de ciclo de vida de solicitud de mantenimiento](media/02-setup-for-requests.png)

> [!NOTE]
> Los estados de ciclo de vida de solicitud de mantenimiento, los grupos de estados de ciclo de vida y sus tipos están relacionados con (y se usan del mismo modo que) los estados de ciclo de vida de la orden de trabajo, los grupos de estados de ciclo de vida y sus tipos. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Configurar modelos de ciclo de vida de solicitud de mantenimiento

Una vez que haya creado los estados de ciclo de vida necesarios para sus solicitudes de mantenimiento, pueden dividirse en grupos de estados de ciclo de vida o modelos de ciclo de vida. Los modelos de ciclo de vida de solicitud de mantenimiento se usan para crear el flujo que se puede usar para los diferentes tipos de solicitudes de mantenimiento. Como mínimo, debe crearse un modelo de ciclo de vida de solicitud de mantenimiento estándar.

1. Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Modelos de ciclo de vida**.
2. Seleccione **Nuevo** para crear un modelo de ciclo de vida de solicitud de mantenimiento.
3. En el campo **Modelo de ciclo de vida**, especifique un identificador para el modelo de ciclo de vida.
4. Escriba un nombre en el campo **Nombre**.

    En el FastTab **Detalles**, **Estados de ciclo de vida** muestra el número de estados de ciclo de vida seleccionados en este modelo de ciclo de vida. El campo **Tipos de solicitud de mantenimiento** muestra el número de tipos de solicitud de mantenimiento que utilizan este modelo de ciclo de vida.

5. En el FastTab **Estados de ciclo de vida**, seleccione los estados de ciclo de vida que se deben incluir en el modelo de ciclo de vida:

    - Para incluir un estado de ciclo de vida en el modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida restantes** y seleccione el botón de la ![flecha derecha](media/03-setup-for-requests.png) para moverlo a la sección **Estados del ciclo de vida seleccionados** .
    - Para incluir todos los estados de ciclo de vida disponibles en el modelo de ciclo de vida, seleccione el botón **Seleccionar todos los estados disponibles** ![Seleccionar todos los estados disponibles](media/04-setup-for-requests.png). Todos los estados de ciclo de vida se mueven a la sección **Estados de ciclo de vida seleccionados**.
    - Para quitar un estado de ciclo de vida del modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de la ![flecha izquierda](media/05-setup-for-requests.png) para moverlo a la sección **Estados del ciclo de vida restantes**.

6. En el FastTab **General**, los campos de la sección **Actualizaciones** son relevantes si usa la reparación interna.

    - En el campo **Estado del ciclo de vida del activo recibido**, seleccione el estado de ciclo de vida del activo al que deben actualizarse automáticamente los activos seleccionados en una solicitud de mantenimiento cuando se reciben para su reparación interna.
    - En el campo **Estado de ciclo de vida del activo entregado**, seleccione el estado de ciclo de vida del activo al que deben actualizarse automáticamente los activos seleccionados en una solicitud de mantenimiento cuando se devuelven después de su reparación.

La ilustración siguiente muestra un ejemplo de la página **Modelos de ciclo de vida de solicitud de mantenimiento**.

![Página de modelos de ciclo de vida de solicitud de mantenimiento](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]