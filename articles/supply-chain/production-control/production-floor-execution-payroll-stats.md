---
title: Mostrar saldos de vacaciones en la interfaz de ejecución de la planta de producción
description: Este tema proporciona un escenario de ejemplo que muestra cómo configurar Microsoft Dynamics 365 Supply Chain Management para que utilice las estadísticas de nómina para proporcionar a los trabajadores una visión general de su saldo de vacaciones para el año en curso.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645362"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Mostrar saldos de vacaciones en la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

Este tema proporciona un escenario de ejemplo que muestra cómo configurar Microsoft Dynamics 365 Supply Chain Management para que utilice las estadísticas de nómina para proporcionar a cada trabajador una visión general de su saldo de vacaciones para el año en curso. Los trabajadores podrán ver su saldo de vacaciones en el cuadro de diálogo **Mi día** en la interfaz de ejecución de la planta de producción.

Este escenario utiliza la ley de vacaciones danesa, donde el año de vacaciones va desde el 1 de septiembre hasta el 31 de agosto. En este escenario, su empresa ha contratado a un nuevo trabajador y le otorgará a ese trabajador un saldo de 10 días de vacaciones por el resto del año de vacaciones en curso.

## <a name="turn-on-the-required-features"></a>Active las funciones requeridas

Para ejecutar este escenario, debe habilitar la característica *Vista "Mi día" para la interfaz de ejecución de la planta de producción* en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Para obtener información sobre cómo habilitar esta y otras características para la interfaz de ejecución de la planta de producción, consulte [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

## <a name="create-a-new-pay-type"></a>Crear un tipo de sueldo nuevo

Comience por crear un nuevo *tipo de sueldo* que hará un seguimiento de los días de vacaciones ganados de los trabajadores (también conocido como su *saldo de vacaciones*). Por lo general, los tipos de sueldo se utilizan para calcular el sueldo de los trabajadores. Sin embargo, el tipo de sueldo que cree aquí se utilizará para calcular un saldo.

1. Vaya a **Tiempo y asistencia \> Configuración \> Nómina \> Tipos de sueldo**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tipo de sueldo:** *5151-1*
    - **Descripción:** *Contador de días de vacaciones del trabajador*
    - **Incluir en exportación:** *No*

## <a name="update-the-pay-agreement"></a>Actualizar el acuerdo de sueldo

En esta sección, editará un archivo existente *acuerdo de sueldo* al agregar el nuevo tipo de sueldo y establecer las reglas que definen cómo se ajusta el saldo de vacaciones de cada trabajador cuando se registran los días de vacaciones.

1. Vaya a **Tiempo y asistencia \> Configuración \> Nómina \> Acuerdos de sueldo**.
1. Seleccione el acuerdo de sueldo donde desea configurar la directiva de vacaciones. (Si está trabajando con datos de muestra de USMF estándar, solo hay un acuerdo de sueldo, *Hombre*).
1. Asegúrese de que el acuerdo de sueldo seleccionado sea válido para la fecha actual. Si está trabajando con datos de muestra de USMF estándar, el campo **Hasta la fecha** del acuerdo de sueldo *Hombre* puede establecerse en una fecha en el pasado. Cambie el valor para que sea uno o dos años en el futuro, según sea necesario.
1. En el panel de acciones, seleccione **Líneas del acuerdo**.
1. En la página **Líneas del acuerdo de sueldo** en la ficha desplegable **Visión de conjunto** establezca los siguientes valores en la barra de herramientas:

    - En la primera lista desplegable seleccione **Lunes**.
    - En la segunda lista desplegable seleccione **Ausencia**.

1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. En la nueva fila, establezca el campo **Tipo de sueldo** en el tipo de sueldo que creó para este escenario (*5151-1*). Deje todos los demás campos en sus valores predeterminados.
1. Mientras la nueva fila aún está seleccionada, en la ficha desplegable **General** establezca los siguientes valores:

    - **Código de ausencia:** *Vacaciones*
    - **Utilizar cantidad fija:** *Sí*
    - **Constante:** *-1*

1. En el panel de acciones, seleccione **Copiar día**.
1. En el cuadro de diálogo **Copiar día**, establezca los valores siguientes:

    - **Martes**, **Miércoles**, **Jueves** y **Viernes:** *Sí*
    - **Sobreescribir:** *Sí*
    - **Ausencia:** *Sí*

1. Seleccione **Aceptar**.

## <a name="create-a-payroll-statistic-group"></a>Crear un grupo de estadística de nómina

Los *grupos de estadísticas de nómina* se utilizan para configurar estadísticas de registros de trabajadores durante un período. En este escenario, utilizará un grupo de estadísticas de nómina para calcular la cantidad de días de vacaciones que ganan los trabajadores durante un período de vacaciones. En Dinamarca, el período de vacaciones va del 1 de septiembre al 31 de agosto.

1. Vaya a **Tiempo y asistencia \> Configuración \> Nómina \> Grupos de estadística de nómina**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Grupo de estadísticas de nómina:** *VAC*
    - **Descripción:** *Saldo de vacaciones*
    - **Transferencia:** *No*

1. Mientras la nueva fila aún está seleccionada, seleccione **Configuración** en el panel de acciones.
1. En la página **Configuración**, en el panel de acciones, seleccione **Nueva** para agregar una fila a la cuadrícula.
1. En la nueva fila, establezca el campo **Tipo de sueldo** en *5151-1*.
1. Seleccione y mantenga presionado el campo **Código de periodo** y luego seleccione **Ver detalles**. Ahora puede configurar el código de período que asignará a este campo más adelante.
1. En la página **Tipos de periodo**, en el panel de Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tipos de período:** *VacYear*
    - **Descripción:** *Año de vacaciones*
    - **Frecuencia:** *Años*

1. Mientras la nueva fila aún está seleccionada, seleccione **Generar periodos** en el panel de acciones.
1. En el cuadro de diálogo **Generar periodos**, establezca los valores siguientes:

    - **Especificar fecha inicial del período:** *1 de septiembre de 2021*
    - **Longitud del período:** *5*

1. Seleccione **Aceptar**.
1. Cierre la página **Tipos de periodo** para volver a la página **Grupos de estadísticas de nómina**.
1. Seleccione el campo **Código de período** al tipo de período que acaba de crear (*VacYear*).

## <a name="create-a-statistical-balance-setup"></a>Crear una configuración de saldo estadístico

En esta sección, creará una *configuración de saldo estadístico* que está vinculada al grupo de estadísticas de nómina que creó en la sección anterior. Posteriormente, vinculará esta configuración de saldo estadístico a la vista **Mi día** en la interfaz de ejecución de la planta de producción. La vista **Mi día** podrá mostrar los saldos de vacaciones para el tipo de sueldo que se asigna al grupo de estadísticas de nómina asociado.

1. Vaya a **Tiempo y asistencia \> Configuración \> Nómina \> Configuración de saldo estadístico**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Grupo de estadísticas de nómina:** *VAC*
    - **Nombre externo:** *Saldo de vacaciones*
    - **Flex:** *No*

## <a name="create-a-manual-premium"></a>Crear una bonificación manual

Las *bonificaciones manuales* se utilizan típicamente para otorgar a los trabajadores un pago adicional por trabajo adicional. En este escenario, creará una bonificación manual que puede usar para establecer el saldo inicial de vacaciones para cada trabajador.

1. Vaya a **Tiempo y asistencia \> Configuración \> Nómina \> bonificaciones manuales**.
1. En el panel de Acciones, seleccione **Nuevo** para agregar un registro.
1. Establezca los siguientes valores en el nuevo registro:

    - **Bonificaciones:** *VAC*
    - **Descripción:** *Ajustes al saldo de vacaciones de los trabajadores*
    - **Tipo de sueldo:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Establezca el saldo inicial de vacaciones de un trabajador y ajústelo por un día

Los administradores de nómina utilizan la página **Aprobar** para revisar y aprobar los registros diarios de los trabajadores. En este escenario, asumirá el rol de administrador para que pueda establecer el saldo inicial de vacaciones para un trabajador y registrar los días de vacaciones que el trabajador toma.

1. Vaya a **Tiempo y asistencia \> Revisar y aprobar \> Aprobar**.
1. En el cuadro de diálogo **Aprobar**, seleccione los siguientes campos:

    - **Grupo de aprobación**: seleccione el grupo de aprobación al que pertenece. (Si está trabajando con datos de muestra de USMF estándar, solo hay un grupo de aprobación *AdmMan*).
    - **Ver todo el grupo, 1 día**: seleccione la opción y luego establezca el campo en la fecha actual.

1. Seleccione **Aceptar**.
1. La página **Aprobar** muestra una lista de registros que coinciden con sus criterios. Seleccione el trabajador que desea aprobar. Si está trabajando con datos de muestra de USMF estándar, seleccione trabajador *000496* (*Cristina Porta*).
1. Otorgar al trabajador seleccionado 10 días de vacaciones:

    1. Mientras el trabajador aún está seleccionado, seleccione **Líneas de bonificación** en el panel de Acciones.
    1. En la página **Líneas de bonificación**, en el panel de Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
    1. Establezca los siguientes valores en la fila nueva:

        - **Bonificaciones:** *VAC*
        - **Cantidad:** *10*

    1. Cierre la página **Líneas de bonificación**.

1. En la página **Aprobar**, registre el hecho de que el trabajador utilizó uno de sus días de vacaciones en la fecha actual:

    1. Mientras el trabajos sigue seleccionado, en la parte inferior de la página, en la pestaña **Descripción general**, seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula.
    1. Establezca los siguientes valores en la fila nueva:

        - **Tipo de registro de diario:** *Ausencia*
        - **Referencia:** *Vacación*

    1. En la parte superior de la página, seleccione **Transferir** en la barra de herramientas para aplicar el saldo de vacaciones y calcular la deducción.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Configurar la interfaz de ejecución de la planta de producción para que incluya el cuadro de diálogo Mi día

En esta sección, agregará un botón **Mi día** a la interfaz de ejecución de la planta de producción. Los trabajadores pueden usar este botón para abrir el cuadro de diálogo **Mi día**.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. Seleccione una configuración como *Predeterminado*.
1. En el panel de Acciones, seleccione **Pestañas de diseño**.
1. En la página **Pestañas de diseño**, en el panel de lista, seleccione *Todos los trabajos* para ver la configuración de esa pestaña. El campo **Vista principal** ahora debe mostrar un valor de *Todos los trabajos*.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **Barra de herramientas secundaria**, en la columna **Acciones disponibles**, seleccione **Mi día**. A continuación, seleccione el botón de la flecha derecha para moverlo a la columna **Acciones seleccionadas**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Compruebe su saldo en la interfaz de ejecución de la planta de producción

En esta sección, iniciará sesión en la interfaz de ejecución de la planta de producción como el trabajador cuyo tiempo de vacaciones configuró anteriormente. A continuación, abrirá el cuadro de diálogo **Mi día** para ver su saldo de vacaciones.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Ejecución de planta de producción**.
1. Si se le solicita que seleccione una configuración, seleccione la configuración que configuró anteriormente en este escenario (*Predeterminado*).
1. Inicie sesión como el usuario que configuró anteriormente en este escenario. Si está trabajando con datos de muestra USMF estándar, debería poder iniciar sesión escribiendo *123* en el campo **Id. de notificación**. Este Id. de notificación corresponde a Christina Portra.
1. Seleccione **Mi día** en la barra de herramientas izquierda.
1. Inspeccionar la sección **Saldos** del cuadro de diálogo. Esta sección ahora debería mostrar que tiene un saldo de nueve días de vacaciones.
