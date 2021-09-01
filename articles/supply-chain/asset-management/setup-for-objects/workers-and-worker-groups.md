---
title: Trabajadores de mantenimiento y grupos de trabajadores
description: Este tema explica los trabajadores de mantenimiento y grupos de trabajadores en la Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e976a28349a4bc7a371d23eb4df724e0ffd36a0553aec2deeb2ff07d0a63579
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750133"
---
# <a name="maintenance-workers-and-worker-groups"></a>Trabajadores de mantenimiento y grupos de trabajadores

[!include [banner](../../includes/banner.md)]

 

Este tema explica los trabajadores de mantenimiento y grupos de trabajadores en la Administración de activos. En Administración de activos, puede conectar trabajadores de mantenimiento a ubicaciones técnicas. (Para obtener más información acerca de las ubicaciones técnicas, consulte [Crear ubicaciones técnias](../functional-locations/create-functional-locations.md)). Esta función puede ser útil si, por ejemplo, se está programando un trabajo de mantenimiento en un equipo ubicado en la ubicación técnica 01 y desea asignar a trabajadores de mantenimiento de la misma ubicación para efectuar el trabajo.

También puede crear grupos de trabajadores de mantenimiento y asociarles trabajadores de mantenimiento. Esta función es de utilidad al hacer la programación simple del pedido de trabajo si desea programar un grupo de trabajadores de mantenimiento en un pedido de trabajo. Puede usar trabajadores de mantenimiento y grupos de trabajadores de mantenimiento para configurar los trabajadores preferidos de mantenimiento y los trabajadores responsables del mantenimiento. 


## <a name="create-workers"></a>Crear trabajadores

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajadores** \> **Trabajadores**.
2. Seleccione **Nuevo** para agregar un trabajador a la lista.
3. Seleccione el trabajador en el campo **Trabajador**.
4. Establezca la opción **Activo** en **Sí** para programar el trabajador en los pedidos de trabajo.

    En el FastTab **General**, los campos **Recurso** y **Descripción** se rellenan automáticamente si se ha seleccionado un recurso para el trabajador. Se rellena el campo **Calendario** también automáticamente, siempre que se haya configurado el trabajador como recurso y se haya asignado un calendario a ese recurso en la página **Recursos** (**Administración de la organización** \> **Recursos** \> **Recursos**).

5. En el FastTab **Grupos** , seleccione **Agregar** y seleccione un grupo de trabajadores de mantenimiento para el trabajador. Un trabajador puede estar afiliado a más de un grupo.
6. En la configuración estándar, la afiliación de un trabajador a un grupo es efectiva partir de la fecha en que se agrega al grupo y nunca caduca. Esta fecha se muestra en el campo **Vigente**. Para ver el campo **Vigente**, seleccione **Ver** \> **Todo**. Si la afiliación del trabajador a un grupo se limita a un período específico, use **Vigente** y **Caducidad** para definir el período.
7. En el FastTab **Ubicaciones técnicas** , seleccione **Agregar** y seleccione una ubicación para el trabajador de mantenimiento. Especifique también qué ubicación es la ubicación técnica principal del trabajador.

    > [!NOTE]
    > Al agregar ubicaciones técnicas a un trabajador, todos los activos activo relacionados con las ubicaciones aparecen en distintos elementos de menú, como **Mis activos activos** y **Mis ubicaciones técnicas activas**. También aparecen en las búsquedas de activos que se muestran al crear un activo, una solicitud de mantenimiento o un pedido de trabajo.

    Los campos del FastTab **Detalles** muestran el número de grupos de trabajadores de mantenimiento y ubicaciones técnicas con las que está relacionado el trabajador de mantenimiento seleccionado.

## <a name="create-worker-groups"></a>Crear grupos de trabajadores

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajadores** \> **Grupos de trabajadores de mantenimiento**.
2. Seleccione **Nuevo** para agregar un grupo de trabajadores a la lista.
3. En el campo **Grupos de trabajadores de mantenimiento**, especifique un id. de grupo.
4. Escriba un nombre en el campo **Nombre**.
5. En el FastTab **Trabajadores** , seleccione **Agregar** y seleccione un grupo de trabajadores de mantenimiento para el grupo de trabajadores. Para obtener información sobre los campos **Vigente** y **Caducidad**, consulte el paso 6 en el procedimiento anterior.
6. Si un grupo de recursos está relacionado con el grupo de trabajadores de mantenimiento seleccionado, seleccione **Copia del grupo de recursos**. En el campo **Grupo** , seleccione el grupo de recursos del que copiar la configuración del calendario. A continuación en el campo **Grupo de trabajadores** seleccione el grupo de trabajadores al que copiar la configuración del calendario. Este paso es relevante si desea que los trabajadores de mantenimiento usen el calendario que está relacionado con un recurso (centro de trabajo) durante la programación de pedidos de trabajo.

    El campo del FastTab **Detalles** muestra el número de trabajadores de mantenimiento que se han configurado en el grupo de trabajadores de mantenimiento seleccionado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]