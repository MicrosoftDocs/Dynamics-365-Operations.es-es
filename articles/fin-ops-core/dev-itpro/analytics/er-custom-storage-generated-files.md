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
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="0da4b-103">Especificar ubicaciones de almacenamiento personalizado para documentos generados</span><span class="sxs-lookup"><span data-stu-id="0da4b-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0da4b-104">La interfaz de programación de aplicaciones (API) del marco de informes electrónicos (ER) permite ampliar la lista de ubicaciones de almacenamiento para los documentos que los formatos de ER generan.</span><span class="sxs-lookup"><span data-stu-id="0da4b-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="0da4b-105">Este tema explica cómo agregar una ubicación de almacenamiento personalizada para documentos generados al delegar la tarea de crear destinos ER a la fábrica de destino predeterminada y luego implementar una clase personalizada que tiene su propia lógica de destino.</span><span class="sxs-lookup"><span data-stu-id="0da4b-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0da4b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0da4b-106">Prerequisites</span></span>

<span data-ttu-id="0da4b-107">Implementar una topología que admita una compilación continua.</span><span class="sxs-lookup"><span data-stu-id="0da4b-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="0da4b-108">Para obtener más información, consulte [Implementar topologías que admiten la automatización continua de la compilación y la prueba](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="0da4b-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="0da4b-109">También debe tener acceso a esta topología para uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="0da4b-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="0da4b-110">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="0da4b-110">Electronic reporting developer</span></span>
- <span data-ttu-id="0da4b-111">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="0da4b-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="0da4b-112">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="0da4b-112">System administrator</span></span>

<span data-ttu-id="0da4b-113">También debe tener acceso al entorno de desarrollo para esta topología.</span><span class="sxs-lookup"><span data-stu-id="0da4b-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="0da4b-114">Todas las tareas de este tema se pueden completar en la empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="0da4b-115">Importar el formato ER de avance de activos fijos</span><span class="sxs-lookup"><span data-stu-id="0da4b-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="0da4b-116">Para generar los documentos para los que planea agregar una ubicación de almacenamiento personalizada, [importe](er-download-configurations-global-repo.md) el formato de configuración de ER **Renovación de activos fijos** en la topología actual.</span><span class="sxs-lookup"><span data-stu-id="0da4b-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Página de configuración del repositorio](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="0da4b-118">Ejecute el Informe de puesta al día para activos fijos</span><span class="sxs-lookup"><span data-stu-id="0da4b-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="0da4b-119">Vaya a **Activos fijos** \> **Consultas e informes** \> **Informes de transacciones** \> **Renovación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="0da4b-120">En el campo **Fecha inicial**, escriba **1/1/2017** (1 de enero de 2017).</span><span class="sxs-lookup"><span data-stu-id="0da4b-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="0da4b-121">En el campo **Fecha final**, escriba **1/31/2017** (31 de enero de 2017).</span><span class="sxs-lookup"><span data-stu-id="0da4b-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="0da4b-122">En el **campo Divisa**, seleccione **Divisa de contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="0da4b-123">En el campo **Asignación de formato**, seleccione **Renovación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="0da4b-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-124">Select **OK**.</span></span>

