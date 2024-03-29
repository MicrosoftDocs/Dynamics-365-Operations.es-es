---
title: Generar informes financieros
description: Este artículo proporciona información acerca de la generación de un informe financiero.
author: jinniew
ms.date: 02/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2f55fe1a23735d8631a5918fa49e08f74eee4d37
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802779"
---
# <a name="generate-financial-reports"></a>Generar informes financieros

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la generación de un informe financiero.

Para generar un informe, abra la definición del informe y seleccione el botón **Generar** en la barra de herramientas. La página **Estado de la cola del informe** se abrirá e indicará la ubicación del informe en la cola.

A medida que avanza la generación del informe, los siguientes indicadores de estado de la cola de informes pueden estar visibles en la página **Estado de la cola de informes**.

| Status          | Estado o provincia | Description|
|-----------------|--------|--------------------|
| Colocando en cola        | Provisional |La definición del informe se valida antes de que el informe se coloque en la cola de generación.                    |
| En cola          | Provisional | El informe entra en la cola de generación de informes y espera a ser procesado.                      |
| En procesamiento      | Provisional | Este estado normalmente sigue al estado **En cola** y, por lo general, pasa a un estado **Final** cuando se completa el procesamiento.       |
| Posprocesando | Provisional | Este estado sigue al estado **En procesamiento** e indica que se recopilaron todos los datos del informe, pero que se están realizando acciones derivadas, como el cálculo y la acumulación.            |
| Cancelando      | Provisional | El informe se cancela a petición del usuario. Este estado es el resultado de una cancelación solicitada por el usuario para un informe en el estado **En cola** o **En procesamiento**. El sistema intenta colocar el informe en el estado **Cancelado**, a menos que el sistema esté demasiado avanzado y deba finalizarlo en otro estado. |
| Cancelada        | Final | El informe terminó de procesarse pero no se completó debido a una detención solicitada por el usuario.            |
| Completado       | Final | El informe está listo para usarse.                      |
| Con error          | Final | El informe terminó de procesarse pero falló y no debe usarse. |

De forma predeterminada, el informe generado se abrirá en el visor de la web. Las siguientes opciones están disponibles para generar informes:

- Configurar una programación para generar un informe o a un grupo de informes automáticamente
- Revisar cuentas o datos que faltan en un informe y validar la precisión de un informe

Al generar un informe, se usan las opciones que ha especificado en la pestaña Definición del informe .

## <a name="generate-a-financial-report"></a>Generar un informe financiero

Para generar un informe financiero, vaya a **Contabilidad general** \> **Consultas e informes** \> **Informes financieros**.

- Seleccione un informe para generarlo y elija **Generar**.
- Rellene el campo **Fecha del informe** y seleccione **Aceptar**.

Una vez que se haya generado el informe, el informe estará disponible para verlo en la sección **Informes**.

Puede seleccionar **Ver** o **Eliminar** el informe.

Para generar un informe usando **Diseñador de informes**, abra la definición del informe y luego elija el botón **Generar** en la barra de herramientas. La página **Estado de la cola del informe** se abrirá e indicará la ubicación del informe en la cola. De forma predeterminada, el informe generado se abrirá en el visor de la web.

## <a name="report-groups"></a>Grupos de informes

Los grupos de informes son una forma eficaz de generar varios informes al mismo tiempo. Por ejemplo, suponga que sabe que a fin de mes sus usuarios generan ocho informes cada mes. Cree un grupo de informes y en lugar de seleccionar **Generar** para cada uno de los ocho informes del grupo, puede seleccionar **Generar** para el grupo de informes y los ocho informes se generarán en un solo paso. Cuando se hayan generado los informes del grupo de informes seleccionado, puede ir a **Informes financieros** (**Libro mayor > Consultas e informes > Informes financieros**) para ver los informes individuales. Complete los pasos siguientes para configurar un grupo de informes.

