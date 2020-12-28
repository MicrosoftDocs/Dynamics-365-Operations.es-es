---
title: Configurar tarjeta de trabajo para dispositivos
description: Este tema describe las diversas opciones para configurar el dispositivo de tarjeta de trabajo.
author: johanhoffmann
manager: tfehr
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: e072f99b0b0df75f1b9706362b429bbc4568473a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436922"
---
# <a name="configure-job-card-for-devices"></a>Configurar tarjeta de trabajo para dispositivos

[!include [banner](../includes/banner.md)]

El dispositivo de tarjeta de trabajo se usa para que los trabajadores de la tienda registren su trabajo diario, como cuando se inician los trabajos, informando de comentarios sobre los trabajos, registrando actividades indirectas e informando de ausencias. Estos registros son la base para seguir el progreso y el coste de las órdenes de producción y para calcular la base del pago de los trabajadores. Este tema describe las diversas opciones para configurar los dispositivos de tarjeta de trabajo.

## <a name="enable-new-features-in-feature-management"></a>Habilitar nuevas características en la administración de características

Algunas de las configuraciones descritas en este tema deben estar habilitadas en su sistema para poder estar disponibles para usted. Utilice la página de [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar cualquiera o todas las siguientes características, según sea necesario.

### <a name="generate-license-plate"></a>Generar matrícula de entidad de almacén

Para que esta característica esté disponible, habilite las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en orden):

1. Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo
1. Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo

### <a name="print-label"></a>Imprimir etiqueta

Para que esta característica esté disponible, habilite las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en orden):

1. Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo
1. Imprimir etiqueta desde dispositivo de tarjeta de trabajo

### <a name="allow-locking-of-touch-screen"></a>Permitir el bloqueo de la pantalla táctil

Para que esta característica esté disponible, habilite la siguiente característica en la [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Vista previa) Función para bloquear un dispositivo de tarjeta de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar

## <a name="manage-your-device-configurations"></a>Administrar las configuraciones del dispositivo

Para establecer las configuraciones del dispositivo, vaya a **Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos**. La página **Configurar la tarjeta de trabajo para dispositivos** se abre, mostrando una lista de configuraciones existentes. A partir de aquí, puede hacer lo siguiente: 

- Seleccione cualquier configuración de dispositivo enumerada en la columna izquierda para verla y editarla.
- Seleccione **Nuevo** en el panel Acciones para agregar una nueva configuración de dispositivo a la lista. Luego escriba un nombre en el campo **Configuración** para identificar la nueva configuración. El valor que introduzca aquí debe ser único entre todas las configuraciones de dispositivos, y no podrá editarlo más tarde.

Consulte las siguientes secciones para obtener detalles sobre cada una de las configuraciones para configurar dispositivos de tarjeta de trabajo.

## <a name="general-settings"></a>Configuración general

La ficha desplegable **General** le permite configurar cada una de las diversas opciones disponibles para la configuración del dispositivo seleccionado. Los siguientes parámetros están disponibles:

- **Informar de cantidad a la salida del trabajo**: establezca esto en **Sí** para solicitar a los trabajadores que den su opinión sobre los trabajos en curso al salir del trabajo. Cuando se establece en **No**, los trabajadores no serán avisados.
- **bloquear empleado**: cuando esta opción está establecida en **No**, cada trabajador cerrará sesión inmediatamente después de registrarse (como un nuevo trabajo) y luego el dispositivo volverá a la página de inicio de sesión. Cuando esta opción se establece en **Sí**, cada trabajador permanecerá conectado al dispositivo de la tarjeta de trabajo. Sin embargo, el trabajador aún podrá cerrar sesión manualmente para permitir que otro trabajador inicie sesión mientras el dispositivo de la tarjeta de trabajo sigue ejecutándose con la misma cuenta de usuario del sistema. Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](#assigned-users).
- **Escáner de código de barras**: establezca esto en **Sí** para proporcionar una opción en el dispositivo de la tarjeta de trabajo que permite a los trabajadores registrar el inicio de un nuevo trabajo escaneando un código de barras.
- **Usear el tiempo real de registro**: establezca esto en **Sí** para establecer que el tiempo para que cada nuevo registro sea igual al tiempo exacto en que un trabajador envió el registro. Establézcalo en **No** para utilizar el tiempo de inicio de sesión en su lugar. Por lo general, querrá configurar esto en **Sí**, caso de que haya habilitado las opciones **Bloquear empleado** y/o **Trabajador único**, donde los trabajadores a menudo permanecen con sesión iniciada durante períodos más largos.
- **Trabajador único**: establezca esta opción en **Sí** si solo un trabajador usa cada dispositivo de tarjeta de trabajo en el que esta configuración está activa. Cuando se selecciona esta opción, la opción **Bloquear empleado** se configura automáticamente en **Sí**. Además, esta opción elimina el requisito (y la capacidad) de que el trabajador inicie sesión con un identificador de distintivo (o similar). En cambio, el trabajador inicia sesión en Supply Chain Management utilizando una cuenta de usuario del sistema vinculada a un *trabajador con tiempo registrado* (desde la tabla *trabajadores*) y se conecta al dispositivo de la tarjeta de trabajo como ese trabajador al mismo tiempo.  Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](#assigned-users).
- **Permitir a los trabajadores establecer filtros personales**: establezca esta opción en **Sí** para permitir que los trabajadores filtren los trabajos que se les muestran en el dispositivo. El trabajador puede modificar valores para cualquiera de los tres criterios de filtro: **Unidad de producción**, **Grupo de recursos** y **Recurso**. Solo se mostrarán en el dispositivo los trabajos programados en recursos que coincidan con los criterios de filtro seleccionados. También puede asignar valores predeterminados para cualquiera o todos estos criterios, y estos se aplicarán incluso con esta opción no seleccionada.
- **Permitir bloquear la pantalla táctil**: establezca esta opción en **Sí** para permitir que los trabajadores bloqueen la pantalla táctil del dispositivo de la tarjeta de trabajo para que puedan desinfectarla. Cuando está habilitado, se agrega un botón **Bloqueo de pantalla para desinfectar** a la página de inicio de sesión del dispositivo. Cuando un trabajador selecciona este botón, la pantalla táctil se bloquea temporalmente para evitar entradas no deseadas y se muestra un temporizador de cuenta descendente. El trabajador ahora puede limpiar de forma segura el dispositivo y la pantalla. Cuando finaliza la cuenta descendente, la pantalla táctil se desbloquea automáticamente de nuevo.
- **Duración del bloqueo de pantalla**: cuando la opción **Permitir bloqueo de pantalla táctil** está habilitada, use esta opción para especificar la cantidad de segundos que la pantalla táctil debe estar bloqueada para desinfectar. La duración debe estar entre 5 y 120 segundos.
- **Unidad de producción**: seleccione una unidad de producción para aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador. El dispositivo solo mostrará inicialmente los trabajos programados en los recursos agrupados en la unidad de producción seleccionada. Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.
- **Grupo de recursos**: seleccione un grupo de recursos a aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador. El dispositivo solo mostrará inicialmente en el dispositivo los trabajos programados en el grupo de recursos seleccionado. Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.
- **Recurso**: seleccione un recurso a aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador. El dispositivo solo mostrará inicialmente los trabajos programados en el recurso seleccionado. Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.
- **Generar matrícula**: establezca esta opción en **Sí** para generar una nueva matrícula cada vez que un trabajador usa el dispositivo de la tarjeta de trabajo para informar como terminado. El número de matrícula de entidad de almacén se genera a partir de una secuencia numérica configurada en la página **Parámetros de gestión de almacén**. Cuando se establece en **No**, los trabajadores deben especificar una matrícula existente al informar de la terminación.
- **Etiqueta de impresión**: establezca esta opción en **Sí** para imprimir una etiqueta de matrícula cuando un trabajador usa el dispositivo de la tarjeta de trabajo para informar de terminación. La configuración de la etiqueta se configura en la ruta del documento, como se describe en [Diseño de ruta de documento para etiqueta de matrícula](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Usuarios asignados

Utilice la ficha desplegable **Usuarios asignados** para asociar uno o más usuarios del sistema con la configuración actual del dispositivo. A cada usuario del sistema solo se le puede asignar una configuración de dispositivo de trabajo.

Al configurar un dispositivo, un trabajador de TI generalmente inicia sesión en Supply Chain Management utilizando una cuenta de usuario del sistema. A partir de entonces, la configuración del dispositivo de trabajo asociada con ese usuario del sistema se aplica mientras el usuario del sistema permanezca conectado. Estas cuentas de usuario del sistema generalmente están limitadas para permitir el acceso solo a la página del dispositivo de la tarjeta de trabajo y a ninguna otra parte de Supply Chain Management.

Después de que el usuario del sistema haya iniciado sesión y se haya cargado la configuración del dispositivo de trabajo, los trabajadores pueden iniciar sesión en el dispositivo de la tarjeta de trabajo utilizando su cuenta de *trabajador de tiempo registrado* (por ejemplo, escaneando un código de barras en su credencial) para que puedan comenzar nuevos trabajos y realizar otros tipos de registros. Varios trabajadores pueden iniciar y cerrar sesión durante el día, mientras que la misma configuración de dispositivo permanece vigente en esa máquina porque el usuario del sistema permanece con sesión iniciada en Supply Chain Management durante el día.

Sin embargo, como se mencionó anteriormente, cuando utiliza una configuración de dispositivo con la opción **Trabajador único**, los propios trabajadores suelen iniciar sesión en Supply Chain Management utilizando un usuario del sistema vinculado a su propia cuenta *trabajador de tiempo registrado*, por lo que cargan la configuración del dispositivo e inician sesión como trabajador en el dispositivo de la tarjeta de trabajo al mismo tiempo.

## <a name="additional-resources"></a>Recursos adicionales

[Informar de terminación desde el dispositivo de tarjeta de trabajo](report-finished-job-device.md)
