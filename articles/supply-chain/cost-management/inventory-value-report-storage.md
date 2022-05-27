---
title: Informes de valor de inventario
description: Este tema explica cómo configurar, generar y usar informes de valor de inventario. Estos informes proporcionan detalles sobre los importes y cantidades físicas y financieras de su inventario.
author: JennySong-SH
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 4f710ff308bac42a284cd506143dd0ae21ff2ec7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676198"
---
# <a name="inventory-value-reports"></a>Informes de valor de inventario

[!include [banner](../includes/banner.md)]

Los informes de valor de inventario proporcionan detalles sobre los importes y cantidades físicas y financieras de su inventario. Puede ver los informes de muchas formas diferentes. Por ejemplo, puede mostrar totales o transacciones, o filtrar por elementos o un intervalo de tiempo. Puede ver los valores del coste de bienes vendidos (COGS) o los valores del trabajo en curso (WIP) y establecer otras opciones.

Los informes de valor de inventario le permiten realizar las siguientes tareas:

- Realizar la conciliación entre la contabilidad general y el inventario.
- Consultar inventario disponible y valores para un período específico.
- Crear configuraciones de informes que se adapten a un propósito específico.
- Guardar configuraciones de informes para que puedan utilizarse varias veces.
- Agregar rangos para filtrar datos cuando ejecute un informe.

## <a name="types-of-inventory-value-report"></a>Tipos de informes de valor de inventario

Hay dos tipos de informes de valor de inventario: **Valor de inventario** (el informe estándar) y **Almacenamiento de informes de valor de inventario**.

### <a name="standard-inventory-value-report"></a>Informe de valor de inventario estándar

El informe **Valor de inventario** estándar es un informe simple que le permite seleccionar la información que se incluye y luego muestra esa información en la pantalla. No guarda los resultados. Tampoco proporciona funciones interactivas para filtrar, profundizar, navegar o exportar. Por estas razones, le recomendamos que utilice el informe **Almacenamiento de informes de valor de inventario** en su lugar en la mayoría de los casos.

### <a name="inventory-value-report-storage-report"></a>Informe de almacenamiento de informes de valor de inventario

El informe **Almacenamiento de informes de valor de inventario** proporciona salida como página interactiva en Microsoft Dynamics 365 Supply Chain Management o como documento exportado en cualquiera de varios formatos.

Cuando vea el informe en su navegador, las columnas y saldos agregados se ajustarán dinámicamente dependiendo del diseño que se haya configurado. Puede ordenar los resultados, filtrarlos, explorarlos en profundidad los datos y más.

Los resultados del informe se almacenan en la entidad de datos **Valor de inventario**. Por lo tanto, puede filtrar y exportar los resultados a un formato como valores separados por comas (CSV) o Microsoft Excel.

El informe **Almacenamiento de informes de valor de inventario** es útil cuando la salida contiene muchas líneas. Por ejemplo, tiene 50 000 artículos y se han creado 300 tiendas como almacenes. En este caso, si solicita saldos finales de inventario por artículo, sitio y almacén, la salida contendrá muchas líneas.

> [!NOTE]
> El informe **Almacenamiento de informes de valor de inventario** no incluye los subtotales definidos en el diseño del informe. Tampoco incluye saldos de contabilidad general, incluso cuando se definen en el diseño del informe. La conciliación con la contabilidad general debe hacerse utilizando saldos de prueba. Sin embargo, el informe **Valor de inventario** estándar incluye estos subtotales y saldos.

## <a name="turn-the-inventory-value-report-storage-feature-on-or-off"></a>Activar o desactivar la característica de almacenamiento de informes de valor de inventario

A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Almacenamiento de informes de valor de inventario* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Definir configuraciones de informes de valor de inventario

Utilice la página **Informes de valor de inventario** para configurar el contenido que se incluye en los diferentes tipos de informe de valor de inventario. Puede definir cualquier número de tipos de informe. Cada vez que genere cualquier un tipo de informe de valor de inventario, seleccionará un tipo de informe.

1. Vaya a **Cost Management \> Configuración de directivas de contabilidad de inventario \> Informes de valor de inventario**.
1. Siga uno de estos pasos:

    - Para editar un informe existente, selecciónelo en el panel de lista y luego seleccione **Editar** en el Panel de acciones.
    - Para crear un nuevo informe, seleccione **Nuevo** en el Panel de acciones.

