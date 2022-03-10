---
title: Escenarios de ejemplo de recuento cíclico
description: Este tema proporciona una colección de escenarios que exploran las características de conteo cíclico de Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ff67198980765f288b5394d91927ae1826266841
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103347"
---
# <a name="cycle-counting-example-scenarios"></a>Escenarios de ejemplo de recuento cíclico

[!include [banner](../includes/banner.md)]

Este tema proporciona una colección de escenarios que exploran las características de conteo cíclico de Microsoft Dynamics 365 Supply Chain Management. En primer lugar, describe los requisitos para su entorno de Supply Chain Management existente. Luego explica cómo configurar el conteo cíclico y describe todas las etapas del conteo cíclico. Cuando haya terminado, debe tener una buena comprensión del conteo cíclico, incluido el conteo cíclico guiado, el conteo cíclico ciego, el conteo cíclico puntual, los umbrales del conteo cíclico y los planes de conteo cíclico.

## <a name="prerequisites"></a>Requisitos previos

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Cada escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras trabaja en los escenarios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica (empresa) en **USMF** antes de empezar.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Activar la compatibilidad con la aplicación móvil Warehouse Management

Para utilizar la aplicación móvil Warehouse Management, la característica *Configuración de usuario, iconos y títulos de pasos mejorados para la nueva aplicación de almacén* debe estar activada en su sistema. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Configuración de usuario, iconos y títulos de pasos mejorados para la nueva aplicación de almacén* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Prepare datos de demostración para los escenarios

Siga estos pasos para confirmar que todos los datos de demostración que se requieren para los escenarios están disponibles en la empresa USMF en su sistema. Cree los registros o valores que falten.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. En el panel de lista, seleccione **Julia Funderburk**.
1. En la ficha desplegable **Usuarios**, seleccione la fila que tiene los siguientes valores. Si ninguna fila existente tiene estos valores, créala.

    - **Id. de usuario:** *61*
    - **Nombre de usuario:** *WH61*
    - **Almacén predeterminado:** *61*
    - **Nombre del menú:** *Principal*

1. En la ficha desplegable **Trabajo**, establezca los siguientes valores para el usuario *61* si aún no están configurados:

    - **Es un supervisor de recuentos cíclicos:** *No*
    - **Límite de porcentaje máximo:** *0*
    - **Límite de la cantidad máxima:** *0*
    - **Límite del valor máximo:** *0*

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Grupos de trabajo**.
1. Los grupos de trabajo se usan para segregar el trabajo del almacén, en función del tipo de trabajo (en este caso, el trabajo de recuento cíclico). Asegúrese de que exista un registro que tenga la siguiente configuración:

    - **Id. del grupo de trabajo:** *CycleCount*
    - **Descripción:** *Recuento de ciclos*

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de lista, seleccione el registro que se llama *Contador de ciclos*. Si ningún registro existente tiene este nombre, créelo. Confirme o establezca los siguientes valores para el registro:

    - **Nombre del elemento del menú:** *Contador de ciclos*
    - **Título:** *Contador de ciclos guiado*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*
    - **Dirigido por:** *Dirigido por el sistema* (Este valor indica que Supply Chain Management asignará un ID de trabajo de recuento cíclico al trabajador).
    - **Mostrar estado de inventario**: *Sí*

1. En el panel de acciones, seleccione **Recuento cíclico**.
1. En el **Recuento de ciclos de dispositivos móviles** cuadro de diálogo, confirme o establezca los siguientes valores:

    - **Mostrar número de artículo:** *Sí*
    - **Mostrar matrícula de entidad de almacén:** *Sí*
    - **Número de intentos:** *1*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En el panel de lista, seleccione el registro que se llama *Contador de ciclos ciego*. Si ningún registro existente tiene este nombre, créelo. Confirme o establezca los siguientes valores para el registro:

    - **Nombre del elemento del menú:** *Contador de ciclos ciego*
    - **Título:** *Contador de ciclos ciego*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*
    - **Dirigido por:** *Agrupación de recuentos cíclicos* (este valor indica que el trabajador puede agrupar los id. de trabajo de recuento cíclico que son específicos de una ubicación, un área o a un grupo de trabajo).

