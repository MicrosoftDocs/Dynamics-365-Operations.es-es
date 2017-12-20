---
title: Vuelva a establecer el data mart de informes financieros
description: "Este tema describe cómo restablecer el data mart de informes financieros."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: es-es
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>Vuelva a establecer el data mart de informes financieros

[!include[banner](../includes/banner.md)]

Este tema explica cómo restablecer el data mart de informes financieros para las siguientes versiones:

- Microsoft Dynamics 365 for Finance and Operations Financial Reporting versión 7.2.6.0 y posteriores
- Microsoft Dynamics 365 for Finance and Operations Financial Reporting versión 7.0.10000.4 y posteriores
- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (localmente)

Para obtener Finance and Operations Financial reporting versión 7.2.6.0, puede descargar el KB 4052514 de <https://support.microsoft.com/en-us/help/4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Restablecer el data mart de informes financieros de Finance and Operations Financial reporting versión 7.2.6.0 y versiones posteriores

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Restablecer el data mart de informes financieros desde el diseñador de informes

> [!NOTE]
> Los pasos de este procedimiento se admiten en Finance and Operations Financial reporting versión 7.2.6.0 y versiones posteriores. Si tiene una versión anterior, póngase en contacto con el equipo de asistencia técnica para obtener ayuda.

En casos específicos, puede que tenga que restablecer el data mart del informe financiero. Puede completar esta tarea en el cliente del diseñador de informes. Aquí hay algunas escenarios donde puede que tenga que restablecer el data mart:

- La base de datos de Finance and Operations se restauró, pero la base de datos de data mart no se restauró.
- Ve datos incorrectos para un período.
- La asistencia técnica le instruye para restablecer el data mart como parte de un paso de solución de problemas.

El reinicio de data mart se debe realizar únicamente cuando el volumen de procesamiento en la base de datos es pequeño. El informe financiero no estará disponible durante el proceso de restablecimiento.

#### <a name="reset-the-data-mart"></a>Restablecer el data mart

Para restablecer el data mart, en el Diseñador de informes, en el menú **Herramientas** , seleccione **Restablecer data mart**. El cuadro de diálogo que aparece tiene dos secciones: **Estadísticas** y **Restablecer**.

[![Cuadro de diálogo Restablecer el data mart](./media/Statistics.png)](./media/Statistics.png)

##### <a name="integration-attempts"></a>Intentos de integración

La cuadrícula **Intentos de integración** muestra el número de veces que el sistema ha intentado integrar transacciones. El sistema sigue intentando integrar datos durante un período de días si los primeros intentos no tienen éxito. Se sabrá que data mart debe ser restablecido es si el número de intentos es de 8 o más, y si hay muchas combinaciones de dimensiones o registros de transacción. En esta situación, no se informará de los datos.

##### <a name="data-status"></a>Estado de los datos

La cuadrícula **Estado de los datos** proporciona una instantánea de las transacciones, de los tipos de cambio, y los valores de dimensión en el data mart. Un gran número de registros obsoletos indican que se han producido numerosas actualizaciones de los registros. Esta situación podría provocar tiempos de generación de informes más lentos.

##### <a name="misaligned-main-account-categories"></a>Categorías de cuenta principal desalineadas

Si utiliza una versión anterior a Microsoft Dynamics 365 for Finance and Operations Financial reporting versión 7.2.1, puede que tenga que restablecer el data mart si cambia el nombre de cuentas y mueve cuentas entre las categorías de cuenta. Estas acciones pueden hacer que las categorías de cuenta principal tengan una alineación incorrecta. El campo **Categorías de cuenta principal desalineada** muestra si está experimentando dicho problema.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Restablecer el data mart de Finance and Operations Financial reporting versión 7.2.6.0

Para restablecer el data mart de Finance and Operations Financial reporting versión 7.2.6.0 y versiones anteriores, en el cuadro de diálogo **Restablecer data mart** , seleccione la casilla de verificación **Restablecer data mart** y, a continuación seleccione **Aceptar**. Debe restablecer el data mart únicamente durante un tiempo de inactividad programado.

