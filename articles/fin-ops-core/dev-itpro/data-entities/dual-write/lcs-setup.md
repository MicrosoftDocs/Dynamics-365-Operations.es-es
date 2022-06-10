---
title: Configuración de la doble escritura de Lifecycle Services
description: Este tema explica cómo configurar una conexión de escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 53e82fbf8cff834c9eb0d14a0597561158b85fa1
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783212"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuración de la doble escritura de Lifecycle Services

[!include [banner](../../includes/banner.md)]



Este tema explica cómo habilitar escritura dual desde Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Requisitos previos

Los clientes deben completar la integración de Power Platform como se describe en los siguientes temas:

- Si aún no usa Microsoft Power Platform y desea expandir sus entornos de Finanzas y Operaciones agregando capacidades de plataforma, consulte [Integración de Power Platform: habilitar durante la implementación del entorno](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Si ya tiene entornos Dataverse y Power Platform y desea conectarlos a entornos de Finanzas y Operaciones, consulte [Integración de Power Platform: Habilitar después de la implementación del entorno](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Configurar escritura dual para entornos de Dataverse nuevos o ya existentes

Siga estos pasos para configurar la escritura dual desde la página de LCS **Detalles del entorno**:

1. En la página **Detalles del entorno**, expanda la sección **Integración de Power Platform**.

2. Seleccione el botón **Aplicación de escritura dual**.

    ![Integración de Power Platform.](media/powerplat_integration_step2.png)

3. Revise los términos y condiciones, y luego seleccione **Configurar**.

4. Seleccione **Aceptar** para continuar.

5. Puede supervisar el progreso actualizando periódicamente la página de detalles del entorno. La configuración suele tardar 30 minutos o menos.  

6. Cuando se complete la configuración, un mensaje le informará si el proceso tuvo éxito o si hubo un error. Si la configuración falla, se muestra un mensaje de error relacionado. Debe corregir cualquier error antes de pasar al siguiente paso.

7. Seleccione **Enlazar al entorno de Power Platform** para crear un vínculo entre Dataverse y las bases de datos del entorno actual. Esto suele tardar menos de 5 minutos.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular al entorno de Power Platform.":::

8. Cuando se completa el vínculo, se muestra un hipervínculo. Utilice el enlace para iniciar sesión en el área de administración de escritura dual en el entorno de Finance and Operations. Desde allí, puede configurar asignaciones de entidades.

## <a name="linking-mismatch"></a>Desajuste de vinculación

Es posible que su entorno de doble escritura esté vinculado a una instancia de Dataverse mientras LCS no está configurado para la integración de Power Platform. Este desajuste de vinculación puede provocar un comportamiento inesperado. Se recomienda que los detalles del entorno LCS coincidan con lo que está conectado en doble escritura para que los eventos comerciales, las tablas virtuales y los complementos puedan usar la misma conexión.

Si su entorno tiene un desajuste de vinculación, LCS muestra una advertencia en la página de detalles de su entorno similar a: "Microsoft ha detectado que su entorno está vinculado mediante escritura dual a un destino diferente al especificado en Integración de Power Platform, lo cual no se recomienda":

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="El enlace de integración de Power Platform no coincide.":::

Si recibe esta advertencia, pruebe una de las siguientes soluciones:

- Si su entorno LCS nunca se ha configurado para la integración de Power Platform, puede conectarse a la instancia de Dataverse que está configurada en doble escritura siguiendo las instrucciones de este artículo.
- Si su entorno LCS ya está configurado para la integración de Power Platform, debe desvincular la doble escritura y volver a conectarla a la especificada por LCS usando el [Escenario: restablecer o cambiar la vinculación](relink-environments.md#scenario-reset-or-change-linking).

En el pasado, estaba disponible una opción de incidencia de soporte técnico, pero eso fue antes de que existiera la opción 1 anterior.  Microsoft ya no admite solicitudes de vinculación manual a través de incidencias de soporte técnico.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
