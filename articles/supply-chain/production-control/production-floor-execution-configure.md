---
title: Configurar la interfaz de ejecución de la planta de producción
description: Este tema describe cómo crear una o más configuraciones para la interfaz de ejecución de la planta de producción. Al abrir la interfaz de ejecución de la planta de producción, carga automáticamente una configuración seleccionada y un filtro de trabajo que son específicos del navegador y el dispositivo. En la configuración se establecen las políticas que deben ser aplicables para un uso específico.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5a0ead85eaeb6b96b80716614990af8c8e5e70f7
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384756"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurar la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

Los trabajadores de planta usan la interfaz de ejecución de la planta de producción para registrar su trabajo diario, como cuando inician un trabajo, notifican comentarios sobre los trabajos, registran actividades indirectas e informan de ausencias. Estos registros son la base para seguir el progreso y el coste de las órdenes de producción y para calcular la base del pago de los trabajadores.

Al abrir la interfaz de ejecución de la planta de producción, carga automáticamente una configuración seleccionada y un filtro de trabajo que son específicos del navegador y el dispositivo. En la configuración se establecen las políticas que deben ser aplicables para un uso específico. A continuación, encontrará algunos ejemplos de uso:

- En un dispositivo en el vestíbulo de la empresa, los empleados registran su entrada cuando entran a la oficina y su salida cuando se van.
- En un dispositivo de planta, los operadores de máquinas se registran cuando comienzan y cuando terminan los trabajos. También registran los descansos y las actividades indirectas.

Este tema describe las diversas opciones para configurar una interfaz de ejecución de la planta de producción para cada dispositivo en uso en su sitio.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Encienda la interfaz de ejecución del piso de producción y sus características opcionales relacionadas

La interfaz de ejecución de la planta de producción en sí, más varias de las configuraciones opcionales que se describen en este tema, deben estar activadas en su sistema antes de poder utilizarlas. Utilice la página [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar alguna o todas las funciones descritas en las siguientes subsecciones según sea necesario.

### <a name="the-production-floor-execution-interface"></a>La interfaz de ejecución de la planta de producción

Esta es la característica principal descrita en este tema y es un requisito previo para todas las demás características mencionadas en esta sección. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Ejecución de la planta de producción* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Generar matrículas de entidad de almacén

Estas características hacen que la funcionalidad de la placa de matrícula esté disponible para la interfaz de ejecución de la planta de producción. Si desea usarlas, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):

1. *Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo*<br>A partir de la versión 10.0.21 de Supply Chain Management, esta característica está activada de forma predeterminada. (A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria).
1. *Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria).

### <a name="print-labels"></a>Imprimir etiquetas

Estas características hacen que la funcionalidad de impresión de etiquetas esté disponible para la interfaz de ejecución de la planta de producción. Si desea usarlas, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):

1. *Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo*<br>A partir de la versión 10.0.21 de Supply Chain Management, esta característica está activada de forma predeterminada. (A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria).
1. *Imprimir etiqueta desde dispositivo de tarjeta de trabajo*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria).

### <a name="allow-locking-the-touch-screen"></a>Permitir el bloqueo de la pantalla táctil

Esta característica permite que los trabajadores bloqueen la pantalla táctil para que puedan desinfectarla.

A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Característica para bloquear un dispositivo de tarjetas de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funcionalidad de administración de activos para la interfaz de ejecución de la planta de producción

Esta función agrega una pestaña de administración de activos a la interfaz de ejecución de la planta de producción. Los trabajadores pueden usar esta pestaña para seleccionar un activo que esté conectado a un recurso de máquina que esté dentro del filtro seleccionado de la lista de trabajos. Para el activo de máquina seleccionado, el trabajador puede ver el estado y la salud del activo a partir de los valores de los contadores de hasta cuatro contadores seleccionados. Si desea usar esta función, active las siguientes funciones en [Administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Funcionalidad de administración de activos para la interfaz de ejecución de la planta de producción*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada).

### <a name="enable-job-search"></a>Habilitar la búsqueda de empleo

Esta función permite agregar un campo de búsqueda a la lista de trabajos. Los trabajadores pueden encontrar un trabajo específico ingresando el ID del trabajo o encontrar todos los trabajos para un pedido específico ingresando el ID del pedido. Los trabajadores pueden ingresar la identificación usando un teclado o escaneando un código de barras. Si desea usarla, active las siguientes funciones en [Administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Búsqueda de trabajos para la interfaz de ejecución de la planta de producción*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada).

### <a name="enable-reporting-on-co-products-and-by-products"></a>Habilitar los informes sobre coproductos y productos derivados

Esta característica permite a los trabajadores utilizar la interfaz de ejecución de la planta de producción para informar el progreso de los pedidos por lotes. Estos informes incluyen coproductos y productos derivados. Para usar esta funcionalidad, active la siguiente característica en la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Informe de coproductos y productos derivados de la interfaz de ejecución de planta de producción*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>Habilite la visualización de números completos de serie, lote y matrícula

