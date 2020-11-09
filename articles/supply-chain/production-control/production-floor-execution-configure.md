---
title: Configurar la interfaz de ejecución de la planta de producción
description: Este tema describe cómo crear una o más configuraciones para la interfaz de ejecución de la planta de producción. Al abrir la interfaz de ejecución de la planta de producción, carga automáticamente una configuración seleccionada y un filtro de trabajo que son específicos del navegador y el dispositivo. En la configuración se establecen las políticas que deben ser aplicables para un uso específico.
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
ms.openlocfilehash: cf58a7d851577854d08bad70cff69794c3841a2d
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012507"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurar la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Los trabajadores de planta usan la interfaz de ejecución de la planta de producción para registrar su trabajo diario, como cuando inician un trabajo, notifican comentarios sobre los trabajos, registran actividades indirectas e informan de ausencias. Estos registros son la base para seguir el progreso y el coste de las órdenes de producción y para calcular la base del pago de los trabajadores.

Al abrir la interfaz de ejecución de la planta de producción, carga automáticamente una configuración seleccionada y un filtro de trabajo que son específicos del navegador y el dispositivo. En la configuración se establecen las políticas que deben ser aplicables para un uso específico. A continuación, encontrará algunos ejemplos de uso:

- En un dispositivo en el vestíbulo de la empresa, los empleados registran su entrada cuando entran a la oficina y su salida cuando se van.
- En un dispositivo de planta, los operadores de máquinas se registran cuando comienzan y cuando terminan los trabajos. También registran los descansos y las actividades indirectas.

Este tema describe las diversas opciones para configurar los dispositivos de tarjeta de trabajo.

## <a name="turn-on-new-features-in-feature-management"></a>Habilitar nuevas características en la administración de características

Algunas de las configuraciones descritas en este tema deben estar habilitadas en su sistema para que estén disponibles. Utilice la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar cualquiera de las siguientes características (o todas ellas), según sea necesario.

### <a name="generate-license-plate"></a>Generar matrícula de entidad de almacén

Para que esta característica esté disponible, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):

1. Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo
1. Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo

### <a name="print-label"></a>Imprimir etiqueta

Para que esta característica esté disponible, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):

1. Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo
1. Imprimir etiqueta desde dispositivo de tarjeta de trabajo

### <a name="allow-locking-the-touch-screen"></a>Permitir el bloqueo de la pantalla táctil

Para que esta característica esté disponible, active la siguiente característica en la [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Vista previa) Función para bloquear un dispositivo de tarjeta de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar

## <a name="work-with-production-floor-execution-configurations"></a>Trabajar con configuraciones de ejecución de la planta de producción

Para crear y mantener configuraciones de dispositivos, vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Configurar la ejecución de la planta de producción**. La página **Configurar la ejecución de la planta de producción** muestra una lista de configuraciones existentes. En esta página , puede realizar las acciones siguientes:

- Seleccione cualquier configuración de planta de producción que figure en la lista de la columna izquierda para verla y editarla.
- Seleccione **Nuevo** en el panel Acciones para agregar una nueva configuración de dispositivo a la lista. A continuación, en el campo **Configuración** , escriba un nombre para identificar la nueva configuración. El nombre que especifique aquí debe ser único entre todas las configuraciones de dispositivos, y no podrá editarlo más tarde.

A continuación, configure los distintos ajustes para la configuración del dispositivo seleccionado. Están disponibles los siguientes campos:

