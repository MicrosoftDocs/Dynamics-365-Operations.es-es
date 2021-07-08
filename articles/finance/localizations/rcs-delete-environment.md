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
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295827"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="30050-103">Regulatory Configuration Service (RCS): eliminar un entorno RCS</span><span class="sxs-lookup"><span data-stu-id="30050-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30050-104">Este tema explica cómo un administrador del sistema del Regulatory Configuration Service (RCS) puede eliminar un entorno RCS y los datos relacionados.</span><span class="sxs-lookup"><span data-stu-id="30050-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="30050-105">Antes de que pueda completar el procedimiento de este tema, debe tener preparados los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="30050-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="30050-106">Debes tener el rol **Administrador del sistema** asignado a usted para el entorno RCS.</span><span class="sxs-lookup"><span data-stu-id="30050-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="30050-107">El rol **Administrador del sistema** debe tener asignado el rol **RCSDeleteEnvironmentDuty**.</span><span class="sxs-lookup"><span data-stu-id="30050-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="30050-108">Eliminar un entorno RCS</span><span class="sxs-lookup"><span data-stu-id="30050-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="30050-109">Abra RCS y seleccione el icono del espacio de trabajo **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="30050-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="30050-110">En la sección **Enlaces relacionados**, seleccione **Eliminar el entorno RCS**.</span><span class="sxs-lookup"><span data-stu-id="30050-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Vínculo Eliminar entorno RCS en la sección Enlaces relacionados](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="30050-112">En el cuadro de diálogo que aparece, revise los mensajes sobre el alcance de la eliminación del entorno.</span><span class="sxs-lookup"><span data-stu-id="30050-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Mensajes en el cuadro de diálogo Eliminar entorno RCS](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="30050-114">La eliminación de un entorno RCS no se puede revertir.</span><span class="sxs-lookup"><span data-stu-id="30050-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="30050-115">La operación elimina el entorno RCS seleccionado y cualquier dato relacionado, incluidas las características y configuraciones que se almacenan en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="30050-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="30050-116">Las funciones y configuraciones que se comparten con otras organizaciones se dejarán de compartir y se eliminarán si no tienen dependencias.</span><span class="sxs-lookup"><span data-stu-id="30050-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="30050-117">Las funciones y configuraciones que tienen dependencias se marcarán como discontinuadas.</span><span class="sxs-lookup"><span data-stu-id="30050-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="30050-118">En el campo que se proporciona, ingrese el identificador único global (GUID) del entorno RCS para confirmar que desea eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="30050-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="30050-119">El GUID del entorno se incluye en el mensaje de eliminación.</span><span class="sxs-lookup"><span data-stu-id="30050-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="30050-120">Seleccione **Eliminar entorno**.</span><span class="sxs-lookup"><span data-stu-id="30050-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="30050-121">Su entorno RCS y todos los datos relacionados ahora se eliminan.</span><span class="sxs-lookup"><span data-stu-id="30050-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30050-122">Después de eliminar un entorno RCS, no hay forma de recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="30050-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="30050-123">Se puede crear un nuevo entorno RCS en cualquier región RCS disponible.</span><span class="sxs-lookup"><span data-stu-id="30050-123">A new RCS environment can be created in any available RCS region.</span></span>