![Cuadro de diálogo de runtime para el informe de avance de activos fijos](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="0da4b-126">En Microsoft Excel, revise el documento saliente que se genera y está disponible para descargar.</span><span class="sxs-lookup"><span data-stu-id="0da4b-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="0da4b-127">Este comportamiento es el [comportamiento por defecto](electronic-reporting-destinations.md#default-behavior) para un formato ER que no tiene [destinos](electronic-reporting-destinations.md) configurados y que se ejecutan en modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="0da4b-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="0da4b-128">Revisar el código fuente</span><span class="sxs-lookup"><span data-stu-id="0da4b-128">Review the source code</span></span>

<span data-ttu-id="0da4b-129">Revise el código del método `generateReportByGER()` de la clase `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="0da4b-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="0da4b-130">Note que el método `Run()` se utiliza para llamar al marco ER y generar el informe de **Renovación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="0da4b-131">Modificación del código de origen</span><span class="sxs-lookup"><span data-stu-id="0da4b-131">Modify the source code</span></span>

1. <span data-ttu-id="0da4b-132">En su proyecto de Visual Studio, agregue una nueva clase (`AssetRollForwardDestination` en este ejemplo) y escriba el código para implementar su destino personalizado para los informes **Renovación de activos fijos** que se generan.</span><span class="sxs-lookup"><span data-stu-id="0da4b-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="0da4b-133">El método `new()` está diseñado para obtener el objeto de destino ER original y el parámetro impulsado por la lógica de la aplicación que especifica la ubicación personalizada donde se deben almacenar los informes generados.</span><span class="sxs-lookup"><span data-stu-id="0da4b-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="0da4b-134">En este ejemplo, la ubicación personalizada es el nombre de una carpeta del sistema de archivos local del servidor que ejecuta el servicio Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="0da4b-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="0da4b-135">El método `saveFile()` está diseñado para guardar un documento generado en una carpeta del sistema de archivos local del servidor que ejecuta el servicio AOS.</span><span class="sxs-lookup"><span data-stu-id="0da4b-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="0da4b-136">En su proyecto de Visual Studio, agregue una nueva clase (`AssetRollForwardDestinationFactory` en este ejemplo) y escriba el código para configurar una fábrica de destino personalizada que delegue la creación de un destino a la fábrica de destino predeterminada y para envolver un destino de archivo con su propio destino.</span><span class="sxs-lookup"><span data-stu-id="0da4b-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="0da4b-137">Modifique la clase existente `AssetRollForwardService` y escriba el código para configurar una fábrica de destino personalizada para el ejecutor de informes.</span><span class="sxs-lookup"><span data-stu-id="0da4b-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="0da4b-138">Observe que cuando se construye una fábrica de destino personalizada, se pasa el parámetro controlado por la aplicación que especifica una carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="0da4b-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="0da4b-139">De esta manera, esa carpeta de destino se usa para almacenar archivos generados.</span><span class="sxs-lookup"><span data-stu-id="0da4b-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="0da4b-140">Asegúrese de que la carpeta especificada (**c:\\0** en este ejemplo) está presente en el sistema de archivos local del servidor que ejecuta el servicio AOS.</span><span class="sxs-lookup"><span data-stu-id="0da4b-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="0da4b-141">De lo contrario, una excepción [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) se lanzará en runtime.</span><span class="sxs-lookup"><span data-stu-id="0da4b-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="0da4b-142">Reconstruir su proyecto.</span><span class="sxs-lookup"><span data-stu-id="0da4b-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="0da4b-143">Vuelva a ejecutar el Informe de puesta al día para activos fijos</span><span class="sxs-lookup"><span data-stu-id="0da4b-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="0da4b-144">Vaya a **Activos fijos** \> **Consultas e informes** \> **Informes de transacciones** \> **Renovación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="0da4b-145">En el campo **Desde fecha**, escriba **1/1/2017**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="0da4b-146">En el campo **Hasta fecha**, escriba **1/31/2017**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="0da4b-147">En el **campo Divisa**, seleccione **Divisa de contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="0da4b-148">En el campo **Asignación de formato**, seleccione **Renovación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="0da4b-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0da4b-149">Select **OK**.</span></span>
7. <span data-ttu-id="0da4b-150">Examine la carpeta **C:\\0** local para encontrar el archivo generado.</span><span class="sxs-lookup"><span data-stu-id="0da4b-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="0da4b-151">Como el objeto `originDestination` no se usa en el objeto `AssetRollForwardDestination` en este ejemplo, las configuraciones para el formato ER de [destinos](electronic-reporting-destinations.md) se ignorará en runtime.</span><span class="sxs-lookup"><span data-stu-id="0da4b-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0da4b-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0da4b-152">Additional resources</span></span>

- [<span data-ttu-id="0da4b-153">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="0da4b-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="0da4b-154">Página de inicio de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="0da4b-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