- **Informar de cantidad a la salida del trabajo** : establezca esta opción en *Sí* para solicitar a los trabajadores que aporten comentarios sobre los trabajos en curso al salir del trabajo. Cuando se establece en *No* , no se avisará a los trabajadores.
- **Bloquear empleado** : cuando esta opción se establece en *No* , se cerrará inmediatamente la sesión de los trabajadores cuando se registren (en un nuevo trabajo, por ejemplo). El dispositivo volverá a la página de inicio de sesión. Cuando esta opción se establece en *Sí* , los trabajadores permanecerán conectados al dispositivo de la tarjeta de trabajo. Sin embargo, un trabajador puede cerrar sesión manualmente para que otro trabajador pueda iniciar sesión mientras el dispositivo de tarjeta de trabajo continúe ejecutándose con la misma cuenta de usuario del sistema. Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](config-job-card-device.md#assigned-users).
- **Usar el tiempo real de registro** : establezca esta opción en *Sí* para establecer la hora de cada nuevo registro en la hora exacta a la que el trabajador envió el registro. Cuando esta opción se establece en *No* , se utiliza en su lugar la hora de inicio de sesión. Por lo general, querrá establecer esta opción en *Sí* , si ha establecido las opciones **Bloquear empleado** o **Trabajador único** , en *Sí* en aquellos casos en los que los trabajadores suelen permanecer conectados durante períodos más largos.
- **Trabajador único** : establezca esta opción en *Sí* si solo un trabajador usa cada dispositivo de tarjeta de trabajo en el que esta configuración está activa. Cuando se establece esta opción en *Sí* , la opción **Bloquear empleado** se configura automáticamente en *Sí*. Además, esta opción elimina el requisito (y la capacidad) de que el trabajador inicie sesión con un identificador de distintivo (o similar). En lugar de ello, el trabajador inicia sesión en Microsoft Dynamics 365 Supply Chain Management con una cuenta de usuario del sistema vinculada a un *trabajador con tiempo registrado* (desde la tabla *trabajadores* ) y se conecta al dispositivo de la tarjeta de trabajo como ese trabajador al mismo tiempo.
- **Permitir bloquear la pantalla táctil** : establezca esta opción en *Sí* para permitir que los trabajadores bloqueen la pantalla táctil del dispositivo de la tarjeta de trabajo para que puedan limpiarla. Cuando esta opción se establece en *Sí* , se agrega un botón **Bloquear pantalla para limpiar** a la página de inicio de sesión del dispositivo. Cuando un trabajador selecciona este botón, la pantalla táctil se bloquea temporalmente para evitar entradas no deseadas. También se muestra un temporizador de cuenta atrás. El trabajador ahora puede limpiar de forma segura el dispositivo y la pantalla. Cuando finaliza la cuenta descendente, la pantalla táctil se desbloquea automáticamente.
- **Duración del bloqueo de pantalla** : cuando la opción **Permitir bloqueo de pantalla táctil** está establecida en *Sí* , use esta opción para especificar la cantidad de segundos que la pantalla táctil debe estar bloqueada para su limpieza. La duración debe estar entre 5 y 120 segundos.
- **Generar matrícula** : establezca esta opción en *Sí* para generar una nueva matrícula cada vez que un trabajador usa el dispositivo de la tarjeta de trabajo para informar como terminado. El número de matrícula de entidad de almacén se genera a partir de una secuencia numérica configurada en la página **Parámetros de gestión de almacén**. Cuando esta opción se establece en *No* , los trabajadores deben especificar una matrícula existente al informar de la conclusión.
- **Etiqueta de impresión** : establezca esta opción en *Sí* para imprimir una etiqueta de matrícula cuando un trabajador usa el dispositivo de la tarjeta de trabajo para informar de su conclusión. La configuración de la etiqueta se configura en la ruta del documento, como se describe en [Diseño de ruta de documento para etiqueta de matrícula](../warehousing/document-routing-layout-for-license-plates.md).

## <a name="clean-up-job-configurations"></a>Limpiar configuraciones de trabajo

Cuando el supervisor de la planta configura la interfaz de ejecución de la planta de producción, selecciona una configuración y un filtro de trabajo. Estas selecciones se almacenan en una tabla de referencia en Supply Chain Management, y el navegador usa un identificador que se almacena en una cookie local para encontrar la fila correcta en esa tabla. La tabla también registra la fecha y hora en que un trabajador inició sesión por última vez en cada dispositivo.

Un trabajo por lotes limpia periódicamente las entradas en la tabla de referencias de los dispositivos que no han registrado ninguna actividad en los últimos 60 días. También puede limpiar manualmente las entradas en cualquier momento siguiendo estos pasos.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. En el panel de acciones, seleccione **Limpiar configuraciones de cliente**.
1. En el cuadro de diálogo **Limpiar configuraciones de cliente** , establecer como valor del campo **Número de días** el número de días de inactividad (antes de hoy) que hay que tener en cuenta. Eliminará todas las configuraciones y los registros de inicio de sesión de los dispositivos que no han estado activos durante ese tiempo.
1. Seleccione **Aceptar** para limpiar las configuraciones relevantes, basándose en la configuración de **Número de días**.
