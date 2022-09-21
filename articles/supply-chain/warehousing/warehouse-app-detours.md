---
title: Configurar desvíos para pasos en los elementos del menú del dispositivo móvil
description: Este artículo describe cómo configurar desvíos para los elementos del menú para que los trabajadores puedan estacionar la tarea actual, realizar otra tarea y luego regresar a la tarea original sin perder ninguna información.
author: Mirzaab
ms.date: 09/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: d8d3d434077fdb145291e2298055f692b78db3d6
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428073"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Configurar desvíos para pasos en los elementos del menú del dispositivo móvil

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Las características que se describen en este artículo se aplican solo a la nueva aplicación móvil Warehouse Management. No afectan a la antigua aplicación de almacén, que ahora está obsoleta.

Este artículo describe cómo configurar desvíos para los elementos del menú para que los trabajadores puedan "estacionar" la tarea actual, realizar otra tarea y luego regresar a la tarea original sin perder ninguna información.

Un desvío es un elemento de menú independiente que se puede abrir desde un paso en una tarea principal. Al final del desvío, el trabajador vuelve al lugar donde dejó la tarea principal. Durante la configuración, especifica el elemento del menú que debe actuar como un desvío. También selecciona qué valores de campo de la tarea principal deben enviarse (copiarse) automáticamente al desvío e introducirse allí. Por lo tanto, debe comprender en qué parte del flujo de tareas desea que el desvío esté disponible para los trabajadores. También debe asegurarse de que la información que se debe copiar al desvío esté disponible para ese paso del flujo de tareas.

## <a name="enable-detours-in-your-system"></a>Habilitar desvíos en su sistema

Antes de poder configurar desvíos para pasos en los elementos del menú del dispositivo móvil, debe completar el siguiente procedimiento para habilitar las funciones requeridas y generar los nombres de campo requeridos en la aplicación móvil Warehouse Management.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Asegúrese de que la función *Instrucciones paso a paso de la aplicación de almacén* está activada para su sistema. A partir de la versión 10.0.29 de Supply Chain Management, esta función está activada de forma predeterminada. Para obtener más información sobre la característica *Instrucciones de los pasos de la aplicación de almacén*, consulte [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](mobile-app-titles-instructions.md). Esta característica es un requisito previo para la característica *Desvíos de aplicaciones de Warehouse Management*.
1. Active las siguientes funciones, que proporcionan la funcionalidad descrita en este artículo:
    - *Desvíos de la aplicación Warehouse Management*<br>(A partir de la versión 10.0.29 de Supply Chain Management, esta función está activada de forma predeterminada).
    - *Desvíos de varios niveles para la aplicación móvil Warehouse Management*
1. Si la característica *Desvíos de la aplicación Warehouse Management* y/o *Desvíos multi nivel para la aplicación móvil Warehouse Management* no estaba ya activada, actualice los nombres de los campos en la aplicación móvil Warehouse Management yendo a **Warehouse Management \> Configuración \> Dispositivo móvil \> Nombres de campo de Warehouse Management** y seleccione **Crear configuración predeterminada**. Para más información, consulte [Configurar campos para la aplicación](configure-app-field-names-priorities-warehouse.md).
1. Repita el paso anterior para cada entidad jurídica (empresa) en la que utilice la aplicación móvil Warehouse Management.

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Configurar un desvío de una invalidación específica del menú

Utilice el siguiente procedimiento para configurar un desvío de una invalidación específica del menú.

1. Cree una invalidación específica del menú para el menú y el paso relevantes como se describe en [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](mobile-app-titles-instructions.md).
1. Busque la combinación de los valores de **Id. de paso** y **Nombre del elemento del menú** que desea editar y luego seleccione el valor en la columna **Id. de paso**.
1. En la página que aparece, en la ficha desplegable **Desvíos disponibles (elementos del menú)**, puede especificar el elemento de menú que debe actuar como un desvío. También puede seleccionar qué valores de campo de la tarea principal deben enviarse automáticamente desde y hasta el desvío. Para ver ejemplos que muestran cómo usar esta configuración, consulte los escenarios más adelante en este artículo.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a>Escenario de ejemplo 1: selección de ventas donde una consulta de ubicación actúa como un desvío

Este escenario muestra cómo configurar una consulta de ubicación como un desvío en un flujo de tareas de selección de ventas dirigido por el trabajador. Este desvío permitirá a los trabajadores buscar todas las matrículas de entidad en el lugar donde están recogiendo y seleccionando las placas de entidad que quieren usar para completar la selección. Este tipo de desvío puede resultar útil si el código de barras está dañado y, por lo tanto, el dispositivo de escáner no puede leerlo. Alternativamente, podría ser útil si un trabajador debe saber lo que realmente está disponible en el sistema. Tenga en cuenta que este escenario solo funciona si realiza la selección en ubicaciones controladas por matrículas.

