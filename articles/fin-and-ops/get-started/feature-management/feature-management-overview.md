---
title: Vista previa de Administración de características
description: Este tema describe la función de Administración de características y cómo puede utilizarla.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538709"
---
# <a name="feature-management-overview"></a>Vista previa de Administración de características

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Las características se suman y se actualizan en cada versión de Microsoft Dynamics 365 for Finance and Operations. La experiencia de administración de la característica proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación.

## <a name="the-feature-management-workspace"></a>El espacio de trabajo Administración de características.

Puede abrir el espacio de trabajo **Administración de características** seleccionando el mosaico adecuado en el panel de información. Verá una página que muestra una lista de características para todos las versiones que son compatibles con la experiencia de Administración de características. Con el tiempo, Microsoft ampliará la experiencia de la Administración de características de modo que incluya funcionalidad adicional para ayudarle a gestionar características.

La lista de características incluye la información siguiente:

- **Nombre de la característica** - Una descripción de la función que se ha agregado.
- **Estado habilitado** - Un símbolo indica si se ha habilitado una característica (marca de verificación), no está habilitada (en blanco), se ha programado para ser habilitada (reloj), o es obligatorio habilitarla (candado). El valor que se muestra aquí se usa para todas las entidades jurídicas. Tenga en cuenta que incluso cuando se ha activado, una característica aún se controla mediante la seguridad. Por lo tanto, la característica sólo estará disponible para los usuarios que tengan acceso a ella, en función de su rol de seguridad. También estará disponible solo para las entidades jurídicas a las que tiene acceso el usuario.
- **Fecha de activación** - La fecha en que la característica se ha activado o se activará si la fecha es en el futuro.
- **Característica agregada** - La fecha en que la característica se ha agregado al entorno. Esta fecha se introduce automáticamente durante la actualización del entorno durante los ciclos de lanzamiento mensuales.
- **Módulo** - El módulo afectado por la nueva característica.

Al seleccionar una característica, información adicional aparece en el panel de información a la derecha de la lista de la función. En la parte superior del panel podrá ver el nombre de la función, la fecha en la que la característica se ha agregado, el módulo afectado por la función, y un vínculo a **Más información** . Seleccione este vínculo para ver la documentación para la característica. Si la documentación no está disponible, le llevarán a una página temporal. El panel de detalles también incluye un campo **Comentarios** donde puede agregar sus propios comentarios acerca de la característica.

El espacio de trabajo **Administración de características** también contiene varias fichas con una lista de funciones de ella. 
- **Nuevo** - Muestra todas las características que se han agregado desde la última actualización de mensual. Si ha omitido Las actualizaciones mensuales, contendrá todas las nuevas características desde la última vez que se actualizó. Las características más nuevas aparecen en la parte superior de la lista. El número total de nuevas características también se muestra en un mosaico en la parte superior de la página.
- **No habilitado** - Muestra todas las funciones que no se han habilitado. Las características más nuevas aparecen en la parte superior de la lista. El número total de nuevas características también se muestra en un mosaico en la parte superior de la página.
- **Programado** - Muestra todas las características que se han programado para ser habilitadas en una fecha futura. Las características que tienen la fecha programada más próxima aparecerán en la parte superior de la lista. El número total de nuevas características también se muestra en un mosaico en la parte superior de la página.
- **Todo** - Muestra todas las características. Las características más nuevas aparecen en la parte superior de la lista.


## <a name="enable-a-feature"></a>Habilitar una característica

Si una característica no se ha habilitado, un botón **Habilitar** aparece en el panel de detalles. Puede usar este botón para habilitar la característica.

1. Seleccione la característica que desea habilitar y, a continuación, en el panel de detalles, seleccione **Habilitar**.
2. Un control deslizante aparece, donde puede especificar la fecha en la que la función debe estar habilitada. De forma predeterminada, esta fecha es la fecha actual.
3. Seleccione **Habilitar** para habilitar la función.

