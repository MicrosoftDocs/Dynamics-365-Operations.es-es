---
title: Crear solicitudes de mantenimiento
description: En este tema se explica cómo crear una solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e97d96a5485f17d0abc7c2fc2f8c4fdf4bbd4bb4
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024646"
---
# <a name="create-maintenance-requests"></a>Crear solicitudes de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Pueden usarse solicitudes de mantenimiento cuando los trabajadores de mantenimiento o los trabajadores de producción detectan que el equipo requiere reparación, y el trabajo de reparación no se puede hacer inmediatamente.

**Ejemplo:** cuando un trabajador de mantenimiento está realizando una reparación, descubre que hay que realizar el mantenimiento de otro activo en esa misma ubicación. Sin embargo, el trabajador de mantenimiento no tiene ni el tiempo ni las piezas de repuesto necesarias para realizar el trabajo de reparación. Así, crea una solicitud de mantenimiento en el activo y especifica una breve descripción del problema.

La sección **Solicitudes de mantenimiento activas** del panel **Información relacionada** a la derecha de la página **Todos los activos** o **Activos activos** (**Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**) muestra las solicitudes de mantenimiento activas vinculados al activo seleccionado.

1. Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.
2. Seleccione **Nuevo**.
3. En el cuadro de diálogo **Crear solicitud**, en el campo **Tipo de solicitud de mantenimiento**, seleccione el tipo de solicitud de mantenimiento. Se sugiere un tipo predeterminado.
4. En el campo **Descripción**, escriba un nombre o un título que describa brevemente la solicitud de mantenimiento.
5. En los campos **Ubicación técnica** y **Activo**, seleccione una ubicación técnica o un activo, o una combinación de una ubicación técnica y un activo, según sea necesario. Puede crear una solicitud de mantenimiento sin seleccionar un activo, y el activo se puede agregar posteriormente a la solicitud de mantenimiento. Si el trabajador de mantenimiento que ha iniciado sesión está relacionado con un recurso relacionado con un activo, el campo **Activo** se establece automáticamente.

    Si una solicitud de mantenimiento ya está vinculada al activo seleccionado, aparece una barra de mensajes en la parte superior del cuadro de diálogo **Crear solicitud** para notificarle el identificador de la solicitud de mantenimiento existente. Una barra de mensajes también le notifica si el activo está cubierto por un acuerdo de garantía.

6. En el campo **Nivel de servicio**, seleccione un nivel de servicio que indique la urgencia de la solicitud.
7. Si ha seleccionado un activo en el paso 5, puede usar los campos **Síntoma del error**, **Área del error** y **Tipo de error** para crear un registro de error.
8. Si la solicitud de mantenimiento ha provocado el tiempo de inactividad de mantenimiento, especifique la fecha y la hora iniciales del tiempo de inactividad.

    Se establece automáticamente el campo **Iniciado por** en su nombre.

10. El campo **Inicio real** se establece automáticamente en la fecha y la hora actuales. Sin embargo, puede cambiar el valor si es necesario.
11. En el campo **Notas**, especifique las notas adicionales necesarias.
12. Seleccione **Aceptar**.

![Figura 1](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Procesamiento posterior de solicitudes de mantenimiento

Una vez creada una solicitud de mantenimiento, y antes de convertirla en una orden de trabajo, hay que actualizar diversos datos. Generalmente esta tarea la completa un planificador u otro empleado administrativo.

- En **Todas las solicitudes de mantenimiento** o en la página **Solicitudes de mantenimiento activas**, seleccione la solicitud de trabajo y, a continuación seleccione **Editar**.

En la vista de detalles puede actualizar diversos datos. A continuación se incluyen algunos ejemplos:

- Seleccione y compruebe el activo. Si tiene que seleccionar un activo diferente más tarde, puede establecer la opción **Activo comprobado** en **No**.
- Seleccione un grupo de trabajadores de mantenimiento responsable o un trabajador de mantenimiento responsable. Para obtener más información sobre la configuración necesaria, consulte [Trabajadores de mantenimiento responsables](../setup-for-maintenance-requests/responsible-workers.md).
- Seleccione un tipo de trabajo de mantenimiento y, si esta información es relevante, elija una variante y un oficio de trabajo de mantenimiento relacionados.
- En los campos **Latitud** y **Longitud**, especifique las coordenadas geográficas. Las coordenadas que se agreguen a una solicitud de mantenimiento se transferirán automáticamente a una orden de trabajo relacionada. 

![Figura 2](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Si selecciona un activo al crear una solicitud de mantenimiento, puede agregar un error a activo. Una vez creada la solicitud de mantenimiento, puede agregar más errores si es necesario. Para agregar errores, seleccione **Error de activo** en la página **Todas las solicitudes de mantenimiento**.
