---
title: Configurar un dispositivo para que ejecute la interfaz de ejecución de la planta de producción
description: La interfaz de ejecución de la planta de producción está configurada para cada dispositivo en la planta de producción. Las empresas suelen configurar cada dispositivo de forma diferente, según su propósito. Por ejemplo, una empresa puede tener un dispositivo en el área de recepción, donde los trabajadores registran la entrada y la salida, y otro en el piso de producción, donde los trabajadores administran sus trabajos.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 57f09bf907407e19ae0e693de64510f7f4efbf0b
ms.sourcegitcommit: f27f5d07c040bdca1bcd616f5d3f2320d3b3337e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "4437162"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Configurar un dispositivo para que ejecute la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La interfaz de ejecución de la planta de producción está configurada para cada dispositivo en la planta de producción. Las empresas suelen configurar cada dispositivo de forma diferente, según su propósito. Por ejemplo, una empresa puede tener un dispositivo en el área de recepción, donde los trabajadores registran la entrada y la salida, y otro en el piso de producción, donde los trabajadores administran sus trabajos.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Establecer la configuración y los filtros para un dispositivo específico

Para establecer la configuración y los filtros de trabajo para un dispositivo, inicie sesión en la página **Ejecución de planta de producción** mediante el uso de una cuenta que tiene un rol de seguridad que incluye la función *Mantener supervisor de tiempo*. (Entre los roles de seguridad listos para usar, solo *Supervisor de planta* tiene esta función). A continuación, siga estos pasos.

1. Vaya al dispositivo que desea configurar e inicie sesión en Microsoft Dynamics 365 Supply Chain Management como supervisor de planta. (Utilice una cuenta que incluya la función *Mantener supervisor de tiempo*).
1. Asegúrese de que haya una configuración disponible para el dispositivo que está configurando. Si no existe ninguna configuración, se proporciona una configuración predeterminada. Para obtener más información sobre cómo configurar una configuración, consulte [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).
1. Vaya a **Control de producción \> Ejecución de fabricación \> Ejecución de planta de producción**.

    Si la interfaz de ejecución de la planta de producción ya se ha configurado al menos una vez en el dispositivo actual, aparece una página de inicio de sesión. De lo contrario, aparece una página de bienvenida.

1. En la página de inicio de sesión o en la página de bienvenida, seleccione **Configurar**.
1. Seleccione una configuración de la lista.
1. Seleccione **Siguiente**.
1. Seleccione uno o más filtros para aplicar al dispositivo actual. Estos filtros ayudarán a garantizar que solo se muestren los trabajos relevantes en el dispositivo. Para establecer un filtro, seleccione el tipo de filtro para abrir una lista de valores y luego seleccione el valor por el que filtrar. Están disponibles los siguientes filtros:

    - **Unidad de producción**: este es el filtro de más alto nivel. Por lo general, se refiere a un área de trabajo grande que tiene varios grupos de recursos y recursos individuales.
    - **Grupo de recursos**: este es un filtro de nivel intermedio. Normalmente se refiere a una colección de recursos relacionados en un área limitada del espacio de trabajo. Si selecciona primero un filtro de **Unidad de producción**, la lista de grupos de recursos solo muestra los grupos de esa unidad. De lo contrario, muestra todos los grupos de recursos disponibles.
    - **Recurso**: este filtro es el más específico. Por lo general, se refiere a un equipo específico u otro recurso único. Si selecciona primero un filtro de **Grupo de recursos** o de **Unidad de producción**, la lista de recursos solo muestra los recursos de ese grupo o unidad. De lo contrario, muestra todos los recursos disponibles.

1. Seleccione **Aceptar**.
1. Aparece la página de inicio de sesión y su dispositivo está listo para usarse.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Permitir que un trabajador anule los filtros predeterminados

Puede otorgar permiso a trabajadores específicos para cambiar la configuración del filtro en cualquier dispositivo que utilicen. Para los trabajadores que tienen este permiso, la interfaz de ejecución de planta de producción proporciona un botón **Filtro** en las páginas **Todos los trabajos** y **Trabajo activo**.

> [!NOTE]
> Si un trabajador cambia un filtro, el nuevo filtro se aplica a partir de ese punto en adelante para todos los usuarios que inicien sesión en el dispositivo.

Para permitir que un trabajador anule los filtros de trabajo predeterminados que se han configurado para un dispositivo, siga estos pasos.

1. Vaya a **Tiempo y asistencia \> Configurar \> Trabajadores con registro de horas**.
1. Seleccione un trabajador de la lista para abrir la página **Trabajadores de registro de tiempo** de ese trabajador.
1. En la pestaña **Registro de tiempo**, configure la opción **Establecer filtros** en *Sí*.

## <a name="run-the-interface-in-full-screen-mode"></a>Ejecutar la interfaz en modo de pantalla completa

A menudo, ejecutará la interfaz de ejecución de la planta de producción en un dispositivo que se utiliza exclusivamente para ese propósito. Por lo tanto, podría tener sentido ejecutar la interfaz en modo de pantalla completa, sin mostrar ninguna navegación ni el navegador Chrome.

- Para ocultar el panel de navegación que se muestra en Supply Chain Management, agregue el siguiente texto al final de la URL en la barra de direcciones del navegador: `\&limitednav=true`.
- Para ocultar también la barra de direcciones del navegador, utilice el modo de pantalla completa nativo del navegador. (Para obtener instrucciones, consulte la documentación de su navegador).

La parte superior de la siguiente ilustración muestra el aspecto predeterminado de la interfaz. La parte inferior muestra cómo se ve en modo de pantalla completa cuando el panel de navegación está oculto.

![Interfaz estándar frente a pantalla completa](media/pfei-full-screen.png "Interfaz estándar frente a pantalla completa")

## <a name="extend-the-session-past-12-hours"></a>Extender la sesión más allá de las 12 horas

De forma predeterminada, la interfaz de ejecución de la planta de producción cierra sesión automáticamente si nadie la usa durante 12 horas. Un usuario de Supply Chain Management deberá volver a iniciar sesión. Sin embargo, puede extender el límite de tiempo de espera hasta 90 días.

Para extender el límite de tiempo de espera, inicie sesión en Supply Chain Management y vaya a **Administración del sistema \> Usuarios \> Extensiones de sesión**. Especifique la cuenta de usuario de Supply Chain Management que se utiliza para iniciar sesión en el dispositivo y el número de horas que la sesión debe permanecer activa.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]