1. En el panel de acciones, seleccione **Recuento cíclico**.
1. En el **Recuento de ciclos de dispositivos móviles** cuadro de diálogo, confirme o establezca los siguientes valores:

    - **Mostrar número de artículo:** *No*
    - **Mostrar matrícula de entidad de almacén:** *No*
    - **Número de intentos:** *0*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En el panel de lista, seleccione el registro que se llama *Recuento puntual*. Si ningún registro existente tiene este nombre, créelo. Confirme o establezca los siguientes valores para el registro:

    - **Nombre del elemento del menú:** *Recuento puntual*
    - **Título:** *Recuento puntual*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *No*
    - **Proceso de creación de trabajo:** *Recuento cíclico puntual* (este valor indica que el trabajador puede contar los artículos de una ubicación de almacén en cualquier momento, sin crear el trabajo de recuento cíclico. Para realizar el recuento cíclico puntual en una ubicación, el trabajador especifica el id. de ubicación).

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En el panel de lista, seleccione el registro que se llama *Inventario*. Si ningún registro existente tiene este nombre, créelo. Confirme que los siguientes elementos del menú de recuento cíclico aparezcan en la columna **Estructura del menú**:

    - Recuento cíclico
    - Contador de ciclos ciego
    - Recuento puntual

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **Recuento cíclico**, establezca los valores siguientes:

    - **Tipo de ajuste de recuento cíclico predeterminado:** *Contador de ciclos* (este campo especifica el tipo de diario que se registra cuando se realiza el recuento cíclico).
    - **ID de clase de trabajo de recuento cíclico predeterminado:** *CCount* (este campo especifica la clase de trabajo que se utiliza para el recuento cíclico).
    - **Prioridad de trabajo del recuento de ciclos predeterminado:** *50* (este campo establece la prioridad que tiene el trabajo de recuento cíclico en relación con otros tipos de trabajo en el almacén. Si especifica un número menor al número que se introduce para otros tipos de trabajo, aumenta la prioridad de trabajo de recuento cíclico).

1. Vaya a **Warehouse Management \> Configurar \> Inventario \> Tipos de ajuste**.
1. La página **Tipos de ajuste** le permite crear códigos para los diferentes ajustes de entrada y salida que pueden ocurrir. Confirme que existe un registro que tenga la siguiente configuración:

    - **Tipo de ajuste de inventario:** *Contador de ciclos*
    - **Descripción:** *Recuento de ciclos*
    - **Nombre:** *ICnt*

1. Vaya a **Warehouse Management \> Configurar \> Configuración de almacén \> Almacenes**.
1. En el panel de lista, seleccione el almacén *61*. Si ningún registro existente tiene este nombre, créelo.
1. En la ficha desplegable **Almacén**, establezca los valores siguientes:

    - **Utilice el proceso de gestión de almacén:** *Sí* (este valor habilita el almacén para los procesos de gestión del almacén).
    - **Permita que la placa de matrícula se mueva durante el conteo cíclico:** *Sí* (este valor permite a los trabajadores mover las placas de matrícula durante un recuento cíclico).

## <a name="scenario-1-guided-cycle-counting"></a>Escenario 1: recuento cíclico guiado

Antes de que pueda ocurrir el recuento cíclico guiado, debe crear algo de trabajo. Este trabajo guiará a la persona asignada a través del almacén, de un lugar a otro, para completar los conteos que se configuran en el trabajo.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Crear trabajo de recuento cíclico para el escenario 1

Siga estos pasos para crear un trabajo de recuento cíclico para la ubicación del artículo *01A02R2S2B* (BULK-06) en el almacén *61*.