1. En el encabezado del informe nuevo o seleccionado, establezca los siguientes campos:

    - **ID** - Especifique un identificador corto para el informe. Este valor debe ser único entre todas las configuraciones de informes de valor de inventario. No se puede editar después de guardar una nueva configuración.
    - **Nombre** - Especifique un nombre descriptivo para el informe.

1. Si está creando una nueva configuración de informe, seleccione **Guardar** en el Panel de acciones para que los campos restantes estén disponibles.
1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Intervalo de fechas** - Seleccione un intervalo de fechas predefinido. Puede anular este intervalo de fechas cuando ejecuta el informe.
    - **Intervalo** - Seleccione *Fecha de registro* o *Tiempo de transacción*, dependiendo de la fecha y hora que se deben usar cuando se recuperan los registros para el informe.
    - **Conjunto de dimensiones** - Seleccione el conjunto de dimensiones para el que se ejecutarán los datos. (Las dimensiones se definen en la contabilidad general). Por ejemplo, puede ejecutar los datos para *Cuenta principal* o para *Cuenta principal + Unidad de negocio*. El conjunto de dimensiones que seleccione no debe tener más de dos dimensiones. Para obtener más información, consulte [Conjuntos de dimensiones financieras](../../finance/general-ledger/financial-dimension-sets.md).

