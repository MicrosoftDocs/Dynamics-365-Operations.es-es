---
title: 'Regulatory Configuration Service (RCS): eliminar un entorno RCS'
description: Este tema explica cómo un administrador del sistema del Regulatory Configuration Service (RCS) puede eliminar un entorno RCS y los datos relacionados.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: f9073a14143423676f23f9bf8dc9c17dbae18a6c3ad0d2f6d1e33919fd9162bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759828"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS): eliminar un entorno RCS

[!include [banner](../includes/banner.md)]

Este tema explica cómo un administrador del sistema del Regulatory Configuration Service (RCS) puede eliminar un entorno RCS y los datos relacionados.

Antes de que pueda completar el procedimiento de este tema, debe tener preparados los siguientes requisitos previos:

- Debes tener el rol **Administrador del sistema** asignado a usted para el entorno RCS.
- El rol **Administrador del sistema** debe tener asignado el rol **RCSDeleteEnvironmentDuty**.

## <a name="delete-an-rcs-environment"></a>Eliminar un entorno RCS

1. Abra RCS y seleccione el icono del espacio de trabajo **Informes electrónicos**.
2. En la sección **Enlaces relacionados**, seleccione **Eliminar el entorno RCS**.

    ![Vínculo Eliminar entorno RCS en la sección Enlaces relacionados.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. En el cuadro de diálogo que aparece, revise los mensajes sobre el alcance de la eliminación del entorno.

    ![Mensajes en el cuadro de diálogo Eliminar entorno RCS.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > La eliminación de un entorno RCS no se puede revertir.
    >
    > La operación elimina el entorno RCS seleccionado y cualquier dato relacionado, incluidas las características y configuraciones que se almacenan en el repositorio global. Las funciones y configuraciones que se comparten con otras organizaciones se dejarán de compartir y se eliminarán si no tienen dependencias. Las funciones y configuraciones que tienen dependencias se marcarán como discontinuadas.

4. En el campo que se proporciona, ingrese el identificador único global (GUID) del entorno RCS para confirmar que desea eliminarlo. El GUID del entorno se incluye en el mensaje de eliminación.
5. Seleccione **Eliminar entorno**.
    
Su entorno RCS y todos los datos relacionados ahora se eliminan.

> [!IMPORTANT]
> Después de eliminar un entorno RCS, no hay forma de recuperar los datos. Se puede crear un nuevo entorno RCS en cualquier región RCS disponible.
