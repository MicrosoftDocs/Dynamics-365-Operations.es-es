---
title: Crear una plantilla de proceso en Attract
description: Este tema proporciona información sobre cómo crear una plantilla de proceso en Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: ca04bb623b9ddd19f02efbf99289461a78ddd7f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "856632"
---
# <a name="create-a-process-template-in-attract"></a>Crear una plantilla de proceso en Attract

[!include [banner](includes/banner.md)]

Una *plantilla de proceso de contratación* contiene todas las actividades que deben incluirse como parte del proceso de contratación para un trabajo. Este tema describe los elementos de una plantilla de proceso en Microsoft Dynamics 365 for Talent: Attract. También se explica cómo crear una plantilla.

> [!NOTE]
> La creación de plantillas es parte del complemento de contratación completo de Attract.

## <a name="template-management"></a>Administración de plantillas

Las organizaciones pueden decidir si los miembros del equipo o solo los administradores pueden crear plantillas de proceso en Attract. Para configurar la gestión de plantillas, vaya **Centro de administración** \> **Administración de plantillas**. Para permitir que los miembros del equipo creen sus propias plantillas, active la administración de plantillas. Si no activa la administración de plantillas, solo los administradores pueden crear plantillas.

## <a name="default-template"></a>Plantilla predeterminada

Solo los administradores pueden establecer la plantilla predeterminada. Se usa la plantilla predeterminada si una plantilla no se selecciona cuando se crea un trabajo. Para configurar la plantilla predeterminada, vaya a **Centro de administración** \> **Administración de plantillas**. En la tarjeta para la plantilla que debe ser la plantilla predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Establecer como predeterminado**.

## <a name="create-a-process-template"></a>Crear una plantilla de proceso

Las administraciones, los reclutadores, y los administradores de contratación pueden crear plantillas de proceso. Una plantilla de proceso consiste en *etapas* y *actividades*. Las etapas agrupan conjuntamente una o varias actividades. De forma predeterminada, cada plantilla de proceso tiene actividades de candidato viable, solicitud y propuesta. Las etapas que contienen estas actividades pueden ser retituladas. Puede agregar más etapas seleccionando **+ Nueva etapa**. Puede agregar actividades a una etapa arrastrándolas a la etapa apropiada o haciendo doble clic en ellas en la lista de actividades.

> [!NOTE]
> Los nombres de etapas están visibles para los candidatos en la página **Estado de la solicitud**. Deberá considerar este hecho cuando elija los nombres para las etapas.

Para obtener más información acerca de actividades, consulte [Actividades de proceso de contratación en Attract](./activities-attract.md).

Siga estos pasos para crear una plantilla de proceso de contratación.

1. Vaya a **Plantillas**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre de plantilla**, escriba un nombre para la plantilla y, a continuación seleccione **Crear**.
4. En el lista **Elegir el proceso de aprobación**, seleccione **Predeterminado** para requerir la aprobación para un trabajo.
5. Seleccione habilitar o deshabilitar los candidatos viables.
6. Opcional: agregar o quitar etapas.

    - Para agregar una etapa, seleccione **+ Nueva etapa**.
    - Para quitar una etapa, mantenga el puntero del mouse sobre la etapa, y seleccione el botón de papelera que aparece.

        > [!NOTE]
        > Las etapas de candidatos potenciales, solicitud u oferta no se pueden eliminar, pero sí se puede cambiar su nombre.

7. Opcional: agregar o quitar actividades.

    - Para agregar una actividad, arrástrela desde la lista de actividades de la derecha a la etapa adecuada. De forma alternativa, haga doble clic en la actividad, y luego seleccione la etapa a la que la agregará.
    - Para quitar una actividad, expándala y seleccione el botón de papelera en el encabezado de la actividad.

8. Seleccione **Guardar**.