1. En la ficha desplegable **Columnas**, establezca los siguientes campos. Estos campos controlan las columnas que incluye su informe y los tipos de datos que contienen esas columnas.

    - **Inventario** - Establezca esta opción en *Sí* para mostrar los valores del inventario. A continuación, puede conciliar esos valores con los saldos de la cuenta de contabilidad general.
    - **Trabajo en curso** - Establezca esta opción en *Sí* para mostrar los valores de trabajo en curso. A continuación, puede conciliar esos valores con los saldos de la cuenta de trabajo en curso en contabilidad general. Cuando configura esta opción en *Sí*, el informe mostrará solo las cantidades físicas y los importes de inventario que tienen el estado Trabajo en curso. Los pedidos de producción que tienen el estado Trabajo en curso se han seleccionado o informado como finalizados, pero no se han finalizado.
    - **COGS diferidos** - Establezca esta opción en *Sí* para mostrar una columna que muestre las cantidades físicas y los importes de inventario para COGS diferidos. Los COGS diferidos se muestran mediante el uso de importes y cantidades físicas, ya que compensan los importes y cantidades del albarán.
    - **COGS** - Establezca esta opción en *Sí* para mostrar una columna que muestre las cantidades físicas y los importes financieros para COGS diferidos. Los COGS se muestran mediante el uso de importes y cantidades financieras, ya que compensan los importes y cantidades de la factura.
    - **Pérdidas y ganancias** - Establezca esta opción en *Sí* para mostrar una columna que muestra el importe financiero que se registró en las cuentas de pérdidas y ganancias para el inventario.
    - **Imprimir valores acumulados de cuenta para comparación** - Establezca esta opción en *Sí* para mostrar una columna que muestra el saldo de la cuenta de contabilidad general. De esta forma, no tendrá que comprobar el saldo de comprobación. Esta opción solo funciona con el informe **Valor de inventario** estándar, no con el informe **Almacenamiento de informes de valor de inventario**. Después de configurar esta opción en *Sí*, debe utilizar los siguientes campos para especificar cada cuenta de contabilidad general que desee enumerar, según las opciones de **Posición financiera** que ha habilitado.

        > [!NOTE]
        > Si selecciona una cuenta *total* para cualquiera de estos campos, se mostrarán tanto el importe de cada cuenta de inventario que se incluye en la cuenta total como el importe de la cuenta total.

        - **Contabilidad de inventario** - Especifique la cuenta de contabilidad general para la que se mostrará la información de inventario. (Tanto la opción **Inventario** como la opción **Imprimir valores acumulados de cuenta para comparación** deben establecerse en *Sí*.)
        - **Cuenta de trabajo en curso** - Especifique la cuenta de contabilidad general para la que se mostrará información de trabajo en curso. (Tanto la opción **Trabajo en curso** como la opción **Imprimir valores acumulados de cuenta para comparación** deben establecerse en *Sí*.)
        - **Cuenta de COGS diferida** - Especifique la cuenta de contabilidad general para la que se mostrará información de COGS diferida. (Tanto la opción **COGS diferida** como la opción **Imprimir valores acumulados de cuenta para comparación** deben establecerse en *Sí*.)
        - **Cuenta de COGS** - Especifique la cuenta de contabilidad general para la que se mostrará información de COGS. (Tanto la opción **COGS** como la opción **Imprimir valores acumulados de cuenta para comparación** deben establecerse en *Sí*.)

    - **Resumir valores físicos y financieros** - Establezca esta opción en *Sí* para mostrar una columna que muestra la cantidad total de inventario y el importe de inventario (un resumen de los valores de inventario físico y financiero). Si esta opción se establece en *No*, el informe mostrará valores de inventario tanto físicos como financieros.
    - **Incluir no contabilizado en el libro mayor** Establezca esta opción en *Sí* para mostrar una columna que muestra las transacciones que no se registraron en contabilidad general. Es posible que las transacciones de los siguientes tipos de artículos no se registren en contabilidad general:

        - Artículos recibidos y aún no facturados cuando la opción **Publicar inventario físico** está desactivada para el grupo de modelos de artículo relevante.
        - Artículos recibidos y aún no facturados cuando la opción **Registrar recepción de producto en el libro mayor** esté desactivada en la ficha desplegable **Recepción de producto** en la pestaña **General** de la página **Parámetros de proveedores** (**Proveedores \> Configuración \> Parámetros de proveedores**).

    - **Calcular coste unitario promedio** - Establezca esta opción en *Sí* para mostrar una columna que muestre el coste unitario promedio. El coste unitario promedio es el importe total dividido por la cantidad total.
    - **Cantidad total y valor** - Establezca esta opción en *Sí* para mostrar columnas que muestran la cantidad total de inventario físico (y cantidades financieras) y el importe de inventario de inventario físico (e importes financieros). Puede establecer esta opción en *Sí* solo si la opción **Resumir valores físicos y financieros** está establecida en *No*.
    - **Dimensiones de inventario** - En esta cuadrícula, seleccione la casilla de verificación **Ver** para cada dimensión que desee mostrar en el informe. Solo dimensiones donde la opción **Inventario financiero** está habilitada mostrarán valores en el informe. Otras dimensiones mostrarán solo columnas en blanco. Para las dimensiones que seleccione mostrar, puede seleccionar la casilla de verificación **Total** para incluir los totales también.
    - **ID de recurso** - Establezca la opción **Ver** como *Sí* para mostrar una columna que identifica el elemento de cada fila. Establezca la opción **Total** como *Sí* para incluir totales también. Según el tipo de artículo que se enumera en cada fila, la columna muestra uno de los siguientes tipos de información:

        - **Material** - La columna muestra el valor de campo `ItemID` para el registro de material relevante.
        - **Mano de obra** - La columna muestra el valor de campo `WorkCenterID` para el registro de mano de obra relevante.
        - **Coste indirecto** - La columna muestra el valor de campo `CodeID` para el registro de coste relevante.

        Si la opción **Ver** está configurada en *No* para el campo **ID de recurso** y el campo **Grupo de recursos**, verá solo un valor de inventario total que se basa en las dimensiones de inventario que seleccionó.

    - **Grupo de recursos** - Establezca la opción **Ver** como *Sí* para mostrar una columna que identifica el grupo de recursos de cada fila. Establezca la opción **Total** como *Sí* para incluir totales también. Según el tipo de artículo que se enumera en cada fila, la columna muestra uno de los siguientes tipos de información:

        - **Material** - La columna muestra el valor de campo `ItemGroup` para el registro de material relevante.
        - **Mano de obra** - La columna muestra el valor de campo `WorkcenterGroup` para el registro de mano de obra relevante.
        - **Coste indirecto** - La columna muestra el valor de campo `CostGroup` para el registro de coste relevante. (El valor de `CostGroupType` debe ser *Indirecto*.)

        Si la opción **Ver** está configurada en *No* para el campo **ID de recurso** y el campo **Grupo de recursos**, verá solo un valor de inventario total que se basa en las dimensiones de inventario que seleccionó.

