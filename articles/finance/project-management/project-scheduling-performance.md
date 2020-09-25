---
title: Rendimiento de la programación de recursos del proyecto
description: Este tema proporciona información sobre cómo mejorar el rendimiento de la programación de los recursos para una gran cantidad de proyectos.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760659"
---
# <a name="project-resource-scheduling-performance"></a>Rendimiento de la programación de recursos del proyecto

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Los problemas de rendimiento relacionados con la programación de recursos pueden ocurrir cuando el número de proyectos llega a miles. Para mejorar el rendimiento de la programación de los recursos, hay una función disponible que permite a los usuarios reducir el tiempo que lleva iniciar el formulario de disponibilidad de recursos. Específicamente, esto elimina el proceso de sincronización de acumulación de capacidad de recursos y utiliza la tabla **ResProjectResource** para acelerar la búsqueda de recursos. Tenga en cuenta que la tabla **ResRollup** la tabla ya no se utilizará.

> [!IMPORTANT]
> Si existe una dependencia del proceso de sincronización de acumulación de capacidad de recursos o de la tabla **ResProjectResource**, no utilice esta función.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Habilitar la mejora del rendimiento de la programación de recursos
Para habilitar la mejora del rendimiento de la programación de recursos, complete los siguientes pasos.

1. Vaya a **Administración de características** > **Todas** y en la lista de características, ubique **Habilitar la función de mejora del rendimiento de la programación de recursos del proyecto**.
2. Seleccione **Habilitar ahora**.

> [!NOTE]
> Si no puede encontrar la función en la lista, seleccione **Buscar actualizaciones** para actualizar la lista.

3. Actualice su navegador y luego vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Recursos del proyecto** > **Sincronizar la capacidad de los calendarios de recursos en todas las empresas**.
4. Establezca **Eliminar registros de capacidad existentes** en **Sí** para eliminar los datos anteriores. Si desea generar datos incrementales, establezca la opción en **No**.
5. En el campo **Código de período**, seleccione el período en el que se deben generar los datos. Si selecciona un código de período, no es necesario definir una fecha de inicio y finalización.
6. Si deja el campo **Código de período** en blanco, seleccione las fechas de inicio y finalización específicas para generar datos.
7. Seleccione **Aceptar**.

 > [!NOTE]
 > Esto distribuirá datos generales a la tabla **ResCalendarCapacity** en todas las empresas de su entorno, por lo que el trabajo por lotes solo debe ejecutarse en una entidad legal. Los datos de este trabajo por lotes son necesarios para calcular la capacidad de recursos a través del calendario asociado.

8. Vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Recursos del proyecto** > **Completar los recursos del proyecto en todas las empresas** y luego seleccione **Aceptar**. Este es el script de actualización de datos para datos generales en las tablas **ResProjectResource**, **ResCalendarDateTimeRange** y **ResEffectiveDateTimeRange**. Los valores para el campo **PSAPRojSchedRole.RootActivity** también se actualizan. Si no se ejecuta, recibirá una advertencia cuando intente ejecutar operaciones de programación de recursos.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Deshabilitar la mejora del rendimiento de la programación de recursos

1. Vaya a **Administración de características** > **Todas** y busque **Habilitar la función de mejora del rendimiento de la programación de recursos del proyecto**.
2. Seleccione la característica y luego seleccione el botón **Deshabilitar**.
3. Actualice su navegador.
4. Vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Sincronización de capacidad** > **Sincronizar acumulaciones de capacidad de recursos**.
5. En la página **Sincronización de acumulación de capacidad**, establezca **Eliminar registros de capacidad existentes** en **Sí** para eliminar los datos anteriores. Si desea generar datos incrementales, establezca la opción en **No**.
6. En el campo **Código de período**, seleccione el período en el que se deben generar los datos. Si selecciona un código de período, no es necesario definir una fecha de inicio y finalización.
7. Si deja el campo **Código de período** en blanco, seleccione las fechas de inicio y finalización específicas para generar datos.
8. Seleccione **Aceptar**.

> [!NOTE]
> Esto distribuirá datos generales a la tabla **ResRollup** en todas las empresas de su entorno, por lo que el trabajo por lotes solo debe ejecutarse en una entidad legal. Este trabajo por lotes es necesario para todas las vistas de **Disponibilidad de recursos**. Si este trabajo por lotes no se ejecuta, los datos de **ResRollup** se generarán sobre la marcha, lo que puede llevar tiempo.
