---
title: Visión general de los trabajos de exportación e importación de datos
description: Use el espacio de trabajo de gestión de datos para crear y administrar trabajos de importación y exportación de datos.
author: Sunil-Garg
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3af49d9355f37e0016f491ed37050f75bbc65d72
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684069"
---
# <a name="data-import-and-export-jobs-overview"></a>Visión general de los trabajos de exportación e importación de datos

[!include [banner](../includes/banner.md)]

Para crear y administrar la importación y exportación de datos de trabajos, debe usar el espacio de trabajo **Gestión de datos**. De forma predeterminada, el proceso de importación y exportación de datos crea una tabla de almacenamiento provisional para cada entidad en la base de datos de destino. Las tablas de almacenamiento provisional le permiten verificar, limpiar o convertir datos antes de moverlos de sitio.

> [!NOTE]
> Este tema asumen que está familiarizado con las [entidades de datos](data-entities.md).

## <a name="data-importexport-process"></a>Proceso de exportación e importación de datos
Aquí tiene los pasos que debe realizar para importar o exportar datos.

1. Cree un trabajo de importación o exportación en el que pueda realizar las tareas siguientes:

    - Defina la categoría del proyecto.
    - Identifique las entidades que se importarán o exportarán.
    - Establezca el formato de datos del trabajo.
    - Ordene las entidades para que puedan procesarse en grupos lógicos que tengan sentido.
    - Determine si quiere usar las tablas de almacenamiento provisional.

2. Confirme que los datos de origen y destino estén asignados correctamente.
3. Compruebe la seguridad del trabajo de importación o exportación.
4. Ejecute el trabajo de importación o exportación.
5. Confirme que el trabajo se ejecutó del modo esperado; para ello, consulte el historial del trabajo.
6. Limpie las tablas de almacenamiento provisional.

En las secciones restantes de este tema se proporcionan más detalles acerca de cada paso del proceso.

> [!NOTE]
> Para actualizar el formulario de importación y exportación de datos para ver el último progreso, utilice el icono de actualización del formulario. No se recomienda la actualización del nivel del explorador porque interrumpirá cualquier trabajo de importación o exportación que no se ejecute en lote.

## <a name="create-an-import-or-export-job"></a>Crear un trabajo de importación o exportación
Un trabajo de importación o exportación de datos puede ejecutarse una o varias veces.

### <a name="define-the-project-category"></a>Definir la categoría del proyecto
Le recomendamos que se tome el tiempo necesario para seleccionar una categoría de proyecto apropiada para el trabajo de importación o exportación. Las categorías de proyecto pueden ayudarle a administrar los trabajos relacionados.

### <a name="identify-the-entities-to-import-or-export"></a>Identificar las entidades que se importarán o exportarán
Puede agregar entidades específicas a un trabajo de importación o exportación o seleccionar la plantilla que se aplicará. Las plantillas rellenan un trabajo con una lista de entidades. La opción **Aplicar la plantilla** solo está disponible después de nombrar el trabajo y guardarlo.

### <a name="set-the-data-format-for-the-job"></a>Establecer el formato de datos del trabajo
Al seleccionar una entidad, debe seleccionar el formato de los datos que se exportarán o importarán. Puede definir los formatos mediante el icono **Configuración de orígenes de datos**. Un formato de datos de origen es una combinación de **Tipo**, **Formato de archivo**, **Delimitador de la fila** y **Delimitador de columna**. También hay otros atributos, pero estos son los clave para comprender. En la tabla siguiente aparecen las combinaciones válidas.

| Formato de archivo            | Delimitador de columna/fila                       | Estilo XML                 |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-N/D-                     |
| XML                    | \-N/D-                                      | Elemento-XML atributo-XML |
| Delimitado, ancho fijo | Coma, punto y coma, tabulador, barra vertical, dos puntos | \-N/D-                     |