### <a name="enable-sample-data"></a>Habilitar datos de muestra

Para usar los registros de ejemplos y valores especificados para trabajar en este escenario, debe usar un sistema donde se hayan instalado los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. También debe seleccionar la entidad legal **USMF** antes de comenzar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Crear una invalidación específica del menú y configurar el desvío para el escenario 1

En este procedimiento, configurará un desvío para el elemento del menú **Selección de ventas** en el paso de la matrícula de entidad.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.
1. Encuentre el id. de paso con el nombre *LicensePlateId* y selecciónelo.
1. En el panel de acciones, seleccione **Agregar configuración de paso**.
1. En el cuadro de diálogo desplegable, utilice el campo **Elemento de menú** para buscar y seleccionar *Selección de ventas*.
1. Seleccione **Aceptar**.
1. Aparece la página de detalles de la invalidación que acaba de crear. En la ficha desplegable **Desvíos disponibles (elementos de menú)**, seleccione **Agregar** en la barra de herramientas.
1. En el cuadro de diálogo **Agregar desvío**, seleccione **Consulta de ubicación** como el desvío que estará disponible en la aplicación móvil Warehouse Management.
1. Seleccione **Aceptar**.
1. En la ficha desplegable **Desvíos disponibles (elementos de menú)**, seleccione el desvío que acaba de agregar y luego seleccione **Seleccionar campos para enviar** en la barra de herramientas.
1. En el cuadro de diálogo **Seleccionar campos para enviar**, especifique la información que se debe enviar hacia y desde el desvío. En este escenario, está permitiendo que los trabajadores utilicen la ubicación que deben elegir como entrada para el desvío de consulta de ubicación. Por lo tanto, en la sección **Enviar desde selección de ventas**, seleccione **Agregar** en la barra de herramientas para agregar una fila a la cuadrícula. Después, establezca los siguientes valores para la fila nueva:

    - **Copiar de Selección de ventas:** *Ubicación*
    - **Pegar en la consulta de ubicación:** *Ubicación*

1. Como el desvío en este escenario se configura en el paso de la matrícula de entidad, será útil si los trabajadores pueden llevar la matrícula de la consulta al flujo principal. Por lo tanto, en la sección **Recuperar desde solicitud de ubicación**, seleccione **Agregar** en la barra de herramientas para agregar una fila a la cuadrícula. Después, establezca los siguientes valores para la fila nueva:

    - **Copiar de la consulta de ubicación:** *Matrícula de entidad*
    - **Pegar en Selección de ventas:** *Matrícula de entidad*

1. Seleccione **Aceptar**.

El desvío ahora está completamente configurado. Un botón para iniciar el desvío **Consulta de ubicación** ahora aparecerá en el paso de la matrícula de entidad para el elemento de menú **Selección de ventas**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Completar una selección de ventas en un dispositivo móvil y usar el desvío

En este procedimiento, completará una selección de ventas mediante la aplicación móvil Warehouse Management. Utilizará el desvío que acaba de configurar para encontrar la matrícula de entidad que utilizará para completar el paso de selección.

1. En Microsoft Dynamics 365 Supply Chain Management, cree un pedido de ventas que requiera un paso de selección para realizar la selección en una ubicación con seguimiento de matrículas de entidad. Después, lance el pedido de ventas al almacén. Anote el identificador de trabajo que se genera.
1. Abra la aplicación móvil Warehouse Management e inicie sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando *24* como el Id. de usuario y *1* como la contraseña).
1. Seleccione el menú **Salida** y luego seleccione el elemento de menú **Selección de ventas**.
1. Siga las instrucciones para introducir datos en la pantalla para escribir el id. de trabajo que se generó en el paso 1.
1. En el paso que contiene el texto **Escanear una matrícula**, abra el menú de acciones. Debería ver un nuevo botón etiquetado como **Consulta de ubicación**. Una flecha en la esquina superior izquierda indica que el botón iniciará un desvío. Seleccione **Consulta de ubicación**.
1. Se inicia el desvío. En la página siguiente, confirme la ubicación que se copió del flujo principal.
1. En la lista de matrículas disponibles en la ubicación, toque la matrícula que desea copiar al flujo principal. Luego seleccione el botón **Atrás**.
1. Regresará al flujo principal de selección de ventas y la matrícula de entidad se ha copiado desde el desvío. Confirme el valor para continuar con el siguiente paso.
1. Ahora puede completar el resto del flujo estándar si introduce las instrucciones de introducción de datos solicitadas.

El trabajo del almacén ahora está terminado. El trabajador abrió con éxito un desvío para realizar una tarea secundaria (consulta de ubicación) sin perder su lugar en la tarea principal y recuperó la información necesaria para completar la tarea principal.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Escenario de ejemplo 2: consulta de artículo con desvíos de movimiento y ajuste

