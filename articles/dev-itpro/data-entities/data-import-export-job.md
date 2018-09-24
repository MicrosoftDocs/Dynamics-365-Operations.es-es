---
title: "Trabajos de exportación e importación de datos"
description: "Use el espacio de trabajo de gestión de datos para crear y administrar trabajos de importación y exportación de datos."
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 68cafc167c178e2feeb0a5af764a491ea6b3c60b
ms.contentlocale: es-es
ms.lasthandoff: 08/13/2018

---

# <a name="data-import-and-export-jobs"></a>Trabajos de exportación e importación de datos

[!include [banner](../includes/banner.md)]

Para crear y administrar trabajos de importación y exportación de datos en Microsoft Dynamics 365 for Finance and Operations debe usar el espacio de trabajo **Administración de datos**. De forma predeterminada, el proceso de importación y exportación de datos crea una tabla de almacenamiento provisional para cada entidad en la base de datos de destino. Las tablas de almacenamiento provisional le permiten verificar, limpiar o convertir datos antes de moverlos de sitio.

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

- Si solo usó un trabajo de datos para todos los cambios, puede usar las opciones para volver a ordenar y así optimizar el tiempo de ejecución del trabajo completo. En estos casos, puede usar la unidad de ejecución para representar el módulo, el nivel para representar el área de características en el módulo y la secuencia para representar la entidad. Al usar este método, puede trabajar en paralelo con diferentes módulos, pero aún así puede seguir trabajando en el orden de un módulo. Para que garantizar que las operaciones paralelas se realizan correctamente, debe tener en cuenta todas las dependencias.
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

## <a name="validate-that-the-job-ran-as-expected"></a>Confirme que el trabajo funciona como es debido.
Tiene disponible el historial de trabajos por si necesita solucionar algún problema o investigar algún trabajo de importación o exportación. Las ejecuciones de trabajos del historial se organizan según intervalos de tiempo.

![Rangos del historial de trabajos](./media/dixf-job-history.md.png)

Cada ejecución de trabajo proporciona los siguientes detalles:

- Detalles de ejecución
- Registro de ejecución

Los detalles de la ejecución muestran el estado de cada entidad de datos que procesó el trabajo. Por lo tanto, puede buscar rápidamente la siguiente información:

- Qué entidades se procesaron
- En una entidad, cuántos registros se procesaron correctamente y cuántos fallaron
- Los registros provisionales de cada entidad

Puede descargar los datos provisionales en un archivo dedicado a los trabajos de exportación, o bien descargarlo como un paquete de los trabajos de exportación e importación.

Desde la opción de detalles de ejecución, también puede abrir el registro de ejecución.

## <a name="clean-up-the-staging-tables"></a>Limpiar las tablas de almacenamiento provisional
Puede limpiar las tablas de almacenamiento provisional si usa la característica **Limpieza del almacenamiento provisional** del espacio de trabajo **Administración de datos**. Puede usar las opciones siguientes para seleccionar qué registros deben ser eliminados de una tabla de almacenamiento provisional específica:

- **Entidad**: si solo se proporciona una entidad, todos los registros de la tabla de almacenamiento provisional de esa entidad se borran. Seleccione esta opción para borrar todos los datos de la entidad incluyendo todos los proyectos y trabajos de datos.
- **Id. de trabajo**: si solo se proporciona un id. de trabajo, todos los registros de todas las entidades del trabajo seleccionado se eliminan de las tablas de almacenamiento provisional adecuadas.
- **Proyectos de datos**: si solo se selecciona un proyecto de datos, todos los registros de las entidades y de todos los trabajos del proyecto de datos seleccionado se eliminan.

También puede combinar estas opciones para restringir aún más el conjunto de registros que se van a eliminar.

