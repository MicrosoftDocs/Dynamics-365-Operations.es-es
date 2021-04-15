---
title: Estados de ciclo de vida de activos
description: Este tema explica los estados de ciclo de vida y los modelos de ciclo de vida de activos en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 985fedc13e28caee90c9db27b145e415d256208d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808309"
---
# <a name="asset-lifecycle-states"></a>Estados de ciclo de vida de activos

[!include [banner](../../includes/banner.md)]

 

Este tema explica los estados de ciclo de vida y los modelos de ciclo de vida de activos en Administración de activos. Los estados de ciclo de vida de activo se uasn para definir si el activo está activo o inactivo. Por ejemplo, puede configurar los estados del ciclo de vida de activo como **Creado**, **Activo** y **Finalizado**.

> [!NOTE]
> - Los estados de ciclo de vida de solicitud están vinculados a los estados de ciclo de vida de activo. Por lo tanto, cuando una solicitud se cambia a un nuevo estado de ciclo de vida, el activo vinculado a la solicitud se cambia a un nuevo estado de ciclo de vida. Por ejemplo, si cambia el estado de ciclo de vida de una solicitud a **Entrante**, el estado de ciclo de vida del activo vinculado se cambia al estado de ciclo de vida seleccionado en el campo **Estado de ciclo de vida de entrada** en el FastTab **Estado del ciclo de vida de activo** de la página **Modelos de estado de ciclo de vida de activo**. 


Los estados de ciclo de vida de activo se pueden configurar en los modelos de ciclo de vida de activo, donde se pueden definir los estados de ciclo de vida necesasrios para los distintos tipos de activos. Primero debe configurar los estados de ciclo de vida. A continuación, crea un modelo de ciclo de vida y selecciona los estados de ciclo de vida para este.

1. Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Estados de ciclo de vida**.
2. Seleccione **Nuevo** para crear un nuevo estado de ciclo de vida de activo.
3. En el campo **Estado de ciclo de vida**, especifique el id. de estado de ciclo de vida.
4. En el campo **Nombre**, escriba una descripción.

    El campo **Modelos de ciclo de vida** muestra el número de modelos de ciclo de vida de activo que usan el estado de ciclo de vida de activo.

5. Establezca la opción **Activo** en **Sí** si este estado de ciclo de vida es una estado de ciclo de vida activo (es decir, si se pueden crear órdenes de trabajo para los activos que se encuentran en este estado de ciclo de vida).
6. Establezca la opción **Eliminar líneas abiertas del calendario** en **Sí** si se deben eliminar las líneas abiertas del calendario de activos que tengan un estado de ciclo de vida de activo **Creado** cuando se encuentren en este estado de ciclo de vida. Esta opción resulta útil si desea limpiar las programaciones de mantenimiento abiertas que ya no sean relevantes para el activo (por ejemplo, si el activo ya no está activo).

> [!NOTE]
> Los estados de ciclo de vida de activo, los modelos de ciclo de vida de activo y los tipos de activo están relacionados. Se usan de la misma forma que los estados de ciclo de vida de orden de trabajo, los modelos de ciclo de vida de orden de trabajo y los tipos de orden de trabajo. 


Una vez que haya creado los estados de ciclo de vida de activo necesarios, puede configurar los estados de ciclo de vida en los modelos de ciclo de vida de activo.

1. Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Modelos de ciclo de vida**.
2. Seleccione **Nuevo** para crear un nuevo modelo de ciclo de vida de activo.
3. En el campo **Modelo de ciclo de vida**, especifique el id. de modelo de ciclo de vida.
4. En el campo **Nombre**, escriba una descripción.

    El campo **Estados de ciclo de vida** muestra el número de estados de ciclo de vida de activo seleccionados en el modelo de ciclo de vida de activo. El campo **Tipos de activo** muestra el número de tipos de activo que utilizan el modelo de ciclo de vida.

5. En el FastTab **Estados de ciclo de vida**, seleccione los estados de ciclo de vida de activo que se deben incluir en el modelo de ciclo de vida de activo:

    - Para usar un estado de ciclo de vida para el modelo, selecciónelo en la sección **Estados de ciclo de vida restantes** y seleccione el botón de la flecha derecha ![Flecha derecha](media/15-setup-for-objects.png) para moverlo a la sección **Estados del ciclo de vida seleccionados**.
    - Para usar todos los estados de ciclo de vida disponibles para el modelo, seleccione el botón **Todos los estados de ciclo de vida disponibles** ![Todos los estados de ciclo de vida disponibles](media/20-setup-for-objects.png). Todos los estados de ciclo de vida se transfieren a la sección **Estados de ciclo de vida seleccionados**.
    - Para quitar un estado de ciclo de vida del modelo, selecciónelo en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de la flecha izquierda ![Flecha izquierda](media/16-setup-for-objects.png) para moverlo a la sección **Estados del ciclo de vida restantes**.

6. Seleccione **Actualizaciones de estado de ciclo de vida** para definir los estados de ciclo de vida de activo que pueden seguir un estado de ciclo de vida seleccionado.
7. Use el FastTab **Estado de activo** si administra activos que recibe para su reparación. En la sección **Entrante/saliente**, puede seleccionar estados de ciclo de vida de activo para indicar el flujo de trabajo de un activo que recibe para reparación. Si ofrece activos de préstamo a los clientes o departamentos, en la sección **Préstamo** puede seleccionar estados de ciclo de vida de activos de préstamo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]