Este escenario muestra cómo configurar el movimiento y los ajustes como múltiples desvíos en el flujo de tareas de consulta de ubicación. Esta capacidad puede ser útil en situaciones en las que un trabajador llega a una ubicación, encuentra que el inventario en la ubicación difiere de lo que está registrado en el sistema y, por lo tanto, debe ajustar o mover mercancías.

Puede reemplazar la consulta de ubicación con una consulta de matrícula de entidad o una consulta de artículo según lo requiera.

### <a name="enable-sample-data"></a>Habilitar datos de muestra

Para usar los registros de ejemplos y valores especificados para trabajar en este escenario, debe usar un sistema donde se hayan instalado los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. También debe seleccionar la entidad legal **USMF** antes de comenzar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Crear una invalidación específica del menú y configurar el desvío para el escenario 2

En este procedimiento, configurará un desvío para el elemento del menú **Selección de ventas** en el paso de la matrícula de entidad.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.
1. Encuentre y seleccione el id. de paso con el nombre *LocationInquiryList*.

    > [!NOTE]
    > Para utilizar una consulta de artículo en lugar de una consulta de ubicación, seleccione una fila donde se nombre el id. de paso *ItemInquiryList*. Para utilizar una consulta de matrícula, seleccione una fila en la que se nombre el id. de paso *LPInquiryList*.

1. En el panel de acciones, seleccione **Agregar configuración de paso**.
1. En el cuadro de diálogo desplegable, utilice el campo **Elemento de menú** para buscar y seleccionar *Consulta de ubicación*.
1. Seleccione **Aceptar**.
1. Aparece la página de detalles de la invalidación que acaba de crear. En la ficha desplegable **Desvíos disponibles (elementos de menú)**, seleccione **Agregar** en la barra de herramientas.
1. En el cuadro de diálogo **Agregar desvío**, seleccione **Movimiento** como el desvío que estará disponible en la aplicación móvil Warehouse Management.
1. Seleccione **Aceptar**.
1. En la ficha desplegable **Desvíos disponibles (elementos de menú)**, seleccione el desvío que acaba de agregar y luego seleccione **Seleccionar campos para enviar** en la barra de herramientas.
1. En el cuadro de diálogo **Seleccionar campos para enviar**, especifique la información que se debe enviar hacia y desde el desvío. En este escenario, espera que los trabajadores busquen ubicaciones controladas por matrículas. Por lo tanto, será útil copiar la matrícula de entidad de la consulta al desvío **Movimiento**. En la sección **Enviar desde selección de ventas**, seleccione **Agregar** en la barra de herramientas para agregar una fila a la cuadrícula. Después, establezca los siguientes valores para la fila nueva:

    - **Copiar desde la consulta de ubicación:** *Ubicación*
    - **Pegar en Movimiento**: *Ubicación / N.º licencia*

    En este desvío, no espera que se vuelva a copiar ninguna información, porque el flujo principal era una consulta en la que no se requieren pasos adicionales.

1. Seleccione **Aceptar**.

El desvío ahora está completamente configurado. Un botón para iniciar el desvío **Movimiento** ahora aparecerá en el paso de la matrícula de entidad para el elemento de menú **Consulta de ubicación**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Hacer una consulta de ubicación en un dispositivo móvil y usar el desvío

En este procedimiento, llevará a cabo una consulta de ubicación mediante la aplicación móvil Warehouse Management. Luego utilizará el desvío para completar un movimiento de mercancías.

1. Abra la aplicación móvil Warehouse Management e inicie sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando *24* como el Id. de usuario y *1* como la contraseña).
1. Seleccione el menú **Inventario** y luego seleccione el elemento de menú **Consulta de ubicación**.
1. Introduzca una ubicación para solicitar información, como *FL-001*.
1. Cuando aparezca la lista, toque y mantenga presionada una de las tarjetas que contiene para mostrar los desvíos disponibles.
1. Seleccione **Movimiento**.
1. Observe que la matrícula se ha copiado de la tarjeta que seleccionó. Confirme el valor.
1. Ahora puede seguir el flujo de tareas estándar para completar el movimiento. Una vez completado el trabajo, abra el menú de acciones y seleccione **Cancelar**.
1. Volverá a la página **Consulta de ubicación**. Tenga en cuenta que los valores no se actualizan automáticamente. Por lo tanto, debe actualizar manualmente la página para ver los cambios del desvío de movimiento.

> [!NOTE]
> La característica *Desvíos de varios niveles para la aplicación móvil Warehouse Management* le permite definir desvíos de varios niveles (desvíos dentro de desvíos), lo que permitirá a los trabajadores saltar de un desvío existente dos por segundo y luego regresar. La función admite dos niveles de desvíos listos para usar y, si es necesario, puede personalizar su sistema para que admita tres o más niveles de desvíos mediante la creación de extensiones de código en la tabla `WHSWorkUserSessionState`.