1. En la ficha desplegable **Filas**, establezca los siguientes campos. Estos campos le permiten agregar subsecciones relacionadas con WIP correspondientes al informe o eliminarlas.

    - **Material** - Establezca esta opción en *Sí* para mostrar información sobre materiales. *Material* es un tipo de recurso predeterminado porque los materiales deben incluirse en todas las configuraciones de informes para crear una salida confiable.
    - **Mano de obra** - Establezca esta opción en *Sí* para mostrar los costos laborales de trabajo en curso.
    - **Coste indirecto** - Establezca esta opción en *Sí* para mostrar los costos indirectos de trabajo en curso.
    - **Subcontratación directa** - Establezca esta opción en *Sí* para mostrar los costes de subcontratación directa de trabajo en curso. Esta información resulta útil para subcontratación.
    - **Nivel de detalle** - Seleccione una opción de vista para el informe:

        - *Transacciones* - Ve todas las transacciones relevantes en el informe. Tenga en cuenta que puede experimentar problemas de rendimiento al ver informes que incluyen un gran volumen de transacciones. Por lo tanto, si desea utilizar esta opción de vista, le recomendamos que utilice el informe **Almacenamiento de informes de valor de inventario**.
        - *Totales* - Ver el resultado total.

    - **Incluir saldo inicial** - Establezca esta opción en *Sí* para mostrar el saldo inicial. Esta opción solo está disponible cuando el campo **Nivel de detalle** está establecido en *Transacciones*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Generar un informe de almacenamiento de informes de valor de inventario

Siga estos pasos para generar y almacenar un informe de **Almacenamiento de informes de valor de inventario**.