1. Vaya a **Warehouse Management \> Recuento de ciclos \> Umbrales de recuento cíclico**.
1. En el cuadro de diálogo **Crear trabajo de conteo cíclico por ubicación**, establezca el campo **ID del grupo de trabajo** en *Contador de ciclos*.
1. En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Distancia**, siga estos pasos:

    - Para la fila donde el campo **Campo** está configurado en *Depósito*, defina el campo **Criterios** en *61*.
    - Para la fila donde el campo **Campo** está configurado en *Ubicación*, defina el campo **Criterios** en *01A02R2S2B*.

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Seleccione **OK** para cerrar el cuadro de diálogo **Crear trabajo de conteo cíclico por ubicación**.

    Cuando se completa el proceso de creación de la obra, aparece un mensaje en el Centro de actividades.

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. Encuentre el trabajo recién creado estableciendo un filtro en la columna **ID del grupo de trabajo** para buscar registros que tengan un valor de *Contador de ciclos*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Reliazar trabajo de recuento cíclico para el escenario 1

Una vez creado el trabajo de recuento cíclico, realice el trabajo de recuento cíclico contando los artículos de una ubicación de almacén y usando a continuación un dispositivo móvil para especificar los resultados en Supply Chain Management. Siga estos pasos para realizar el trabajo de recuento cíclico en la aplicación móvil Warehouse Management.