Algunas funciones no se pueden deshabilitar tras habilitarlas. Si la función que intenta habilitar no se puede deshabilitar, se mostrará una advertencia. En este punto, puede seleccionar **Cancelar** para cancelar la operación y para dejar la característica deshabilitada. Sin embargo, si se selecciona **Habilitar** y habilita la característica, no podrá deshabilitarla posteriormente.

Después de que se habilite la característica, aparece un mensaje bajo el vínculo **Más información** en el panel de detalles. Este mensaje confirma que la característica se ha activado o indica cuándo lo hará en el futuro. Si usa una fecha futura, la característica mostrará en la lista **Programado** . Este mensaje aparecerá cada vez que seleccione la característica en la lista de la función. Las características programadas en el futuro se habilitarán a medianoche por un proceso por lotes basado en la zona horaria de la fecha del sistema. 

## <a name="reschedule-a-feature"></a>Reprogramar una característica

Si una característica se ha habilitado en el futuro, un botón **Reprogramar** aparece en el panel de detalles. Puede usar este botón para cambiar la **Fecha de habilitación** a otra distinta.

1. Seleccione la característica programada que desea reprogramar y, a continuación, en el panel de detalles, seleccione **Reprogramar**.
2. Un control deslizante aparece, donde puede especificar la fecha en la que la función debe estar habilitada. 
3. Seleccione **Habilitar** para volver a programar la característica o **Deshabilitar** para cancelar la programación.

## <a name="disable-a-feature"></a>Deshabilitar una característica

Si una característica ya se ha habilitado, un botón **Deshbilitar** aparece en el panel de detalles. Puede usar este botón para deshabilitar la característica. El botón **Deshabilitar** no está disponible si la característica no se puede deshabilitar después de que se habilite.

- Seleccione la característica que desea desactivar y, a continuación, en el panel de detalles, seleccione **Deshabilitar**.

- Se deshabilita la función y se desactiva la fecha.

Después de que se deshabilite la característica, aparece un mensaje bajo el vínculo **Más información** en el panel de detalles. Los estados de este mensaje que la característica aún no se ha habilitado y aparecerá en la lista **No habilitada** . El mensaje aparecerá cada vez que seleccione la característica en la lista de la función.

## <a name="features-that-must-be-enabled"></a>Características que deben habilitarse

Puede lanzarse una característica crítica que se habilitará automáticamente cuando se actualice. Será habilitada automáticamente en **Fecha de habilitación**. Un mensaje aparecerá bajo el vínculo **Más información** en el panel de detalles. Este mensaje dirá que la característica se habilitó o se habilitará automáticamente en **Fecha de habilitación**. Aparecerá cada vez que seleccione la característica en la lista de la función.

## <a name="assigning-roles"></a>Asignar roles

El espacio de trabajo **Administración de características** lo pueden abrir administraciones del sistema, y los usuarios que están asignados a roles de Administrador de características o Visores de características creados para admitir la experiencia de Administración de características. Los usuarios del rol de Administrador de características pueden activar o desactivar cualquier característica. También pueden actualizar la sección de comentarios para la característica. Los usuarios en el rol de Visor de características solo pueden ver el espacio de trabajo **Administración de características** . No pueden activar o desactivar las características.

El rol de Administrador de características y el de Visor de características no anulan la seguridad existente que tiene un usuario. Los roles so controlan el acceso a la habilitación de características. No proporciona acceso a las características en sí.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Usar la Administración de características para habilitar las características de ISV o las personalizadas

El proceso de Administración de características no está actualmente disponible para las características de ISV o las personalizadas. Estamos agregando funcionalidad adicional para ampliar la Administración de características y, cuando se completen las mejoras, abriremos la Administración de características a todas las características y proporcionaremos instrucciones específicas de cómo actualizar su característica para utilizarla.

## <a name="feature-management-and-flighting"></a>Administración de características y distribución de paquetes piloto

La Administración de características le permite controlar las características que forman parte de cada versión. La distribución de paquetes piloto permite a los Microsoft Teams presentar características a un número limitado de clientes para poder ser probadas y validarlas las características sin afectar a todos los clientes. La Administración de características no controla la distribución de paquetes piloto de cualquier característica.