1. En **Report designer**, seleccione **Grupos de informes**. 
2. Seleccione las definiciones de informes existentes para incluirlas en su grupo de informes. 
3. Seleccione anular la configuración de la empresa, los detalles y la fecha de cada uno de los informes que se incluirán en el grupo.
   Recomendamos configurar **Empresa**, **Período**, **Año** y **Nivel de detalle** para cada informe. 
4. Guarde el grupo de informes.

## <a name="schedule-report-generation"></a>Programar la generación de informes
Muchas compañías cuentan con un conjunto base de informes que se ejecutan en intervalos programados para la alineación con sus procesos empresariales. Puede programar un informe para que se genere con regularidad, por ejemplo diaria, semanal, mensual o anualmente. Esto puede realizarse en un solo informe o en un grupo de informes que incluye varias compañías. Deberá especificar las credenciales para cada una de las compañías especificadas, tales como las de una definición de organigrama. Si las credenciales no son válidas, el informe mostrará solo la información a la que tiene permiso de acceso, como la empresa en la que ha iniciado sesión en este momento. La información de salida se lee primero en el grupo de informes y luego en los informes individuales.

A medida que se crean y se guardan las programaciones del informe, se muestran en el panel de navegación en **Programaciones del informe**. Puede crear carpetas para organizar los informes. Si un informe único de una programación no se ejecuta, se seguirán ejecutando los demás informes.

> [!IMPORTANT]
> Para crear, modificar y eliminar programaciones de informe, deberá tener el rol Diseñador o Administrador. Cuando se ejecuta un informe, se usan las credenciales del usuario que creó la programaciónpara generar el informe.

### <a name="create-a-report-schedule"></a>Crear una programación del informe

1. En el **Report designer**, en el menú **Archivo**, seleccione **Nuevo** y luego seleccione **Programación de informes**. Se abre el cuadro de diálogo **Nueva programación de informes**.
2. En **Configuración**, seleccione un informe individual o un grupo de informes a programar. Solo estarán disponibles los informes o grupos de informes de la selección de compañía o bloque de creación en la que haya iniciado sesión.
3. Seleccione la casilla **Activar** para activar la programación de informes. Solamente el creador del informe o un administrador puede activar o desactivar una programación de informe.
4. Seleccione el botón **Permisos** para especificar las credenciales de la empresa. De manera predeterminada, la información de inicio de sesión se usa para la compañía en la que haya iniciado sesión. Si se incluyen otras empresas, como en los informes de definiciones de organigramas, seleccione **Usar credenciales independientes** y, a continuación, especifique las credenciales para cualquier otra empresa incluida en la programación del informe. Puede seleccionar **Autenticación de Windows** o escribir un nombre de usuario y una contraseña para cada empresa. Seleccione la casilla **Guardar credenciales** para guardar las credenciales de dichas empresas y, a continuación, elija **Aceptar** para cerrar el cuadro de diálogo.
5. En **Frecuencia**, en el campo **Iniciar periodicidad**, seleccione la fecha en la que comenzará la programación. De manera predeterminada, se selecciona la fecha de sistema actual del equipo cliente.
6. En el campo **Generar informe a las**, seleccione la hora a la que se debe generar el informe. Si especifica una hora anterior a la hora actual del sistema, el informe se ejecutará en la siguiente fecha programada.
7. En el área **Patrón de periodicidad**, especifique la frecuencia con la que se ejecuta el informe. De forma predeterminada, se selecciona **Diariamente**, con un valor de **Intervalo (días)** de **1**. Otras opciones incluyen **Todas las semanas**, **Todos los meses** y **Todos los años**.
8. En el área **Intervalo de periodicidad**, seleccione cuando se debe dejar de generar el informe.

    - **Sin fecha de finalización**: la programación del informe se ejecuta de forma indefinida.
    - **Establecer número de ocurrencias**: la programación de informes se ejecuta el número de veces especificado y después se desactiva.
    - **Finalizar el**: la programación de informes finaliza en la fecha especificada.