### <a name="sequence-the-entities"></a>Ordenar las entidades
Puede ordenar las entidades en una plantilla de datos o en trabajos de importación y exportación. Cuando ejecute un trabajo que contenga más de una entidad de datos, asegúrese de que están correctamente ordenadas. Puede ordenar las entidades principales para trabajar con cualquier dependencia funcional que esté entre ellas. Si las entidades no tienen dependencias funcionales, pueden ser programadas en una la importación o exportación paralela.

#### <a name="execution-units-levels-and-sequences"></a>Unidades de ejecución, niveles y secuencias
La unidad de ejecución, el nivel de la unidad de ejecución y el orden de una entidad le permiten controlar el orden de los datos que se exportan o importan.

- Las entidades que estén en unidades de ejecución diferentes se procesarán en paralelo.
- En cada unidad de ejecución, se procesan las entidades en paralelo si tienen el mismo nivel.
- En cada nivel, se procesan las entidades según su número de secuencia en dicho nivel.
- Una vez procesado un nivel, se procesa el siguiente.

#### <a name="resequencing"></a>Volver a ordenar
Es posible que quiera volver a ordenar las entidades según las siguientes situaciones:

- Si solo usó un trabajo de datos para todos los cambios, puede usar las opciones para volver a ordenar y así optimizar el tiempo de ejecución del trabajo completo. En estos casos, puede usar la unidad de ejecución para representar el módulo, el nivel para representar el área de características en el módulo y la secuencia para representar la entidad. Al usar este método, puede trabajar en paralelo con diferentes módulos, pero aun así puede seguir trabajando en el orden de un módulo. Para que garantizar que las operaciones paralelas se realizan correctamente, debe tener en cuenta todas las dependencias.
- Si se utilizan varios trabajos de datos (por ejemplo, un trabajo para cada módulo), puede utilizar la secuenciación en el nivel y ordenar las entidades para asegurar una ejecución óptima.
- Si no hay dependencias en absoluto, puede ordenar las entidades en diferentes unidades de ejecución para garantizar una optimización máxima.

El menú **Volver a ordenar** está disponible cuando se seleccionan varias entidades. Puede volver a ordenar según la unidad de ejecución, el nivel o las opciones de secuencia. Puede establecer un incremento al volver a ordenar las entidades que haya seleccionado. Cada incremento específico actualizará la unidad, el nivel o el número de secuencia que se haya seleccionado para cada entidad.

#### <a name="sorting"></a>Ordenación
Puede usar la opción **Ordenar por** para ver la lista de entidades en orden secuencial.

### <a name="truncating"></a>Truncar
Para proyectos de importación, puede optar por truncar registros en las entidades antes de la importación. Esto resulta útil si los registros deben importarse en un conjunto claro de tablas. Esta configuración está desactivada de forma predeterminada.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Confirmar que los datos de origen y destino estén asignados correctamente
La asignación es una función que se aplica a los trabajos de exportación e importación.

- En un trabajo de importación, la función de asignación indica qué columnas del archivo de origen serán las columnas de la tabla de almacenamiento provisional. Por lo tanto, el sistema puede determinar qué datos de columna del archivo de origen se deberán copiar las columnas correspondientes de la tabla de almacenamiento provisional.
- En un trabajo de exportación, la función de asignación indica qué columnas de la tabla de almacenamiento provisional (esto es, el origen) serán las columnas del archivo de destino.

Si coinciden los nombres de columna en la tabla de almacenamiento provisional y el archivo, el sistema establecerá automáticamente la asignación según esos nombres. Sin embargo, si los nombres difieren, las columnas no se asignarán automáticamente. En estos casos, debe completar la asignación seleccionando la opción **Ver mapa** en la entidad del trabajo de datos.

Existen dos vistas de asignación: **Visualización de la asignación** que es la vista predeterminada y **Detalles de la asignación**. Un asterisco rojo (\*) identifica los campos requeridos en la entidad. Estos campos deben asignarse para poder ejecutar la entidad. Puede desasignar otros campos según necesite cuando trabaje con la entidad. Para desasignar un campo seleccione el campo de la columna **Entidad** o la columna **Origen** y, a continuación, seleccione **Eliminar selección**. Seleccione **Guardar** para guardar los cambios y cierre la página para volver al proyecto. Puede usar el mismo proceso para editar la asignación de campos de origen para que se ejecute una vez realizada la importación.

