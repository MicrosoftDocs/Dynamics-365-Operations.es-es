---
title: 'Consolidación de artículos: utilización de ubicación'
description: Este tema proporciona información sobre la funcionalidad que facilita a los gerentes de almacén ver y filtrar la utilización volumétrica de ubicaciones en todo el almacén. Los gerentes pueden seleccionar ubicaciones y crear trabajos de movimiento de inventario directamente desde la página Consolidación de artículos para consolidar artículos y, por lo tanto, hacer un mejor uso del espacio de almacén.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 97ebc9ff9c50ec5e6bd7ee62b486ce453da420127f546b3199cfba4f3d610a07
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757551"
---
# <a name="item-consolidation---location-utilization"></a>Consolidación de artículos: utilización de ubicación

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre la funcionalidad que facilita a los gerentes de almacén ver y filtrar la utilización volumétrica de ubicaciones en todo el almacén. Los gerentes pueden seleccionar ubicaciones y crear trabajos de movimiento de inventario directamente desde la página **Consolidación de artículos** para consolidar artículos y, por lo tanto, hacer un mejor uso del espacio de almacén.

## <a name="turn-on-the-features"></a>Activar las características

Antes de poder usar las funciones que se describen en este tema, debe activarlas en su sistema. Los administradores pueden usar la configuración de [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas funciones y activarlas si es necesario. Active las dos siguientes características, en el orden en que se enumeran. (Ambas características son para el módulo **Gestión de almacenes**).

1. Estado de ubicación de almacén
2. Uso de la ubicación de consolidación de artículos

## <a name="warehouse-location-status"></a>Estado de ubicación de almacén

La característica *Estado de ubicación del almacén* agrega cuatro nuevos campos a la página **Ubicaciones** para rastrear información adicional sobre el estado actual de la ubicación:

- **Número de artículo**: el artículo que se encuentra actualmente en la ubicación. Si la ubicación contiene varios artículos, este campo estará en blanco.
- **Fecha y hora de la última actividad**: la marca de tiempo de la última transacción de almacén que se realizó en la ubicación.
- **Fecha de vencimiento**: la fecha en la que se llevó al almacén el inventario en la ubicación. Esta fecha se calcula en función de la fecha de vencimiento de la matrícula. Aunque esta fecha es precisa para ubicaciones que tienen seguimiento de matrícula, podría no serla para ubicaciones que no lo tienen.
- **Estado de ubicación**: el estado de la ubicación. Hay cuatro valores disponibles:

    - **Indeterminado**: el perfil de ubicación no sigue el estado. Por lo tanto, el estado actual es desconocido.
    - **Vacío**: actualmente no hay inventario en la ubicación.
    - **Selección**: se han realizado transacciones de salida en la ubicación después de estar vacía por última vez.
    - **Almacenamiento**: se han realizado transacciones de entrada desde que estuvo vacía por última vez.

Estos campos permiten a los directores de almacén obtener una mejor visión general del estado de las ubicaciones del almacén. También permiten generar informes y filtros más avanzados.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Configurar la consolidación de artículos y la utilización de ubicación

Esta sección describe cómo preparar su sistema para utilizar la consolidación de artículos y la utilización de la ubicación. Los procedimientos utilizan valores de muestra de los datos de demostración estándar. Si planea trabajar en el escenario de ejemplo que se proporciona más adelante en este tema, seleccione la entidad jurídica **USMF** (que contiene los datos de demostración estándar) y cree cada registro que se describe en esta sección. Si no planea trabajar en el escenario de ejemplo, los valores que se proporcionan aquí pueden considerarse ejemplos de los tipos de configuración que debe completar para usar las funciones.

### <a name="released-product"></a>Producto emitido

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En el campo **Número de artículo**, seleccione *M9201* y abra la página de detalles.
1. En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.
1. En la página **Dimensión física**, en el panel Acciones, seleccione **Nuevo**.

    Se agrega una nueva línea a la cuadrícula. El campo **Número de artículo** está preestablecido.

1. En el campo **Unidad**, seleccione *ea*. Los campos restantes de la línea se configuran automáticamente.
1. Seleccione **Guardar** y cierre la página.

### <a name="location-profile"></a>Perfil de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En la lista de perfiles de ubicación, seleccione **PLANTA-05**.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, asegúrese de que las siguientes opciones estén configuradas en *Sí*:

    - Habilitar artículo en ubicación
    - Habilitar estado de la ubicación

1. Seleccione **Guardar**.

    > [!IMPORTANT]
    > Si las opciones **Habilitar elemento en la ubicación** y **Habilitar estado de ubicación** ya estaban configuradas en *Sí*, salte a las instrucciones para configurar la ficha desplegable **Dimensiones** en el paso 10. Si las opciones aún no estaban configuradas en *Sí*, debe ejecutar una comprobación de coherencia para el módulo **Gestión de almacenes** después de configurarlos manualmente. En este caso, continúe con el siguiente paso.

1. Para ejecutar la comprobación de coherencia, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Verificación de coherencia**.
1. En el cuadro de diálogo **Comprobación de coherencia**, establezca los valores siguientes:

    - **Módulo:** *Gestión de almacén*
    - **Comprobar/corregir:** *Comprobar*
    - **Fecha desde**: deje este campo en blanco.
    - **Comprobación de consistencia del estado de ubicación del almacén:** seleccione esta casilla de verificación.

1. Seleccione **Aceptar**.

    > [!TIP]
    > Recibirá una notificación cuando se complete la comprobación de coherencia. Abra el [Centro de acciones](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) para ver el mensaje. Seleccione **Detalles del mensaje** para ver los detalles.
    >
    > Si el mensaje para la comprobación de coherencia dice: "Se encontró información de estado de ubicación incorrecta para la ubicación XXXX en el almacén XX", debe volver a ejecutar la comprobación de coherencia. Esta vez, configure el campo **Comprobar/arreglar** en *Arreglar error*. Vea los mensajes para asegurarse de que no se encontraron errores.

1. Ahora debe terminar de configurar el perfil de ubicación. Vuelva a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**, seleccione el perfil de ubicación **PLANTA-05** y luego, en el panel de acciones, seleccione **Editar**.
1. En la ficha desplegable **Dimensiones**, establezca los valores siguientes:

    - **Porcentaje de utilización de volumen:** *100*
    - **Método volumétrico utilizado para la ubicación del inventario:** *usar volumen de ubicación*
    - **Altura real de la ubicación:** *10*
    - **Ancho real de la ubicación:** *10*
    - **Profundidad real de la ubicación:** *10*
    - **Peso máximo:** *100*

1. Seleccione **Guardar**.

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel Acciones, seleccione **Nuevo** para crear un elemento de menú para ordenación.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento del menú:** *Ajustar en*
    - **Título:** *Ajustar en*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Proceso de creación de trabajo:** *Ajuste en*
    - **Tipos de ajuste de inventario:** *Ajustar en*

1. Seleccione **Guardar**.

### <a name="mobile-device-menu"></a>Menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En la lista de menús, seleccione **Inventario**.
1. En el panel Acciones, seleccione **Editar**.
1. En la lista **Menús disponibles y elementos de menú**, busque y seleccione el elemento de menú **Ajustar en**.
1. Seleccione el botón de flecha derecha para mover **Ajustar en** a la lista **Estructura del menú**. De esta manera, agrega su nuevo elemento de menú al menú seleccionado.
1. Seleccione **Guardar**.

### <a name="movement-types"></a>Tipos de movimiento

1. Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Tipos de movimiento**.
1. En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:

    - **Código de tipo de movimiento:** *CONSOLIDAR*
    - **Descripción:** *Consolidar ubicaciones*
    - **Id. de la clase de trabajo:** *InvMov*

1. Seleccione **Guardar**.

## <a name="example-scenario"></a>Supuesto de ejemplo

El siguiente escenario usa la aplicación móvil Warehouse Management para hacer un *ajuste en* inventario a dos ubicaciones del almacén.

### <a name="add-inventory-to-locations"></a>Agregar inventario a ubicaciones

1. Inicie sesión en el dispositivo móvil como un usuario configurado para el almacén *51*.
1. Vaya a **Inventario \> Ajustar en**.

    Ahora introducirá el primer ajuste de ubicación.

1. En la tarea **Ajuste en**, seleccione la ubicación para realizar el ajuste de inventario. En el campo **Ubicación**, seleccione *LP-001*.
1. Confirme la ubicación.
1. Cree un Id. de matrícula para el artículo que se agregará a la ubicación. En el campo **Matrícula**, introduzca *LP00101*.
1. Confirme la matrícula.
1. Introduzca el artículo que se agregará a la matrícula. En el campo **ITEM**, introduzca *M9201*.
1. Confirme el artículo.
1. Introduzca la cantidad del artículo que se agregará. En el campo **CANTIDAD**, escriba *10*.
1. Confirme la cantidad.

    Recibe un mensaje "Trabajo completado". Ahora introducirá el segundo ajuste de ubicación.

1. En la tarea **Ajuste en**, seleccione la ubicación para realizar el ajuste de inventario. En el campo **Ubicación**, seleccione *LP-002*.
1. Confirme la ubicación.
1. Cree un Id. de matrícula para el artículo que se agregará a la ubicación. En el campo **Matrícula**, introduzca *LP00201*.
1. Confirme la matrícula.
1. Introduzca el artículo que se agregará a la matrícula. En el campo **ITEM**, introduzca *M9201*.
1. Confirme el artículo.
1. Introduzca la cantidad del artículo que se agregará. En el campo **CANTIDAD**, escriba *15*.
1. Confirme la cantidad.

    Recibe un mensaje "Trabajo completado".

1. Seleccione el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Cancelar** para salir de la tarea **Ajuste en**.

### <a name="consolidate-locations"></a>Consolidar ubicaciones

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Consolidación de artículos**.
1. En el encabezado, seleccione un almacén para realizar la consolidación. En el campo **Almacén**, introduzca *51*.

    Se muestra un registro para cada ubicación donde el artículo *M9201* se ajustó. La columna **Porcentaje de utilización** muestra la utilización volumétrica de cada ubicación.

1. Para consolidar el inventario, seleccione todas las ubicaciones que deben consolidarse y luego, en el panel Acciones, seleccione **Consolidar inventario**.
1. En el cuadro de diálogo **Consolidar inventario**, especifique la ubicación y el tipo de movimiento que se debe utilizar para crear el trabajo para el movimiento de inventario. Establezca los valores siguientes:

    - **Ubicación:** *LP-001*
    - **Código de tipo de movimiento:** *CONSOLIDAR*

1. Seleccione **Aceptar**.
1. Recibirá un mensaje informativo que muestra el trabajo de movimiento que se ha creado. Anote el Id. del trabajo de movimiento.

### <a name="view-movement-work"></a>Ver trabajo de movimiento

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. Ver el trabajo que se creó. Use el Id. de trabajo de movimiento de la consolidación de inventario para filtrar o buscar en la cuadrícula de trabajo.

    En este escenario, se utilizó una ubicación existente que tenía inventario como ubicación de consolidación de inventario. Por lo tanto, solo se creó un Id. de trabajo.

    > [!NOTE]
   > El sistema crea un Id. de trabajo para cada movimiento que debe completarse. Si especifica una ubicación que ya contiene inventario, solo se crea un Id. de trabajo. Si especifica una nueva ubicación, se crean dos Id. de trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]