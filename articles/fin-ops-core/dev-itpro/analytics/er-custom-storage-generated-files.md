---
title: Especificar ubicaciones de almacenamiento personalizado para documentos generados
description: Este tema explica cómo ampliar la lista de ubicaciones de almacenamiento para los documentos generados por los formatos de informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 362ac7f10cc61e26be89dfbae0e84745d42588a3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680767"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Especificar ubicaciones de almacenamiento personalizado para documentos generados

[!include[banner](../includes/banner.md)]

La interfaz de programación de aplicaciones (API) del marco de informes electrónicos (ER) permite ampliar la lista de ubicaciones de almacenamiento para los documentos que los formatos de ER generan. Este tema explica cómo agregar una ubicación de almacenamiento personalizada para documentos generados al delegar la tarea de crear destinos ER a la fábrica de destino predeterminada y luego implementar una clase personalizada que tiene su propia lógica de destino.

## <a name="prerequisites"></a>Requisitos previos

Implementar una topología que admita una compilación continua. Para obtener más información, consulte [Implementar topologías que admiten la automatización continua de la compilación y la prueba](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). También debe tener acceso a esta topología para uno de los siguientes roles:

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

También debe tener acceso al entorno de desarrollo para esta topología.

Todas las tareas de este tema se pueden completar en la empresa **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importar el formato ER de avance de activos fijos

Para generar los documentos para los que planea agregar una ubicación de almacenamiento personalizada, [importe](er-download-configurations-global-repo.md) el formato de configuración de ER **Renovación de activos fijos** en la topología actual.

![Página de configuración del repositorio](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Ejecute el Informe de puesta al día para activos fijos

1. Vaya a **Activos fijos** \> **Consultas e informes** \> **Informes de transacciones** \> **Renovación de activos fijos**.
2. En el campo **Fecha inicial**, escriba **1/1/2017** (1 de enero de 2017).
3. En el campo **Fecha final**, escriba **1/31/2017** (31 de enero de 2017).
4. En el **campo Divisa**, seleccione **Divisa de contabilidad**.
5. En el campo **Asignación de formato**, seleccione **Renovación de activos fijos**.
6. Seleccione **Aceptar**.

![Cuadro de diálogo de runtime para el informe de avance de activos fijos](./media/er-custom-storage-generated-files-runtime-dialog.png)

En Microsoft Excel, revise el documento saliente que se genera y está disponible para descargar. Este comportamiento es el [comportamiento por defecto](electronic-reporting-destinations.md#default-behavior) para un formato ER que no tiene [destinos](electronic-reporting-destinations.md) configurados y que se ejecutan en modo interactivo.

## <a name="review-the-source-code"></a>Revisar el código fuente

Revise el código del método `generateReportByGER()` de la clase `AssetRollForwardService`. Note que el método `Run()` se utiliza para llamar al marco ER y generar el informe de **Renovación de activos fijos**.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>Modificación del código de origen

1. En su proyecto de Visual Studio, agregue una nueva clase (`AssetRollForwardDestination` en este ejemplo) y escriba el código para implementar su destino personalizado para los informes **Renovación de activos fijos** que se generan.

    - El método `new()` está diseñado para obtener el objeto de destino ER original y el parámetro impulsado por la lógica de la aplicación que especifica la ubicación personalizada donde se deben almacenar los informes generados. En este ejemplo, la ubicación personalizada es el nombre de una carpeta del sistema de archivos local del servidor que ejecuta el servicio Application Object Server (AOS).
    - El método `saveFile()` está diseñado para guardar un documento generado en una carpeta del sistema de archivos local del servidor que ejecuta el servicio AOS.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. En su proyecto de Visual Studio, agregue una nueva clase (`AssetRollForwardDestinationFactory` en este ejemplo) y escriba el código para configurar una fábrica de destino personalizada que delegue la creación de un destino a la fábrica de destino predeterminada y para envolver un destino de archivo con su propio destino.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Modifique la clase existente `AssetRollForwardService` y escriba el código para configurar una fábrica de destino personalizada para el ejecutor de informes. Observe que cuando se construye una fábrica de destino personalizada, se pasa el parámetro controlado por la aplicación que especifica una carpeta de destino. De esta manera, esa carpeta de destino se usa para almacenar archivos generados.

    > [!NOTE] 
    > Asegúrese de que la carpeta especificada (**c:\\0** en este ejemplo) está presente en el sistema de archivos local del servidor que ejecuta el servicio AOS. De lo contrario, una excepción [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) se lanzará en runtime.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Reconstruir su proyecto.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Vuelva a ejecutar el Informe de puesta al día para activos fijos

1. Vaya a **Activos fijos** \> **Consultas e informes** \> **Informes de transacciones** \> **Renovación de activos fijos**.
2. En el campo **Desde fecha**, escriba **1/1/2017**.
3. En el campo **Hasta fecha**, escriba **1/31/2017**.
4. En el **campo Divisa**, seleccione **Divisa de contabilidad**.
5. En el campo **Asignación de formato**, seleccione **Renovación de activos fijos**.
6. Seleccione **Aceptar**.
7. Examine la carpeta **C:\\0** local para encontrar el archivo generado.

> [!NOTE]
> Como el objeto `originDestination` no se usa en el objeto `AssetRollForwardDestination` en este ejemplo, las configuraciones para el formato ER de [destinos](electronic-reporting-destinations.md) se ignorará en runtime.

## <a name="additional-resources"></a>Recursos adicionales

- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Página de inicio de extensibilidad](../extensibility/extensibility-home-page.md)
