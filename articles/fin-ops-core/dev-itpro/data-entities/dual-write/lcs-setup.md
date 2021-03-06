---
title: Configuración de la doble escritura de Lifecycle Services
description: Este tema explica cómo configurar una conexión de escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103578"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuración de la doble escritura de Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema explica cómo habilitar escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Requisitos previos

Debe completar la integración de Power Platform como se describe en los siguientes temas:

+ [Integración de Power Platform: habilitar durante la implementación del entorno](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Integración de Power Platform: configurará tras la implementación del entorno](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Configurar escritura dual para nuevos entornos de Dataverse

Siga estos pasos para configurar la escritura dual desde la página de LCS **Detalles del entorno**:

1. En la página **Detalles del entorno**, expanda la sección **Integración de Power Platform**.

2. Seleccione el botón **Aplicación de escritura dual**.

    ![Integración de Power Platform](media/powerplat_integration_step2.png)

3. Revise los términos y condiciones, y luego seleccione **Configurar**.

4. Seleccione **Aceptar** para continuar.

5. Puede supervisar el progreso actualizando periódicamente la página de detalles del entorno. La configuración suele tardar 30 minutos o menos.  

6. Cuando se complete la configuración, un mensaje le informará si el proceso tuvo éxito o si hubo un error. Si la configuración falla, se muestra un mensaje de error relacionado. Debe corregir cualquier error antes de pasar al siguiente paso.

7. Seleccione **Enlazar al entorno de Power Platform** para crear un vínculo entre Dataverse y las bases de datos del entorno actual. Esto suele tardar menos de 5 minutos.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular al entorno de Power Platform":::

8. Cuando se completa el vínculo, se muestra un hipervínculo. Utilice el enlace para iniciar sesión en el área de administración de escritura dual en el entorno de Finance and Operations. Desde allí, puede configurar asignaciones de entidades.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurar escritura dual para un entorno de Dataverse ya existente

Para configurar la escritura dual para un entorno de Dataverse, debe crear una [incidencia de soporte técnico](../../lifecycle-services/lcs-support.md) de Microsoft. La incidencia debe incluir:

+ Su Id. de entorno de Finance and Operations.
+ El nombre de su entorno de Lifecycle Services.
+ La ID de organización de Dataverse la ID de entorno de Power Platform del Centro de administración de Power Platform. En su ticket, solicite que el ID sea la instancia utilizada para la integración de Power Platform.

> [!NOTE]
> No puede desvincular entornos utilizando LCS. Para desvincular un entorno, abra el espacio de trabajo **Integración de datos** en el entorno Finance and Operations, y luego seleccione **Desvincular**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
