---
title: Restablecer la sincronización de Dataverse
description: Este tema describe cómo solucionar problemas de registros que no se sincronizan correctamente entre Microsoft Dynamics 365 Human Resources y la solución común de gestión del capital humano (HCM) en Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 8bfcd51b023c02590919155abbb836326408d298
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696246"
---
# <a name="reset-dataverse-synchronization"></a>Restablecer la sincronización de Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problema

Los registros no están sincronizados entre Microsoft Dynamics 365 Human Resources y las entidades de la solución común de gestión del capital humano (HCM) en Microsoft Dataverse. Para obtener más información sobre la sincronización, vaya a [Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md). No se puede sincronizar correctamente cuando los trabajos por lotes **Dataverse reintento de integración** o **Dataverse sincronización de solicitud perdida de integración** están atascados en un estado **Ejecutando**.

## <a name="resolution"></a>Resolución

Cuando los trabajos por lotes **Reintento de integración en Dataverse** o **Se perdió la solicitud de sincronización de la integración de Dataverse** están atascados en un estado **Ejecutando** o **Cancelando**, puede restablecer el estado. Esto se puede hacer cancelando el trabajo por lotes siguiendo las instrucciones en [Restablecer trabajos por lotes atascados](hr-admin-troubleshooting-batch-execution.md). Después de cancelar el trabajo por lotes, puede restablecer el trabajo por lotes configurándolo en un estado **Esperando**. El trabajo por lotes se ejecutará durante el próximo tiempo de ejecución programado.

1. Si aún no lo ha hecho, habilite la función **Anulación por lotes mejorada** en **Gestión de funciones**.
   1. Vaya a la página **Gestión de funciones** (**Administración del sistema** > **Resumen** > **Gestión de funciones**).
   2. Seleccione la ficha **Todo**.
   3. Seleccione la columna **Nombre de la función** y filtre por **Anulación por lotes mejorada**.
   4. Seleccione la acción **Habilitar** si aún no está habilitada.

2. Desactivar la integración de Dataverse.
   1. Vaya a la página **Integración de Microsoft Dataverse** (**Administración del sistema** vaya a **Enlaces** > **Integraciones** > **Configuración de Dataverse**).
   2. Establezca **Habilitar integración con Dataverse** a **No**.

3. Cancelar el trabajo por lotes **Reintento de integración de Dataverse**.
   1. Vaya a la página **Trabajos por lotes** (**Administración del sistema** vaya a **Enlaces** > **Trabajos por lotes** > **Trabajos por lotes**).
   2. Filtre la columna **Descripción del trabajo** por **Integración**.
   3. Seleccione el trabajo por lotes **Reintento de integración de Dataverse**.
   4. En la cinta de acciones, seleccione **Trabajo por lotes**, **Forzar cancelación** y luego seleccione **Sí** para confirmar.

   > [!NOTE]
   > Dependiendo de cuándo se habilitó la integración por primera vez, el trabajo por lotes puede tener la descripción **Reintento de integración de Common Data Service**. Seleccione este trabajo por lotes si aparece en la lista, en lugar del trabajo por lotes **Reintento de integración de Dataverse**.

4. Eliminar todos los trabajos por lotes de integración de Dataverse.
   1. En la página **Trabajos por lotes**, seleccione los trabajos por lotes **Sincronización de solicitud perdida de integración de Dataverse**, **Reintento de integración de Dataverse**, y **Sincronización inicial de integración de Dataverse**.
   2. En la cinta de acciones, seleccione la acción **Cambiar estado**. 
   3. Seleccione **Retener** y, a continuación, seleccione **Aceptar**.
   4. En la cinta de acciones, seleccione la acción **Eliminar**, y luego seleccione **Sí** para confirmar la acción.

5. Activar los trabajos por lotes de integración de Dataverse.
   1. Vaya a la página **Integración de Microsoft Dataverse** (**Administración del sistema** > **Enlaces** > **Integraciones** > **Configuración de Dataverse**).
   2. Establezca **Habilitar integración con Dataverse** a **Sí**.

6. Ve a la página **Trabajos por lotes** y confirme que los trabajos por lotes **Reintento de integración de Dataverse** y **Sincronización de solicitud perdida de integración de Dataverse** se han creado.

Con los trabajos por lotes vueltos a crear, puede supervisar el trabajo por lotes **Reintento de integración de Dataverse** para ver cuánto tarda el trabajo en ejecutarse. Entonces puede verificar que los registros se están sincronizando correctamente a la solución HCM Common en Microsoft Dataverse.

## <a name="see-also"></a>Consulte también

[Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md)<br>
[Restablecer trabajos por lotes bloqueados](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
