---
title: Empaquetar contenedores para envío
description: Este artículo describe el proceso de empaque que le permite validar artículos de inventario y empaquetarlos en contenedores.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 118b1c79d23cd1b5044ede9aa9c469409cd22166
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708793"
---
# <a name="pack-containers-for-shipment"></a>Empaquetar contenedores para envío

[!include [banner](../../includes/banner.md)]

El proceso de empaque de contnedores le permite validar artículos de inventario y empaquetarlos en contenedores. Durante este proceso, los trabajadores del almacén normalmente seleccionan artículos de inventario de las áreas de almacenamiento a granel y los trasladan a un área de embalaje. Allí, varios trabajadores del almacén verifican las cantidades y los tipos de artículos y los asignan a los tamaños de contenedor apropiados. Cuando un contenedor se empaqueta por completo, se cierra y se mueve al área de muelles de salida, donde se prepara para enviarse.

Los contenedores representan estructuras físicas en las que se empaquetan los artículos y puede realizar un seguimiento de la información del contenedor en el sistema. Esta información puede resultar útil durante la planificación del transporte, especialmente si calcula los gastos de envío en función de los contenedores. Antes de enviar, puede ver la cantidad de contenedores que se utilizan en un envío, los tipos de contenedores que se utilizan y las dimensiones físicas de cada contenedor (como el volumen y el peso totales).

Se pueden usar varias capacidades de almacén de salida relacionadas con los contenedores. Para obtener más información, consulte los siguientes artículos:

- [Creación de contenedores de oleada](wave-containerization.md)
- [Ordenación de salida](outbound-sorting.md)
- [Envío de paquetes pequeños](small-parcel-shipping.md)
- [Confirmar y transferir](confirm-and-transfer.md)
- [Establecer diferentes dimensiones para el embalaje y almacenamiento](packing-vs-storage-dimensions.md)
- [Trabajos de embalaje para empaquetar contenedores de salida y procesar envíos](packing-work.md)
- [Contenedores de embalaje con la aplicación móvil Warehouse Management](warehouse-app-packing-containers.md)
- [Escenario de ejemplo: contenedores de embalaje con la aplicación móvil Warehouse Management](warehouse-app-pack-containers-scenario.md)
- [Imprimir etiquetas de contenedores](print-container-labels.md)

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Configurar su almacén para utilizar operaciones de embalaje manual

Hay dos formas básicas de organizar sus operaciones de salida:

- **Creación y procesamiento de oleadas** – Los trabajadores seleccionan artículos según el trabajo del almacén de salida. Luego colocan los artículos directamente en una ubicación de envío saliente, donde están listos para su envío inmediato. Para obtener más información sobre la configuración y el uso de este proceso, consulte [Creación y procesamiento de oleadas](wave-processing.md).
- **Empaque manual en estaciones de empaque** – Este proceso tiene una operación adicional entre las operaciones de recolección y envío. En lugar de poner el inventario en una *ubicación de envío final en el muelle*, los trabajadores lo ponen en un *lugar de embalaje*. A continuación, gestionan el proceso de embalaje en la estación de embalaje utilizando la página **Paquete** del cliente web. Para habilitar este proceso, primero debe configurar su sistema como se describe en esta sección.

### <a name="set-up-warehouse-locations-for-packing"></a>Configurar ubicaciones de almacén para el embalaje

Debe tener al menos una ubicación de empaque donde los trabajadores colocarán los artículos de inventario para que puedan empaquetarse en contenedores. Para obtener más información sobre cómo crear ubicaciones de almacén, consulte [Configurar ubicaciones en un almacén con WMS](tasks\configure-locations-wms-enabled-warehouse.md). En las siguientes subsecciones se explica cómo crear y configurar ubicaciones de embalaje.

#### <a name="set-up-location-types-for-packing"></a>Configurar tipos de ubicación para embalaje

Debe definir un *Tipo de ubicacion* para los lugares de empaque. Los tipos de ubicación se pueden usar como opciones de filtrado para controlar los distintos procesos de gestión de almacenes. El nombre de cada tipo de ubicación generalmente describe algo sobre cómo se debe usar ese tipo de ubicación. El tipo de ubicación que configure aquí debe estar asociado con cada ubicación que se utilice para las operaciones de empaque.