9. Seleccione **Guardar**. En el cuadro de diálogo **Guardar como**, especifique un nombre y una descripción únicos para la programación de informes.

Para copiar una programación de informe, debe tener el rol de diseñador o de administrador. Incluso si un administrador modifica la programación del informe, el informe mantiene las credenciales del usuario que creó el informe.

### <a name="copy-a-report-schedule"></a>Copiar una programación nueva

1. En Report designer, seleccione **Programaciones de informes** en el panel de navegación y abra la programación de informes que desea copiar.
2. En el menú **Archivo**, seleccione **Guardar como** y especifique un nuevo nombre y una descripción para la programación en el cuadro de diálogo **Guardar como**. Seleccione **Aceptar** y la nueva programación se mostrará en el panel de navegación.
3. En la nueva programación, modifique los campos y la información según sea necesario, y luego seleccione **Guardar** en la barra de herramientas, o elija **Guardar** en el menú **Archivo**.

Para eliminar una programación del informe, debe ser el propietario de la programación del informe o tener un rol de administrador.

### <a name="delete-a-report-schedule"></a>Eliminar una programación del informe

1. En Report designer, seleccione **Programaciones de informes** en el panel de navegación.
2. Seleccione la programación de informes que desee eliminar y, a continuación, seleccione **Eliminar** o presione la tecla **Eliminar**.
3. En el cuadro de diálogo de verificación de eliminación, seleccione **Sí** para eliminar permanentemente la programación del informe. Si no tiene permiso para eliminar la programación, se mostrará un mensaje y el informe no se eliminará.

### <a name="credentials-and-report-schedules"></a>Credenciales y programaciones de informes

Si no especifica las credenciales necesarias para todas las empresas incluidas en los informes, aparece el siguiente mensaje al guardar la programación del informe: "Debe especificar sus credenciales para las empresas que se incluyen en esta programación del informe. Seleccione el botón **Permisos** para especificar las credenciales".

Por ejemplo, un usuario inicia sesión en la Compañía A con su nombre de usuario y contraseña. El usuario crea una programación para un informe que usa una definición del organigrama para recopilar datos de varias empresas. Al guardar la programación del informe, se le solicita al usuario que especifique las credenciales para las demás compañías especificadas en la definición de organigrama. Cuando caduquen sus credenciales, los informes afectados en la programación del informe no se generarán hasta que se hayan actualizado las credenciales. Aparecerá un mensaje en la cola de informes para indicar que se deben actualizar los permisos. La programación del informe falla si tienen lugar las siguientes situaciones (porque requieren credenciales):

- Se ha agregado a una nueva empresa a un árbol de informes para un informe individual.
- Se modificó un informe en un grupo de informes.
- Se agregó a un grupo de informes un nuevo informe para una compañía adicional.

Para continuar, seleccione el botón **Permisos** en el cuadro de diálogo **Programación de informes** y, a continuación, especifique las credenciales adecuadas.

## <a name="missing-account-analysis-feature"></a>Característica que falta de análisis de la cuenta
Puede buscar las dimensiones y las cuentas financieras que podrían faltar en las definiciones de filas, informando definiciones de organigramas y definiciones del informe en un grupo de bloques de creación. Esto es útil cuando crea o se actualizan varias cuentas o bloques de creación durante un período de tiempo corto, y desea comprobar que toda la nueva información se incluye en los informes.

Las cuentas que faltan se determinan mediante los valores más bajos y más altos de la definición de filas o de la definición del organigrama, y después muestra una lista de cuentas que no están en la definición de filas o en la definición del organigrama, sino en los datos financieros. Si una cuenta que falta es mayor o menor que los valores de la definición de fila, dicha cuenta no se incluye en la lista de cuentas que faltan.

> [!TIP]
> Por motivos de validación, este proceso debería ejecutarse antes de generar los informes mensuales y cuando se crean bloques de creación nuevos.