Puede crear una asignación en la página seleccionando **Crear la asignación de origen**. Una asignación generada actúa como una asignación automática. Por lo tanto, debe asignar manualmente cualquier campo sin asignar.

![Asignación de datos](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Compruebe la seguridad del trabajo de importación o exportación
El acceso al área de trabajo **Administración de datos** puede ser limitado, de modo que los usuarios que no sean administradores solo pueden acceder a ciertos trabajos de datos. El acceso a un trabajo de datos implica acceso total al historial de ejecución de ese trabajo y acceso a las tablas de ensayo. Por lo tanto, debe asegurarse de que los controles de acceso son los adecuados al crear un trabajo de datos.

### <a name="secure-a-job-by-roles-and-users"></a>Proteger un trabajo mediante roles y usuarios
Utilice el menú **Roles aplicables** para limitar el trabajo a una o más funciones de seguridad. Solo los usuarios que tengan esos roles tendrán acceso al trabajo.

También puede restringir un trabajo a usuarios específicos. Al asegurar un trabajo mediante usuarios en vez de roles, conseguirá más control si se asignan varios usuarios a un rol.

### <a name="secure-a-job-by-legal-entity"></a>Proteger un trabajo mediante una entidad jurídica
Los trabajos de datos son globales por naturaleza. Por lo tanto, si un trabajo de datos se creó y se usó en una entidad jurídica, ese trabajo será visible en otras entidades jurídicas del sistema. Este comportamiento predeterminado puede ser útil en algunos escenarios de aplicaciones. Por ejemplo, una organización que importa facturas mediante entidades de datos, puede proporcionar un equipo de procesamiento de facturas centralizado que sea responsable de administrar los errores de facturación de todas las divisiones de la organización. En esta situación, resulta útil que el equipo de procesamiento de facturas centralizado tenga acceso a los trabajos de importación de facturas de todas las entidades jurídicas. Por lo tanto, el comportamiento predeterminado cumple con los requisitos establecidos para la entidad jurídica.

Sin embargo, es posible que una organización quiera tener varios equipos de procesamiento de facturas por cada entidad jurídica. En este caso, un equipo en una entidad jurídica debe tener acceso solo al trabajo de importación de facturas en su propia entidad jurídica. Para cumplir este requisito, puede configurar el control de acceso basado en entidades jurídicas mediante el menú **Entidades jurídicas aplicables** que está dentro del trabajo de datos. Una vez realizada la configuración, los usuarios podrán ver solo los trabajos que estén disponibles en la entidad jurídica en la que hayan iniciado sesión. Para ver trabajos de otra entidad jurídica, los usuarios deben cambiarse a esa entidad jurídica.

Un trabajo se puede proteger según los roles, usuarios y entidades jurídicas al mismo tiempo.

## <a name="run-the-import-or-export-job"></a>Ejecutar el trabajo de importación o exportación
Puede ejecutar un trabajo una vez; para ello, seleccione el botón **Importar** o **Exportar** después de definir el trabajo. Para configurar un trabajo periódico, seleccione **Crear un trabajo de datos recurrente**.

> [!NOTE]
> Un trabajo de importación o exportación se puede ejecutar seleccionando el botón **Importar** o **Exportar**. Esto programará un trabajo por lotes para que se ejecute solo una vez. Es posible que el trabajo no se ejecute inmediatamente si el servicio por lotes se está ralentizando debido a la carga del servicio por lotes. Los trabajos también se pueden ejecutar sincrónicamente seleccionando **Importar ahora** o **Exportar ahora**. Esto inicia el trabajo inmediatamente y resulta útil si el lote no empiezan debido a limitaciones. Los trabajos también se pueden programar para que se ejecuten en un momento posterior. Esto se puede hacer eligiendo la opción **Ejecutar por lotes**. Los recursos por lote están sujetos a limitaciones, por lo que el trabajo por lotes podría no empezar inmediatamente. El uso de un lote es la opción recomendada porque también ayudará con grandes volúmenes de datos que se deben importar o exportar. Los trabajos por lotes se pueden programar para su ejecución en grupos por lotes específicos, que permiten más control desde una perspectiva de equilibrio de carga.

## <a name="validate-that-the-job-ran-as-expected"></a>Confirme que el trabajo funciona como es debido.
Tiene disponible el historial de trabajos por si necesita solucionar algún problema o investigar algún trabajo de importación o exportación. Las ejecuciones de trabajos del historial se organizan según intervalos de tiempo.

![Rangos del historial de trabajos](./media/dixf-job-history.md.png)

Cada ejecución de trabajo proporciona los siguientes detalles:

- Detalles de ejecución
- Registro de ejecución

Los detalles de la ejecución muestran el estado de cada entidad de datos que procesó el trabajo. Por lo tanto, puede buscar rápidamente la siguiente información:

- Qué entidades se procesaron.
- En una entidad, cuántos registros se procesaron correctamente y cuántos fallaron.
- Los registros provisionales de cada entidad.

Puede descargar los datos provisionales en un archivo dedicado a los trabajos de exportación, o bien descargarlo como un paquete de los trabajos de exportación e importación.

Desde la opción de detalles de ejecución, también puede abrir el registro de ejecución.

## <a name="parallel-imports"></a>Importaciones paralelas
Para acelerar la importación de datos, se puede habilitar el procesamiento paralelo de la importación de un archivo si la entidad admite importaciones paralelas. Para configurar la importación paralela para una entidad, se deben seguir los siguientes pasos.

1. Vaya a **Administración del sistema \> Áreas de trabajo \> Administración de datos**.
2. En la sección **Importación y exportación**, seleccione el icono **Parámetros de marco** para abrir la página **Parámetros del marco de importación/exportación de datos**.
3. En la pestaña **Configuraciones de entidad**, seleccione **Configurar parámetros de ejecución de entidad** para abrir la página **Parámetros de ejecución de importación de entidad**.
4. Establezca los siguientes campos para configurar la importación paralela para una entidad:

    - En el campo **Entidad**, seleccione la entidad.
    - En el campo **Importar recuento de registros de umbral**, ingrese el recuento de registros de umbral para la importación. Esto determina el recuento de registros que debe procesar un subproceso. Si un archivo tiene 10K registros, un recuento de registros de 2500 con un recuento de tareas de 4 significará que cada subproceso procesará 2500 registros.
    - En el campo **Recuento de tareas de importación**, ingrese el recuento de tareas de importación. Este no debe exceder los subprocesos de lote máximos asignados para el procesamiento por lotes en **Administracion del sistema \>Configuración del servidor**.

## <a name="clean-up-the-staging-tables"></a>Limpiar las tablas de almacenamiento provisional
Esta funcionalidad ha quedado en desuso desde la Platform update 29. Se ha reemplazado por una nueva versión de la funcionalidad de limpieza del historial de trabajo que se explica a continuación.

Puede limpiar las tablas de almacenamiento provisional si usa la característica **Limpieza del almacenamiento provisional** del espacio de trabajo **Administración de datos**. Puede usar las opciones siguientes para seleccionar qué registros deben ser eliminados de una tabla de almacenamiento provisional específica:

- **Entidad**: si solo se proporciona una entidad, todos los registros de la tabla de almacenamiento provisional de esa entidad se borran. Seleccione esta opción para borrar todos los datos de la entidad incluyendo todos los proyectos y trabajos de datos.
- **Id. de trabajo**: si solo se proporciona un id. de trabajo, todos los registros de todas las entidades del trabajo seleccionado se eliminan de las tablas de almacenamiento provisional adecuadas.
- **Proyectos de datos**: si solo se selecciona un proyecto de datos, todos los registros de las entidades y de todos los trabajos del proyecto de datos seleccionado se eliminan.

También puede combinar estas opciones para restringir aún más el conjunto de registros que se van a eliminar.

## <a name="job-history-clean-up-available-in-platform-update-29-and-later"></a>Limpieza del historial de trabajo (disponible en Platform update 29 y actualizaciones posteriores)

La funcionalidad de limpieza del historial de trabajo de la administración de datos debe usarse para programar una limpieza periódica del historial de ejecución. Esta funcionalidad reemplaza la funcionalidad anterior de limpieza de tablas de almacenamiento provisional, que ahora ha quedado en desuso. Se limpiarán las tablas siguientes mediante el proceso de limpieza.

-   Todas las tablas de almacenamiento provisional

-   DMFSTAGINGVALIDATIONLOG

-   DMFSTAGINGEXECUTIONERRORS

-   DMFSTAGINGLOGDETAIL

-   DMFSTAGINGLOG

-   DMFDEFINITIONGROUPEXECUTIONHISTORY

-   DMFEXECUTION

-   DMFDEFINITIONGROUPEXECUTION

La funcionalidad **Limpieza del historial de ejecución** debe estar habilitada en la administración de características y, después, se puede obtener acceso a ella desde **Administración de datos \> Limpieza del historial de trabajos**.

### <a name="scheduling-parameters"></a>Parámetros de programación

Al programar el proceso de limpieza hay que especificar los siguientes parámetros para definir los criterios de limpieza.

-   **Número de días del historial que se conservarán**: este valor se usa para controlar la cantidad de historial de ejecución que se va a conservar. Se especifica como un número de días. Cuando el trabajo de limpieza se programa como trabajo por lotes periódico, este valor representa un intervalo de tiempo que se mueve continuamente, manteniendo siempre intacto el número de días especificado del historial y eliminando el resto. El valor predeterminado es de 7 días.

-   **Número total de horas necesarias para ejecutar el trabajo**: en función de la cantidad de historial que haya que limpiar, el tiempo total de ejecución del trabajo de limpieza puede variar de unos minutos a unas horas. Este parámetro debe establecerse en la cantidad de horas que se ejecutará el trabajo. Después de que el trabajo de limpieza se haya ejecutado durante el número de horas especificado, el trabajo saldrá y reanudará la limpieza la próxima vez que se ejecute según el programa de repetición.

    Con esta opción de configuración se puede especificar un tiempo de ejecución máximo estableciendo un límite máximo del número de horas que el trabajo debe ejecutarse. La lógica de limpieza pasa por un identificador de ejecución de trabajo a la vez en una secuencia ordenada cronológicamente, donde el más antiguo es el primero para la limpieza del historial de ejecución relacionado. Dejará de seleccionar nuevos id. de ejecución para la limpieza cuando la duración restante de la ejecución esté dentro del último 10 % de la duración especificada. En algunos casos, se esperará que el trabajo de limpieza continúe más allá del tiempo máximo especificado. Esto dependerá en gran parte del número de registros que se deben eliminar para el id. de ejecución actual que se inició antes de que se alcanzara el umbral del 10 %. La limpieza iniciada debe completarse para garantizar la integridad de los datos, lo que significa que la limpieza continuará aunque se supere el límite especificado. Una vez completada, no se seleccionarán nuevos identificadores de ejecución y el trabajo de limpieza finalizará. El historial de ejecución restante que no se haya limpiado por falta de tiempo de ejecución se seleccionará la próxima vez que se programe el trabajo de limpieza. El valor predeterminado (y el valor mínimo) de esta configuración está establecido en 2 horas.

-   **Lote periódico**: el trabajo de limpieza se puede ejecutar como una ejecución manual puntual o se puede programar para una ejecución periódica por lotes. El lote se puede programar con la opción de configuración **Ejecutar en segundo plano**, que es la configuración de lote estándar.

> [!NOTE]
> Si los registros en las tablas de preparación no se limpian por completo, asegúrese de que el trabajo de limpieza esté programado para ejecutarse periódicamente. Como se explicó anteriormente, en cualquier ejecución de limpieza, el trabajo solo limpiará tantas ID de ejecución como sea posible dentro de las horas máximas proporcionadas. Para continuar la limpieza de los registros de etapas restantes, el trabajo debe programarse para ejecutarse periódicamente.

## <a name="job-history-clean-up-and-archival-available-for-preview-in-platform-update-39-or-version-10015"></a>Limpieza y archivo del historial de trabajos (disponible para vista previa en la Platform update 39 o versión 10.0.15)
La función de limpieza y archivo del historial de trabajos reemplaza las versiones anteriores de la función de limpieza. Esta sección explicará estas nuevas capacidades.

Uno de los principales cambios en la funcionalidad de limpieza es el uso del trabajo por lotes del sistema para limpiar el historial. El uso del trabajo por lotes del sistema permite a las aplicaciones de Finance and Operations que el trabajo por lotes de limpieza se programe y se ejecute automáticamente tan pronto como el sistema esté listo. Ya no es necesario programar el trabajo por lotes manualmente. En este modo de ejecución predeterminado, el trabajo por lotes se ejecutará cada hora a partir de las 12 de la noche y conservará el historial de ejecución de los 7 días más recientes. El historial depurado se archiva para su futura recuperación.

> [!NOTE]
> Debido a que esta funcionalidad está en vista previa, el trabajo por lotes del sistema no eliminará ningún historial de ejecución hasta que se habilite a través del paquete piloto DMFEnableExecutionHistoryCleanupSystemJob. Cuando la función esté generalmente disponible en una versión futura, este paquete piloto no será necesario y el trabajo por lotes del sistema comenzará a purgarse y archivarse una vez que el sistema esté listo, según el programa definido como se explicó anteriormente. 

> [!NOTE]
> En una versión futura, las versiones anteriores de la función de limpieza se eliminarán de las aplicaciones Finance and Operations.

El segundo cambio en el proceso de limpieza es el archivo del historial de ejecución depurado. El trabajo de limpieza archivará los registros eliminados en el almacenamiento de blobs que DIXF usa para integraciones regulares. El archivo archivado estará en el formato de paquete DIXF y estará disponible durante 7 días en el blob durante el cual se podrá descargar. La longevidad predeterminada de 7 días para el archivo archivado se puede cambiar a un máximo de 90 días en los parámetros.

### <a name="changing-the-default-settings"></a>Cambiar la configuración predeterminada
Esta funcionalidad se encuentra actualmente en versión preliminar y debe activarse explícitamente habilitando el paquete piloto DMFEnableExecutionHistoryCleanupSystemJob. La función de limpieza por etapas también debe estar activada en la gestión de funciones.

Para cambiar la configuración predeterminada para la longevidad del archivo archivado, vaya al espacio de trabajo de administración de datos y seleccione **Limpieza del historial de trabajos**. Establezca **Días para retener el paquete en blob** a un valor entre 7 y 90 (inclusive). Esto tendrá efecto en los archivos que se creen después de que se realizó este cambio.

### <a name="downloading-the-archived-package"></a>Descarga del paquete archivado
Esta funcionalidad se encuentra actualmente en versión preliminar y debe activarse explícitamente habilitando el paquete piloto DMFEnableExecutionHistoryCleanupSystemJob. La función de limpieza por etapas también debe estar activada en la gestión de funciones.

Para descargar el historial de ejecución archivado, vaya al espacio de trabajo de gestión de datos y seleccione **Limpieza del historial de trabajos**. Seleccione **Historial de copias de seguridad del paquete** para abrir el formulario de historial. Este formulario muestra la lista de todos los paquetes archivados. Se puede seleccionar y descargar un archivo seleccionando **Descargar paquete**. El paquete descargado tendrá el formato de paquete DIXF y contendrá los siguientes archivos:

-   El archivo de la tabla de etapas de entidad
-   DMFDEFINITIONGROUPEXECUTION
-   DMFDEFINITIONGROUPEXECUTIONHISTORY
-   DMFEXECUTION
-   DMFSTAGINGEXECUTIONERRORS
-   DMFSTAGINGLOG
-   DMFSTAGINGLOGDETAILS
-   DMFSTAGINGVALIDATIONLOG