Para configurar un tipo de ubicación, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Tipos de ubicación**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un tipo de ubicación a la cuadrícula.
1. Configure los siguientes campos para el nuevo tipo de ubicación:

    - **Tipo de ubicación**: escriba un nombre para el tipo de ubicación. Cada nombre debe ser único y debe describir algo sobre cómo se pretende utilizar el tipo de ubicación.
    - **Descripción**: escriba una breve descripción del tipo de ubicación.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Informar al sistema sobre el tipo de lugar de embalaje

Una vez que haya creado un tipo de ubicación, debe configurar su sistema para que lo reconozca como el tipo de ubicación que se usará para las operaciones de embalaje.

Siga estos pasos para configurar el tipo de ubicación que se utiliza para las operaciones de embalaje.

1. Vaya a **Gestión de almacenes \> Configurar \> Parámetros de gestión de inventario y almacenes**.
2. En la pestaña **General**, en la ficha desplegable **Tipos de ubicación**, establezca el campo **Tipo de lugar de embalaje** en el tipo de ubicación que usará para identificar las estaciones de empaque.

> [!NOTE]
> Si está actualizando una versión de Microsoft Dynamics AX, el estado *En embalaje* se ha quitado de los envíos y las cargas, porque no funcionaba de manera consistente y generaba datos redundantes. Por lo tanto, las páginas de lista **En envíos** y **Cargas en embalaje** han quedado obsoletas. Los contenedores que deben empaquetarse se rastrean en el nivel de ubicación.
>
> En versiones anteriores, definía la ubicación de embalaje utilizando el campo **ID de perfil para ubicación de embalaje** en la ficha **Embalaje** de la página **Parámetros de gestión de almacenes** para especificar un *perfil de ubicación*. En la versión actual, se utiliza el campo **Tipo de lugar de embalaje** en la ficha **General** de la página **Parámetros de gestión de almacenes** para especificar un *Tipo de ubicacion*, como se describe en este artículo. El nuevo campo está mejor alineado con el proceso para identificar ubicaciones de preparación y ubicaciones de envío final.
>
> Aunque puede seguir usando el antiguo campo **ID de perfil para ubicación de embalaje**, le recomendamos que empiece a utilizar el nuevo **Tipo de lugar de embalaje** en su lugar, porque el campo anterior eventualmente quedará obsoleto.
>
> Si borra la configuración del campo antiguo **ID de perfil para ubicación de embalaje** y luego guarda la página, el campo se desactivará permanentemente. Para instalaciones donde el campo **ID de perfil para ubicación de embalaje** nunca se ha utilizado, siempre estará deshabilitado. Después de borrar la configuración del campo **ID de perfil para ubicación de embalaje**, use la configuración que se describe en este artículo para configurar e identificar su ubicación de empaque.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Configurar perfiles de ubicación para ubicaciones de embalaje

Cada *perfil de ubicación* establece información y reglas que se aplican a las ubicaciones asociadas. Debido a que necesita al menos una ubicación para usar en las operaciones de empaque, debe crear un perfil de ubicación para ella además de un tipo de ubicación. Cada perfil puede ser utilizado por cualquier número de ubicaciones. Las ubicaciones que se utilizan para empacar deben configurarse para realizar un seguimiento de las matrículas.

Siga estos pasos para configurar un perfil de ubicación para una ubicación de embalaje.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. Seleccione un perfil existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En el encabezado del perfil nuevo o seleccionado, establezca los siguientes campos:

    - **Id. de perfil de ubicación**: especifique un identificador y un nombre exclusivos para el perfil de ubicación.
    - **Nombre** - Especifique un nombre descriptivo para el perfil.