1. Vaya a **Gestión de costes \> Consultas e informes \> Informe de almacenamiento de valor de inventario**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Valor de inventario**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Nombre** – Escriba un nombre único para el informe.
    - **ID** - Seleccione la [configuración de informe de valor de inventario](#report-configuration) para utilizar para el informe. La configuración establece opciones para las columnas y filas que se incluirán en su informe.
    - **Intervalo de fechas** - Utilice los campos de esta sección para definir qué registros se incluyen en el informe. Para definir el intervalo de fechas, puede seleccionar un rango preestablecido (relativo a la fecha de generación del informe) en **Código de intervalo de fecha** o seleccionar fechas específicas en los campos **Fecha desde** y **Fecha hasta**.

1. En la ficha desplegable **Registros para incluir**, configure filtros y restricciones para definir qué datos se incluyen en el informe. Seleccione **Filtro** para abrir un diálogo de editor de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Supply Chain Management. Todos estos filtros se aplicarán a las transacciones de inventario, pero no al saldo del libro mayor. Tenga en cuenta este comportamiento cuando configure sus filtros. De lo contrario, es posible que vea una discrepancia entre el inventario y el libro mayor.
1. En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia se genera el informe. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.

    > [!NOTE]
    > Este informe siempre se ejecuta como parte de un trabajo por lotes.

1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo.

Después de que el trabajo por lotes se complete, el informe aparecerá en la página **Almacenamiento del informe de valor de inventario**. Es posible que deba actualizar la página para ver el informe.

> [!IMPORTANT]
> En la configuración del informe de valor de inventario seleccionado, es posible que obtenga un saldo inicial incorrecto si selecciona la misma fecha en el campo **Fecha de inicio** y el campo **Fecha de finalización**, y si también establece la opción **Incluir saldo inicial** en *Sí*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Explorar un informe de almacenamiento de informes de valor de inventario

Después de generar un informe, puede verlo y explorarlo en cualquier momento mediante estos pasos.

1. Vaya a **Gestión de costes \> Consultas e informes \> Informe de almacenamiento de valor de inventario**.
1. Seleccione un informe de la lista. La página muestra los detalles de la [configuración del informe de valor de inventario](#report-configuration) que se utilizó para generar el informe seleccionado.
1. En el panel de acciones, seleccione **Ver detalles** para ver el contenido del informe.
1. Explore el informe siguiendo cualquiera de estos pasos:

    - Como sucede con la mayoría de las páginas estándar de Supply Chain Management, puede seleccionar casi cualquier encabezado de columna para ordenar o filtrar la cuadrícula por los valores en esa columna.
    - Utilice el campo **Filtro** para filtrar el informe por cualquier valor en cualquiera de las distintas columnas disponibles.
    - Use el menú de vista (sobre el campo **Filtro**) para guardar y cargar sus combinaciones favoritas de opciones de clasificación y filtro.

## <a name="export-an-inventory-value-report-storage-report"></a>Exportar un informe de almacenamiento de informes de valor de inventario

Cada informe que genera se almacena en la entidad de datos **Valor de inventario**. Puede usar las funciones estándar de administración de datos de Supply Chain Management para exportar datos de esta entidad a cualquier formato de datos compatible, como CSV o Excel.

El siguiente ejemplo muestra cómo exportar un informe **Almacenamiento de informes de valor de inventario**.

1. Vaya a **Administración del sistema \> Áreas de trabajo \> Administración de datos**.
1. En la sección **Importación y exportación**, seleccione el icono **Exportar**.
1. En la página **Exportar** que aparece, configurará el trabajo de exportación. Primero especifique un nombre de grupo para el trabajo.
1. En la sección **Entidades seleccionadas**, seleccione **Agregar entidad**.
1. En el cuadro de diálogo que aparece, establezca los campos siguientes:

    - **Nombre de la entidad**: seleccione *Valor de inventario*.
    - **Formato de datos objetivo**: seleccione el formato para exportar datos.

1. Seleccione **Agregar** para añadir la fila nueva y luego seleccione **Cerrar** para cerrar el cuadro de diálogo.
1. Por lo general, exportará un informe a la vez. Para exportar un solo informe, configure un filtro para la fila que acaba de agregar al cuadro de diálogo **Consulta**. De esta forma, puede definir qué informe de la entidad **Valor de inventario** se incluye en la exportación. Siga estos pasos para establecer las siguientes opciones de filtro para exportar un solo informe:

    1. En la pestaña **Rango**, seleccione **Agregar** para agregar una fila.
    2. Establezca el campo **Tabla** en *Valor de inventario*.
    3. Establezca el campo **Tabla derivada** en *Valor de inventario*.
    4. Establezca el campo **Campo** en el campo por el que desea filtrar. Por lo general, usará el campo **Nombre de ejecución** y/o el campo **Tiempo de ejecución**.
    5. Establezca el campo **Criterios** en el valor que desea buscar en el campo seleccionado. (Si seleccionó el campo **Nombre de ejecución** en el paso anterior, este valor será el nombre del informe. Si seleccionó el campo **Tiempo de ejecución**, será el momento en que se generó el informe).
    6. Agregue más filas a la pestaña **Rango** según sea necesario, hasta que haya identificado de forma exclusiva el informe que está buscando.

1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.
1. Seleccione **Guardar** para guardar su configuración de exportación.
1. En la pestaña **Opciones de exportación**, seleccione **Exportar ahora** para generar el archivo de exportación.
1. En la página **Resumen de ejecución** que aparece, puede ver el estado de su trabajo de exportación y una lista de las entidades que se exportaron. En la sección **Estado de procesamiento de la entidad**, seleccione la entidad **Valor de inventario** en la lista y luego seleccione **Descargar archivo** para descargar los datos que se exportaron desde esa entidad.

Para obtener más información sobre cómo usar la administración de datos para exportar datos, vea [Resumen de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Generar un informe de valor de inventario estándar

Utilice el siguiente procedimiento para generar un informe **Valor de inventario** estándar.

1. Vaya a **Cost Management \> Consultas e informes \> Contabilidad de inventario - informes de estado \> Valor de inventario**.
1. En el cuadro de diálogo **Informe de valor de inventario**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Nombre** – Escriba un nombre único para el informe.
    - **ID** - Seleccione la [configuración de informe de valor de inventario](#report-configuration) para utilizar para el informe. La configuración establece opciones para las columnas y filas que se incluirán en su informe.
    - **Intervalo de fechas** - Utilice los campos de esta sección para definir qué registros se incluyen en el informe. Para definir el intervalo de fechas, puede seleccionar un rango preestablecido (relativo a la fecha de generación del informe) en **Código de intervalo de fecha** o seleccionar fechas específicas en los campos **Fecha desde** y **Fecha hasta**.

1. En la ficha desplegable **Registros para incluir**, configure filtros y restricciones para definir qué datos se incluyen en el informe. Seleccione **Filtro** para abrir un diálogo de editor de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia se genera el informe. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo. El informe aparece.

## <a name="reading-inventory-value-reports"></a>Lectura de informes de valor de inventario

Esta sección proporciona una guía sobre cómo leer y comprender un informe de valor de inventario.

Supply Chain Management admite los siguientes dos conceptos importantes relacionados con el estado del inventario:

- **Financieras actualizadas** - Este concepto indica que las transacciones de inventario ya están facturadas. Para órdenes de producción, indica el final de una orden de producción.
- **Físicas actualizadas** - Este concepto indica que las transacciones de inventario aún no se han facturado, pero se han recibido o enviado. Para las órdenes de producción, indica que se ha recogido el material o que el pedido de producción se ha informado como terminado.

Cuando comprenda estos dos conceptos, será fácil comprender las siguientes columnas en el resultado del informe:

- **Inventario: Cantidad financiera** - La cantidad actualizada financieramente.
- **Inventario: Importe financiero** - El valor de importe del inventario que se ha actualizado financieramente.
- **Inventario: Cantidad física registrada** - La cantidad actualizada físicamente.
- **Inventario: Importe físico registrado** - El valor de importe del inventario que seha actualizado físicamente.
- **Inventario: Cantidad física no registrada** - La cantidad que tiene transacciones de inventario pero que no se ha registrado en contabilidad general. Por ejemplo, tiene un grupo de modelos de artículos donde las opciones **Registrar inventario físico** y **Registrar inventario financiero** están desactivadas y tiene un artículo vinculado a ese grupo. A continuación, crea un pedido de compra, lo recibe y lo factura. En este punto, si revisa el informe de valor de inventario para el artículo, verá que la cantidad y el valor del pedido de compra se muestran en las columnas **Inventario: Cantidad física no registrada** e **Inventario: Cantidad física no registrada**.
- **Inventario: Cantidad física no registrada** - Puede configurar sus informes para que muestren importes no registrados. Sin embargo, si usa el informe para la conciliación de inventario, no use este valor. De lo contrario, la cantidad no se registra en la contabilidad general.
- **Inventario: Cantidad** - La cantidad total de todas las columnas de cantidad del informe.
- **Inventario: Importe** - La cantidad total de todas las columnas de importe del informe. Cuando realice la conciliación de inventario, no utilice esta columna si su informe incluye la columna **Inventario: Cantidad física no registrada**. En este caso, debe excluir el importe **Inventario: Cantidad física no registrada** del importe total.
- **Coste unitario promedio** - El importe total dividido por la cantidad total.

Normalmente, utilizará un informe de valor de inventario para ver el valor y la cantidad de inventario. Sin embargo, a veces el informe no mostrará todas las dimensiones relevantes del inventario. Si no ve las dimensiones que espera, valide la siguiente configuración:

- Revise los grupos almacenamiento de artículos y dimensión de seguimiento. Solo dimensiones donde la opción **Inventario financiero** está habilitada pueden mostrarse en el informe.
- Vaya a **Cost Management \> Configuración de directivas de contabilidad de inventario \> Informes de valor de inventario**, seleccione la configuración del informe que utilizó para generar el informe y asegúrese de que las dimensiones de inventario necesarias estén seleccionadas en la columna **Vista**.

Por ejemplo, tiene un artículo que tiene el número de artículo *A0001*. En el grupo de dimensiones de almacenamiento, solo el sitio está habilitado para el inventario financiero. El sitio y el almacén están habilitados para el inventario físico. En el grupo de dimensiones de seguimiento, el número de lote está habilitado para inventario físico pero no para inventario financiero. Luego, utiliza una configuración de informe en la que se seleccionan el sitio, el almacén y el número de lote. Cuando ve el informe, ve un valor solo para el sitio. Las columnas para el almacén y el número de lote están en blanco. Como muestra este ejemplo, los informes de valor de inventario solo pueden mostrar la dimensión de inventario que está habilitada para el inventario financiero.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