No suelen faltar cuentas en los informes que tiene intervalos de valores. Si es posible, use los intervalos en el bloque de creación para incluir nuevas cuentas cuando se crean. Si una definición de informe se establece en una compañía @ANY, podrá iniciar sesión en una compañía específica y ejecutar un análisis de cuenta que falta para ella.

> [!NOTE]
> Si se ha agregado una nueva empresa, debe agregar la nueva empresa a los organigramas en cualquier informe existente o la empresa no estará incluida en el análisis de cuentas que faltan.

### <a name="run-missing-account-analysis"></a>Ejecutar análisis de cuentas que faltan

1. En Report designer, seleccione **Herramientas** y luego elija **Análisis de cuentas que faltan**.
2. En el campo **Filtro de empresas**, seleccione una empresa para filtrar los resultados o seleccione **Todas (sin filtro)** para mostrar los resultados de todas las empresas disponibles.
3. En el campo **Filtro de dimensiones**, seleccione una dimensión para filtrar los resultados o seleccione **Todas (sin filtro)** para ver toda la información de dimensiones para todas las dimensiones disponibles.
4. En el campo **Agrupar por**, seleccione una opción para ordenar los resultados. Puede ordenar los resultados según el bloque de creación afectado u ordenar los resultados por conjuntos de dimensiones y valores.
5. Revise los resultados que se muestran. Cuando selecciona un elemento en el panel superior, el panel inferior muestra información adicional acerca de la excepción. Esto incluye las dimensiones, los valores y los informes relacionados.
6. Para abrir el elemento afectado, seleccione el icono asociado que se muestra en el panel de la lista o haga clic con el botón secundario en el elemento y seleccione **Abrir**. Para seleccionar varios elementos, mantenga presionada la tecla **Ctrl** mientras selecciona los elementos en el panel inferior.
7. Si se devuelven algunos valores, bloques de creación o informes que no deberían estar incluidos en el análisis, haga clic con el botón derecho en el elemento y seleccione **Excluir**, o active la casilla **Excluir** junto al elemento para quitar el elemento de la lista. Los artículos excluidos no se incluyen al actualizar la lista. Para seleccionar varios elementos, mantenga presionada la tecla **Ctrl** mientras selecciona los elementos en el panel inferior. Para ver todos los elementos, incluidos los resultados seleccionados anteriormente para su exclusión del análisis, seleccione la casilla **Mostrar bloques de creación y valores excluidos** y luego elija **Actualizar**.
8. Seleccione **Actualizar** para actualizar las excepciones que ha abordado. Seleccione **Sí** para realizar una actualización completa de todos los resultados o seleccione **No** para realizar una actualización parcial.

    > [!NOTE]
    > El formulario se actualiza automáticamente al abrirse, a menos que la página se haya abierto en los últimos 15 minutos.

9. Cuando los problemas estén resueltos, seleccione **Aceptar** para cerrar el cuadro de diálogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Métodos abreviados de teclado para el análisis de cuentas que faltan
Cuando se ejecuta un análisis de cuentas que faltan, los métodos abreviados de teclado siguientes están disponibles.

| Acción                           | Presione  |
|--------------------------------------|----------------------------|
| Filtrar por empresa                    | Alt+C                      |
| Filtrar por dimensión                  | Alt+D                      |
| Seleccionar el campo Agrupar por            | Alt+G                      |
| Mostrar bloques de creación y valores excluidos      | Alt+S                      |
| Actualizar los resultados                      | Alt+R                      |
| Excluir el bloque de creación seleccionado  | Alt+X                      |
| Excluir la definición de fila seleccionada  | Ctrl+B                     |
| Excluir el valor de dimensión seleccionado | Ctrl+D                     |
| Abrir la definición de informe seleccionada  | Ctrl+R                     |
| Abrir la definición de fila seleccionada     | Ctrl+O                     |


## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)

[Interfaz del Diseñador de informes](report-designer-interface.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