1. Inicie sesión en la aplicación móvil Warehouse Management como el usuario de trabajo que configuró en la sección [Prepare datos de demostración para los escenarios](#prepare-demo-data) anterior en este tema. Para el ejemplo de este tema, el nombre del usuario *Julia Funderburk* y está configurado para almacén *61*. (Los datos de demostración de USMF deberían permitirle iniciar sesión como este usuario de trabajo ingresando *61* como ID de usuario y *1* como contraseña).
1. En el menú principal, seleccione **Inventario**.
1. En el menú **Inventario**, seleccione **Contador de ciclos guiado**.
1. Seleccione el campo **Cant.**, ingrese *9* utilizando el teclado numérico y luego seleccione **Aceptar** (botón de marca de verificación).
1. El sistema esperaba que ingresara un recuento de 10 piezas para este artículo, ubicación y matrícula. Por lo tanto, se le pide que vuelva a contar. Seleccione el campo **Cant.**, ingrese *9* de nuevo utilizando el teclado numérico y luego seleccione **Aceptar** (botón de marca de verificación). En el segundo intento, se aceptará su recuento.

    > [!NOTE]
    > Cuando el sistema detectó una diferencia entre la cantidad disponible esperada y la cantidad que ingresó, le pidió que contara por segunda vez porque el campo **Número de intentos** está configurado en *1* para el elemento de menú **Contador de ciclos guiado** del dispositivo móvil. Fue guiado a un número de artículo específico y un número de placa porque las opciones **Mostrar número de artículo** y **Mostrar matrícula** están configuradas en *Sí* para el elemento de menú del dispositivo móvil.

1. Seleccione **Aceptar** (botón de de marca de verificación).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Revise las diferencias de recuento cíclico para el escenario 1

Siga estos pasos para revisar las diferencias de recuento cíclico.

1. Vuelva a Supply Chain Management.
1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. Busque y seleccione el trabajo de recuento cíclico que miró anteriormente. (Por ejemplo, establezca un filtro en la columna **ID del grupo de trabajo** para buscar registros que tengan un valor de *Contador de ciclos*). Observe que el campo **Situación laboral** para este trabajo ahora está configurado en *Revisión pendiente*.

    > [!NOTE]
    > Para la cuenta de usuario del trabajo que usó para hacer el trabajo de conteo, la opción **Supervisor de conteo de ciclos** está configurada en *No* y **Límite máximo porcentual**, **Límite de cantidad máxima** y **Límite de valor máximo** están configurados en *0* (cero). Por lo tanto, todas las diferencias de recuento que informa este usuario deben aprobarse manualmente, y el campo **Situación laboral** para el trabajo relacionado se establece en *Revisión pendiente*. Si el valor contado estuviera dentro de los límites de desviación (como se especifica en **Límite máximo porcentual** o **Límite de cantidad máxima** en la página **Usuarios de trabajo**), o si la opción **Supervisor de conteo de ciclos** se estableció en *Sí* para el usuario, la obra se habría cerrado automáticamente.

1. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Recuento cíclico**.
1. En el panel de acciones, seleccione **Aceptar recuento**.

    La diferencia se registra utilizando el diario de recuento estándar y se crea una nueva orden de trabajo.

1. En la página **Transacciones de recuento cíclico**, en el Panel de acciones, seleccione **Trabajo derivado** para encontrar el trabajo que fue creado para la diferencia aprobada.

## <a name="scenario-2-blind-cycle-counting"></a>Escenario 2: recuento cíclico ciego

Este escenario requiere que el escenario 1 ya esté completado en su sistema.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Crear trabajo de recuento cíclico para el escenario 2

Antes de que pueda ocurrir el recuento cíclico ciego, debe crear algo de trabajo. Siga estos pasos para crear un trabajo de recuento cíclico para la ubicación del artículo *01A02R2S2B* (BULK-06) en el almacén *61*.

1. Vaya a **Warehouse Management \> Recuento de ciclos \> Trabajo de recuento cíclico por elemento**.
1. En el cuadro de diálogo **Crear trabajo de conteo cíclico por elemento**, establezca el campo **ID del grupo de trabajo** en *Contador de ciclos*.
1. En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.
1. Agregue tres filas que tengan la siguiente configuración en la pestaña **Intervalo** del cuadro de diálogo del editor de consultas.

    - Fila 1:

        - **Tabla:** *Artículos*
        - **Campo:** *Número de artículo*
        - **Criterios**: *L0101*

    - Fila 2:

        - **Tabla**: *Dimensiones de inventario*
        - **Campo:** *Almacén*
        - **Criterio:** *61*

    - Fila 3:

        - **Tabla**: *Dimensiones de inventario*
        - **Campo:** *Ubicación*
        - **Criterios**: *01A02R2S2B*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Seleccione **OK** para cerrar el cuadro de diálogo **Crear trabajo de conteo cíclico por elemento**.

    Cuando se completa el proceso de creación del trabajo, recibe un mensaje informativo.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Reliazar trabajo de recuento cíclico para el escenario 2

Después de crear el trabajo de recuento cíclico, siga estos pasos para realizar el trabajo en la aplicación móvil Warehouse Management.

1. Inicie sesión en la aplicación móvil Warehouse Management como el usuario de trabajo que configuró en la sección [Prepare datos de demostración para los escenarios](#prepare-demo-data) anterior en este tema. Para el ejemplo de este tema, el nombre del usuario *Julia Funderburk* y está configurado para almacén *61*. (Los datos de demostración de USMF deberían permitirle iniciar sesión como este usuario de trabajo ingresando *61* como ID de usuario y *1* como contraseña).
1. En el menú principal, seleccione **Inventario**.
1. En el menú **Inventario**, seleccione **Contador de ciclos ciego**.
1. Seleccione el campo **ID de zona**, ingrese *BULK06* y luego seleccione **OK** (el botón de la marca de verificación).
1. Seleccione el campo **Elemento**, ingrese *L0101* y luego seleccione **OK** (el botón de la marca de verificación).
1. Seleccione el campo **Matrícula**, ingrese *LP\_BULK\_06\_01* y luego seleccione **OK** (el botón de la marca de verificación).
1. Seleccione el campo **Cant.**, ingrese *10* y luego seleccione **OK** (el botón de la marca de verificación).

    > [!NOTE]
    > Aunque el sistema detecte una diferencia entre la cantidad disponible esperada y la cantidad que ingresó, no le pidió que contara por segunda vez porque el campo **Número de intentos** está configurado en *0* (cero) para el elemento de menú **Contador de ciclos ciego** del dispositivo móvil. Se le pidió escanear el número de artículo y de placa porque las opciones **Mostrar número de artículo** y **Mostrar matrícula** están configuradas en *No* para el elemento de menú del dispositivo móvil.

1. Seleccione **Aceptar** (botón de de marca de verificación).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Revise las diferencias de recuento cíclico para el escenario 2

Siga estos pasos para revisar las diferencias de recuento cíclico.

1. Vuelva a Supply Chain Management.
1. Vaya a **Warehouse Management \> Recuento cíclico \> Trabajo \> Revisión pendiente del trabajo de recuento cíclico**.
1. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Recuento cíclico**.
1. En el panel de acciones, seleccione **Rechazar recuento**.

    Debido a que se rechazó la diferencia de conteo, el trabajo se cierra.

## <a name="scenario-3-spot-cycle-counting"></a>Escenario 3: recuento cíclico puntual

El registro disponible indica que hay una cantidad disponible de artículo *L0101* en el lugar *01A02R2S2B*. El trabajador del almacén está en el lugar *01A02R2S1B*. Aunque esta ubicación debería estar vacía, está llena. Por lo tanto, el trabajador del almacén hace un recuento inmediato de esta ubicación.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Reliazar trabajo de recuento cíclico para el escenario 3

Siga estos pasos para realizar el trabajo de recuento cíclico en la aplicación móvil Warehouse Management.

1. Inicie sesión en la aplicación móvil Warehouse Management como el usuario de trabajo que configuró en la sección [Prepare datos de demostración para los escenarios](#prepare-demo-data) anterior en este tema. Para el ejemplo de este tema, el nombre del usuario *Julia Funderburk* y está configurado para almacén *61*. (Los datos de demostración de USMF deberían permitirle iniciar sesión como este usuario de trabajo ingresando *61* como ID de usuario y *1* como contraseña).
1. En el menú principal, seleccione **Inventario**.
1. En el menú **Inventario**, seleccione **Recuento puntual**.
1. Seleccione el campo **Ubicación**, ingrese *01A02R2S1B* y luego seleccione **OK** (el botón de la marca de verificación).

    El sistema detecta que la ubicación está vacía en Supply Chain Management.

1. Seleccione **Agregar LP o artículo**.
1. Seleccione el campo **Elemento**, ingrese *L0101* y luego seleccione **OK** (el botón de la marca de verificación).
1. Seleccione el campo **Matrícula**, ingrese *LP\_BULK\_06\_01* y luego seleccione **OK** (el botón de la marca de verificación).
1. Seleccione el campo **Cant.**, ingrese *9* y luego seleccione **OK** (el botón de la marca de verificación).

    Debido a que el sistema detecta que la matrícula especificada ya está disponible en otra ubicación en Supply Chain Management, esa matrícula se moverá a la ubicación actual. Por tanto, el sistema le pide que confirme el movimiento.

1. Seleccione **Aceptar** (botón de de marca de verificación).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Revise las diferencias de recuento cíclico para el escenario 3

Siga estos pasos para revisar los resultados del recuento.

1. Vuelva a Supply Chain Management.
1. Vaya a **Warehouse Management \> Común \> Detalles de trabajo**.
1. Seleccione la casilla de verificación **Mostrar cerrado** en la parte superior de la cuadrícula.
1. Establecer el filtro para la columna **Tipo de orden de trabajo** a *Movimiento de inventario*.

    El sistema detectó automáticamente este recuento como un movimiento de inventario. Este movimiento está permitido porque la opción **Permitir que la placa de matrícula se mueva durante el conteo cíclico** está configurada en *Sí* para el almacén *61* en la página **Almacenes**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Escenario 4: definir umbrales de recuento de ciclos

Una forma de crear un trabajo de recuento cíclico es utilizar umbrales. Un umbral de recuento cíclico indica el límite de cantidad o porcentaje de los artículos de inventario. El trabajo de recuento cíclico se crea automáticamente cuando se alcance el umbral.

Por ejemplo, hay 60 artículos en una ubicación que tiene un umbral del recuento cíclico de 40. Durante una transacción de pedido de ventas, 25 artículos se seleccionan de la ubicación y se colocan en una ubicación provisional. Dado que el nuevo recuento de artículos, 35, es inferior a la cantidad umbral, el trabajo de recuento cíclico se crea automáticamente para la ubicación.

Para configurar los umbrales de recuento cíclico, siga estos pasos:

1. Vaya a **Warehouse Management \> Configuración \> Recuento de ciclos \> Umbrales de recuento cíclico**.
1. En el panel de acciones, seleccione **Nuevo** para crear un umbral y establecer los siguientes valores para él:

    - **Id. de umbral de recuento cíclico:** *L0101*
    - **Descripción:** *Umbral L0101*
    - **Cantidad umbral:** *2*
    - **Unidad**: *u*
    - **Umbral de capacidad según porcentaje:** *0,00*
    - **Tipo de umbral de recuento de ciclos:** *Cantidad*
    - **Recuento de ciclos de proceso inmediatamente:** *Sí*
    - **Días entre recuentos cíclicos:** *1*
    - **Id. del grupo de trabajo:** *CycleCount*

1. En el panel de acciones, haga clic en **Seleccionar artículos**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Número de artículo*. Seleccione el campo **Criterios** en esa fila para *L0101*.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.

    Ahora ha definido un umbral de recuento de ciclos para el artículo *L0101*.

El recuento cíclico ahora se creará para el artículo *L0101* en cualquier lugar si la cantidad disponible es menor que 2, y si la fecha del último recuento del ciclo para el lugar no es hoy.

## <a name="scenario-5-define-cycle-count-plans"></a>Escenario 5: definir planes de recuento de ciclos

Los planes de recuento cíclico le permiten automatizar la creación del trabajo de recuento cíclico. Puede configurar cada plan de recuento de ciclos con consultas específicas de artículos y ubicaciones. Cuando se ejecuta el trabajo por lotes, creará un trabajo de recuento cíclico para todas las ubicaciones que coincidan con el artículo y los criterios de ubicación (hasta el número máximo de recuentos que se especifica para el plan). Cuando se crea el trabajo de recuento cíclico, la línea de trabajo de recuento incluye información acerca de la ubicación que se debe contar. El inventario disponible que está asociado con esa ubicación no está bloqueado. Por lo tanto, está disponible para reserva y procesamiento de salida, aunque exista trabajo de conteo abierto.

Para configurar un plan de recuento cíclico, siga estos pasos:

1. Vaya a **Warehouse Management \> Configuración \> Recuento de ciclos \> Planes de recuento cíclico**.
1. En el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula y después establezca los siguientes valores.

    - **Id. de plan de recuento cíclico:** *BULK06*
    - **Descripción:** *Recuento de ubicación para BULK06*
    - **Id. del grupo de trabajo:** *CycleCount*
    - **Número máximo de recuentos cíclicos:** *10*
    - **Días entre recuentos cíclicos:** *10*
    - **Ubicaciones vacías:** *Excluir vacío*
    - **Plantilla de trabajo**: deje este campo en blanco.

1. En el panel de acciones, haga clic en **Seleccionar ubicaciones**.
1. Aparece un cuadro de diálogo de editor de consultas estándar. En la pestaña **Intervalo**, agregue una fila y establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Campo**: *ID de zona*
    - **Criterios**: *BULK06*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. En el panel de acciones, seleccione **Procesar plan de recuento cíclico**.
1. En el cuadro de diálogo **Planes de recuento cíclico**, en la ficha desplegable **Ejecutar en segundo plano**, configure la opción **Procesamiento por lotes** como *Sí*.
1. Seleccione **Periodicidad**.
1. En el cuadro de diálogo **Definir recurrencia**, configure el trabajo por lotes para que comience inmediatamente y se ejecute una vez cada minuto, y para que no haya una fecha de finalización.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Definir periodicidad**.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Planes de recuento cíclico**.

    Un mensaje le informa que el trabajo se agregó a la cola por lotes.

1. Vaya a **Warehouse Management \> Común \> Programación del recuento cíclico**. El plan comienza de inmediato y crea trabajo de conteo. Debido a que el trabajo de conteo no se ha completado, el campo **Estado** está configurado en *En proceso*. Después de un minuto, el valor de la columna **Recuento total de ciclos** cambia a *1*.

    > [!NOTE]
    > El trabajo de recuento de ciclos no se creará si el número de días desde el último recuento de ciclo es menor que el valor que estableció para el campo **Días entre recuento de ciclos** para el plan de recuento cíclico. Por ejemplo, si el valor en el campo **Días entre recuentos cíclicos** es *5*, el trabajo de recuento cíclico se creará cada cinco días. Sin embargo, si el trabajo de recuento cíclico se procesa el día 3, el siguiente trabajo de recuento cíclico se creará cinco días después del último recuento cíclico procesado, el día 8.

1. En el panel de acciones, seleccione **Trabajo** para ver el trabajo de recuento que se creó.