[![Cuadro de diálogo Restablecer el data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Restablecer el data mart y seleccionar un motivo en Microsoft Dynamics 365 for Finance and Operations Financial reporting versión 7.3.0

Si determina que un reinicio de data mart es necesario, seleccione la casilla de verificación **Restaurar data mart** , y seleccione un motivo en el campo **Motivo**. Las opciones siguientes están disponibles:

- **Faltan datos o son incorrectos**: Basándose en las estadísticas, ha determinado que podrían faltar datos. Antes de que pueda continuar, se recomienda que trabaje con el soporte para determinar la causa original.
- **Restablecer base de datos**: la base de datos Finance and Operations se restauró, pero la base de datos del data mart de Financial reporting no se restauró.
- **Otros**: está restableciendo el data mart por otro motivo. Si le preocupa que haya un problema, póngase en contacto con Soporte para identificarlo.

> [!NOTE]
> Compruebe que todas las tareas existentes hayan terminado de integrarse antes de completar los pasos. Puede ver el estado de la integración seleccionando &gt; **Herramientas** **Estado de integración**.

#### <a name="clear-users-and-companies"></a>Borrar usuarios y empresas

Seleccione la casilla de verificación **Borrar usuarios y empresas** si se restauró la base de datos, pero realizó cambios en usuarios o empresas. En pocas ocasiones tendrá que seleccionar esta casilla de verificación.

Cuando esté listo para iniciar el proceso de restablecimiento, seleccione **Aceptar**. Se le pedirá que confirme que está listo para iniciar el proceso. Tenga en cuenta que el informe financiero no estará disponible durante el reinicio y la integración de datos inicial que se produce después.

Si desea revisar el estado de la integración, seleccione &gt; **Herramientas** **Estado de integración** para ver la última vez que la integración se ejecutó y el estado.

[![Permite ver el estado de la integración.](./media/Integration.png)](./media/Integration.png)

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Restablecer el data mart de informes financieros de Finance and Operations Financial reporting versión 7.0.10000.4 y versiones posteriores

Si se restablece la base de datos de Finance and Operations desde una copia de seguridad o copia de la base de datos de otro entorno, debe seguir los pasos de esta sección para ayudar a garantizar que el data mart del informe financiero usa correctamente la base de datos restaurada de Finance and Operations.

> [!NOTE]
> Los pasos de este proceso se admiten para Microsoft Dynamics AX application versión 7.0.1 (mayo de 2016) (compilación de la aplicación 7.0.1265.23014 y compilación de Financial reporting 7.0.10000.4) y versiones posteriores. Si tiene una versión anterior de Finance and Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.

### <a name="export-report-definitions"></a>Exportar las definiciones de informe

En primer lugar, siga estos pasos para exportar los diseños de informe desde el diseñador de informes.

1. En el Diseñador de informes, seleccione **Empresa** &gt; **Grupos de bloques de creación**.
2. Seleccione el grupo de bloques de creación para exportar y seleccione **Exportar**.

    > [!NOTE]
    > Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.

3. Seleccione las definiciones del informe que quiere exportar:

    - Para exportar todas las definiciones de informe y los bloques de creación asociados, seleccione **Seleccionar todo**.
    - Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla Ctrl para seleccionar varios artículos de una pestaña. Al seleccionar los informes para exportar, las filas, columnas, árboles y conjuntos de dimensiones asociados se seleccionan también.

4. Seleccione **Exportar**.
5. Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.
6. Seleccione **Guardar**.

Puede copiar o cargar el archivo en una ubicación segura. De esta manera, el archivo se puede importar a un entorno diferente posteriormente. Para obtener información sobre el uso de una cuenta de almacenamiento de Microsoft Azure, consulte [transferir datos con el programa de línea de comandos de AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Finance and Operations. Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente.

> [!WARNING]
> Tenga en cuenta el comportamiento de la unidad D en las máquinas virtuales (VM) Azure. No almacene permanentemente los grupos de bloques de creación exportados en la unidad D. Para obtener más información acerca de unidades temporales, consulte [Comprensión de la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Detener servicios

Los servicios de Microsoft Windows siguientes tendrán conexiones abiertas con la base de datos de Finance and Operations. Por lo tanto, debe utilizar el escritorio remoto de Microsoft para conectarse con todos los equipos del entorno y utilizar services.msc para detener estos servicios.

- Servicio de publicación de la World Wide Web (en todos los equipos Application Object Servers [AOS])
- Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)
- Servicio de proceso de Management Reporter 2012 (solo en equipos de Business Intelligence BI)

### <a name="reset"></a>Restablecer

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Descargue el último paquete de MinorVersionDataUpgrade.zip

Descargue el último paquete de MinorVersionDataUpgrade.zip. Para obtener instrucciones acerca de cómo encontrar y descargar la versión correcta de embalaje de la actualización de datos, vea[Descarga del paquete desplegable de la última actualización de datos](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). No se requiere una actualización para descargar el paquete de MinorVersionDataUpgrade.zip. Por tanto, solo tiene que seguir los pasos de la sección “Descarga de paquete desplegable de la última actualización de datos” de este tema. Puede omitir el resto de pasos del tema.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Ejecute las secuencias de comandos en la base de datos de Finance and Operations

Ejecute las secuencias de comandos siguientes en la base de datos de Finance and Operations (no en la base de datos del informe financiero):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Estas secuencias de comandos ayudan a garantizar que la configuración de usuarios, roles y seguimiento de cambios sea correcta.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Ejecutar un comando de Windows PowerShell para restablecer la base de datos

En el equipo de AOS, empiece como administrador de Microsoft Windows PowerShell y ejecute los comandos siguientes para restablecer la integración entre Finance and Operations y el informe financiero.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

A continuación se indica una explicación de los parámetros del comando **Reset-DatamartIntegration** :

- Los valores válidos de **-Reason** son **SERVICING**, **BADDATA**, y **OTHER**.
- El parámetro **-ReasonDetail** es de texto libre.
- El motivo y el detalle del motivo se registrarán en telemetría/supervisión de entorno.

> [!NOTE]
> Tras ejecutar los comandos, se le pedirá que especifique **Y** para confirmar que desea restablecer la base de datos.

#### <a name="restart-services"></a>Restablecer servicios

Use services.msc para reiniciar los servicios que ha detenido anteriormente:

- Servicio de publicación de la World Wide Web (en todos los equipos AOS)
- Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)
- Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)

#### <a name="import-report-definitions"></a>Importar las definiciones de informe

Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación.

1. En el Diseñador de informes, seleccione **Empresa** &gt; **Grupos de bloques de creación**.
2. Seleccione el grupo de bloques de creación para exportar y seleccione **Exportar**.

    > [!NOTE]
    > Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.

3. Seleccione el bloque de creación **Predeterminado** y seleccione **Importar**.
4. Seleccione el archivo que contiene las definiciones de informe exportadas y seleccione **Abrir**.
5. En el cuadro de diálogo **Importar**, seleccione las definiciones de informe que se van a importar:

    - Para importar todas las definiciones de informe y los bloques de creación asociados, seleccione **Seleccionar todo**.
    - Para importar informes, filas, columnas, organigramas o grupos de dimensión específicos, seleccione los informes, las filas, las columnas, los organigramas o los grupos de dimensión que se deben importar y, a continuación, haga clic en Importar.

6. Seleccione **Importar**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Restablecer el data mart de informes financieros de Finance and Operations (localmente)

1. Solicite a todos los usuarios que salgan del diseñador de informes y el área de informes financieros de Finance and Operations.
2. Ejecute la siguiente secuencia de comandos en la base de datos de informes financieros (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. Trunque o elimine todos los registros de la tabla FINANCIALREPORTS en la base de datos de Finance and Operations (AXDB).
4. Trunque o elimine todos los registros de la tabla FINANCIALREPORTVERSION, si esta tabla existe en la base de datos de Finance and Operations. Si la tabla no existe en la base de datos de Finance and Operations, omita este paso.
5. Ejecute la secuencia de comandos **ResetDatamart.sql** en la base de datos de informes financieros. Este script deshabilita la integración de data mart, elimina todos los datos de data mart, y vuelve a permitir la integración de data mart.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. Después de restablecimiento, puede comprobar manualmente la recarga de datos ejecutando la consulta siguiente en la base de datos de informes financieros.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Confirme que todas las filas tienen un valor **LastRunTime** , y que **StateType** está establecido en **5**. Un valor **StateType** de **5** indica que los datos se recargaron correctamente. Un valor de **7** indica un estado erróneo. En ocasiones, el mapa de la jerarquía organizativa tiene este estado la primera vez que se ejecuta. Sin embargo, el estado erróneo debe resolverse automáticamente.