Esta función proporciona una experiencia mejorada para ver listas de números de serie, lote y matrícula de entidad de almacén en la interfaz de ejecución de la planta de producción. La pantalla cambia de una vista de tarjeta que muestra un número limitado de caracteres a una vista de lista que proporciona suficiente espacio para mostrar los valores completos. La lista también ofrece la posibilidad de buscar números específicos.

A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Mostrar número de serie completo, lote y matrículas de entidad de almacén en la interfaz de ejecución de la planta de producción* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-registering-of-material-consumption"></a>Habilitar el registro de consumo de material

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Esta característica permite a los trabajadores utilizar la interfaz de ejecución de la planta de producción para registrar el consumo de material, los números de lote y los números de serie. Algunos fabricantes, especialmente aquellos dentro de las industrias de proceso, necesitan registrar explícitamente la cantidad de material consumido para cada lote o pedido de producción. Por ejemplo, los trabajadores pueden usar una balanza para pesar la cantidad de material consumido mientras trabajan. Para garantizar la trazabilidad total del material, estas organizaciones también deben registrar qué números de lote se consumieron al producir cada producto.

Existen dos versiones de esta característica. Una admite artículos que *no están* habilitados para utilizar procesos de almacén avanzados (WMS). El otro admite elementos que *están* habilitado para usar WMS. Para usar esta funcionalidad, active una o ambas de las siguientes características en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden), dependiendo de si tiene elementos habilitados para WMS:

- *(Versión preliminar) Registrar el consumo de material en la interfaz de ejecución de planta de producción (no WMS)*
- *(Vista previa) Registrar el consumo de material en la interfaz de ejecución de planta de producción (con WMS habilitado)*

> [!IMPORTANT]
> Puede usar solo la función que no es WMS. Sin embargo, si usa WMS, debe habilitar ambas funciones.

### <a name="enable-reporting-on-catch-weight-items"></a>Habilitar informes sobre artículos con peso capturado

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Los trabajadores pueden utilizar la interfaz de ejecución de la planta de producción para informar el progreso de los pedidos por lotes para artículos de peso capturado. Los pedidos por lotes se crean a partir de fórmulas, que se pueden definir para que tengan productos de peso capturado y productos de fórmula, coproductos y subproductos. También se puede definir una fórmula para que tenga líneas de fórmula para los ingredientes definidos para el peso capturado. Los artículos con peso capturado utilizan dos unidades de medida para realizar un seguimiento del inventario: cantidad de peso capturado y cantidad de inventario. Por ejemplo, en la industria alimentaria, la carne en caja se puede definir como un artículo con peso capturado, en el que la cantidad de peso capturado se usa para rastrear el número de cajas y la cantidad de inventario se usa para rastrear el peso de las cajas.

Para usar esta funcionalidad, active la siguiente característica en la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *(Versión preliminar) Informe sobre artículos con peso capturado desde la interfaz de ejecución de la planta de producción*

## <a name="work-with-production-floor-execution-configurations"></a>Trabajar con configuraciones de ejecución de la planta de producción

Para crear y mantener configuraciones de ejecución de la planta de producción, vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Configurar la ejecución de la planta de producción**. La página **Configurar la ejecución de la planta de producción** muestra una lista de configuraciones existentes. En esta página , puede realizar las acciones siguientes:

- Seleccione cualquier configuración de planta de producción que figure en la lista de la columna izquierda para verla y editarla.
- Seleccione **Nuevo** en el panel Acciones para agregar una nueva configuración a la lista. A continuación, en el campo **Configuración**, escriba un nombre para identificar la nueva configuración. El nombre que especifique aquí debe ser único entre todas las configuraciones, y no podrá editarlo más tarde.

A continuación, configure los distintos ajustes para la configuración seleccionada. Están disponibles los siguientes campos:

- **Ficha de entrada y salida solamente** - Establezca esta opción en *Sí* para crear una interfaz simplificada que solo proporcione funciones de reloj de entrada y salida. Esto desactiva la mayoría de las otras opciones de esta página. Debe eliminar todas las líneas de la ficha desplegable **Selección de pestaña** antes de que pueda habilitar esta opción.
- **Habilitar búsqueda**: establezca esta opción en *Sí* para incluir un campo de búsqueda en la lista de trabajos. Los trabajadores pueden encontrar un trabajo específico ingresando el ID del trabajo o encontrar todos los trabajos para un pedido específico ingresando el ID del pedido. Los trabajadores pueden ingresar la identificación usando un teclado o escaneando un código de barras.
- **Informar de cantidad a la salida del trabajo**: establezca esta opción en *Sí* para solicitar a los trabajadores que aporten comentarios sobre los trabajos en curso al salir del trabajo. Cuando se establece en *No*, no se avisará a los trabajadores.
- **Bloquear empleado**: cuando esta opción se establece en *No*, se cerrará inmediatamente la sesión de los trabajadores cuando se registren (en un nuevo trabajo, por ejemplo). La interfaz volverá a la página de inicio de sesión. Cuando esta opción se establece en *Sí*, los trabajadores permanecerán conectados a la interfaz de ejecución de la planta de producción. Sin embargo, un trabajador puede cerrar sesión manualmente para que otro trabajador pueda iniciar sesión mientras la interfaz de ejecución de la planta de producción continúe ejecutándose con la misma cuenta de usuario del sistema. Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](config-job-card-device.md#assigned-users).
- **Usar el tiempo real de registro**: establezca esta opción en *Sí* para establecer la hora de cada nuevo registro en la hora exacta a la que el trabajador envió el registro. Cuando esta opción se establece en *No*, se utiliza en su lugar la hora de inicio de sesión. Por lo general, querrá establecer esta opción en *Sí*, si ha establecido las opciones **Bloquear empleado** o **Trabajador único**, en *Sí* en aquellos casos en los que los trabajadores suelen permanecer conectados durante períodos más largos.
- **Trabajador único**: establezca esta opción en *Sí* si solo un trabajador usa cada interfaz de ejecución de la planta de producción en el que esta configuración está activa. Cuando se establece esta opción en *Sí*, la opción **Bloquear empleado** se configura automáticamente en *Sí*. Además, esta opción elimina el requisito (y la capacidad) de que el trabajador inicie sesión con un identificador de distintivo (o similar). En lugar de ello, el trabajador inicia sesión en Microsoft Dynamics 365 Supply Chain Management con una cuenta de usuario del sistema vinculada a un *trabajador con tiempo registrado* (desde la tabla *trabajadores*) y se conecta a la interfaz de ejecución de la planta de producción como ese trabajador al mismo tiempo.
- **Permitir bloquear la pantalla táctil**: establezca esta opción en *Sí* para permitir que los trabajadores bloqueen la pantalla táctil de la interfaz de ejecución de la planta de producción para que puedan limpiarla. Cuando esta opción se establece en *Sí*, se agrega un botón **Bloquear pantalla para limpiar** a la página de inicio de sesión. Cuando un trabajador selecciona este botón, la pantalla táctil se bloquea temporalmente para evitar entradas no deseadas. También se muestra un temporizador de cuenta atrás. El trabajador ahora puede limpiar de forma segura el dispositivo y la pantalla. Cuando finaliza la cuenta descendente, la pantalla táctil se desbloquea automáticamente.
- **Duración del bloqueo de pantalla**: cuando la opción **Permitir bloqueo de pantalla táctil** está establecida en *Sí*, use esta opción para especificar la cantidad de segundos que la pantalla táctil debe estar bloqueada para su limpieza. La duración debe estar entre 5 y 120 segundos.
- **Generar matrícula**: establezca esta opción en *Sí* para generar una nueva matrícula cada vez que un trabajador usa la interfaz de ejecución de la planta de producción para informar como terminado. El número de matrícula de entidad de almacén se genera a partir de una secuencia numérica configurada en la página **Parámetros de gestión de almacén**. Cuando esta opción se establece en *No*, los trabajadores deben especificar una matrícula existente al informar de la conclusión.
- **Etiqueta de impresión**: establezca esta opción en *Sí* para imprimir una etiqueta de matrícula cuando un trabajador usa la interfaz de ejecución de la planta de producción para informar de su conclusión. La configuración de la etiqueta se configura en la ruta del documento, como se describe en [Diseño de ruta de documento para etiqueta de matrícula](../warehousing/document-routing-layout-for-license-plates.md).
- **Selección de pestaña** - Utilice la configuración de esta sección para elegir qué pestañas debe mostrar la interfaz de ejecución de la planta de producción cuando la configuración actual está activa. Puede diseñar tantas pestañas como necesite y luego agregarlas y organizarlas aquí según sea necesario. Para obtener detalles sobre cómo diseñar pestañas y trabajar con la configuración aquí, consulte [Diseñar la interfaz de ejecución del piso de producción](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Limpiar configuraciones de trabajo

Cuando el supervisor de la planta configura la interfaz de ejecución de la planta de producción, selecciona una configuración y un filtro de trabajo. Estas selecciones se almacenan en una tabla de referencia en Supply Chain Management, y el navegador usa un identificador que se almacena en una cookie local para encontrar la fila correcta en esa tabla. La tabla también registra la fecha y hora en que un trabajador inició sesión por última vez en cada dispositivo.

Un trabajo por lotes limpia periódicamente las entradas en la tabla de referencias de los dispositivos que no han registrado ninguna actividad en los últimos 60 días. También puede limpiar manualmente las entradas en cualquier momento siguiendo estos pasos.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. En el panel de acciones, seleccione **Limpiar configuraciones de cliente**.
1. En el cuadro de diálogo **Limpiar configuraciones de cliente**, establecer como valor del campo **Número de días** el número de días de inactividad (antes de hoy) que hay que tener en cuenta. Eliminará todas las configuraciones y los registros de inicio de sesión de los dispositivos que no han estado activos durante ese tiempo.
1. Seleccione **Aceptar** para limpiar las configuraciones relevantes, basándose en la configuración de **Número de días**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