1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Formato de ubicación** – Seleccione el formato de ubicación que se usará para la ubicación actual. Los formatos de ubicación son sistemas de nombres que se usan para crear nombres únicos y coherentes para distintos huecos de ubicación que se usan dentro de un almacén. Si aún no tiene el formato que necesita, puede crearlo yendo a **Gestion de almacenes \> Configuración \> Depósito \> Formatos de ubicación**. Para obtener más información, consulte [Configurar ubicaciones en un almacén con WMS](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Tipo de ubicacion** – Seleccione el tipo de ubicación que está configurado como el tipo de ubicación de embalaje en la página **Parámetros de gestión de almacenes**, como se describe anteriormente en este artículo.
    - **Utilice el seguimiento de matrículas** – Para las ubicaciones de embalaje, establezca esta opción en *Sí*. El sistema debe poder realizar un seguimiento de las identificaciones de matrículas en las ubicaciones de empaque, de modo que pueda controlar el proceso de empaque.
    - **Permitir inventario negativo** – Para las ubicaciones de embalaje, establezca esta opción en *No*.
    - **Permitir artículos combinados** – Para las ubicaciones de embalaje, establezca esta opción en *Sí*. Esta configuración es necesaria porque normalmente se llevan muchos números de artículo diferentes a las ubicaciones de embalaje al mismo tiempo.
    - **Permitir estados de inventario combinados** – Para las ubicaciones de embalaje, establezca esta opción en *Sí*. Esta configuración es necesaria porque los artículos que tienen distintos estados de inventario normalmente se llevan a las ubicaciones de embalaje al mismo tiempo.
    - **Permitir lotes de inventario combinados** – Para las ubicaciones de embalaje, establezca esta opción en *Sí*. Esta opción se establece automáticamenet en *Sí*, siempre que la opción **Permitir artículos combinados** se configura como *Sí*.

#### <a name="set-up-packing-locations"></a>Configurar ubicaciones de embalaje

Debe tener al menos una *ubicación* donde los trabajadores colocarán los artículos de inventario que deben empaquetarse en contenedores.

Para configurar una ubicación de embalaje, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. En el Panel de acciones, haga clic en **Nuevo** para agregar una ubicación.
1. Establezca los siguientes campos para la nueva ubicación:

    - **Almacén** - Especifique el almacén donde debe existir la ubicación de empaque.
    - **Ubicación**: Especifique un nombre para la nueva ubicación.
    - **ID de perfil de ubicación** – Asegúrese de especificar el ID que creó en la sección anterior.

## <a name="set-up-the-packing-process"></a>Configurar el proceso de embalaje

Esta sección describe cómo configurar los ajustes que habilitan el proceso de empaque y permiten que los trabajadores empaquen el inventario en contenedores.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Configurar políticas de embalaje de contenedores

Cada *política de embalaje de contenedores* define cómo se debe procesar un contenedor. Cada vez que cree un nuevo contenedor, también seleccionará una política de empaque de contenedores para aplicarle.

Siga estos pasos para configurar una directiva de embalaje de contenedores.

1. Vaya a **Administración de almacenes \> Configurar \> Contenedores \> Perfiles de cierre de contenedor**.
1. Seleccione una política existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En el encabezado de la directiva nueva o seleccionada, establezca los siguientes campos:

    - **Política de embalaje de contenedores** – Ingrese un nombre único para la política.
    - **Descripción**: especifique un nombre descriptivo para la política.

1. En la pestaña **Visión general**, establezca los campos siguientes: Estos campos le permiten especificar qué acciones se deben tomar cuando el contenedor está cerrado, si operar con o sin creación de trabajo y cuándo se debe liberar el contenedor de la estación de empaque.

    - **Almacén** - Seleccione el almacén donde se aplica la política de empaque.
    - **Ubicación predeterminada para el envío final** – Especifique la ubicación preferida para el contenedor después de que esté cerrado. Este campo solo está disponible cuando el campo **Directiva de liberación de contenedor** se establece en *Hacer que esté disponible en la ubicación de envío final*.
    - **Ubicación predeterminada para ordenar** – Este campo se utiliza con la capacidad [clasificación de salida](outbound-sorting.md).
    - **Unidad de peso** – Seleccione la unidad de medida predeterminada que se usará cuando se cierre y se manifieste un contenedor. Por lo general, esta unidad de medida será la unidad de medida utilizada por una báscula en la estación de empaque. Este campo se aplica a pólizas con o sin creación de trabajo.
    - **Política de cierre de contenedores** – Seleccione una de las siguientes opciones para definir lo que debe ocurrir cuando se cierra el contenedor:

        - *Liberación automática* – El contenedor se considerará liberado de la estación de empaque, y la acción que se especifica en el campo **Política de liberación de contenedores** se activará.
        - *Liberación retardada* – El contenedor no se liberará inmediatamente de la estación de embalaje. Un trabajador del almacén debe liberarlo manualmente más tarde.
        - *Opcional* – Mientras un trabajador está cerrando el contenedor, podrá elegir si el contenedor debe ser liberado.

        Si la estación de empaque maneja principalmente contenedores individuales que se envían directamente a los clientes, el enfoque más natural es liberar los contenedores de inmediato. Si la estación de empaque maneja envíos que consisten en varios contenedores o incluso paletas, probablemente sea mejor retrasar la liberación hasta que se haya empacado todo el envío o la paleta y esté listo para su recolección.

    - **Política de liberación de contenedores** – Seleccione una de las siguientes opciones para definir lo que debe ocurrir cuando el contenedor se libera en la ubicación de embalaje:

        - *Poner a disposición en la ubicación de envío final* – Actualice el contenedor a la ubicación de envío final. Si selecciona esta opción, use el campo **Ubicación predeterminada para el envío final** para especificar la ubicación preferida para el contenedor después de que esté cerrado.
        - *Crear trabajo para mover el contenedor desde la estación de empaque* – Cree trabajo para mover el contenedor desde la estación de empaque al área de preparación o directamente a la puerta de la bahía. Utilice el campo **Plantilla de trabajo** para especificar la plantilla de trabajo que debe aplicarse cuando se crea el trabajo para el contenedor.
        - *Asignar contenedor a la posición de clasificación de salida* – Esta opción se utiliza con la capacidad [clasificación de salida](outbound-sorting.md).

        En la mayoría de los casos, le recomendamos que cree trabajo para mover contenedores, ya que este enfoque representa mejor los procesos manuales reales en el almacén. Sin embargo, para escenarios simples, o situaciones donde la estación de empaque está ubicada directamente en el área de la puerta de la bahía, podría ser preferible que el contenedor esté disponible de inmediato en la ubicación de envío final.

    - **Plantilla de trabajo**: seleccione la plantilla de trabajo que debe aplicarse cuando se crea el trabajo para el contenedor. Este campo está disponible sólo cuando el campo **Política de liberación de contenedores** se establece en *Crear trabajo para mover el contenedor desde la estación de empaque* y relacionado con un tipo de orden de trabajo que se denomina *Recogida de contenedores llenos*. Para obtener más información, vea [Plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).

    En los pasos restantes, configurará los ajustes relacionados con *manifiestos*. La creación de manifiestos es el proceso de especificar el peso de un contenedor, grupo de contenedores o envío, junto con el ID de seguimiento que se recibe de un proveedor de transporte. Dynamics 365 Supply Chain Management no se integra con sistemas de proveedores de transporte externos. En su lugar, los trabajadores del almacén deben imprimir las etiquetas que reciben del proveedor de transporte y luego escanear un número de seguimiento cuando completan el procedimiento de manifiesto.

    Debido a que los requisitos del manifiesto varían de un cliente a otro, e incluso de un envío a otro, las políticas de empaque permiten una flexibilidad significativa en el flujo de trabajo. Puede configurar manifiestos para contenedores, grupos de contenedores y envíos en cualquier combinación.

    Si utiliza un procedimiento de manifiesto de varios niveles, los trabajadores deben manifestar todos los contenedores antes de manifestar el grupo de contenedores relacionado y deben manifestar todos los grupos de contenedores antes de manifestar el envío relacionado.

1. En la ficha rápida **Manifiesto de contenedor**, puede establecer los siguientes campos:

    - **Manifiesto automático al cierre del contenedor** – Establezca esta opción en *Sí* para aplicar la información del manifiesto como parte del proceso de cierre del contenedor. Si no está utilizando la integración de transporte, la información debe registrarse manualmente.
    - **Manifiesto de requisitos para el contenedor.** - Selecciona una de las siguientes opciones:

        - *Ninguna*: no se utilizará ningún proceso de manifiesto.
        - *Manual* – El flujo de trabajo de embalaje requerirá la manifestación. El sistema no permitirá que se cierre o libere un contenedor hasta que se complete el manifiesto.
        - *Gestión de transporte* – La manifestación se realizará a través de motores de tarifas de gestión de transporte (TMS). Debido a que esta opción requiere un desarrollo personalizado para implementar un motor específico para el proveedor de transporte, no funcionará en la versión actual.

    - **Imprimir el contenido del contenedor** – Establezca esta opción en *Sí* para imprimir automáticamente el informe de contenido del contenedor cuando un contenedor se registra como cerrado. También se puede imprimir el informe a petición.

1. Sobre la ficha rápida **Manifiesto de grupo de contenedores**, en el campo **Manifiesto de requisitos para el grupo de contenedores**, seleccione una de las siguientes opciones:

    - *Ninguna* – El manifiesto del grupo de contenedores no se incluirá como requisito en el flujo de trabajo de embalaje.
    - *Manual* – El manifiesto del grupo de contenedores se incluirá como requisito en el flujo de trabajo de embalaje. Todos los contenedores que se incluyen en el grupo se deben cerrar para poder crear manifiestos para el grupo. Seleccione esta opción si debe completar un manifiesto para cada grupo de contenedores que se empaqueta en la estación de empaque. Por lo general, seleccionará esta opción si los contenedores se empacan en un palé y se manifiesta todo el palé.

    > [!NOTE]
    > La versión actual no admite informes de manifiesto para grupos de contenedores y no hay soporte de motor TMS para grupos de contenedores.

1. En la ficha rápida **Manifiesto de envío**, puede establecer los siguientes campos:

    - **Manifiesto de requisitos para el envío** - Seleccione una de las siguientes opciones:

        - *Ninguna* – El manifiesto de envío no se incluirá como requisito en el flujo de trabajo de embalaje.
        - *Manual* – El manifiesto de envío se incluirá como requisito en el flujo de trabajo de embalaje. No se pueden liberar contenedores para un envío hasta que se complete el manifiesto.
        - *Gestión de transporte* – Los manifiestos se crearán a través de motores de tarifas de TMS. Debido a que esta opción requiere un desarrollo personalizado para implementar un motor específico para el proveedor de transporte, no funcionará en la versión actual.

        El manifiesto de envío debe estar habilitado si debe completar un manifiesto para todo el envío que se embala en la estación de embalaje. Por lo general, se usa cuando se requiere un manifiesto consolidado, aunque el envío consta de varios contenedores o grupos de contenedores.

    - **Imprimir albarán** – Establezca esta opción en *Sí* para imprimir automáticamente el albarán como parte del manifiesto de envío. También se puede imprimir el albarán a petición.

### <a name="set-up-container-types"></a>Configurar tipos de contenedor

Durante el proceso de embalaje manual, se deben crear contenedores antes de que se puedan embalar artículos en ellos. Cada contenedor debe basarse en un *tipo de contenedor*, que define el volumen físico máximo y la capacidad de peso de un contenedor.

Para crear un tipo de contenedor, siga estos pasos.

1. Vaya a **Warehouse Management \> Configurar \> Contenedores \> Tipos de contenedor**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un tipo de contenedor.
1. Configure los siguientes campos para el nuevo tipo de contenedor:

    - **Código de tipo de contenedor** – Ingrese una ID única para el tipo de contenedor.
    - **Descripción**: escriba una descripción del nuevo tipo de contenedor.
    - **Peso tara**: especifique el peso real o estimado del contenedor.
    - **Peso neto máximo**: especifique el peso máximo que el contenedor puede soportar.

1. En la sección **Dimensiones del contenedor**, en los campos **Longitud**, **Ancho**, **Altura** y **Volumen**, introduzca las dimensiones físicas del propio contenedor.
1. En la sección **Máximos**, en los campos **Longitud**, **Ancho**, **Altura** y **Volumen**, introduzca las dimensiones físicas máximas que el contenedor puede manejar.
1. Puede definir atributos adicionales para tipos de contenedores que están asociados con otras operaciones que usan contenedores. Para obtener más información, consulte [Creación de contenedores](wave-containerization.md).

> [!NOTE]
> Para el proceso de embalaje manual, el sistema utiliza sólo el valor del campo **Peso neto máximo** y el valor del campo **Volumen** en la sección **Máximos**.

### <a name="set-up-packing-profiles"></a>Configurar perfiles de embalaje

*Perfiles de embalaje* son necesarios para el proceso de embalaje. Se pueden seleccionar o establecer de forma predeterminada cuando inicia una operación de embalaje en la página **Paquete**.

Para configurar un perfil de embalaje, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.
1. Seleccione un perfil existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En el encabezado del perfil nuevo o seleccionado, establezca los siguientes campos:

    - **Id. de perfil de embalaje**: especifique un identificador corto para el perfil.
    - **Descripción**: escriba una descripción del perfil de embalaje.
    - **Política de embalaje de contenedores** – Seleccione la política de embalaje que se aplica al perfil. Para obtener más información, consulte la sección [Configurar políticas de contenedor](#packing-policy) de este artículo.
    - **Modo de id. de contenedor**: seleccione si se generará automáticamente un id. de contenedor cuando se cree un contenedor o si se creará manualmente.
    - **Tipo de contenedor**: seleccione el tipo de contenedor que se usa de forma predeterminada cuando se crea un nuevo contenedor.
    - **Crear contenedor automáticamente al cerrar el contenedor** – Seleccione esta casilla de verificación para crear automáticamente un nuevo contenedor si el contenedor anterior está cerrado y quedan una o más líneas en el envío actual.

### <a name="set-up-warehouse-workers"></a>Configurar trabajadores de almacén

Todo usuario o trabajador que envasa envases utilizando la página **Paquete** del cliente web o el código de actividad *Embalaje* en la aplicación móvil de gestión de almacenes debe tener una cuenta de usuario asociada con un registro *trabajador/persona* al que se asignan los derechos de acceso de seguridad requeridos. (Para obtener más información sobre la configuración de los usuarios, consulte [Crear nuevos usuarios](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md)).

Siga estos pasos para configurar un registro *trabajador/persona* para el proceso de embalaje.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un usuario trabajador.
1. Establezca el campo **Trabajador** en el registro de trabajador existente que se define en el módulo **Recursos humanos** para el usuario que completará el proceso de embalaje.
1. En la ficha desplegable **Perfil**, establezca los siguientes campos:

    - **Política de embalaje de contenedores** - Seleccione una política de empaque de contenedores que defina cómo se deben procesar los contenedores en la estación de empaque. La política de empaque de contenedores que seleccione aquí será preseleccionada para el trabajador cuando abra la estación de empaque. Para obtener más información, consulte la siguiente publicación de blog: [Funcionalidad de empaque mejorada](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **ID de perfil de embalaje** - Seleccione un ID de perfil de embalaje que defina la política de embalaje y la configuración del contenedor que se deben utilizar. Si el ID de perfil de embalaje seleccionado está asociado con una política de embalaje de contenedores, no podrá cambiar la configuración del campo **Política de embalaje de contenedores** en esta página.

1. Sobre la ficha desplegable **Estación de embalaje por defecto**, seleccione el sitio, el almacén y la ubicación predeterminados que se aplican al trabajador.
1. Si el trabajador utilizará la aplicación móvil Gestión de almacenes para gestionar y registrar su trabajo de embalaje de contenedores, en la ficha desplegable **Usuarios**, configure una o más cuentas que el trabajador puede usar para iniciar sesión en la aplicación. Para obtener más información, consulte [Cuentas de usuario de dispositivo móvil](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Supuesto de ejemplo

Esta sección proporciona un escenario de ejemplo que muestra cómo crear un pedido y empaquetar los artículos.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar este escenario como guía para usar la característica en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores para cada configuración aquí descrita.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Inicie sesión como un usuario que puede hacer el trabajo de embalaje

Inicie sesión en Supply Chain Management con una cuenta de usuario que tenga los permisos necesarios para empacar contenedores. El usuario *Julia Funderburk* se incluye como parte de los datos de demostración y tiene los permisos necesarios. Este usuario tiene el ID de usuario *Administración*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Crear un pedido de venta y completar el trabajo

Siga estos pasos para crear una orden de venta y completar el trabajo de mover los artículos pedidos a la estación de empaque.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione *US-005*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. El nuevo pedido de venta se abre e incluye una única línea vacía en la ficha rápida **Líneas de orden de venta**. Establezca los siguientes valores para la nueva línea de pedido:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *2*
    - **Sitio**: *6*
    - **Almacén**: *62*

1. Con la línea de pedido aún seleccionada, seleccione **Inventario \> Reserva** en la barra de herramientas de la ficha desplegable **Líneas de pedido de ventas**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Un mensaje muestra los ID de envío y oleada del pedido.

1. Con la línea de pedido aún seleccionada, seleccione **Almacén** \> **Detalles de trabajo** en la barra de herramientas de la ficha desplegable **Líneas de pedido de ventas**. Si usa el procesamiento por lotes para ejecutar sus olas, es posible que deba esperar un poco para que se cree el trabajo.
1. En la página **Trabajo**, en el panel de acciones, en la pestaña **Trabajo**, seleccione **Completar trabajo**.
1. En la página **Finalización de trabajo**, establezca el campo **Id. de usuario** en *62*.
1. En el panel de acciones, seleccione **Validar trabajo**.
1. Cuando reciba un mensaje que indique que su trabajo es válido, seleccione **Completar trabajo** para completar el proceso de elegir los artículos del inventario y ponerlos en la ubicación *Paquete*.
1. Tome nota del valor **Identificación del envío** que se muestra para el trabajo en la cuadrícula superior.

### <a name="pack-the-ordered-items-into-a-container"></a>Empacar los artículos pedidos en un contenedor

Los artículos del inventario ahora se han llevado al área de empaque y están listos para ser empacados en contenedores. Para crear un nuevo contenedor en el sistema y empaquetarlo, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Paquete**.
1. En el cuadro de diálogo **Seleccionar estación de embalaje**, establezca los siguientes valores:

    - **Sitio**: *6*
    - **Almacén**: *62*
    - **Ubicación:** *Paquete*
    - **Id. del perfil de empaquetado**: *WH62*

1. Seleccione **Aceptar**.
1. En la página **Paquete**, en el campo **Matrícula o envío**, introduzca el id. de envío que anotó antes. Ahora debería ver los elementos restantes desempaquetados en la ficha rápida **Líneas abiertas**.
1. En el Panel de acciones, seleccione **Nuevo contenedor** para crear un contenedor en el sistema.
1. En el cuadro de diálogo **Id. del nuevo contenedor**, establezca el campo **Tipo de contenedor** en *Caja pequeña*.
1. Seleccione **Aceptar** para crear el contenedor.
1. Seleccione **Aceptar** para volver a la página **Empaquetar**. La ficha despelgable **Contenedores abiertos** ahora muestra el valor de **Id. de contenedor** del contenedor que ha creado.
1. Para este escenario, empacará solo uno de los artículos pedidos por ahora. Por tanto, en la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:

    - **Cantidad:** *1.00*
    - **Identificador**: *A0001*

    Inmediatamente después de seleccionar el valor **Identificador**, la página actualiza las fichas desplegables **Líneas abiertas** y **Todas las líneas** para indicar que se ha empaquetado un artículo. Ahora debería haber empacado una de las dos piezas del artículo *A0001*.

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para llenar el valor **Peso bruto** predeterminado.
1. Seleccione **Aceptar** para cerrar el contenedor.

> [!TIP]
> Hay varias formas de ver los contenedores según el contexto. Por ejemplo, cuando empaqueta un envío, suele ser útil ver los contenedores que forman parte del envío o todos los contenedores que se encuentran físicamente en una estación de empaque. La página **Estación de embalaje** tiene botones que puede usar para ver todos los contenedores abiertos y cerrados en una estación de empaque. Estas vistas no están restringidas a un envío específico. Pueden ser muy útiles en situaciones en las que un trabajador está empacando un contenedor y otro trabajador está manifestando y liberando el contenedor.
>
> También está disponible una vista consolidada de todos los contenedores. Esta vista es útil principalmente para usuarios que trabajan fuera del contexto de una sola estación de empaque. Para verla, vaya a **Gestión de almacenes \> Empaquetado y puesta en contenedores \> Contenedores**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
